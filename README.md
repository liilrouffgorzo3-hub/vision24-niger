VISION 24 NIGER — PACK NETLIFY FINAL

CONTENU
- index.html : interface média style Netflix d'origine, enrichie des commandes Radio 95.1 FM et Studio de diffusion.
- manifest.json : métadonnées d'installation mobile (PWA).
- netlify.toml : publication du dossier racine et routes serveur.
- netlify/functions/status.js : contrôle /api/status.
- netlify/functions/facebook-publish.js, youtube-upload.js, whatsapp-send.js : routes désactivées par sécurité.

INSTALLATION SUR LE PROJET NETLIFY EXISTANT
1. Décompressez ce ZIP.
2. Remplacez les fichiers du dépôt GitHub relié à votre site avec les fichiers de ce dossier.
3. Conservez index.html à la racine du dépôt.
4. Envoyez les modifications dans le même dépôt et attendez le nouveau déploiement Netlify.
5. Vérifiez https://VOTRE-SITE/api/status.

RADIO 95.1 FM
La fréquence 95.1 MHz est affichée dans l'interface. Pour entendre la radio en ligne, saisissez l'URL réelle du flux audio de la station dans la section Radio puis cliquez sur « Enregistrer le flux ». La fréquence seule ne constitue pas un flux Internet; l'URL doit venir de l'opérateur radio.

FACEBOOK / YOUTUBE / WHATSAPP
Les liens de direct peuvent être enregistrés dans le navigateur et ouverts depuis l'application; le partage WhatsApp ouvre l'application/site WhatsApp avec le message prérempli. La publication ou diffusion automatique exige les API officielles, OAuth et une authentification serveur sécurisée. Les routes d'envoi restent désactivées, intentionnellement, jusqu'à cette configuration.
Ne placez jamais de mots de passe ni de jetons privés dans index.html.
