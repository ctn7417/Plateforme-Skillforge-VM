# Plateforme Skillforge (MVP)

Ce dépôt initialise le projet d'une **plateforme de formation en ligne** (inspirée d'Udemy) destinée à être déployée sur une **VM Windows avec IIS**.

## Objectif

Créer un MVP permettant :
- la publication de cours vidéo par des formateurs,
- l'inscription et le suivi de progression par des apprenants,
- la gestion des paiements, coupons et promotions.

## Stack recommandée (MVP)

- **Back-end** : ASP.NET Core (API REST)
- **Front-end** : React (SPA) ou Razor Pages pour un démarrage rapide
- **Base de données** : SQL Server
- **Stockage médias** : Azure Blob Storage (ou stockage local pour le MVP)
- **Hébergement** : IIS sur Windows Server

## Contenu du dépôt

- `docs/requirements.md` : besoins fonctionnels et rôles
- `docs/roadmap.md` : étapes et livrables du MVP
- `docs/iis-setup.md` : guide de déploiement IIS (VM Windows)

## Prochaines étapes proposées

1. Valider les fonctionnalités MVP (cours, paiement, vidéo, progression).
2. Initialiser la solution (`dotnet new sln` + API + UI).
3. Définir le modèle de données et le schéma SQL.
4. Mettre en place l'authentification et les rôles.
5. Déployer une première version sur IIS.

## Questions ouvertes

- Souhaitez-vous **multi-langue** dès le MVP ?
- Faut-il prévoir **des certificats** à la fin des cours ?
- Avez-vous un **prestataire de paiement** préféré (Stripe, PayPal, autre) ?
