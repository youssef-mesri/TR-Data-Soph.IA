# TR-Data-Soph.IA

Ce dépôt contient le matériel du module "Géométrie des Données et Apprentissage sur Variétés" : notes, slides et notebooks de TP.

## Structure du dépôt

- `notes/` : sources LaTeX des notes de cours (peuvent être exclues du dépôt public)
- `labs/` : notebooks Jupyter pour les travaux pratiques (ex : `TP5_GNN_message_passing.ipynb`, `TP1_MNIST_structure.ipynb`)
- `lectures/` : sources LaTeX et slides (fichiers compilés et images)
- `.vscode/` : configuration VSCode
- `.conda/` : environnement Conda local (ne pas versionner)

Note : certains dossiers (par ex. `lectures/tex/`, `labs/sol/`, `notes/`) sont listés dans `.gitignore` pour éviter de publier des corrigés ou fichiers volumineux.

## Exemples de notebooks

- `labs/graphe_knn_epsilon.ipynb` : génération et visualisation de graphes k-NN et epsilon, propagation de labels, sauvegarde d'images.
- `labs/TP1_MNIST_corrige.ipynb` : exemples de réduction de dimension (PCA, Isomap, Diffusion Maps, t-SNE) sur MNIST.

## Environnement Python (Conda)

Un environnement Conda local a été configuré pour le projet (chemin projet : `.conda`). Pour l'activer sous PowerShell :

```powershell
conda activate "c:\local\ymesri\TR-Data Soph.IA\TR-Data-Soph.IA\.conda"
```

Si l'environnement n'existe pas sur votre machine, vous pouvez le créer avec (optionnel) :

```powershell
conda create -p "c:\local\ymesri\TR-Data Soph.IA\TR-Data-Soph.IA\.conda" python=3.11
conda activate "c:\local\ymesri\TR-Data Soph.IA\TR-Data-Soph.IA\.conda"
```

Installer les dépendances utiles pour les notebooks :

```powershell
conda install numpy matplotlib scikit-learn networkx -y
# ou pip install -r requirements.txt si vous préférez pip
```

## Compiler les slides / notes

Une distribution LaTeX est nécessaire (MiKTeX ou TeX Live). Exemple de commande pour compiler les slides depuis `lectures/` :

```powershell
cd lectures
pdflatex main.tex
```

Remarque : Si `pdflatex` n'est pas installé, installez MiKTeX (https://miktex.org) ou TeX Live.

## Exécution des notebooks

Ouvrez les notebooks depuis Jupyter (`jupyter lab` / `jupyter notebook`) ou dans VSCode. Les images générées par les notebooks sont sauvegardées localement (voir cellules qui enregistrent PNG dans `labs/`).

## Git / Publication

Si vous modifiez le README et souhaitez pousser les changements vers GitHub (si Git est configuré) :

```powershell
git add README.md
git commit -m "Mise à jour du README pour refléter le contenu du dépôt"
git push origin master
```

## Contact
Youssef MESRI - MINES Paris - PSL
