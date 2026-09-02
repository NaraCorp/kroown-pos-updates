# Licences des composants tiers — Kroown POS

L'installeur publié ici embarque des composants tiers. Cette page en dresse la liste et porte les
avis exigés par leurs licences.

Elle vit dans ce dépôt, et non dans le dépôt de code, parce que **c'est ici que le binaire est
distribué** — donc ici que l'avis doit être visible pour la personne qui le télécharge.

---

## SumatraPDF 3.4.6 — GPL-3.0

**Ce que c'est.** Un lecteur PDF Windows, utilisé pour envoyer un document PDF à une imprimante
Windows classique (factures, rapports). Il arrive avec la bibliothèque
[`pdf-to-printer`](https://www.npmjs.com/package/pdf-to-printer) 5.6.0, épinglée à cette version
exacte.

**Fichier distribué.** `SumatraPDF-3.4.6-32.exe` (12 644 824 octets).

**Comment il est utilisé.** Kroown POS le lance comme **programme séparé** (`execFile`), avec des
arguments en ligne de commande. Il n'est ni lié, ni chargé dans le processus de Kroown POS.

**Copyright.** Copyright 2006-2022 all authors (GPLv3) — tel que déclaré par le binaire lui-même.

**Amont.**
- Site : <https://www.sumatrapdfreader.org/>
- Source : <https://github.com/sumatrapdfreader/sumatrapdf>
- Texte de la licence : <https://www.gnu.org/licenses/gpl-3.0.html>

### Offre écrite de fourniture du code source

Conformément à la section 6 de la GPL-3.0, nous nous engageons à fournir, à toute personne qui
reçoit cet installeur, une copie du code source correspondant de la version de SumatraPDF qui y est
embarquée, pour un coût n'excédant pas celui de la distribution.

**Pour en faire la demande** : ouvrez une *issue* sur ce dépôt
(<https://github.com/NaraCorp/kroown-pos-updates/issues>) en précisant la version de l'installeur
concernée. Cette offre reste valable tant que la version correspondante est distribuée ici.

---

## Les autres composants

Le reste de l'application repose sur des composants sous licences permissives — MIT, BSD ou
Apache-2.0 — qui n'imposent que la conservation de leur avis de copyright, laquelle est assurée par
leur présence inchangée dans l'installeur : Electron et Chromium, Node.js, React, MUI, Express,
better-sqlite3, `escpos`, `iconv-lite`, `electron-updater`.

**Aucune bibliothèque LGPL n'est distribuée.** Les deux modules natifs qui en auraient apporté
(`usb`, qui embarque libusb, et `serialport`) ne font pas partie du produit.

---

## Comment cette page reste vraie

La version de SumatraPDF ne change que si `pdf-to-printer` change de version — c'est pourquoi elle
est **épinglée** dans le `package.json` du produit, sans accent circonflexe. Une mise à jour mineure
qui embarquerait un autre SumatraPDF rendrait cette page fausse sans que personne ne le remarque.

*Dernière vérification : 2026-09-02, sur `pdf-to-printer@5.6.0`.*
