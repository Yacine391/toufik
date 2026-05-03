# Spec — Animations scroll bidirectionnelles GSAP
**Date:** 2026-05-03 | **Projet:** Moove & Dream VTC (`index.html`)

## Objectif
Rendre le site vivant avec des animations scroll bidirectionnelles : chaque élément **entre** depuis une direction en scrollant vers le bas, **sort** dans le sens inverse en scrollant vers le haut.

## Stack technique
- **GSAP 3** via CDN (`gsap.min.js` + `ScrollTrigger.min.js`)
- Toutes les animations via `ScrollTrigger` avec `toggleActions: "play reverse play reverse"`
- `prefers-reduced-motion` respecté (désactive toutes les animations GSAP)
- Suppression du système `.reveal` / IntersectionObserver existant (remplacé par GSAP)

## Animations par section

### Hero (déjà en CSS on-load — pas touché)
Les animations d'entrée hero restent en CSS pur (on-load, une seule fois).

### Ticker band
- Aucune animation scroll (déjà en loop CSS, correct)

### Services header
- `.services-header-left` : `x: -60` → `x: 0` (from left)
- `.services-ghost-num` : `x: 80` → `x: 0` (from right, parallax inverse)

### 3 cards services
- Card 1 : `x: -80, opacity: 0` → `x: 0, opacity: 1`
- Card 2 : `y: 60, opacity: 0` → `y: 0, opacity: 1` (delay 0.15s)
- Card 3 : `x: 80, opacity: 0` → `x: 0, opacity: 1` (delay 0.3s)
- Trigger individuel sur chaque card

### Section flotte
- `.fleet-text` : `x: -70, opacity: 0` → entrée depuis la gauche
- `.fleet-svg` : `x: 70, opacity: 0` → entrée depuis la droite + clip-path existant conservé
- `.fleet-specs li` : stagger depuis x: -20 (0.1s entre chaque)

### Booking
- `.booking-title` : `y: -50, opacity: 0` → plonge depuis le haut
- `.booking-tagline` : `y: 30, opacity: 0` → montée douce (delay 0.2s)
- `.form-group` éléments : stagger `y: 20, opacity: 0` (0.07s entre chaque)

### Footer
- `.footer-brand-center` : `scaleX: 0.8, opacity: 0` → scale vers 1
- `.footer-grid .footer-col` : stagger `y: 30, opacity: 0`

## Paramètres globaux
- Durée standard : `0.8s`
- Ease : `power3.out` (entrée) / `power3.in` (sortie)
- `toggleActions: "play reverse play reverse"` sur tous les triggers
- `start: "top 85%"`, `end: "top 20%"` (déclenche tôt, sort tôt)

## Suppression code existant
- Retirer les classes `.reveal` et `.reveal.visible` du CSS
- Retirer `IntersectionObserver` du JS existant (sauf counter stats qui reste)
- Retirer `clip-path` sur `.fleet-svg` (géré par GSAP `x`)
- Retirer `fleet-specs li` opacity/transform CSS (géré par GSAP)
