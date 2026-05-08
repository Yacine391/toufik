# Road Map — Moove & Dream VTC (Toufik)

## État actuel du projet
- **Date** : 2026-05-08
- **Phase** : Design final noir-doré livré avec van 3D Three.js
- **Stack** : HTML5 + CSS3 vanilla + Three.js (CDN ES module)
- **Repo** : `git@github.com:Yacine391/toufik.git`

## Client
- **Nom** : Toufik (Moove & Dream Private Driver)
- **Tel** : 0769385715
- **Email** : adouditoufik@gmail.com
- **Slogan** : "Votre Confort, Notre priorité"
- **Services** : Paris / Transferts aéroports / Mise à Dispo
- **Véhicule** : Mercedes van 7 places

## Structure des fichiers
| Fichier | Rôle |
|---------|------|
| `index.html` | iframe → `noir-dore.html` (design final retenu par client) |
| `vert-dore.html` | Design 1 — Vert forêt + Or antique (Héritage VTC style) |
| `mineral.html` | Design 2 — Taupe, Moka, Blanc pur, Gris perle (Aurora VTC style) |
| `bordeaux.html` | Design 3 — Fond noir + accents bordeaux (Playfair + Raleway) |
| `rouge-velvet.html` | Design 4 — Fond rouge bordeaux profond + ivoire + or (Cormorant Garamond + Outfit) |
| `noir-dore.html` | Design 5 — Fond noir pur + écriture dorée et blanche (Cinzel + Josefin Sans) |

## Tâches terminées
- [x] Design 1 : Vert Doré (`vert-dore.html`) — hero, services, flotte SVG, réservation, contact
- [x] Design 2 : Minéral (`mineral.html`) — style épuré lumineux, Cormorant Garamond + Inter
- [x] Design 3 : Luxe Intemporel (`bordeaux.html`) — style baroque opulent, shimmer animations
- [x] Design 4 : Rouge Velvet (`rouge-velvet.html`) — fond bordeaux wine, ivoire, orb stats, Cormorant
- [x] Design 5 : Noir Doré (`noir-dore.html`) — fond noir pur, or #D4AF37, Cinzel romain, frame géométrique
- [x] `index.html` = iframe noir-doré (design final retenu)
- [x] Tous responsive mobile-first
- [x] Formulaires réservation → `mailto:adouditoufik@gmail.com`
- [x] Section flotte : van 3D WebGL (Three.js) avec rotation auto
- [x] Couleur or mise à jour : #D4A824 (ambre chaud, 86 occurrences)
- [x] Blueprint callout diagram (6 specs autour du van)
- [x] Push GitHub — `Yacine391/toufik` branch `main`

## Tâches en cours
- [ ] Déployer sur Vercel (connecter le repo GitHub)

## Prochaines étapes
1. Déployer sur Vercel (import GitHub repo → deploy automatique)
2. Envoyer le lien Vercel au client pour qu'il choisisse son design
3. Récupérer les vraies photos (chauffeur, véhicule, ambiance)
4. Remplacer les gradients/SVG par les vraies photos dans le design retenu
5. Optionnel : formulaire branché sur Formspree ou Netlify Forms

## Consignes permanentes
- Toucher le minimum de code
- Causes racines uniquement, pas de fixes temporaires
- Vérifier avant de supposer
- Sécurité toujours
