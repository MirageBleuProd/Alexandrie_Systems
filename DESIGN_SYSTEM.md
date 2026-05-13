# Alexandrie Systems — Design System

> Source de vérité unique pour recréer un système cohérent avec la marque Alexandrie Systems. Self-contained : tout ce qu'il faut pour reconstruire l'identité visuelle, la voix éditoriale, et les patterns d'interaction.
>
> Maintenu dans le repo `Alexandrie_Systems` à la racine. Toute évolution majeure doit passer par ce fichier en premier.

---

## 1. Identité & Voix

### 1.1 Positioning

**Alexandrie Systems** est un studio suisse (Neuchâtel) qui conçoit des **Backoffices propriétaires sur mesure** pour PME (10-150 personnes). Le positionnement n'est pas "agence digitale" ni "consultant SaaS" — c'est **architecte de systèmes d'information à transmettre**.

Tagline officielle : **« Un spécialiste se reconnaît à son système, pas à sa taille. »**

H1 actuel : **« Architecture, mémoire, continuité. »**

Sous-titre : **« Nous concevons des systèmes pour les organisations qui refusent la dispersion. Des structures sur mesure, pensées pour durer. »**

### 1.2 Voix de marque

**Caractéristiques** :
- Phrases courtes, denses, affirmatives
- Conviction tranquille, jamais commerciale ni démonstrative
- Vocabulaire récurrent : *système, souveraineté, dispersion, transmission, axiomes, structures, continuité, durer, refuser, propriétaire, mémoire opérationnelle*
- Anti-SaaS / anti-dispersion / pro-souveraineté technique
- Premium-confident, jamais condescendant
- Français suisse-romand : pas d'anglicismes inutiles, pas de gallicismes lourds
- **Bannir** : superlatifs marketing ("révolutionnaire", "incroyable"), checkmarks dans des listes, points d'exclamation, jargon commercial ("monétiser", "scaler", "best-in-class"), interjections ("alors", "écoutez")

**Patterns rhétoriques** :
- Affirmation + ajustement : *« Le SaaS a sa place. Mais quand on parle du cœur opérationnel d'une entreprise… »*
- Définition par opposition : *« La réversibilité n'est pas une option commerciale, c'est une propriété structurelle du système. »*
- Métaphores opérationnelles, jamais grandiloquentes : *« Vous êtes locataire de votre propre mémoire. »*

**Tournures à privilégier** :
- *« Tout dirigeant finit par se poser la même question. »*
- *« Pour les organisations qui refusent la dispersion. »*
- *« Conçu pour survivre à son auteur. »*
- *« Aux logiciels, aux modes, aux fournisseurs. »*

### 1.3 Cible lecteur

Dirigeant ou bras droit d'une PME suisse (10-150 personnes), 40-55 ans, technique mais pas dev. Déjà échaudé par 1-2 outils SaaS. Méfiant des promesses. Cherche à comprendre AVANT d'acheter.

---

## 2. Design Tokens

### 2.1 Couleurs

```css
:root{
  /* Neutres */
  --bone:        #f4f0e8;   /* Fond principal (crème chaude) */
  --bone-deep:   #ebe5d8;   /* Fond cartes intervention */
  --ink:         #0a0a0a;   /* Texte principal */
  --ink-soft:    #3a3a3a;   /* Texte secondaire */
  --ink-faint:   #7a7a78;   /* Texte tertiaire / metadata */
  --ink-muted:   #6a6a6a;   /* (variante blog/article) */
  --line:        #1a1a1a;   /* Sections sombres */
  --rule:        rgba(10,10,10,.12);  /* Filets */

  /* Accent */
  --violet:       #7326BB;  /* Accent primaire */
  --violet-deep:  #5a1a99;  /* Hover état foncé */
  --violet-light: #a672e0;  /* Sur fond sombre */

  /* Catégoriels (constellation chronométrée — usage rare) */
  --cat-p: #ff6fa3;  /* Personnes */
  --cat-k: #7be88e;  /* Connaissance */
  --cat-v: #5fb8ff;  /* Valeur */
  --cat-n: #c084fc;  /* Numérique */
  --cat-w: #fbbf24;  /* Workflow */
}
```

