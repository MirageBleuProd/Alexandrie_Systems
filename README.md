# Alexandrie Systems

Landing page autonome — [alexandrie.systems](https://alexandrie.systems) (à venir).

**Architecture · Conseil · Transition IA** pour les PME suisses qui refusent la dispersion.

## Stack

Page statique HTML + CSS + JS vanilla, zéro build.

- **GSAP 3.12.5 + ScrollTrigger** (via CDN jsdelivr) pour le motion system
- **Google Fonts** : Bricolage Grotesque, Instrument Serif, JetBrains Mono
- **D3** non utilisé (la constellation est SVG + JS pur)

## Structure

```
.
├── index.html                              Page complète (HTML + CSS inline + JS inline)
└── assets/img/
    ├── alexandrie-systems-logo.svg         Logo standard (mark + wordmark, fond clair)
    ├── alexandrie-systems-logo-light.svg   Variante pour fond sombre
    ├── alexandrie-systems-mark.svg         Mark seul (favicon, app icon)
    ├── alexandrie-systems-og.svg           Image Open Graph 1200×630 (source)
    ├── alexandrie-systems-og.png           Image OG rendue (social preview)
    └── logo.svg                            Logo Mirage Bleu (utilisé dans le case study)
```

## Sections

1. **Prologue cinematic** — overlay full-screen au load, mark + wordmark animés, tagline mono
2. **Hero** — titre éditorial XXL avec accent italique, baseline + CTAs
3. **Constellation chronométrée** — démo interactive 23 artefacts révélés en 3s
4. **Stats** — 3 chiffres clés en bloc violet
5. **Interventions** — 4 portes d'entrée (Audit / Architecture / Construction / Transmission)
6. **Pour qui ?** — auto-qualification 3 profils sectoriels PME
7. **Axiomes** — méthodologie (8 principes en grille)
8. **Études de cas** — Mirage Bleu (8 pôles + statistiques inline)
9. **Pull / Manifeste** — citation centrale §05
10. **FAQ** — 5 objections / 5 réponses
11. **Contact** — formulaire + coordonnées

## Motion system

`window.MB_MOTION` expose 8 helpers (revealText, scrubParallax, sectionEnter, magneticCta, floatY, heroExit, pinReveal, runPrologue, wireAll).

Auto-wire via `data-motion="…"` attribute API + `data-reveal` pour les enfants de section. Respecte `prefers-reduced-motion`. Budget mobile : les scrubs sont désactivés `<768px`.

## Déploiement

Page autoportée — n'importe quel hébergement statique (GitHub Pages, Cloudflare Pages, Netlify, Vercel, Infomaniak SiteCreator).

Pour GitHub Pages :
```bash
# Settings > Pages > Branch: main, Folder: / (root)
# URL: https://miragebleuprod.github.io/Alexandrie_Systems/
# Domaine custom : alexandrie.systems via CNAME
```

## Historique

Cette page a été développée incrémentalement en mai 2026 sous le repo `Backoffice_MirageBleu` (route `/alex`), puis extraite en projet standalone pour devenir le site officiel `alexandrie.systems`.

5 phases de motion design (audace 8/10) :
- **Phase 1** — motion foundation (GSAP + 4 helpers data-motion API)
- **Phase 2** — prologue cinematic + crossover event-driven
- **Phase 3** — scrub transitions (parallax, float-y, hero exit, pin reveal)
- **Phase 4** — micro-interactions premium (focus ring, hover lift, polestar underline)
- **Phase 5** — cleanup + perf budget mobile + drop Inter (2 polices canoniques)

## Licence

© Mirage Bleu Productions. Tous droits réservés.
