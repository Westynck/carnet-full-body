# Carnet Full Body

Application web installable pour suivre un programme **full body en 3 séances de 45 minutes par semaine** : mode séance guidé, minuteur de repos, échauffement calculé, fiches animées des mouvements, remplacement d'exercices et suivi des performances.

## Installer l'application sur ton téléphone

L'application est publiée avec GitHub Pages. Ouvre son adresse sur ton téléphone, puis :

**iPhone (Safari obligatoire)**
1. Touche le bouton **Partager** (carré avec une flèche vers le haut).
2. Choisis **Sur l'écran d'accueil**, puis **Ajouter**.

**Android (Chrome)**
1. Touche le menu **⋮** en haut à droite.
2. Choisis **Installer l'application** (ou **Ajouter à l'écran d'accueil**).

L'icône « Full Body » apparaît ensuite sur ton écran d'accueil. L'application s'ouvre en plein écran et fonctionne sans réseau après le premier lancement.

## Où sont mes données ?

Tes séances sont enregistrées **uniquement sur ton téléphone**, dans le stockage de l'application. Conséquences :
- elles ne sont pas partagées avec la version de l'application ouverte dans Claude ;
- si tu supprimes l'application de l'écran d'accueil ou si tu effaces les données du navigateur, elles sont perdues.

## Structure du projet

```
index.html              l'application (HTML, CSS et JavaScript dans un seul fichier)
manifest.webmanifest    nom, icônes et couleurs pour l'installation
sw.js                   service worker : cache pour le fonctionnement hors ligne
icons/                  icônes de l'application
```

## Mettre à jour l'application

1. Modifie `index.html`.
2. Dans `sw.js`, augmente `VERSION` (par exemple `"v1"` → `"v2"`), sinon les téléphones garderont l'ancienne version en cache.
3. Pousse sur la branche `main`. GitHub Pages republie en une à deux minutes.
4. Sur le téléphone, ferme complètement l'application et rouvre-la (deux fois si besoin).

## Tester en local

```
python3 -m http.server 8000
```

Puis ouvre http://localhost:8000. Le service worker ne fonctionne qu'en `localhost` ou en HTTPS.
