
![plan1](./etape_passive.png)
# 🧠 Analyse des Applications Web (Phase Passive)

## 🎯 Objectifs

- Comprendre le fonctionnement technique du site web cible (ex. `website.com`)
- Collecter des informations visibles dans le navigateur **sans interagir activement avec le serveur**
- Identifier les frameworks, technologies, redirections et éléments sensibles accessibles publiquement

---

## 🔍 Points d’analyse

| Élément cible                  | Objectif                                                                 |
|-------------------------------|--------------------------------------------------------------------------|
| **Code source HTML**          | Rechercher des **commentaires**, **clés API**, **bibliothèques JS**     |
| **Fichiers JavaScript**       | Identifier les fonctions critiques, endpoints API, logique frontend      |
| **URLs et redirections**      | Identifier les paramètres, redirections internes/externes                |
| **Headers HTTP**              | Voir technos, cookies, redirections, politiques de sécurité              |
| **Frameworks détectés**       | Déterminer les versions (React, WordPress, Laravel, etc.)                |
| **Pages bloquées**            | Contourner les murs JavaScript, contenu caché accessible via l’inspecteur |
| **Comportements dynamiques**  | Observer si le site charge du contenu via JS (AJAX/fetch)               |
| **Fichiers externes**         | Scripts, styles, fontes, trackers (Analytics, etc.)                      |
| **Infos utilisateurs affichées** | Voir si des données sont exposées dans le DOM ou JavaScript            |

---

## 🛠️ Outils à utiliser

| Outil DevTools      | Fonction principale                                                  |
|---------------------|-----------------------------------------------------------------------|
| Inspecteur DOM      | Lire HTML, observer commentaires, analyser structure du document     |
| Console             | Voir erreurs JavaScript, logs, injections ou comportements suspects   |
| Sources             | Accès à tous les JS / CSS / fichiers sources du site                 |
| Network             | Requêtes, cookies, headers, endpoints AJAX, XHR, fetch, etc.         |
| Storage             | Analyse LocalStorage, SessionStorage, IndexedDB                      |
| Application         | Voir le manifeste, workers, cache, données persistées                |
| Security            | Infos HTTPS, TLS, cookies sécurisés, mixed content                   |

---

## 🧪 Techniques supplémentaires à explorer

- **Analyse de fichiers .map** : tenter d'accéder à `main.js.map` pour reconstruire du code JS non minifié
- **Observation des cookies** : présence de JWT, sessions ou infos sensibles
- **Suivi des requêtes AJAX** : repérage d’endpoints internes `/api`, `/v1/`, etc.
- **Reconstruction d’arborescence** : `/admin/`, `/login`, `/dashboard` visibles dans les scripts ou redirections
- **Détection de framework** : analyse manuelle (présence de `wp-content`, `_next`, `csrf_token`, etc.)
- **Analyse des headers de sécurité** : CSP, X-Frame-Options, X-XSS-Protection, etc.

---

## 📎 Exemple de sources utiles

- Code source visible (clic droit > "Afficher le code source")
- Chrome DevTools ou Firefox Developer Edition
- Extension Wappalyzer (pour comparaison automatique de technos)
- Wayback Machine (si les JS ont changé dans le temps)

---

## 📌 Résumé

Cette phase permet de **cartographier l'environnement applicatif** du site sans aucune action intrusive. Elle est indispensable pour mieux cibler les prochaines étapes (enum, vulnérabilités, fuzzing).
