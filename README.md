# Traitement de l'eau — application d'interventions

Première version statique pour GitHub Pages, avec formulaires d'intervention, recherche, connexion administrateur Supabase, liste de documents approuvés et impression PDF via le navigateur.

## Installation

1. Importer `index.html`, `app.js` et `config.js` à la racine du dépôt GitHub.
2. Renseigner **uniquement** l'URL du projet et la clé **publishable/anon** dans `config.js` (jamais de clé secrète/service_role).
3. Vérifier la structure réelle de `public.interventions` dans Supabase : le code utilise `id`, `date_intervention`, `technicien`, `numero_serie`, `numero_parc`, `materiel`, `type_intervention`, `travaux_effectues`, `remarques`, `statut_validation`. Adapter le code ou la table avant l'usage réel.
4. Vérifier et tester les politiques RLS, notamment les accès visiteurs, administrateur et documents, avant de publier.
5. Pour GitHub Pages gratuit, un dépôt public est généralement nécessaire sur un compte Free. **Ne rendre public qu'après audit de sécurité** ; ne jamais publier de données réelles dans le dépôt.

## Limitations importantes

- Sans configuration Supabase, le mode démonstration ne conserve les fiches qu'en mémoire pendant la session.
- La génération PDF utilise « Imprimer / Enregistrer en PDF » du navigateur ; l'envoi automatique par e-mail n'est pas implémenté.
- Les documents du bucket privé ne sont pas téléchargeables depuis cette version : il faudra une fonction serveur autorisée pour délivrer des liens temporaires après contrôle des droits.
- Aucune donnée personnelle, patient ou médicale sensible ne doit être saisie avant revue de la sécurité et conformité.
- L'interface administrateur n'est pas un mécanisme de sécurité : seules les politiques Supabase font autorité.
