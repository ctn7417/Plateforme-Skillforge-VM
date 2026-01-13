# Déploiement IIS (VM Windows)

Ce guide décrit le déploiement d'une application **ASP.NET Core** sur **IIS**.

## Prérequis

- Windows Server (ou Windows 10/11 avec IIS)
- .NET Hosting Bundle (correspondant à la version .NET utilisée)
- IIS installé avec les modules nécessaires

## Étapes

1. **Installer IIS**
   - Panneau de configuration → Activer/Désactiver des fonctionnalités Windows
   - Activer : IIS, ASP.NET, .NET Extensibility, WebSocket (si nécessaire)

2. **Installer le .NET Hosting Bundle**
   - Téléchargement via Microsoft (version correspondant au projet)
   - Redémarrer IIS après installation

3. **Publier l'application**
   - `dotnet publish -c Release -o <chemin>`
   - Copier le dossier publié sur la VM (ex: `C:\sites\skillforge`)

4. **Créer le site IIS**
   - IIS Manager → Sites → Add Website
   - Physical path : `C:\sites\skillforge`
   - Binding : http/https + port

5. **Configurer le pool d'applications**
   - .NET CLR version : **No Managed Code** (ASP.NET Core)
   - Identity : utilisateur avec accès au dossier

6. **Configurer la base de données**
   - Chaîne de connexion dans `appsettings.Production.json`
   - Vérifier les droits SQL Server

7. **Test de disponibilité**
   - Ouvrir l'URL publique
   - Vérifier le fichier `stdout` (logs de démarrage)

## Dépannage rapide

- 500.30 : le runtime .NET manque ou l'app ne démarre pas
- 502.5 : erreurs de démarrage (voir logs)
- Permissions insuffisantes sur le dossier publié
