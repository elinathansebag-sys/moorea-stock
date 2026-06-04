# Inventaire Stock — GMS & Prestige

Plateforme de comptage de stock pour les équipes GMS (19h) et Prestige (nuit).

## Fonctionnement

1. La page d'accueil permet d'**uploader un nouveau fichier Excel** à chaque inventaire
2. Le fichier Excel doit avoir en **colonne A** : `GMS` ou `gms` pour les articles GMS, et **vide** pour Prestige
3. Cliquez sur **GMS** ou **Prestige** pour voir uniquement vos articles
4. Saisissez les comptages, consultez les écarts en temps réel
5. Exportez en CSV à la fin

## Structure du fichier Excel attendu

| Col A | Col B | Col C | Col D | Col E | Col F |
|-------|-------|-------|-------|-------|-------|
| (GMS ou vide) | Famille | Code article | Article | Dépot | Nb colis |

## Déploiement sur GitHub + Vercel

### 1. GitHub
```bash
git init
git add .
git commit -m "Initial commit — Inventaire Stock"
git branch -M main
git remote add origin https://github.com/VOTRE-USERNAME/inventaire-stock.git
git push -u origin main
```

### 2. Vercel
1. Allez sur [vercel.com](https://vercel.com)
2. Cliquez **"Add New Project"**
3. Importez votre repo GitHub `inventaire-stock`
4. **Framework Preset** : Other
5. **Root Directory** : laisser vide
6. Cliquez **Deploy**

Votre site sera accessible à : `https://inventaire-stock.vercel.app`

## Mettre à jour le stock

Pour changer le stock par défaut (affiché sans upload) :
1. Remplacez `public/stock_data.js` avec votre nouveau fichier
2. `git add . && git commit -m "Mise à jour stock" && git push`
3. Vercel redéploie automatiquement

## Fichiers

```
inventaire-stock/
├── public/
│   ├── index.html      ← Application principale
│   ├── stock_data.js   ← Données stock par défaut
│   └── stock_data.json ← Données brutes
├── vercel.json         ← Config Vercel
├── package.json
└── README.md
```
