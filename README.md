# Loyal Qotation — MVP PWA

Application web progressive (PWA) autonome pour **Loyal Engineering SARL**.

## Objectif du MVP
Créer et gérer des qotations/devis directement sur l'appareil, sans serveur et sans base de données externe.

### Données
- Stockage local du navigateur avec `localStorage`.
- Sauvegarde manuelle en fichier JSON.
- Restauration depuis un fichier JSON.
- Aucune API, aucun backend et aucune base de données externe.

### Qotation
- Devis estimatif ou définitif.
- N°, date, validité et statut.
- Projet et fournisseur principal (`Loyal Hardware` par défaut).
- Client : nom, adresse, téléphone, e-mail.
- Préparateur : nom, fonction, téléphone.
- Articles : référence, désignation, spécification, unité, quantité, coût d'achat interne, majoration, prix de vente, marque, fournisseur.
- Calcul automatique du prix de vente et des totaux.
- Remise séparée des paiements/avances.
- Taxes, main-d'œuvre, transport et solde restant.
- Résumé interne des coûts/marges non imprimé dans le document client.
- Impression A4 / enregistrement PDF via la boîte d'impression du navigateur.

### PWA Android + iPhone
- `manifest.json` inclus.
- Service worker inclus pour le fonctionnement hors connexion après première visite.
- Icônes 192×192, 512×512, 1024×1024 et Apple Touch Icon.
- Installation via les options du navigateur compatible (Chrome/Edge, etc.).
- Sur iPhone/iPad : Safari → Partager → « Sur l’écran d’accueil ».
- Mode application `standalone`.

## Héberger soi-même avec GitHub Pages
1. Créer un dépôt GitHub.
2. Copier **le contenu de ce dossier** à la racine du dépôt.
3. Activer **Settings → Pages → Deploy from branch** sur la branche souhaitée et le dossier `/root`.
4. Ouvrir l'adresse HTTPS GitHub Pages sur Android ou Safari iPhone.
5. Sur Android/Chrome/Edge : utiliser le menu du navigateur → **Installer l’application** / **Ajouter à l’écran d’accueil**.
6. Sur iPhone/iPad : Safari → **Partager** → **Sur l’écran d’accueil**.

> Le PWA, son service worker et Bootstrap local nécessitent une URL HTTPS pour fonctionner correctement en production. GitHub Pages fournit HTTPS.

## Test local
Depuis ce dossier :

```bash
python -m http.server 8080
```

Puis ouvrir `http://localhost:8080`.

## Sécurité MVP
- PIN local modifiable depuis Paramètres.
- PIN initial : `1234`.
- Code de réinitialisation : `0509`.
- Le PIN n'est pas une authentification serveur : il sert uniquement à protéger l'interface sur l'appareil.

## Limites volontaires du MVP
- Pas de synchronisation entre appareils.
- Pas de compte utilisateur.
- Pas de serveur.
- Pas de base de données externe.
- Pas de facturation en ligne.


### Interface
L’interface utilise **Bootstrap 5.3.6 en local** (aucun CDN), avec une couche de style personnalisée. Cela conserve le fonctionnement autonome et hors connexion.
