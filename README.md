# Alexandrie Systems

Site officiel — [alexandrie.systems](https://alexandrie.systems)

**Architecture · Conseil · Transition IA** pour les PME suisses qui refusent la dispersion.

## Stack

Site statique HTML + CSS + JS vanilla, zéro build, aucun script externe.

- **Google Fonts** : Bricolage Grotesque, Instrument Serif, JetBrains Mono
- Animations : transitions CSS + apparition au défilement (`data-reveal`, IntersectionObserver)

## Structure

```
.
├── index.html                              Landing (HTML + CSS inline + ~15 lignes de JS)
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

Version courte depuis la v1.1 (novembre 2026) : 6 sections, environ 9 écrans sur mobile.

1. **Hero** — « Architecture, mémoire, continuité. » + rendez-vous / exemple
2. **Interventions** — Cartographie, Construction, Transition IA, Transmission (durée et prix) + public visé
3. **Exemple** — Mirage Bleu : avant / aujourd'hui, 4 chiffres, maquette du Backoffice, citation du fondateur
4. **Engagements** — propriété, formats ouverts, traçabilité, pas d'abonnement
5. **FAQ** — 5 questions en accordéon + lien vers l'article du Journal
6. **Contact** — e-mail

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