**Règles d'usage** :
- Background par défaut = `--bone` (jamais blanc pur)
- Background sections sombres = `--ink` (#0a0a0a, jamais noir pur)
- Accent unique = `--violet` (#7326BB) — utiliser avec parcimonie : H2 spans, CTAs primaires, kickers
- Sur fond sombre, accent = `--violet-light` pour suffisamment de contraste

**Sélection texte** : `::selection { background: var(--violet); color: var(--bone); }`

### 2.2 Typographie

**Fonts utilisées** (loadées depuis Google Fonts) :

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&family=Instrument+Serif&display=swap">
```

| Rôle | Family | Weights | Usage |
|------|--------|---------|-------|
| Display + body | **Bricolage Grotesque** | 400, 500, 600, 700, 800 | Tout sauf cas particuliers |
| Mono / metadata | **JetBrains Mono** | 400, 500 | Kickers, eyebrows, dates, breadcrumbs, code |
| Italique éditorial | **Instrument Serif** | 400 (italic) | Timer h2 + emphasis rares |

**Échelle typographique** (clamp-based pour responsive) :

| Token | Valeur | Usage |
|-------|--------|-------|
| `h1-hero` | `clamp(72px, 14vw, 200px)` | H1 du hero principal |
| `h1-article` | `clamp(38px, 5.4vw, 68px)` | H1 d'article |
| `h2-section` | `clamp(40px, 6vw, 84px)` | H2 grands titres section |
| `h2-mid` | `30px` | H2 dans article body |
| `h3-card` | `24px` ou `32px` | Titres cartes |
| `body-lede` | `clamp(18px, 2vw, 22px)` | Sous-titres / chapeaux |
| `body-large` | `19px` / `21px` | Premier para article + lede |
| `body` | `16px` / `17px` / `18px` | Corps de texte |
| `meta` | `11px` | JetBrains Mono kickers |
| `small` | `13.5px` à `14.5px` | Liens nav, CTAs |

**Letter-spacing** :
- H1/H2 grands : `-.04em` à `-.05em` (resserré)
- Body : `-.005em` à `-.01em`
- Meta (uppercase) : `+.16em` à `+.24em` (espacé)

**Line-height** :
- Display (H1/H2 grands) : `.86` à `1.02`
- Titres mid : `1.15` à `1.2`
- Body : `1.5` à `1.75`
- Article body : `1.75` (lecture longue)
- Meta : `1`

### 2.3 Espacement

Système non strict, mais conventions :

| Token | Valeur | Usage |
|-------|--------|-------|
| `gap-xs` | `8px` | Inline gap |
| `gap-sm` | `12px` à `14px` | Bouton interne |
| `gap-md` | `24px` | Card body |
| `gap-lg` | `32px` à `40px` | Sections layout |
| `gap-xl` | `48px` à `80px` | Section-head margin-bottom |
| `pad-section` | `120-140px vertical / 32px horizontal` | Padding section principale |
| `max-w-container` | `1320px` | Max-width des `*-inner` |
| `max-w-prose` | `560-760px` | Texte de lecture |

### 2.4 Border radius

| Token | Valeur | Usage |
|-------|--------|-------|
| `radius-sm` | `8px` | Petites étiquettes |
| `radius-md` | `14px` | Cartes article |
| `radius-lg` | `24px` | Cartes interv |
| `radius-pill` | `100px` | Boutons + tags |
| `radius-full` | `50%` | Avatars, dots |

### 2.5 Shadows

Le design n'utilise quasi pas d'ombres — privilégier les **filets** (1px solid `--rule`) et les **fonds différenciés**. Si shadow nécessaire :

```css
box-shadow: 0 2px 8px rgba(10,10,10,.06);  /* léger */
box-shadow: 0 8px 32px rgba(10,10,10,.12); /* hover card */
```

### 2.6 Z-index layers

| Niveau | Valeur | Usage |
|--------|--------|-------|
| Base | `1` | |
| Sticky nav | `50` | |
| Overlays | `80` | Dropdowns |
| Prologue cinematic | `9999` | |
| Modal | `99999` | |

---

## 3. Hiérarchie typographique

### H1 (hero)
```html
<h1>Architecture, mémoire, <span class="v">continuité.</span></h1>
```
```css
font: 700 clamp(72px,14vw,200px)/.86 'Bricolage Grotesque';
letter-spacing: -.045em;
color: var(--ink);
.v { color: var(--violet); }
```

### H2 (section)
```html
<h2 class="section-h">Quatre <span class="v">portes d'entrée.</span></h2>
```
```css
font: 600 clamp(40px,6vw,84px)/.92 'Bricolage Grotesque';
letter-spacing: -.04em;
max-width: 880px;
```

### Kicker / Eyebrow
```html
<div class="section-kicker">— Interventions</div>
```
```css
font: 500 11px 'JetBrains Mono', monospace;
letter-spacing: .16em;
text-transform: uppercase;
color: var(--violet);
margin-bottom: 16px;
```

### Lede / Sous-titre
```html
<p class="hero-deck">Nous concevons des systèmes pour les organisations qui <strong>refusent la dispersion</strong>.</p>
```
```css
font: 400 clamp(18px,2vw,22px)/1.45 'Bricolage Grotesque';
color: var(--ink-soft);
strong { color: var(--ink); font-weight: 600; }
```

---

## 4. Composants

### 4.1 Boutons

```css
.btn{
  font-family:'Bricolage Grotesque',sans-serif;font-size:14px;font-weight:600;
  padding:16px 28px;text-decoration:none;border-radius:100px;
  transition:all .18s;display:inline-flex;align-items:center;gap:8px;
  border:1px solid transparent;
}
.btn-primary    { background:var(--ink);    color:var(--bone); }
.btn-primary:hover { background:var(--violet); }
.btn-violet     { background:var(--violet); color:var(--bone); }
.btn-violet:hover  { background:var(--ink); }
.btn-ghost      { background:transparent;   color:var(--ink);  border-color:var(--ink);  }
.btn-ghost:hover   { background:var(--ink); color:var(--bone); }
.btn-ghost-light{ background:transparent;   color:var(--bone); border-color:var(--bone); }
```

**Pattern arrow** : ajouter `<span class="cta-arrow">→</span>` dans le bouton. Anime sur hover via :
```css
.cta-arrow{ display:inline-block; transition:transform .4s cubic-bezier(.16,1,.3,1); }
.btn:hover .cta-arrow{ transform:translateX(4px); }
```

### 4.2 Nav

```html
<nav class="nav">
  <div class="nav-inner">
    <a href="#" class="brand">
      <span class="brand-letter-wrap">
        <svg class="brand-letter" viewBox="8.5 5 83.5 90" xmlns="http://www.w3.org/2000/svg">
          <polygon points="36.5,5 46.5,5 18.5,95 8.5,95" fill="currentColor"/>
          <polygon points="53,5 64,5 92,95 81,95" fill="#7326BB"/>
        </svg>
      </span>lexandrie Systems
    </a>
    <div class="nav-links">
      <a href="#interventions">Interventions</a>
      <a href="#methode">Méthode</a>
      <a href="#case">Travail</a>
      <a href="/blog/">Journal</a>
    </div>
    <a href="#contact" class="nav-cta">Prendre rendez-vous</a>
  </div>
</nav>
```

**Comportement scroll-aware** : ajouter classe `.is-scrolled` après ~24px de scroll → bg `rgba(244,240,232,.88)` + `backdrop-filter:blur(16px)` + padding réduit.

**Alignement mark** (critique) :
- `.brand { display:flex; align-items:baseline; gap:10px }`
- `.brand-letter-wrap { display:inline-block; width:.48em; height:.72em; position:relative; vertical-align:baseline }`
- `.brand-letter { position:absolute; bottom:-.02em; left:0; height:1em; width:auto }`

### 4.3 Cartes — variantes

**Card "intervention"** (4 cartes en grid)
- bg `--bone-deep`, padding `36px 28px 28px`, `border-radius:24px`
- Variant `.featured` : bg violet, texte bone

**Card "audience"** (3 cartes secteur)
- Layout grid 3 colonnes responsive
- Titre `.audience-card-title`

**Card "article" (journal)**
- Layout list-style, séparateurs `border-top: 1px solid var(--rule)`
- Padding vertical `36px 0 32px`
- Hover : `transform: translateY(-4px)` (desktop only)
- Variant `.jc-coming` : opacity .58, link non-clickable

**Card "FAQ"**
- Q/A pliable optionnel ou ouvert par défaut
- Titre 18-22px, body 15-17px

### 4.4 Tags & badges

**Tag éditorial** (article meta) :
```html
<span class="jc-tag">Conseil</span>
```
```css
font: 500 10.5px 'JetBrains Mono',monospace;
letter-spacing: .16em;
text-transform: uppercase;
color: var(--violet);
```

**Status dot** (live indicators) :
```html
<span class="dot"></span>Q3 2026 · Conversations ouvertes
```
```css
.dot{
  display:inline-block;width:7px;height:7px;border-radius:50%;
  background:var(--violet);margin-right:8px;
}
```

### 4.5 Section structure standard

```html
<section class="[name]" id="[id]" data-motion="section">
  <div class="[name]-inner">
    <div class="section-head">
      <div>
        <div class="section-kicker" data-motion="float-y" data-distance="35">— [Nom section]</div>
        <h2 class="section-h" data-motion="text">[Titre court] <span class="v">[partie violette].</span></h2>
      </div>
      <!-- Optional right-aligned action link -->
    </div>
    <!-- Content -->
  </div>
</section>
```

### 4.6 Footer minimal

```html
<footer class="footer">
  <div class="footer-inner">
    <div>© MMXXVI · Alexandrie Systems</div>
    <a href="https://miragebleu.ch" target="_blank" rel="noopener">
      <span style="opacity:.6;margin-right:10px">Marque de</span>
      <img src="/assets/img/logo.svg" alt="Mirage Bleu" style="height:18px">
    </a>
  </div>
</footer>
```

---

## 5. Layout patterns

### 5.1 Container

Toujours dans un `<div class="*-inner">` avec `max-width:1320px; margin:0 auto; padding-x:32px`. Mobile : padding `24px`.

### 5.2 Grid responsive type

```css
/* Pattern grid 3 colonnes auto-fit */
.[name]-grid{
  display:grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}
@media (max-width:900px){
  .[name]-grid{ grid-template-columns: 1fr; gap: 0; }
}
```

### 5.3 Section-head pattern

`display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:24px; margin-bottom:56-80px`

---

## 6. Motion system

### 6.1 Tokens easing

```css
--ease-snap:  cubic-bezier(.16, 1, .3, 1);    /* expo.out doux — défaut tout */
--ease-pop:   cubic-bezier(.2, .9, .3, 1.3);  /* léger overshoot — micro-interactions */
--ease-scroll: cubic-bezier(.6, 0, .4, 1);    /* indicateur scroll */
```

GSAP equivalent : `expo.out` (durée 0.55-0.95s).

### 6.2 Durées

| Token | Valeur | Usage |
|-------|--------|-------|
| `dur-instant` | `120ms` | Hover état couleur |
| `dur-quick` | `180-220ms` | Hover boutons/cards |
| `dur-base` | `350-450ms` | Reveals |
| `dur-slow` | `550-750ms` | Hero text reveal |
| `dur-cinematic` | `950ms+` | Prologue cinematic |

### 6.3 API data-motion (auto-wire)

Le site utilise un système d'auto-wire via attributs HTML. Inclure dans tout nouveau composant.

```html
<h2 data-motion="text">Titre révélé ligne-par-ligne au scroll</h2>
<section data-motion="section">
  <div data-reveal>...</div>     <!-- stagger fade-up -->
  <div data-motion="float-y" data-distance="35">...</div>
  <a data-motion="magnetic" data-strength="0.25">CTA cursor-follow</a>
</section>
<div data-motion="parallax" data-distance="60">...</div>
<section data-motion="pin-reveal">...</section>
```

**Respecter** `prefers-reduced-motion` : timeline gelée, ScrollTriggers désactivés.

### 6.4 GSAP — pattern d'init

```js
<script defer src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/ScrollTrigger.min.js"></script>
<script>
function motionInit(){
  if (typeof gsap === 'undefined' || typeof ScrollTrigger === 'undefined') return;
  gsap.registerPlugin(ScrollTrigger);
  gsap.defaults({ ease: 'expo.out', duration: 0.95 });
  if (matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  // ... auto-wire handlers
}
if (document.readyState === 'loading') {
  document.addEventListener('DOMContentLoaded', motionInit);
} else {
  motionInit();
}
</script>
```

### 6.5 SVG animation — pitfall

Pour `scaleY` sur un `<polygon>` SVG : ne **PAS** utiliser CSS `transform-origin: 50% 95px` (pixel-based), GSAP bake une translation parasite. Utiliser `svgOrigin: 'x y'` (coords viewBox) à la place :

```js
// ❌ BUG : génère translateY(-95) parasite
.prologue-mark { transform-origin: 50% 95px; transform: scaleY(0); }

// ✅ OK : svgOrigin GSAP-native
gsap.set(markL, { scaleY: 0, svgOrigin: '27.5 95' });
gsap.to(markL,  { scaleY: 1, duration: .55 });
```

---

## 7. Iconographie & marque

### 7.1 Mark (logo)

Le mark "/\" est un A stylisé en deux polygones :

```svg
<svg viewBox="8.5 5 83.5 90" xmlns="http://www.w3.org/2000/svg">
  <polygon points="36.5,5 46.5,5 18.5,95 8.5,95" fill="#0a0a0a"/>
  <polygon points="53,5 64,5 92,95 81,95" fill="#7326BB"/>
</svg>
```

Aspect ratio : `83.5 / 90 = 0.928` (presque carré, légèrement portrait).

### 7.2 Logo canonical (mark + wordmark)

ViewBox `0 0 920 100`, mark + texte `<text x="105" y="83" font-size="95" font-family="'Bricolage Grotesque',sans-serif" font-weight="700" letter-spacing="-2.85">lexandrie Systems</text>`. La lettre A du mark complète le mot.

Fichier source : `/assets/img/alexandrie-systems-logo.svg`

### 7.3 Pas d'icônes décoratives

Le système n'utilise quasi pas d'icônes (pas de feather/lucide). Privilégier :
- Texte typé avec accent violet
- SVG inline pour les éléments graphiques de marque
- Caractères Unicode pour flèches (`→`, `↗`, `›`)

---

## 8. Accessibilité (baseline)

### 8.1 Règles obligatoires

- `prefers-reduced-motion: reduce` → désactiver animations, forcer états finaux visibles
- Focus visible : `:focus-visible { outline: 2px solid var(--violet); outline-offset: 3px; }`
- Texte minimum 14px, body 16-18px
- Contraste WCAG AA mini : `--ink` sur `--bone` = 18.5:1 ✓, `--violet` sur `--bone` = 7.1:1 ✓
- Alt sur toutes les images
- `aria-label` sur boutons icon-only

### 8.2 Pattern reduced-motion

```css
@media (prefers-reduced-motion: reduce){
  *, *::before, *::after{
    animation-duration: .01ms !important;
    transition-duration: .01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

Dans GSAP : `if (matchMedia('(prefers-reduced-motion: reduce)').matches) { killAnimations(); return; }`

---

## 9. SEO / Metadata baseline

### 9.1 `<head>` standard

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>[Titre page] — Alexandrie Systems</title>
<meta name="description" content="[~155 char description, sans keyword stuffing]">
<meta name="author" content="Alexandrie Systems">
<meta name="theme-color" content="#f4f0e8">
<meta name="color-scheme" content="light dark">

<meta name="robots" content="index,follow,max-snippet:-1,max-image-preview:large">
<meta name="geo.region" content="CH-NE">
<meta name="geo.placename" content="Neuchâtel, Suisse">
<meta name="language" content="fr-CH">
<meta http-equiv="content-language" content="fr-CH">

<link rel="canonical" href="https://alexandrie.systems/[path]">
<link rel="alternate" hreflang="fr" href="...">
<link rel="alternate" hreflang="fr-CH" href="...">
<link rel="alternate" hreflang="x-default" href="...">

<!-- Open Graph -->
<meta property="og:type" content="website|article">
<meta property="og:locale" content="fr_CH">
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:url" content="https://alexandrie.systems/...">
<meta property="og:image" content="https://alexandrie.systems/assets/img/alexandrie-systems-og.png">
```

### 9.2 robots.txt opt-ins IA

```
User-agent: GPTBot
Allow: /
User-agent: ClaudeBot
Allow: /
User-agent: anthropic-ai
Allow: /
User-agent: PerplexityBot
Allow: /
User-agent: Google-Extended
Allow: /
User-agent: CCBot
Allow: /
```

### 9.3 JSON-LD obligatoire

Sur chaque page : `@graph` avec au minimum `Organization`, `WebPage`, et `BreadcrumbList`. Sur articles : ajouter `Article` avec `headline`, `author`, `datePublished`, `image`, `publisher`. Schema validé via Rich Results Test.

---

## 10. Patterns rédactionnels

### 10.1 Structure d'article (blog)

```
H1 (~12-18 mots, factuel, sans clickbait)
Lede (200-250 mots) : pose le contexte sans pirouette commerciale
H2 (par chapitre, 3-7 sections)
  150-180 mots par section, prose dense
Conclusion (150-200 mots) : pas de "et vous, qu'en pensez-vous?"
                            → ton "si après ça vous trouvez X, c'est X."
CTA discret vers /#interventions ou /#contact
```

### 10.2 Titres-promesses (à éviter / à utiliser)

❌ « 7 secrets pour exploser votre productivité ! »
❌ « Le guide ULTIME du backoffice »
❌ « Vous ne devinerez jamais... »

✅ « Backoffice sur mesure vs SaaS : 7 critères pour choisir »
✅ « Quitter un ERP propriétaire en 90 jours »
✅ « Audit système PME : à quoi s'attendre »

### 10.3 Formules approuvées

- *« Tout dirigeant finit par se poser la même question. »*
- *« La réponse honnête, c'est que… »*
- *« Ce n'est pas une hypothèse théorique. »*
- *« C'est précisément ce qui fait que… »*
- *« Une propriété structurelle, pas une option commerciale. »*

---

## 11. Stack technique

### 11.1 Hébergement & déploiement

- **Hébergement** : GitHub Pages (gratuit, statique, CDN inclus)
- **Domaine** : `alexandrie.systems` (CNAME via GitHub Pages, HTTPS Let's Encrypt auto)
- **Repo** : `MirageBleuProd/Alexandrie_Systems` (branch `main` = production)
- **Build** : zero — HTML statique avec inline CSS/JS

### 11.2 Dépendances externes

| Lib | Version | Usage | CDN |
|-----|---------|-------|-----|
| GSAP | 3.12.5 | Motion + ScrollTrigger | `cdn.jsdelivr.net/npm/gsap@3.12.5` |
| Bricolage Grotesque | latest | Display font | Google Fonts |
| JetBrains Mono | latest | Mono font | Google Fonts |
| Instrument Serif | latest | Italique rare | Google Fonts |

### 11.3 Performance defaults

- GSAP en `defer` (non-bloquant)
- IIFE motion-system wrappée dans `DOMContentLoaded`
- Google Fonts en `preconnect` + `display=swap`
- Pas de framework JS (vanilla)
- CSS inline pour FCP (HTML file ~130KB single-page)

---

## 12. Checklist nouveau composant

Quand tu crées un nouveau composant ou une nouvelle page, vérifier :

- [ ] Utilise `--bone` / `--ink` / `--violet` (pas de couleurs hardcodées)
- [ ] Family Bricolage Grotesque ou JetBrains Mono (pas d'autre font)
- [ ] Border-radius `100px` (pill) ou `14-24px` (cards)
- [ ] Letter-spacing négatif sur les titres, positif sur les meta uppercase
- [ ] `data-motion` attribute si l'élément doit s'animer (auto-wired)
- [ ] `prefers-reduced-motion` respecté (motion-safe par défaut)
- [ ] Focus visible (outline violet)
- [ ] Contraste AA minimum
- [ ] Alt sur images
- [ ] Texte en français-CH (pas d'anglicismes, pas de superlatifs)
- [ ] Hover state défini (scale, color, ou translate)
- [ ] Responsive testé < 540px (mobile), 540-900px (tablet), > 900px (desktop)

---

## 13. Anti-patterns interdits

Ne **JAMAIS** :
- Utiliser blanc pur (`#fff`) — toujours `--bone`
- Utiliser noir pur (`#000`) — toujours `--ink` (`#0a0a0a`)
- Ajouter des emojis dans le contenu du site (sauf si JV demande explicitement)
- Mettre de la "social proof" inventée (faux logos, faux testimonials)
- Multiplier les CTAs sur une même page (1 primaire + max 1 secondaire)
- Utiliser des icônes décoratives (feather, lucide) — privilégier le typo
- Mettre des animations infinies (loop sans fin) à l'exception du `eyebrowDotPulse`
- Inclure des trackers (GA, FB Pixel) — privilégier Plausible/Umami self-hosted
- Mettre des shadow heavy ou des effets glassmorphism criards
- Faire des H2/H3 sans `letter-spacing` négatif

---

## 14. Référence visuelle

Pour vérifier rendu :
- Production : https://alexandrie.systems
- Logo source : `/assets/img/alexandrie-systems-logo.svg`
- OG image : `/assets/img/alexandrie-systems-og.png` (1200×630)
- Sitemap : `/sitemap.xml`
- robots.txt : `/robots.txt`

---

**Dernière révision** : 2026-05-14
**Mainteneur** : Jules-Emile Vanhalle (JVHLS) — Alexandrie Systems / Mirage Bleu
