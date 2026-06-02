# CLAUDE.md — EA|IA (Site vitrine public github.io)

> Ce fichier est lu automatiquement par Claude Code à chaque session.
> Il décrit l'architecture complète du dépôt pour éviter toute improvisation.
> Format aligné sur le gabarit canonique : `Factory/90_KNOWLEDGE/BUNDLE_PACK__TEAM_TEMPLATE/TEMPLATE__CLAUDE_MD.md`.

---

## 1. IDENTITÉ DU PRODUIT

| Champ | Valeur |
|---|---|
| **Nom** | EA\|IA — Site vitrine public + kit de lancement |
| **Code repo** | `eriqallain-afk/github.io` |
| **Nature** | Site web **statique** (HTML/CSS/JS) — GitHub Pages |
| **Rôle** | Vitrine ombrelle de la **Factory EA\|IA** et de ses **6 armées** |
| **Produit par** | Factory (repo `eriqallain-afk/Factory`) |
| **Responsable** | EA (validation manuelle obligatoire pour toute mise en ligne) |

Ce dépôt est le **site public ombrelle d'EA\|IA** : il présente la Factory (usine à agents) et les 6 armées déployées (IT, DAM, TRAD, IASM, EDU, NEA), avec un **kit de lancement** (textes de campagne, charte, specs φ). Il ne contient **pas d'agents IA** — c'est la couche marketing/présentation publique.

**Positionnement officiel :** *« La prochaine étape de l'IA n'est pas une conversation. C'est une armée. »*

---

## 2. STRUCTURE DU REPO

```
github.io/
├── CLAUDE.md                    ← Ce fichier
├── README.md                    ← Présentation EA|IA, 6 armées, charte, déploiement
├── index.html                   ← Landing publique (GitHub Pages)
├── msp-preview.html             ← Preview MSP Intelligence IT
├── .nojekyll                    ← Désactive Jekyll (HTML brut)
├── CHANGELOG.md                 ← Historique de version (1.0.0-lancement)
├── DEPLOYMENT.md                ← Procédure de déploiement
├── EAIA_LOGO_UNIFICATION.md     ← Règles d'unification du logo
├── LICENSE                      ← Licence propriétaire
├── pages/                       ← 14 pages produit + cases/ (22 casepages)
│   ├── factory.html, armees-eaia.html, dam-design-interieur.html
│   ├── nea-writing.html, edu-services.html, iasm-sante-mentale.html
│   ├── msp-lancement.html, msp-demos.html, campagne-lancement-msp.html
│   └── cases/                   ← 22 casepages partagées
├── kit/                         ← Kit de lancement public
│   ├── KIT_LANCEMENT_MSP_2026.md
│   ├── armees.md, palette.md, specs-phi.md, textes-campagne.md
│   ├── social/                  ← Visuels et textes réseaux sociaux
│   └── MSP_Intelligence_OS_Launch_Pack/
├── assets/
│   ├── {admk,dam,factory,iasm,msp,nea,trad}-bg/   ← Fonds par armée
│   ├── images/, LOGO.png
│   └── eaia-sitewide.js         ← JS commun à tout le site
├── img/                         ← Bannières, OG images, visuels
└── og-image*.png                ← Open Graph (partage social)
```

---

## 3. LES 6 ARMÉES PRÉSENTÉES (pas d'agents ici)

Ce site **présente** les armées — les agents vivent dans leurs repos respectifs. Le tableau remplace la section « Agents » du gabarit.

| Code | Armée | Page vitrine | Repo source des agents |
|---|---|---|---|
| **IT** | MSP Intelligence IT (phare) | `pages/msp-lancement.html` | `eriqallain-afk/IT` |
| **DAM** | ARMY DAM DESIGN | `pages/dam-design-interieur.html` | `eriqallain-afk/ARMY_DAM_DESIGN` |
| **TRAD** | ARMY TRAD INTEL | `pages/armees-eaia.html` | `eriqallain-afk/ARMY_TRAD_INTEL` |
| **IASM** | IASM (santé mentale) | `pages/iasm-sante-mentale.html` | `eriqallain-afk/IASM` |
| **EDU** | EDU SERVICES | `pages/edu-services.html` | `eriqallain-afk/EDU_SERVICES` |
| **NEA** | ARMY NEA WRITING | `pages/nea-writing.html` | `eriqallain-afk/ARMY_NEA_WRITING` |
| — | La Factory elle-même | `pages/factory.html` | `eriqallain-afk/Factory` |

> Chaque armée a son fond visuel dédié dans `assets/{code}-bg/`. Le fond `admk-bg/` correspond à l'armée **Marketing (ADMKT)**.

---

## 4. STRUCTURE D'UNE PAGE

Chaque page de `pages/` est autonome (HTML + charte commune via `assets/eaia-sitewide.js`). Les casepages de `pages/cases/` suivent la même logique d'**anonymisation** que les sites MSP.

---

## 5. RÈGLES ABSOLUES

### Identité visuelle (charte φ — non négociable)
| Élément | HEX | Usage |
|---|---|---|
| Fond | `#000000` | Arrière-plan principal |
| Or EA | `#EDAF45` | Logo EA, accents primaires |
| Or cercle | `#DC961A` | Cercle logo, séparateurs |
| Or foncé | `#CC8E28` | Bordures, labels |
| Or lumineux | `#FFD04F` | Hover, highlights |
| Argent IA | `#D5D5D1` | Logo IA, texte secondaire |

**Composition selon φ = 1.618034** — zone logo 38.2 % / zone visuelle 61.8 %. Référence : `kit/specs-phi.md` et `kit/palette.md`.
**Logo :** respecter `EAIA_LOGO_UNIFICATION.md` (une seule version unifiée).

### Avant toute mise en ligne
1. Anonymisation des casepages (`pages/cases/`) — 0 donnée identifiante
2. Cohérence charte (couleurs, logo, φ)
3. Mettre à jour `CHANGELOG.md`
4. Vérifier le rendu local

### Git
- **Branche de développement : `claude/keen-curie-OIgRs`**
- Jamais de push direct sur `main` sans PR + validation EA

---

## 6. DÉPLOIEMENT — GitHub Pages

Suivre `DEPLOYMENT.md`. Site statique (`.nojekyll` actif).

```
Settings → Pages → Source : main / root
# Domaine custom (optionnel) : créer un fichier CNAME (ex. eaia.ca) — actuellement absent
```

---

## 7. KIT DE LANCEMENT

Le dossier `kit/` est la source des contenus de campagne publics :
- `armees.md` — description des 6 armées
- `palette.md` / `specs-phi.md` — charte couleurs + nombre d'or
- `textes-campagne.md` / `KIT_LANCEMENT_MSP_2026.md` — textes officiels
- `social/` — déclinaisons réseaux sociaux

> Les contenus marketing produits ici peuvent provenir de l'armée **ADMKT** (`eriqallain-afk/PRODUCT__MARKETING_FACTORY_IA`). Garder la cohérence des messages entre les deux.

---

## 8. QUALITÉ ATTENDUE

- Respect strict de la charte φ et du logo unifié
- **0 donnée identifiante** dans les casepages
- Pages directement publiables — pas de placeholder, pas de lien mort
- Contact officiel : `info@ea-ia.ca`

---

*CLAUDE.md v1.0 — EA|IA Site vitrine (github.io) — Mis à jour le 2026-06-01*
*Format dérivé de : Factory/90_KNOWLEDGE/BUNDLE_PACK__TEAM_TEMPLATE/TEMPLATE__CLAUDE_MD.md v1.0 (adapté site statique)*
