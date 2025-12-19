# Dossier d'architecture technique - Homelab
![projectimage](intro.png)
## Gestion documentaire
| Élément | Information |
|--------|-------------|
| Titre du document | Dossier d’Architecture Technique |
| Projet | AI Proof Roadmap |
| Organisation | fabfromthesnow |
| Version | v1.0 |
| Statut | Brouillon |
| Date de création | [19/12/2025] |
| Auteur | [FabSnow] |
---
## 1) Introduction
Le homelab décrit dans ce document vise à simuler une infrastructure d’entreprise
à petite échelle, en reproduisant les composants techniques et les bonnes pratiques
couramment rencontrés dans un contexte professionnel.

L’environnement est conçu comme une plateforme on-premise structurée, segmentée
et documentée, servant à la fois de support d’apprentissage, de démonstration
technique et de base évolutive pour des usages plus avancés (automatisation,
sauvegarde, sécurité, cloud et plateformes).

Au cours du premier mois, l’accent est mis sur la mise en place d’un socle
fonctionnel et stable comprenant :
- une segmentation réseau claire (VLAN MGMT, LAN et DMZ le cas échéant),
- un pare-feu central assurant le filtrage, le routage et la journalisation,
- des services cœur (DNS, DHCP),
- une gestion centralisée des identités et des accès,
- un accès distant sécurisé avec authentification forte,
- une observabilité de base permettant le suivi de l’état et des événements
  de l’infrastructure,
- une documentation centralisée décrivant l’architecture, les accès et les
  procédures de dépannage élémentaires.

À ce stade, l’environnement ne vise pas la haute disponibilité ni la résilience
complète, mais fournit une base réaliste, cohérente et opérable, alignée avec les
contraintes et pratiques d’une infrastructure d’entreprise standard.
## 2) Architecture Globale
### 2.1) Présentation générale
L’ensemble des composants de l’architecture on-premise est virtualisé sur un PC hôte via VirtualBox. Afin de se rapprocher d’un contexte d’entreprise, Proxmox VE est utilisé comme plateforme de virtualisation pour héberger les machines virtuelles ; toutefois, dans ce laboratoire, Proxmox est exécuté de manière imbriquée (nested) à l’intérieur de VirtualBox. Dans ces conditions, Proxmox ne contrôle pas directement le matériel physique et ne peut donc pas être considéré comme un véritable hyperviseur de type 1. 

L’hyperviseur Proxmox héberge les machines virtuelles constituant les principaux
services de l’infrastructure. Ces machines sont réparties par rôle fonctionnel
afin de refléter une organisation classique dans un environnement d’entreprise hybride (Cloud et On-Prem). La gestion des identités repose sur un Active Directory on-premise (AD DS), dont les comptes et groupes sont synchronisés vers Microsoft Entra ID afin de permettre l’accès aux services cloud (SSO, MFA) tout en conservant l’administration des postes et ressources internes côté on-premise.

Les machines déployés à ce stade sont :
- Un pare-feu virtualisé **(OPNsense)** pour gérer la sécurité périmétrique, le filtrage, le routage et la journalisation des flux
- Une machine virtuelle (Windows Server 2022) jouant le rôle de contrôleur de domaine Active Directory (AD DS) pour l’infrastructure on-premise.
Elle fournit également les services DNS et DHCP :
    - **DNS** : résolution de noms interne, intégrée au domaine AD.
    - **DHCP** : attribution dynamique des adresses IP aux hôtes du réseau.
Les identités du domaine on-premise sont synchronisées vers Microsoft Entra ID via un mécanisme de synchronisation (ex. Entra Connect / Cloud Sync), afin de permettre un modèle hybride (SSO, MFA et accès aux services cloud), tout en conservant un AD on-prem pour la gestion des machines et des comptes.
- Un serveur de journalisation et d’observabilité **(Debian 13)** dédié à la
  centralisation des journaux et à la supervision de base de l’infrastructure.
  Ce serveur héberge une stack d’observabilité légère composée de
  **Grafana**, **Loki** et des agents de collecte associés, permettant :
  - la réception des journaux issus du pare-feu OPNsense et des serveurs,
  - la visualisation des événements via des tableaux de bord,
  - la mise en place de règles d’alerte simples (disponibilité, ressources,
    anomalies basiques).
- Une machine utilisateur **(Windows 10)** représentant un
  poste standard d’entreprise joint au domaine. Cette machine est utilisée pour valider le bon
  fonctionnement des services réseau (DNS, DHCP), des accès utilisateur, des
  flux réseau et de la journalisation côté client, sans privilèges
  administratifs sur l’infrastructure.
### 2.1) Convention de Nommages
| Élément | Pattern |
|--------|-------------|
| Hyperviseur | HV-{NN} |
| Serveur Windows | SRVW-{RolePrincipal}-{NN} |
| Serveur Linux | SRVL-{RolePrincipal}-{NN} |
| Workstation | PC-{Service}-{NN}
### 2.2) Diagrammes
## 3) Architeture réseau
### 3.1) Plan d'adressage et VLANs
Le plan d'adressage a été établis en suivant la méthode **(VLSM)** pour garantir la scallabillité
| Réseau  | Besoin | Réseau (CIDR)   | Passerelle (suggestion) | Plage utilisable            | Broadcast    |
| ------- | -----: | --------------- | ----------------------- | --------------------------- | ------------ |
| Users   |    200 | 10.60.10.0/24   | 10.60.10.1              | 10.60.10.1 – 10.60.10.254   | 10.60.10.255 |
| VPN     |    200 | 10.60.11.0/24   | 10.60.11.1              | 10.60.11.1 – 10.60.11.254   | 10.60.11.255 |
| Servers |    100 | 10.60.12.0/25   | 10.60.12.1              | 10.60.12.1 – 10.60.12.126   | 10.60.12.127 |
| MGMT    |     10 | 10.60.12.128/28 | 10.60.12.129            | 10.60.12.129 – 10.60.12.142 | 10.60.12.143 |
| Infra   |     10 | 10.60.12.144/28 | 10.60.12.145            | 10.60.12.145 – 10.60.12.158 | 10.60.12.159 |
| DMZ     |     10 | 10.60.12.160/28 | 10.60.12.161            | 10.60.12.161 – 10.60.12.174 | 10.60.12.175 |
| Obs     |     10 | 10.60.12.176/28 | 10.60.12.177            | 10.60.12.177 – 10.60.12.190 | 10.60.12.191 |
| Backup  |     10 | 10.60.12.192/28 | 10.60.12.193            | 10.60.12.193 – 10.60.12.206 | 10.60.12.207 |
| Storage |     10 | 10.60.12.208/28 | 10.60.12.209            | 10.60.12.209 – 10.60.12.222 | 10.60.12.223 |
| Devops  |     10 | 10.60.12.224/28 | 10.60.12.225            | 10.60.12.225 – 10.60.12.238 | 10.60.12.239 |
| Secops  |     10 | 10.60.12.240/28 | 10.60.12.241            | 10.60.12.241 – 10.60.12.254 | 10.60.12.255 |

### 3.2) Pare-feu
### 3.3) Service Réseau

