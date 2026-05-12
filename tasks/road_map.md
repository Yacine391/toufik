# Road Map — Moove & Dream VTC (Toufik)

## État actuel du projet
- **Date** : 2026-05-12
- **Phase** : Site one-page noir argenté livré — 6 sections + animations — pushé sur GitHub
- **Stack** : HTML5 + CSS3 vanilla + model-viewer (Google CDN) + JS vanilla
- **Repo** : `git@github.com:Yacine391/toufik.git`

## Client
- **Nom** : Toufik (Moove & Dream Private Driver)
- **Tel** : 0769385715
- **Email** : adouditoufik@gmail.com
- **Services** : Paris · Nice · Cannes · Saint-Tropez · Monaco · Aéroports · France entière
- **Véhicule** : Mercedes Classe V — 7 places

## Structure des fichiers
| Fichier | Rôle |
|---------|------|
| `index.html` | iframe → `noir-argente.html` (design final actuel) |
| `noir-argente.html` | **Design final** — one-page noir argenté, 6 sections, animations |
| `assets/van.glb` | Modèle 3D Mercedes Classe V (model-viewer) |

> Toutes les anciennes maquettes (vert-dore, mineral, bordeaux, rouge-velvet, noir-dore) supprimées le 2026-05-12.

## Session du 2026-05-12 — Ce qui a été fait

### Refonte complète (noir-argente.html)
- **Thème** : Noir pur `#070707` + accents argent `#c0c0c0` / `#e8e8e8` (remplace l'or)
- **Typographie** : Raleway uniquement (200→800), zéro serif, zéro italic — esprit Mercedes
- **Destinations élargies** : Nice, Cannes, Saint-Tropez, Monaco, Antibes ajoutés en plus de Paris

### Site one-page — 6 sections
| # | Section | Contenu |
|---|---------|---------|
| 1 | **Hero** | "RÉSERVER VOTRE TRAJET." + van 3D auto-rotate + CTA |
| 2 | **Services** | 3 cartes : Transferts aéroports / Paris & IDF / Côte d'Azur & Monaco |
| 3 | **Flotte** | Mercedes Classe V — van 3D pleine largeur + 6 specs (7 places, WiFi, A/C, USB, 24/7, VIP) |
| 4 | **Destinations** | Carte SVG France + points lumineux animés + liste 6 villes |
| 5 | **À propos** | Compteurs : 5+ ans · 500+ clients · 2000+ trajets · 7 places |
| 6 | **Réservation** | Formulaire dark + calendrier JS interactif + passagers +/- |

### Animations implémentées
- **Hero** : stagger word-by-word (opacity + translateY, délais 0.5→1.2s)
- **Scroll reveal** : IntersectionObserver sur tous les blocs (`.rev`, `.rev-l`, `.rev-r`)
- **Stagger cartes** : délais `d1→d6` (0.1s→0.6s) sur services et specs flotte
- **Carte destinations** : points SVG qui s'allument en séquence (+220ms par point)
- **Compteurs** : easing cubic (ease-out³) sur 1800ms au premier scroll
- **Nav dots latérale** : 6 points argentés, dot actif surligné au scroll (IntersectionObserver)
- **Header compact** : réduit de 58px → 48px après 80px de scroll
- **Hover cartes** : `translateY(-3px)` + bordure argent sur `.srv-card`
- **Ticker** : défilement infini destinations (32s loop)

### Navigation
- Header fixe avec liens sections (masqué mobile)
- Nav dots verticale droite (masquée < 900px)
- Smooth scroll natif CSS

### Formulaire
- Soumission → `mailto:adouditoufik@gmail.com` via JS (corps formaté)
- Calendrier JS custom (navigation mois, sélection jour, today highlight)
- Compteur passagers 1→7 avec boutons +/-

## Tâches terminées
- [x] Refonte complète design noir argenté (inspiré Move & Dream référence)
- [x] Suppression des 5 anciennes maquettes
- [x] Site one-page 6 sections scrollables
- [x] Animations premium (stagger, compteurs, carte SVG, reveal)
- [x] Nav dots latérale + header compact
- [x] Destinations Côte d'Azur intégrées partout (header, ticker, services, carte)
- [x] Push GitHub → Vercel déploie automatiquement

## Tâches en cours
- [ ] Connecter le repo sur Vercel si pas encore fait (`vercel.com` → import `Yacine391/toufik`)

## Prochaines étapes
1. **Vérifier le déploiement Vercel** — envoyer le lien live au client
2. **Vraies photos** — remplacer le van 3D par une photo réelle du véhicule (hero + flotte)
3. **Formulaire backend** — brancher Formspree ou Netlify Forms pour recevoir les réservations par email proprement
4. **Contenu client** — vrai texte "À propos", vrais chiffres (années, clients, trajets)
5. **SEO** — meta description, og:image, sitemap
6. **Mobile polish** — tester sur iPhone (Safari) et Android

## Consignes permanentes
- Toucher le minimum de code
- Causes racines uniquement, pas de fixes temporaires
- Vérifier avant de supposer
- Sécurité toujours
