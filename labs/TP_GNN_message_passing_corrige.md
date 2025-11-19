# Corrigé — TP GNN : Message Passing, GCN et GAT

## Question 1 — Quelle différence observez-vous entre les résultats du GCN et du GAT ?

- Le GCN applique une agrégation normalisée fixe (par multiplication par D^{-1/2} A D^{-1/2}) : tous les voisins contribuent selon une normalisation déterministe. Le résultat est une moyenne (linéaire) pondérée par la structure du graphe mais non adaptée à la tâche.
- Le GAT apprend des coefficients d'attention \(\alpha_{ij}\) pour chaque arête : il peut favoriser certains voisins et atténuer d'autres lors de l'agrégation. En pratique, cela produit des représentations où l'information venant des voisins « pertinents » pèse plus.
- Numériquement, les sorties peuvent être proches ou différentes selon la tâche et le graphe : sur des graphes où tous les voisins sont informatifs, les différences seront faibles ; si certains voisins sont bruyants/irrélevants, le GAT peut donner de meilleurs résultats.

## Question 2 — Dans quels cas l'attention (GAT) apporte-t-elle un avantage ?

- Graphes hétérogènes ou bruyants : quand la qualité des voisins varie (ex. réseaux sociaux avec amis peu pertinents), l'attention permet de filtrer.
- Relations multi-typiques : si certaines arêtes sont plus informatives que d'autres, l'attention apprend à pondérer.
- Tâches nécessitant une sélection fine d'information locale (ex. classification de nœuds avec signaux locaux faibles).

Coûts et limites : l'attention augmente la complexité (plus de paramètres, calcul des coefficients), et peut sur-ajuster sur petits jeux si on ne régularise pas.

## Question 3 — Comment adapteriez-vous ces modèles à des graphes plus grands ou hétérogènes ?

- Échantillonnage / mini-batching : utiliser GraphSAGE (neighbor sampling), PyG `NeighborSampler` ou méthodes comme `GraphSAINT` pour former sur des sous-graphes.
- Traitement sparse et opérations en mémoire limitée : profiter des opérateurs sparses optimisés et d'algorithmes mini-batch.
- Hétérogénéité : utiliser des modèles relationnels (RGCN) ou GNNs pour graphes hétérogènes (HeteroConv, relational layers) et encoder types de nœuds/arêtes.
- Scalabilité : distillation, pré-calcul de features, pooling hiérarchique (DiffPool), ou entraînement distribué.
- Robustesse : normalisation (BatchNorm/LayerNorm), dropedge, régularisation, et résidus/skip-connections pour éviter l'oversmoothing.

**Conseil pratique** : commencez par un modèle léger (GCN/GraphSAGE), profilez le coût mémoire/temps, puis essayez GAT/relational uniquement si la structure le justifie.

---

## Comparaison numérique des sorties GCN vs GAT (exemple de code)

```python
import numpy as np
# Si les tenseurs existent (exécutés précédemment), affichez-les et leur différence
try:
    gcn_out = out.detach().cpu().numpy()
    gat_out = gat_out.detach().cpu().numpy()
    print("GCN output:\n", gcn_out)
    print("GAT output:\n", gat_out)
    print("L2 diff:", np.linalg.norm(gcn_out - gat_out))
except NameError as e:
    print("Les variables `out` ou `gat_out` ne sont pas définies. Executez d'abord les cellules GCN et GAT.")
```
