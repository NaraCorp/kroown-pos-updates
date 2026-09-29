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

Le reste de l'application repose sur des composants sous licences permissives — **MIT, ISC, BSD,
Apache-2.0, et la police Inter sous SIL OFL-1.1** — qui n'imposent que la conservation de leur avis
de copyright, laquelle est assurée par leur présence inchangée dans l'installeur : Electron et
Chromium, Node.js, React, MUI, Express, better-sqlite3, `escpos`, `iconv-lite`, `electron-updater`.

Quatre paquets portent une licence isolée, tout aussi permissive : `argparse` (Python-2.0), `sax`
(BlueOak-1.0.0), `tslib` (0BSD) et `tweetnacl` (Unlicense) ; `json-schema` est sous double licence
(AFL-2.1 ou BSD-3-Clause, au choix de qui redistribue). La liste exacte, paquet par paquet, est en
annexe.

**Aucune bibliothèque LGPL n'est distribuée.** Les deux modules natifs qui en auraient apporté
(`usb`, qui embarque libusb, et `serialport`) ne font pas partie du produit.

---

## Comment cette page reste vraie

La version de SumatraPDF ne change que si `pdf-to-printer` change de version — c'est pourquoi elle
est **épinglée** dans le `package.json` du produit, sans accent circonflexe. Une mise à jour mineure
qui embarquerait un autre SumatraPDF rendrait cette page fausse sans que personne ne le remarque.

La liste de l'annexe est **générée**, jamais recopiée à la main : `npm ls --omit=dev --all` dans le
dépôt du produit pour les modules du serveur local (elle coïncide avec l'arbre que l'installeur
embarque), et le relevé que la construction écrit pour l'écran d'administration
(`out/paquet/modules-ecran.json`). Une dépendance ajoutée au produit rend cette annexe fausse : elle
se régénère dans le même geste.

*Dernière vérification : 2026-09-29, sur `pdf-to-printer@5.6.0` ; annexe générée depuis
`kroown-pos` (`package-lock.json` de `master`, commit `6765411`).*

---

## Annexe — la liste exacte des composants

### Modules du serveur local — `npm ls --omit=dev` (155 paquets)

