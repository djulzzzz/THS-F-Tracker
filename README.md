# THS Track 🌸

Une web app mobile pour suivre son traitement hormonal féminisant (THS), conçue pour fonctionner directement dans Safari sur iPhone — sans installation, sans compte, sans serveur.

> Développée en collaboration avec [Claude](https://claude.ai) (Anthropic).

---

## Fonctionnalités

- **Suivi des prises** — médicament, dose, site d'application, intervalle, notes
- **Compte à rebours** jusqu'à la prochaine prise
- **Bilans sanguins** — E2, testostérone, LH, FSH, prolactine avec indicateurs de cible
- **Mensurations** — poids, poitrine, taille, hanches, ratio hanches/taille automatique
- **Photos d'évolution** — stockées uniquement en local sur le téléphone
- **Graphiques** — E2, T, poids, mensurations, ratio, intervalles entre prises
- **Jalons THS** — de J1 à 3 ans, avec compte à rebours et confettis 🎉
- **RDV médecin** — compte à rebours visible sur l'accueil
- **Rapport médecin** — document HTML imprimable avec tous les historiques
- **Export / Import JSON** — backup complète des données
- **Icône personnalisée** sur l'écran d'accueil iOS

---

## Installation

Aucune. C'est un fichier HTML unique.

1. Télécharge `ths-tracker.html`
2. Ouvre-le dans **Safari** sur iPhone
3. Partager → **Sur l'écran d'accueil**
4. C'est une app.

---

## Données & confidentialité

Toutes les données sont stockées en local via `localStorage` dans Safari. Rien n'est envoyé sur un serveur. Les photos ne quittent jamais le téléphone.

> ⚠️ Si tu vides Safari ou changes de téléphone, utilise l'export JSON dans Réglages pour sauvegarder tes données.

---

## Stack

- HTML / CSS / JavaScript vanilla
- [Chart.js](https://www.chartjs.org/) pour les graphiques
- Google Fonts (Syne + Nunito)
- Zéro dépendance, zéro backend

---

## Genèse

Ce projet a été conçu et itéré en conversation avec **Claude Sonnet** (Anthropic). L'idée de départ était simple — avoir un endroit discret pour suivre un THS féminisant sans passer par une appli du store qui demande un compte, des permissions, ou qui revend des données. Quatre versions plus tard, ça a une vraie gueule.

---

## Licence

[GNU General Public License v3.0](LICENSE) — libre d'utilisation, de modification et de distribution, à condition que tout projet dérivé reste sous la même licence open source.
