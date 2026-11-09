# Alexandrie Systems

Site officiel — [alexandrie.systems](https://alexandrie.systems)

**Architecture · Conseil · Transition IA** pour les PME suisses qui refusent la dispersion.

## Stack

Site statique HTML + CSS + JS vanilla, zéro build, aucune ressource tierce.

- **Polices auto-hébergées** dans `assets/fonts/` (Bricolage Grotesque, Instrument Serif, JetBrains Mono — SIL OFL 1.1, voir `OFL.txt`) : pas d'appel à Google Fonts, donc pas d'adresse IP des visiteurs transmise à Google
- Animations : transitions CSS + apparition au défilement (`data-reveal`, IntersectionObserver)

## Structure

```
.
├── index.html                    Landing FR
├── en/index.html                 Landing EN (même structure, textes adaptés)
├── 404.html                      Page d'erreur bilingue (servie par GitHub Pages)
├── blog/                         Journal (FR uniquement)
├── assets/
│   ├── css/site.css              Styles partagés FR / EN / 404 (polices incluses)
│   ├── css/fonts.css             Polices seules, pour le blog (qui a son propre CSS inline)
│   ├── js/site.js                Nav au défilement + apparition des blocs
│   ├── fonts/                    Polices woff2 + licences
│   └── img/                      Logos, images de partage FR et EN (SVG source + PNG rendu)
├── favicon.ico · apple-touch-icon.png
├── robots.txt · sitemap.xml · humans.txt · CNAME
├── _config.yml                   Exclut les docs internes de la publication
└── DESIGN_SYSTEM.md              Source de vérité design (non publiée)
```

**Modifier un texte** : le changer dans `index.html` ET dans `en/index.html`. Les réponses de la FAQ
sont aussi dans les données structurées (bloc JSON-LD en haut de chaque page) : garder les deux identiques.

## Sections de la landing

Version courte depuis la v1.1 (novembre 2026) : 6 sections, environ 9 écrans sur mobile.

1. **Hero** — « Architecture, mémoire, continuité. » + rendez-vous / exemple
2. **Interventions** — Cartographie, Construction, Transition IA, Transmission (durée et prix) + public visé
3. **Exemple** — Mirage Bleu : avant / aujourd'hui, 4 chiffres, maquette du Backoffice, citation du fondateur
4. **Engagements** — propriété, formats ouverts, traçabilité, pas d'abonnement
5. **FAQ** — 5 questions en accordéon + lien vers l'article du Journal
6. **Contact** — e-mail

Version anglaise : `/en/`. Sélecteur FR / EN dans la barre de navigation, balises `hreflang` réciproques, déclarées aussi dans `sitemap.xml`.

Retirés en v1.1 (récupérables dans l'historique git, commit `317486b`) : prologue animé, démo
constellation, section Pour qui, axiomes en anglais, 8 pôles Mirage Bleu, manifeste, cartes Journal, GSAP.

## Développement local

```bash
python3 -m http.server 4173
```

Puis ouvrir http://localhost:4173. Le serveur Python ne résout pas les URL sans extension : ouvrir l'article via `/blog/backoffice-sur-mesure-vs-saas-7-criteres.html` (GitHub Pages, lui, sert aussi `/blog/backoffice-sur-mesure-vs-saas-7-criteres`).

## Déploiement

GitHub Pages, branche `main`, dossier racine. Chaque push sur `main` est en ligne en moins d'une minute. Domaine custom `alexandrie.systems` via `CNAME`.

## À compléter

- Métriques avant/après de l'étude de cas Mirage Bleu (bloc retiré tant que les chiffres ne sont pas validés ; gabarit dans l'historique git, commit `651e73f`)
- Autres références clients, dès qu'elles acceptent d'être citées (section Confiance)
- Articles « en préparation » du Journal

## Historique

Page développée en mai 2026 dans le repo `Backoffice_MirageBleu`, puis extraite en projet autonome pour devenir le site officiel `alexandrie.systems`. Version partageable v1.0 : novembre 2026.

## Licence

© Mirage Bleu Productions. Tous droits réservés.
