# Laboratoire pratique 0101 : Gestion des identités dans Entra ID


##  Exercice 1 : Création d'utilisateurs dans Entra ID
🎯 Objectif

Créer des comptes utilisateurs directement dans Microsoft Entra ID via le portail d’administration.

| Name            | User Name                          | Password  | Job title          | Department |
|-----------------|------------------------------------|-----------|--------------------|------------|
| Edmund Reeve    | ereeve@yourtenant.onmicrosoft.com  | Pa55-w.rd! | HR Rep             | HR         |
| Miranda Snider  | msnider@yourtenant.onmicrosoft.com | Pa55-w.rd! | Helpdesk Manager   | Operations |
| Cody Godinez    | cgodinez@yourtenant.onmicrosoft.com | Pa55-w.rd!  | Sales Rep          | Sales      |


1. Connexion au Microsoft Entra Admin Center
👉 https://entra.microsoft.com

(Compte administrateur)

2. Accès au menu Users > All users

   ![](../screenshots/Tous-les-utilisateurs.png)

Création d’un nouvel utilisateur

Type : Member

Mot de passe défini manuellement

Renseignements : nom, fonction, département

Usage location : United States

Aucune affectation de groupes ou rôles
(Configuration par défaut)

![](../screenshots/Info-Erevee.png)

Vérification et validation de la création
![](../screenshots/All-Users.png)

## Tâche 2 – Création d’utilisateurs avec PowerShell (Microsoft Graph)
🎯 Objectif

Créer un utilisateur Microsoft Entra ID via PowerShell 7 en utilisant le module Microsoft Graph.

1. Connexion au tenant
2. Création du profil mot de passe
3. Création de l’utilisateur Cody Godinez
4. Vérification
 ![](../screenshots/All-UsersPwsh.png)

## Exercise 2 – Attribution des rôles administratifs dans Microsoft Entra ID

🎯 Objectif

Analyser et attribuer des rôles administratifs aux utilisateurs du tenant Microsoft Entra ID selon leurs responsabilités.

| Nom             | Responsabilités principales              | Rôle administratif            |
|-----------------|------------------------------------------|-------------------------------|
| Allan Deyoung   | Gestion complète du tenant               | **Global Administrator**      |
| Edmund Reeve    | Gestion des utilisateurs et des groupes  | **User Administrator**        |
| Miranda Snider  | Réinitialisation des mots de passe       | **Helpdesk Administrator**    |


1. Accès à la gestion des rôles
2. Attribution du rôle Global Administrator au Allan Deyoung
    ![](../screenshots/Roles-Allan.png)
4. Attribution du rôle User Administrator au Edmund Reeve
    ![](../screenshots/Roles-Reeve.png)
6. Attribution du rôle Helpdesk Administrator au Miranda Snider
  ![](../screenshots/Roles-Miranda.png)

## Exercise 3: Creating and managing groups and validating license assignment
### Scénario - Attribution des groupes et des licences.
| Name            | Member of          | License to assign                                                                 |
|-----------------|--------------------|-----------------------------------------------------------------------------------|
| Edmund Reeve    | Contoso_Managers   | Office 365 E5 + EMS E5 (**group-based licensing**)                                 |
| Miranda Snider  | Contoso_Managers   | Office 365 E5 + EMS E5 (**group-based licensing**)                                 |
| Cody Godinez    | Contoso_Sales      | Office 365 E5 + EMS E5 (**direct assignment**)                                     |


### Tâche 1 – Création d’un groupe de sécurité dans Microsoft Entra ID
🎯 Objectif

Créer un groupe de sécurité et y ajouter des utilisateurs via le portail Microsoft Entra.

Accéder au Microsoft Entra Admin Center
👉 Groups

Sélectionner New group

Configurer le groupe :

Group type : Security

Group name : Contoso_Managers

Membership type : Assigned

Ajouter les membres :

Edmund Reeve

Miranda Snider

Sélectionner Create
![](../screenshots/Contoso_Managers.png)

### Tâche 2 – Création d’un groupe et ajout d’un membre via PowerShell

🎯 Objectif

Créer un groupe de sécurité et ajouter un utilisateur à l’aide de PowerShell 7 et du module Microsoft Graph.

1. Création du groupe de sécurité. 
2. Vérification de la créatrion du groupe.
3. Définition des variables.
4. Ajout de l'utilisateur au groupe
5. Vérification de l'appartenance au groupe.
   
![](../screenshots/Grupos-pwsh.png)

## Tâche 3 – Gestion des licences et personnalisation du branding Microsoft Entra

🎯 Objectif

Configurer et gérer les licences Microsoft 365 dans un tenant Entra ID, personnaliser l’expérience de connexion (branding) et attribuer des licences via utilisateur et via groupe, en utilisant les centres d’administration Microsoft Entra et Microsoft 365.

1. Vérification des licences disponibles.
   
![](../screenshots/Licence-Disp.png)

3. Personnalisation du branding (Sign-in page)
   
![](../screenshots/Conn-Person.png)

5. Vérification des licences utilisateur (Cody Godinez)
   
![](../screenshots/Cody-NoLicence.png)

7. Attribution des licences via Microsoft 365 Admin Center
   
![](../screenshots/Add-LicenseCody.png)

9. Attribution des licences par groupe (Contoso_Managers)
    
![](../screenshots/Add-Licen-Group.png)

11. Vérification de l’héritage des licences
    
![](../screenshots/Ver-Grups.png)

![](../screenshots/Ver-UtiDirect.png)


