# Alexandrie Systems

Site officiel — [alexandrie.systems](https://alexandrie.systems)

**Architecture · Conseil · Transition IA** pour les PME suisses qui refusent la dispersion.

## Stack

Site statique HTML + CSS + JS vanilla, zéro build.

- **GSAP 3.12.5 + ScrollTrigger** (via CDN jsdelivr) pour le motion system
- **Google Fonts** : Bricolage Grotesque, Instrument Serif, JetBrains Mono
- La constellation de la démo est en SVG + JS pur (pas de D3)

## Structure

```
.
├── index.html                              Landing (HTML + CSS inline + JS inline)
├── blog/
│   ├── index.html                          Journal : liste des articles
│   └── backoffice-sur-mesure-vs-saas-7-criteres.html
├── assets/img/
│   ├── alexandrie-systems-logo.svg         Logo standard (mark + wordmark, fond clair)
│   ├── alexandrie-systems-logo-light.svg   Variante pour fond sombre
│   ├── alexandrie-systems-mark.svg         Mark seul (favicon, app icon)
│   ├── alexandrie-systems-og.svg           Image de partage 1200×630 (source)
│   ├── alexandrie-systems-og.png           Image de partage rendue (à régénérer si le SVG change)
│   └── logo.svg                            Logo Mirage Bleu (fond sombre uniquement)
├── robots.txt · sitemap.xml · humans.txt · CNAME
├── _config.yml                             Exclut les docs internes de la publication
└── DESIGN_SYSTEM.md                        Source de vérité design (non publiée)
```

## Sections de la landing

1. **Prologue** — overlay plein écran au chargement, mark + wordmark animés
2. **Hero** — « Architecture, mémoire, continuité. » + CTA rendez-vous
3. **Confiance** — citation du fondateur + référence Mirage Bleu (lien vers l'étude de cas)
4. **Démo interactive** — constellation chronométrée : 3 mandats fictifs, jusqu'à 23 artefacts révélés en 3 s
5. **Interventions** — 4 portes d'entrée : Cartographie, Construction, Transition IA, Transmission
6. **Pour qui** — 3 profils de PME
7. **Méthode** — 4 axiomes (Locality, Readability, Persistence, Traceability)
8. **Étude de cas** — Mirage Bleu : chiffres clés, maquette du Backoffice, 4 pôles
9. **Manifeste** — citation §05
10. **FAQ** — 5 questions (prix, durée, réversibilité, taille, après-livraison)
11. **Journal** — article à la une
12. **Contact** — e-mail + demande de rendez-vous par e-mail

## Motion system

`window.MB_MOTION` expose les helpers (revealText, scrubParallax, sectionEnter, magneticCta, floatY, heroExit, pinReveal, runPrologue, wireAll).

Auto-wire via l'attribut `data-motion="…"` + `data-reveal` pour les enfants de section. Respecte `prefers-reduced-motion`. Budget mobile : les scrubs sont désactivés sous 768 px.

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
