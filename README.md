# Projet Toolbox

L'objectif ultime de ce projet professionnel dans le domaine de la cybersécurité est de concevoir une boîte à outils automatisée dédiée à l'exécution de tests d'intrusion. Cette solution innovante, axée sur l'Active Directory, vise à renforcer la sécurité des systèmes informatiques et des réseaux de l'entreprise X. En fournissant une solution automatisée pour des tests d'intrusion de haute qualité, le projet aspire à consolider la réputation de l'entreprise, tout en optimisant la satisfaction des clients dans le domaine dynamique de la cybersécurité

Ce projet contient deux scripts PowerShell :
1. **Reconnaissance** (Tool2.ps1)
2. **Exploitation** (Toolbox.ps1)

## Table des matières

- [Installation](#installation)
- [Utilisation](#utilisation)
- [Schéma d'architecture](#schémad'architecture).
- [Fonctionnalités](#fonctionnalités)

### Installation

- [x] Windows Server 2025
- [x] Windows 11
- [x] Outils non présent sur OS Windows (Nmap)
- [x] Environnement de développement intégré

### Utilisation

Voici la manière d’exécuter le script en cli :

+	Si le script est à la racine :
```powershell
.\Tool2.ps1
.\Toolbox.ps1
```

+	Si le script est dans un répertoire spécifique :
```powershell
cd "path"
.\Tool2.ps1
```

### Schéma d'architecture

![image](https://github.com/Mina-choco/Toolbox/assets/155466776/cc231e05-73fa-4d03-9537-ce119362808a)


### Fonctionnalités

#### Reconnaissance  (Tool2.ps1)

Le script de reconnaissance offre les fonctionnalités suivantes :

```powershell
Write-Host "================== Menu ======================"
Write-Host "1: Press '1' for Scanning."
Write-Host "2: Press '2' for dictionary."
Write-Host "3: Press '3' for Complexity of Password."
Write-Host "4: Press '4' for Authentication."
Write-Host "5: Press '5' for Post-Exploitation."
Write-Host "6: Press '6' for the Report."
Write-Host "7: Press 'Q' to quit."
```


1. **Scanning**

+ Version : Nmap 7.95
+ Mode d’emploi : Scanne les ports d'un hôte pour identifier les services disponibles et évaluer la sécurité.
+ Dépendances : Nmap, WinPcap/Npcap

2. **Dictionnaire**

+ Mode d’emploi : Teste une liste de mots de passe sur plusieurs comptes utilisateurs en utilisant une méthode de brute-force.
+ Dépendances : Aucune

3. **Analyse de la sécurité des mots de passe**

+ Mode d’emploi : Évalue la force d'un mot de passe sur quatre critères (caractères spéciaux, chiffres, minuscules, majuscules).
+ Dépendances : Aucune

4. **Tests d'authentification**
+ Mode d’emploi : Accède à la session de l’Active Directory à distance en utilisant des informations d'identification.
+ Dépendances : PowerShell, activation des scripts PowerShell

5. **Post-exploitation**
+ Mode d’emploi : Affiche les dix dernières vulnérabilités du site CIRCL pour une veille informatique.
+ Dépendances : Requête API à CIRCL API

6. **Rapport**
+ Mode d’emploi : Génère un rapport des actions effectuées et des résultats obtenus.
+ Dépendances : Aucune

#### Exploitation (Toolbox.ps1)

Le script d'exploitation effectue des requêtes LDAP sur l'Active Directory et génère toutes les informations importantes qu’un attaquant peut exploiter dans un environnement Active Directory (ordinateurs, utilisateurs, GPO, etc.).

1. **Dashboard Overview**

- FSMO Role Holders: Identification des détenteurs de rôles FSMO.
- AD Recycle Bin Status: État de la corbeille Active Directory.
- Valid UPN Suffixes: Affichage des suffixes UPN valides.
- Group Memberships: Domain Admins et Enterprise Admins.
- Default OU Objects: Ordinateurs et utilisateurs dans les OU par défaut.
- AD Objects Modified: Objets AD modifiés dans les "X" derniers jours.
- User Activity: Utilisateurs inactifs, nouveaux comptes utilisateurs, logs de sécurité.

2. **Groups Report**

- Group Details: Affiche tous les groupes et leurs membres.
- Interactive Pie Charts: Graphiques circulaires dynamiques.

3. **Organizational Units (OU) Report**

- OU Details: Date de modification, protection contre la suppression accidentelle, GPO liés.
- Pie Charts: Vue d’ensemble des OUs avec des liens GPO et protection contre la suppression accidentelle.

4. **Users Report**

- User Account Health: Nombre total d’utilisateurs, mots de passe expirant bientôt, comptes arrivant à expiration, utilisateurs inactifs, nouveaux comptes.
- Active Directory Users Table: Détail des utilisateurs et leurs attributs principaux.

5. **Group Policy Report**

- Group Policy Objects: État des objets de stratégie de groupe, date de modification, versions utilisateurs et ordinateurs.

6. **Computers Report**

- Computer Objects Overview: Nombre total d’objets ordinateur, répartition des systèmes d’exploitation, statut de protection contre la suppression accidentelle, ordinateurs activés vs désactivés.
