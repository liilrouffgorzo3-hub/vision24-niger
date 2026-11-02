VISION 24 NIGER — PACK NETLIFY AVEC ESPACE ADMINISTRATEUR (VERSION DE PRÉPARATION)

CONTENU
- index.html : site public d'origine conservé, lecteur radio, studio média et nouvel espace / bouton ADMIN VISION24.
- supabase-config.js : Project URL et Publishable Key du projet Vision24. Cette clé est publique par conception; aucune clé service_role/secret n'est incluse.
- INSTALLATION-ADMIN-SUPABASE.sql : migration SQL idempotente pour les tables et règles RLS.
- netlify/functions : endpoints existants; les publications automatiques sociales restent désactivées jusqu'à OAuth et configuration des secrets serveur.

AVANT LE DÉPLOIEMENT — À FAIRE UNE FOIS
1. Dans Supabase > Éditeur SQL > Nouvelle requête, ouvrir INSTALLATION-ADMIN-SUPABASE.sql, copier tout son contenu et l'exécuter.
2. Vérifier dans public.profiles que le compte administrateur existant a role = 'admin'. Le ZIP ne modifie pas les utilisateurs ni les mots de passe.
3. Vérifier que Authentication > Users contient le même e-mail et que la connexion par mot de passe est activée.

INSTALLATION SUR LE PROJET NETLIFY EXISTANT
1. Décompresser ce ZIP.
2. Remplacer les fichiers du dépôt GitHub relié au site avec le contenu du dossier VISION24_NETLIFY_FINAL_MIX (index.html à la racine du dépôt).
3. Envoyer les modifications dans le même dépôt GitHub et attendre le déploiement Netlify.
4. Ouvrir le site et appuyer sur ADMIN VISION24. Se connecter avec l'e-mail et le mot de passe du compte Supabase déjà créé.
5. Si la connexion échoue, vérifier que le SQL ci-dessus a été exécuté intégralement et que le rôle du compte est bien admin.

FONCTIONS ADMIN DISPONIBLES APRÈS CONFIGURATION SQL
- Connexion Supabase Auth et vérification du rôle admin.
- Création de brouillons et publication d'actualités dans Supabase.
- Affichage public des six dernières publications publiées.
- Enregistrement de l'URL du flux radio dans Supabase et préparation du lecteur public.
- Enregistrement de vidéos dans la base.

LIMITES IMPORTANTES
- La lecture radio nécessite l'URL réelle du flux audio fournie par l'opérateur. La fréquence 95.1 MHz ne suffit pas.
- L'URL du flux est enregistrable dans l'administration, mais il faut vérifier que le serveur de radio autorise la lecture web (HTTPS/CORS et format audio compatible).
- Facebook, YouTube et WhatsApp ne sont PAS encore connectés pour publication automatique. Les comptes doivent être autorisés par OAuth/API officielles; les jetons privés seront stockés dans les variables d'environnement Netlify, jamais dans le navigateur.
- WhatsApp Business Platform permet l'envoi de messages selon ses règles et consentements; elle ne permet pas la publication automatique de statuts WhatsApp via l'API standard.
- L'upload de fichiers média et le stockage Supabase Storage ne sont pas encore intégrés; les champs média acceptent pour le moment des URL accessibles publiquement.

SÉCURITÉ
La Publishable Key dans supabase-config.js est une clé publique. La sécurité des données dépend des politiques RLS du fichier SQL. Ne jamais publier une clé secret/service_role ni un jeton de réseau social dans index.html ou supabase-config.js.
