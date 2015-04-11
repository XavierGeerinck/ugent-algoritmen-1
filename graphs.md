# 2.8 Graphs
* Abstract model
* Exists of n nodes or vertices
* Has a collection of m edges
* The nodes represent objects with connections
* Can have a direction.
* The grade of a node is the amount of neighbours of that node.
* For a graph with a direction, we have an ingrade, this is the amount of incoming neighbours. The same goes for the outgrade which is the amount of outgoing neighbours.
* 2 Basic representations of graphs:
    * Neighbour matrix: takes a connection (i,j) and represents it on a square neighbourmatrix. This value can be logical or can be the weight. The problem is that matrices take a lot of memory en the initialisation takes $$\Theta(n^2)$$ operations.
    * Neighbour lists: Mostly used when we do not have a lot of connections (m << $$n^2$$). In reality most graphs are like this. The neighbours of every node are saved in a neighbour list and the graph is represented by a table of n neighbourlists.

These pictures show a normal graph, it's neighbour list and the neighbour matrix

![](Screen Shot 2015-04-02 at 13.21.33.png)![](Screen Shot 2015-04-02 at 13.21.39.png)

Looping through a graph is different then looping through a tree, this because a graph has multiple pathways and we have to find a way to only go through each path once.

For this looping we have several methods:
## 2.8.1. Depth-first searching
This is analog to recursive searching in a tree. We start at any node and we continue forward. It also keeps a log of the already visited nodes so we do not visit them twice. On the end we discover the remaining nodes.

```c++
void check_node(int i) {
    discovered[i] = true;
    
    for (every neighbour j of node i) {
        if (!discovered[j]) {
            check_node(j);
        }
    }
}

void depth_first_search() {
    // No nodes discovered
    for (int i = 0; i < n; i++) {
        discovered[i] = false;
    }
    
    // Go through each node
    for (int i = 0; i < n; i++) {
        if (!discovered[i]) {
            check_node(i); // start a new tree
        }
    }
}
```

We have discovered a