| Paquet | Version | Licence |
|---|---|---|
| `accepts` | 2.0.0 | MIT |
| `ajv` | 6.15.0 | MIT |
| `append-field` | 1.0.0 | MIT |
| `argparse` | 2.0.1 | Python-2.0 |
| `asn1` | 0.2.6 | MIT |
| `assert-plus` | 1.0.0 | MIT |
| `asynckit` | 0.4.0 | MIT |
| `aws-sign2` | 0.7.0 | Apache-2.0 |
| `aws4` | 1.13.2 | MIT |
| `bcrypt-pbkdf` | 1.0.2 | BSD-3-Clause |
| `better-sqlite3` | 13.0.3 | MIT |
| `body-parser` | 2.3.0 | MIT |
| `builder-util-runtime` | 9.7.0 | MIT |
| `busboy` | 1.6.0 | MIT |
| `bytes` | 3.1.2 | MIT |
| `call-bind-apply-helpers` | 1.0.2 | MIT |
| `call-bound` | 1.0.4 | MIT |
| `caseless` | 0.12.0 | Apache-2.0 |
| `combined-stream` | 1.0.8 | MIT |
| `content-disposition` | 1.1.0 | MIT |
| `content-type` | 1.0.5 | MIT |
| `content-type` | 2.1.0 | MIT |
| `cookie` | 0.7.2 | MIT |
| `cookie-signature` | 1.2.2 | MIT |
| `core-util-is` | 1.0.2 | MIT |
| `cwise-compiler` | 1.1.3 | MIT |
| `dashdash` | 1.14.1 | MIT |
| `data-uri-to-buffer` | 0.0.3 | MIT |
| `debug` | 4.4.3 | MIT |
| `delayed-stream` | 1.0.0 | MIT |
| `depd` | 2.0.0 | MIT |
| `dunder-proto` | 1.0.1 | MIT |
| `ecc-jsbn` | 0.1.2 | MIT |
| `ee-first` | 1.1.1 | MIT |
| `electron-log` | 5.4.4 | MIT |
| `electron-updater` | 6.8.9 | MIT |
| `encodeurl` | 2.0.0 | MIT |
| `es-define-property` | 1.0.1 | MIT |
| `es-errors` | 1.3.0 | MIT |
| `es-object-atoms` | 1.1.2 | MIT |
| `escape-html` | 1.0.3 | MIT |
| `escpos` | 3.0.0-alpha.6 | MIT |
| `etag` | 1.8.1 | MIT |
| `express` | 5.2.1 | MIT |
| `extend` | 3.0.2 | MIT |
| `extsprintf` | 1.3.0 | MIT |
| `fast-deep-equal` | 3.1.3 | MIT |
| `fast-json-stable-stringify` | 2.1.0 | MIT |
| `finalhandler` | 2.1.1 | MIT |
| `forever-agent` | 0.6.1 | Apache-2.0 |
| `form-data` | 2.3.3 | MIT |
| `forwarded` | 0.2.0 | MIT |
| `fresh` | 2.0.0 | MIT |
| `fs-extra` | 10.1.0 | MIT |
| `function-bind` | 1.1.2 | MIT |
| `get-intrinsic` | 1.3.0 | MIT |
| `get-pixels` | 3.3.3 | MIT |
| `get-proto` | 1.0.1 | MIT |
| `getpass` | 0.1.7 | MIT |
| `gopd` | 1.2.0 | MIT |
| `graceful-fs` | 4.2.11 | ISC |
| `har-schema` | 2.0.0 | ISC |
| `har-validator` | 5.1.5 | MIT |
| `has-symbols` | 1.1.0 | MIT |
| `hasown` | 2.0.4 | MIT |
| `http-errors` | 2.0.1 | MIT |
| `http-signature` | 1.2.0 | MIT |
| `iconv-lite` | 0.6.3 | MIT |
| `iconv-lite` | 0.7.3 | MIT |
| `inherits` | 2.0.4 | ISC |
| `iota-array` | 1.0.0 | MIT |
| `ipaddr.js` | 1.9.1 | MIT |
| `is-buffer` | 1.1.6 | MIT |
| `is-promise` | 4.0.0 | MIT |
| `is-typedarray` | 1.0.0 | MIT |
| `isstream` | 0.1.2 | MIT |
| `jpeg-js` | 0.4.4 | BSD-3-Clause |
| `js-yaml` | 4.3.2 | MIT |
| `jsbn` | 0.1.1 | MIT |
| `json-schema` | 0.4.0 | (AFL-2.1 OR BSD-3-Clause) |
| `json-schema-traverse` | 0.4.1 | MIT |
| `json-stringify-safe` | 5.0.1 | ISC |
| `jsonfile` | 6.2.1 | MIT |
| `jsprim` | 1.4.2 | MIT |
| `lazy-val` | 1.0.5 | MIT |
| `lodash.escaperegexp` | 4.1.2 | MIT |
| `lodash.isequal` | 4.5.0 | MIT |
| `math-intrinsics` | 1.1.0 | MIT |
| `media-typer` | 0.3.0 | MIT |
| `media-typer` | 1.1.1 | MIT |
| `merge-descriptors` | 2.0.0 | MIT |
| `mime-db` | 1.52.0 | MIT |
| `mime-db` | 1.54.0 | MIT |
| `mime-types` | 2.1.35 | MIT |
| `mime-types` | 3.0.2 | MIT |
| `ms` | 2.1.3 | MIT |
| `multer` | 2.4.0 | MIT |
| `mutable-buffer` | 2.2.5 | MIT |
| `ndarray` | 1.1.1 | MIT |
| `ndarray-pack` | 1.2.1 | MIT |
| `negotiator` | 1.1.0 | MIT |
| `node-addon-api` | 8.9.2 | MIT |
| `node-bitmap` | 0.0.1 | MIT (déclarée dans son README, sans champ `license`) |
| `oauth-sign` | 0.9.0 | Apache-2.0 |
| `object-inspect` | 1.13.4 | MIT |
| `omggif` | 1.0.10 | MIT |
| `on-finished` | 2.4.1 | MIT |
| `once` | 1.4.0 | ISC |
| `parse-data-uri` | 0.2.0 | ISC |
| `parseurl` | 1.3.3 | MIT |
| `path-to-regexp` | 8.4.2 | MIT |
| `pdf-to-printer` | 5.6.0 | MIT |
| `performance-now` | 2.1.0 | MIT |
| `pngjs` | 3.4.0 | MIT |
| `proxy-addr` | 2.0.7 | MIT |
| `psl` | 1.15.0 | MIT |
| `punycode` | 2.3.1 | MIT |
| `qr-image` | 3.2.0 | MIT |
| `qs` | 6.16.0 | BSD-3-Clause |
| `qs` | 6.5.5 | BSD-3-Clause |
| `range-parser` | 1.3.0 | MIT |
| `raw-body` | 3.0.2 | MIT |
| `request` | 2.88.2 | Apache-2.0 |
| `router` | 2.2.0 | MIT |
| `safe-buffer` | 5.1.2 | MIT |
| `safer-buffer` | 2.1.2 | MIT |
| `sax` | 1.6.1 | BlueOak-1.0.0 |
| `semver` | 7.7.4 | ISC |
| `send` | 1.2.1 | MIT |
| `serve-static` | 2.2.1 | MIT |
| `setprototypeof` | 1.2.0 | ISC |
| `side-channel` | 1.1.1 | MIT |
| `side-channel-list` | 1.0.1 | MIT |
| `side-channel-map` | 1.0.1 | MIT |
| `side-channel-weakmap` | 1.0.2 | MIT |
| `sshpk` | 1.18.0 | MIT |
| `statuses` | 2.0.2 | MIT |
| `streamsearch` | 1.1.0 | MIT |
| `through` | 2.3.8 | MIT |
| `tiny-typed-emitter` | 2.1.0 | MIT |
| `toidentifier` | 1.0.1 | MIT |
| `tough-cookie` | 2.5.0 | BSD-3-Clause |
| `tslib` | 2.8.1 | 0BSD |
| `tunnel-agent` | 0.6.0 | Apache-2.0 |
| `tweetnacl` | 0.14.5 | Unlicense |
| `type-is` | 1.6.18 | MIT |
| `type-is` | 2.1.0 | MIT |
| `uniq` | 1.0.1 | MIT |
| `universalify` | 2.0.1 | MIT |
| `unpipe` | 1.0.0 | MIT |
| `uri-js` | 4.4.1 | BSD-2-Clause |
| `uuid` | 3.4.0 | MIT |
| `vary` | 1.1.2 | MIT |
| `verror` | 1.10.0 | MIT |
| `wrappy` | 1.0.2 | ISC |

