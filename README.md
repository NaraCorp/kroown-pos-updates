# Kroown POS — feed de releases

Artefacts de mise à jour automatique (electron-updater) pour **Kroown POS**, le serveur matériel
local du SaaS Kroown : impression ESC/POS, tiroir-caisse, TPE Worldline, balances Bizerba.

Code source privé : `NaraCorp/kroown-pos`.

---

## À quoi sert ce dépôt

Un poste installé chez un client vérifie ici s'il existe une version plus récente que la sienne, et
la télécharge. Ce dépôt est **public** pour cette seule raison : `electron-updater` doit pouvoir lire
le flux sans jeton, depuis le PC du magasin.

Il ne contient **aucun code source** — seulement les installeurs publiés et leur manifeste.

| Canal | Fichier | Publié par |
|---|---|---|
| stable | `latest.yml` | un tag `vX.Y.Z` |
| test | `beta.yml` | un tag `vX.Y.Z-beta.N` |

## Licences des composants tiers

L'installeur embarque **SumatraPDF 3.4.6, sous GPL-3.0**, invoqué comme programme séparé pour
l'impression PDF. L'avis, les liens amont et **l'offre écrite de fourniture du source** sont dans
[`LICENCES-TIERS.md`](LICENCES-TIERS.md).

## Publier une version

Depuis le dépôt de code, jamais ici :

```bash
npm version patch --no-git-tag-version   # ou minor / major
git commit -am "chore(release): vX.Y.Z"
git tag vX.Y.Z
git push --follow-tags
```

Le workflow `release.yml` du dépôt de code prend la suite : il rejoue les tests, refuse le tag s'il
ne correspond pas à la version du `package.json`, construit l'installeur Windows et dépose les
artefacts ici.
