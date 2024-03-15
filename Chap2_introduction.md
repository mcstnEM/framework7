# Introduction à Framework7

On a vu qu'on pouvez créer un projet Framework7 avec `framework7 create --ui`, rentrons maintenant plus en détail sur Framework7 dans ce cours.

# Structure de base d'un projet Framework7

```txt
our_framework7_project
├── README.md
├── assets-src
│   ├── apple-touch-icon.png
│   └── web-icon.png
├── build
├── framework7.json
├── package-lock.json
├── package.json
├── postcss.config.js
├── public
│   └── icons
├── src
│   ├── app.f7
│   ├── assets
│   ├── css
│   ├── fonts
│   ├── index.html
│   ├── js
│   ├── manifest.json
│   └── pages
├── vite.config.js
├── workbox-config.js
└── www
```

# Gérer les assets

https://framework7.io/cli/generate-assets

Les assets sont des images, polices et autre médias. Quand on parle d'asset, en particulier des images, il est important de les adapter pour que notre application soit performante. Par exemple, il est inutile qu'un png soit trop lourd pour une icone.

On doit d'abord placer nos images dans le dossier `assets-src/` se trouvant à la racine de notre projet.

Ensuite, nous pouvons lancer la commande `framework7 assets` pour optimizer nos images.

Vous avez aussi la commande `framework7 assets --ui` pour l'interface grafique.