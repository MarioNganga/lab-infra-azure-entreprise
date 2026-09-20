# Laboratoire d'Infrastructure d'Entreprise Azure

## 📌 Présentation du projet

Ce projet consiste à construire et administrer une petite infrastructure d'entreprise sur Microsoft Azure.

L'objectif est de simuler l'environnement informatique d'une petite entreprise et de mettre en pratique l'administration système, le réseau, la sécurité et le dépannage.

L'infrastructure comprend Windows Server, Active Directory, DNS, la Stratégie de groupe et un client Windows.

---

## 🎯 Objectifs

Les principaux objectifs de ce projet sont :

* Déployer des machines virtuelles sur Microsoft Azure
* Concevoir un réseau virtuel de base
* Déployer et configurer Windows Server
* Mettre en place les services de domaine Active Directory
* Configurer le DNS
* Créer des utilisateurs, groupes et unités d'organisation
* Joindre un client Windows au domaine
* Mettre en place des stratégies de sécurité via la Stratégie de groupe
* Configurer le partage de fichiers et les permissions
* Dépanner les problèmes courants d'infrastructure
* Documenter l'environnement selon les standards professionnels de l'IT

---

## 🏗️ Architecture

Le laboratoire est composé des éléments suivants :

| Composant         | Rôle                                          |
| ----------------- | ---------------------------------------------- |
| DC01              | Windows Server / Contrôleur de domaine / DNS  |
| CLIENT01          | Client Windows                                 |
| Azure VNet        | Réseau privé                                   |
| NSG               | Contrôle d'accès réseau                        |
| Active Directory  | Identité et authentification                   |
| DNS               | Résolution de noms                             |
| Stratégie de groupe | Configuration centralisée                    |

### Réseau

```text
VNet : 10.10.0.0/16
Sous-réseau : 10.10.10.0/24
```

### Schéma d'architecture

![Architecture](01-architecture/network-diagram.png)

---

## 🔧 Technologies

* Microsoft Azure
* Windows Server
* Windows
* Active Directory
* DNS
* Stratégie de groupe
* Réseau virtuel Azure
* Groupes de sécurité réseau
* PowerShell

---

## 🚀 Mise en œuvre

### 1. Infrastructure Azure

La première étape a consisté à créer le groupe de ressources Azure, le réseau virtuel, le sous-réseau et les règles de sécurité réseau.

### 2. Windows Server

Une machine virtuelle Windows Server a été déployée et configurée en tant que contrôleur de domaine.

### 3. Active Directory

Active Directory a été configuré avec le domaine `corp.local`.

Des utilisateurs, groupes et unités d'organisation ont été créés pour simuler l'environnement d'une petite entreprise.

### 4. DNS

Le DNS a été configuré pour assurer la résolution de noms du domaine interne.

### 5. Client Windows

Un client Windows a été déployé et joint au domaine `corp.local`.

### 6. Stratégie de groupe

Une base de référence de sécurité a été mise en place via la Stratégie de groupe.

### 7. Serveur de fichiers

Des dossiers partagés ont été créés avec des permissions basées sur l'appartenance aux départements.

---

## 🔐 Sécurité

L'environnement a été conçu avec des contrôles de sécurité de base, notamment :

* Accès réseau restreint via les NSG Azure
* Accès administratif limité
* Authentification basée sur le domaine
* Permissions basées sur les groupes
* Stratégies de mot de passe et de verrouillage de compte
* Pare-feu Windows
* Séparation entre utilisateurs administrateurs et standards

---

## 🧪 Dépannage

Une panne DNS contrôlée a été introduite pour simuler un incident d'infrastructure réel.

### Problème

Le client Windows était incapable de résoudre le nom d'hôte du contrôleur de domaine.

### Investigation

Le problème a été investigué à l'aide de :

* `ipconfig`
* `nslookup`
* Vérifications de la configuration DNS
* Tests de connectivité réseau

### Cause racine

Le client était configuré avec un serveur DNS incorrect.

### Résolution

La configuration DNS du client a été corrigée pour utiliser le contrôleur de domaine.

### Vérification

La résolution de noms a été testée à nouveau et a résolu avec succès le domaine interne.

---

## 📚 Ce que j'ai appris

Ce projet m'a permis de mettre en pratique :

* L'administration de Windows Server
* L'administration d'Active Directory
* Le dépannage DNS
* La gestion de la Stratégie de groupe
* Le réseau Azure
* Le contrôle d'accès
* Le dépannage d'infrastructure
* La documentation technique

---

## 🔮 Améliorations futures

Les futures versions du laboratoire pourraient inclure :

* Un serveur Linux
* La segmentation réseau
* La centralisation des journaux (logging)
* Un SIEM Wazuh
* La supervision (monitoring)
* Le déploiement automatisé avec Terraform
* Des tests de sauvegarde et de restauration
* Des investigations d'alertes de sécurité
