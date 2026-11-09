# Portfolio — Houcine Drifi

[![GitHub Pages](https://github.com/dhoucine62/portfolio/actions/workflows/deploy.yml/badge.svg)](https://github.com/dhoucine62/portfolio/actions/workflows/deploy.yml)

Mon portfolio personnel, développé avec Vue 3 et TypeScript. J’y présente ma formation en informatique, mes compétences et mes projets.

**Lien pour ouvrir le portfolio : [hdrifi.fr](hdrifi.fr)**


## Technologies

Vue 3 · TypeScript · Vite · Tailwind CSS

## Lancer le projet

Prérequis : **Node.js 22.18+ (branche 22) ou 24.12+**, et npm. Le workflow de déploiement utilise Node.js 24.

```sh
git clone https://github.com/dhoucine62/portfolio.git
cd portfolio
npm ci
npm run dev
```

Ouvrir l’adresse indiquée par Vite, généralement `http://localhost:5173/`.

## Vérifier et compiler

```sh
# Vérification TypeScript et compilation de production
npm run build

# Aperçu local du site compilé
npm run preview
```

La compilation produit le dossier `dist/`. Pour lancer uniquement la vérification TypeScript :

```sh
npm run type-check
```

## Organisation

```text
.github/workflows/deploy.yml  Vérification et déploiement GitHub Pages
src/pages/Home.vue           Présentation et projets
src/component/               Navigation, compétences et statistiques GitHub
src/style.css                Styles, adaptation mobile et impression
public/icon/                 Icônes des langages
public/projects/             Captures et sources des visuels
public/fonts/                Police locale et licence
```

Les captures des projets et leurs sources sont documentées dans [public/projects/README.md](public/projects/README.md). La police Barlow Condensed est distribuée avec sa [licence SIL Open Font License](public/fonts/OFL-BarlowCondensed.txt).

## Droits d’utilisation

© 2026 Houcine Drifi — **Tous droits réservés (All Rights Reserved / ARR)**.

Le code, le design et les contenus originaux du portfolio ne sont pas proposés sous licence libre. Leur réutilisation nécessite mon autorisation écrite préalable, sous réserve des droits prévus par la loi et des conditions de la plateforme d’hébergement. Voir le fichier [LICENSE](LICENSE).

Les dépendances, polices, icônes et captures de projets conservent leurs propres licences et les droits de leurs auteurs.

Références : [déploiement Vite sur GitHub Pages](https://vite.dev/guide/static-deploy.html#github-pages) et [workflows GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).
