# GCN Assignment for 11441/11641/11741

## Getting started

- Unzip the data from `data.zip`.
- Install the required packages listed in `requirements.txt`.
- Please use Python 3.6 or above.


## Outline

This goal of this assignment is to implement a basic GCN model for node classification, link prediction, and graph classification. Most of the code related to training, data loading, and evaluation is provided. You need to implement the parts marked as # TODO. Each TODO needs a few lines of code to complete (2-3 lines in most cases).

### Part 1: Graph exploration
- The notebook notebooks/GraphExploration.ipynb contains the code for the first part of this assignment. The goal of this part is to introduce you to `graph.py`, the class that represents a graph and some of its methods.


### Part 2: Implementing a GCN

- This has two sub-parts:
1. Implementing a GCN layer
2. Using the GCN layer to implement a GCN model

### Part 3: Node classification

- Use the GCN model implemented in part 2 to classify nodes in the graph.

### Part 4: Link prediction

- Use the GCN model implemented in part 2 to predict links in the graph.

### Part 5: Graph classification

- We will use the GCN model implemented in part 2 to classify graphs (i.e., predict a label for each graph).


## Scripts

### Node classification
```sh
bash scripts/run_node_classification.sh [GRAPH_NAME]
```

Where:
- GRAPH_NAME is the name of the graph to use (e.g., `cora`, `citeseer`).

E.g., to run node classification on `citeseer` with topological features, run:

```sh
bash scripts/run_node_classification.sh citeseer_plus_topo
```

- The usage link prediction is similar.

### Graph classification
```sh
bash scripts/run_graph_classification.sh [GRAPH_PATH] [NUM_CLASSES] [POOLING_OP (max|mean|last)] [NUM_EPOCHS]
```

Where:
- GRAPH_PATH: path to the graph file.
- NUM_CLASSES: number of classes in the graph.
- POOLING_OP: pooling operation to use.
- NUM_EPOCHS: number of epochs to train the model.

More details can be found in scripts/run_graph_classification.sh.


E.g., to run graph classification on mutag (2 classes) with max pooling and 200 epochs:

```sh
bash scripts/run_graph_classification.sh data/graph_classification/graph_mutag_with_node_num.pt 2 max 200
```

## Attributions
- Parts of the dataloader code are based on [this repo](https://github.com/tkipf/gcn).
