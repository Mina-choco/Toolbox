# Projet Toolbox

Ce projet contient deux scripts PowerShell :
1. **Reconnaissance** (Tool2.ps1)
2. **Exploitation** (Toolbox.ps1)

## Table des matières

- [Installation](#installation)
- [Utilisation](#utilisation)
- [Fonctionnalités](#fonctionnalités)


![image](https://github.com/Mina-choco/Toolbox/assets/155466776/cc231e05-73fa-4d03-9537-ce119362808a)


### Fonctionnalités

<u> Reconnaissance </u> (Tool2.ps1)

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

***Exploitation (Toolbox.ps1)

Le script d'exploitation effectue des requêtes LDAP sur l'Active Directory et génère toutes les informations importantes qu’un attaquant peut exploiter dans un environnement Active Directory (ordinateurs, utilisateurs, GPO, etc.).

**Dashboard Overview**

- FSMO Role Holders: Identification des détenteurs de rôles FSMO.
- AD Recycle Bin Status: État de la corbeille Active Directory.
- Valid UPN Suffixes: Affichage des suffixes UPN valides.
- Group Memberships: Domain Admins et Enterprise Admins.
- Default OU Objects: Ordinateurs et utilisateurs dans les OU par défaut.
- AD Objects Modified: Objets AD modifiés dans les "X" derniers jours.
- User Activity: Utilisateurs inactifs, nouveaux comptes utilisateurs, logs de sécurité.

**Groups Report**

- Group Details: Affiche tous les groupes et leurs membres.
- Interactive Pie Charts: Graphiques circulaires dynamiques.

**Organizational Units (OU) Report**

- OU Details: Date de modification, protection contre la suppression accidentelle, GPO liés.
- Pie Charts: Vue d’ensemble des OUs avec des liens GPO et protection contre la suppression accidentelle.

**Users Report**

- User Account Health: Nombre total d’utilisateurs, mots de passe expirant bientôt, comptes arrivant à expiration, utilisateurs inactifs, nouveaux comptes.
- Active Directory Users Table: Détail des utilisateurs et leurs attributs principaux.

**Group Policy Report**

- Group Policy Objects: État des objets de stratégie de groupe, date de modification, versions utilisateurs et ordinateurs.

**Computers Report**

- Computer Objects Overview: Nombre total d’objets ordinateur, répartition des systèmes d’exploitation, statut de protection contre la suppression accidentelle, ordinateurs activés vs désactivés.
