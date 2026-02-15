# Guide d'installation — Plateforme Primes 2026

## Vue d'ensemble

L'application se compose de 3 éléments :
- Votre Google Sheet existant (Simulation_de_primes_2026) = la base de données
- Un Google Apps Script = le pont entre le site et le Sheet
- Un site web sur GitHub Pages = l'interface pour les managers

---

## ÉTAPE 1 — Configurer Google Apps Script

1. Ouvrez votre Google Sheet Simulation_de_primes_2026
2. Allez dans Extensions > Apps Script
3. Supprimez tout le code existant dans l'éditeur
4. Copiez-collez tout le contenu du fichier google-apps-script.js
5. IMPORTANT : En haut du fichier, changez le mot de passe :
   const MOT_DE_PASSE = "votre_mot_de_passe_ici";
6. Cliquez sur Enregistrer (Ctrl+S)
7. Cliquez sur Déployer > Nouveau déploiement
8. Cliquez sur l'engrenage et sélectionnez Application Web
9. Configurez :
   - Exécuter en tant que : Moi
   - Accès : Tout le monde
10. Cliquez Déployer et autorisez l'accès
11. Si "Application non vérifiée" apparaît : Paramètres avancés > Accéder
12. Copiez l'URL du déploiement (https://script.google.com/macros/s/xxxxx/exec)

---

## ÉTAPE 2 — Déployer le site sur GitHub Pages

1. Allez sur github.com/new
2. Nom du repo : gestion-primes (en privé)
3. Cliquez Create repository
4. Cliquez "uploading an existing file"
5. Glissez index.html et le dossier .github
6. Cliquez Commit changes
7. Allez dans Settings > Pages
8. Source : GitHub Actions
9. Votre site sera à : https://VOTRE-USERNAME.github.io/gestion-primes/

---

## ÉTAPE 3 — Première connexion

1. Ouvrez le site
2. En bas de la page de connexion, collez l'URL Apps Script
3. Entrez le mot de passe
4. Vos données se chargent automatiquement

L'URL est sauvegardée dans le navigateur, les managers ne la configurent qu'une fois.

---

## Utilisation

Managers : ouvrir le site, mot de passe, sélectionner société, cliquer sur le mois, entrer le CA.
Pour les volants : déclarer le nombre de jours par magasin.

Contrôleuse de gestion : modifier paliers, augmentation, formule, ajouter/supprimer magasins et vendeurs, objectif manuel (clic sur le crayon), export Excel.

---

## Onglets créés automatiquement dans le Sheet

- _CONFIG : paliers, augmentation, formule par société
- _SAISIE_CA : CA réalisé et objectifs manuels
- _VOLANTS : jours des vendeurs volants

Ne supprimez pas ces onglets.

---

## FAQ

- Modification directe du Sheet : oui, cliquez actualiser dans le site
- Deux managers en même temps : pas de problème
- Changer le mot de passe : modifiez dans Apps Script puis Nouveau déploiement
- Ajouter une société : créez un nouvel onglet dans le Sheet avec le même format
- Objectifs faux : cliquez sur le crayon pour objectif manuel
