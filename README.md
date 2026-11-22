# TR-Data-Soph.IA

Ce dépôt contient le matériel des modules « Géométrie des Données et Apprentissage sur Variétés » et « IA Générative » : slides des lectures (PDF) et notebooks de TP.

## Structure du dépôt

- `lectures/pdf/` : slides des lectures
- `labs/` : notebooks Jupyter des travaux pratiques (énoncés)

| Lecture | Thème |
|---|---|
| `lecture_1.pdf` | Introduction à la géométrie des données : concentration, variétés, PCA, Isomap, Diffusion Maps, t-SNE, UMAP (démonstrations en annexe) |
| `lecture_2.pdf` | Graphes et diffusion : Laplacien, noyau de chaleur, semi-supervisé, Cheeger, courbure |
| `lecture_3.pdf` | Deep learning sur graphes et variétés : passage de messages, GCN, GAT, WL, sur-lissage, équivariance |
| `lecture_4.pdf` | Topologie des données, variétés riemanniennes, transport optimal |
| `lecture_5.pdf` | IA générative : VAE, GAN, flows, diffusion, flow matching |
| `lecture_6.pdf` | Géométrie des représentations apprises, mini-projets |

## Travaux pratiques

| TP | Lecture | Notebook (`labs/`) |
|---|---|---|
| TP0 | 1 | `TP0_Lecture_1_concentration_structure.ipynb` : concentration des distances |
| TP1 | 1 | `TP1_Lecture_1_MNIST_structure.ipynb` : PCA, Isomap, Diffusion Maps, t-SNE sur MNIST |
| TP2 | 1 | `TP2_Lecture_1_SwissRoll_structure.ipynb` : déroulement d'une variété |
| TP3 | 1 | `TP3_Lecture_1_parametres_structure.ipynb` : paramètres et robustesse |
| TP | 2 | `TP_Lecture_2_Graphes_Diffusion_structure.ipynb` : Laplacien, diffusion, semi-supervisé, segmentation |
| TP | 3 | `TP_Lecture_3_GNN_message_passing.ipynb` : passage de messages, GCN/GAT sur Cora, sur-lissage, WL |
| TP | 5 | `TP_Lecture_5_Generative_Models.ipynb` : VAE, GAN, RealNVP, DDPM |

`labs/graphe_knn_epsilon.ipynb` est une démonstration (graphes k-NN et ε, propagation de labels) qui produit les figures de la lecture 2.

## Installation

```bash
pip install -r requirements.txt
```

Sous Windows, si PyTorch et scikit-learn chargent deux runtimes OpenMP, définir `KMP_DUPLICATE_LIB_OK=TRUE` (voir `requirements.txt`).

## Exécution des notebooks

Ouvrez les notebooks avec Jupyter (`jupyter lab`) ou dans VSCode. Les jeux de données (MNIST, Cora) sont téléchargés automatiquement au premier lancement.

## Contact
Youssef MESRI - MINES Paris - PSL