### Écran d'administration — les paquets que le bundle contient (29)

| Paquet | Version | Licence |
|---|---|---|
| `@babel/runtime` | 7.29.7 | MIT |
| `@emotion/cache` | 11.14.0 | MIT |
| `@emotion/hash` | 0.9.2 | MIT |
| `@emotion/is-prop-valid` | 1.4.0 | MIT |
| `@emotion/memoize` | 0.9.0 | MIT |
| `@emotion/react` | 11.14.0 | MIT |
| `@emotion/serialize` | 1.3.3 | MIT |
| `@emotion/sheet` | 1.4.0 | MIT |
| `@emotion/styled` | 11.14.1 | MIT |
| `@emotion/unitless` | 0.10.0 | MIT |
| `@emotion/use-insertion-effect-with-fallbacks` | 1.2.0 | MIT |
| `@emotion/utils` | 1.4.2 | MIT |
| `@fontsource/inter` | 5.3.0 | OFL-1.1 |
| `@mui/icons-material` | 7.3.11 | MIT |
| `@mui/material` | 7.3.11 | MIT |
| `@mui/private-theming` | 7.3.11 | MIT |
| `@mui/styled-engine` | 7.3.10 | MIT |
| `@mui/system` | 7.3.11 | MIT |
| `@mui/utils` | 7.3.11 | MIT |
| `@popperjs/core` | 2.11.8 | MIT |
| `clsx` | 2.1.1 | MIT |
| `hoist-non-react-statics` | 3.3.2 | BSD-3-Clause |
| `react` | 19.2.8 | MIT |
| `react-dom` | 19.2.8 | MIT |
| `react-is` | 16.13.1 | MIT |
| `react-is` | 19.2.8 | MIT |
| `react-transition-group` | 4.4.5 | BSD-3-Clause |
| `scheduler` | 0.27.0 | MIT |
| `stylis` | 4.2.0 | MIT |

