# TR-Data-Soph.IA

Ce dépôt contient le matériel des modules "Géométrie des Données et Apprentissage sur Variétés" et "IA Générative" : Lectures et notebooks de TPs.

## Structure du dépôt

- `labs/` : notebooks Jupyter pour les travaux pratiques (ex : `TP5_GNN_message_passing.ipynb`, `TP1_MNIST_structure.ipynb`)
- `lectures/` : lecture_1.pdf, lecture_2.pdf et lecture_3.pdf sont associés au module "Géométrie des Données et Apprentissage sur Variétés"  et lecture_5.pdf est associé au module "IA Générative"

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

## Exécution des notebooks

Ouvrez les notebooks depuis Jupyter (`jupyter lab` / `jupyter notebook`) ou dans VSCode. Les images générées par les notebooks sont sauvegardées localement (voir cellules qui enregistrent PNG dans `labs/`).

## Contact
Youssef MESRI - MINES Paris - PSL
