## Questions from notebook 1

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: Analyze the code (in KohonenUtils.py) to understand what are the uses of each block in the cell right above.</p>

The first block initializes the Kohonen map with its size. The second block sets up the hyperparameters like epochs, learning rate and neighborhood size for the algorithm. The third block (single line) trains the Kohonen map on the animals data. The last line processes and displays the U-matrix of the calculated Kohonen map.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: What do you think about the clustering quality ? </p>

The birds are well grouped together, even as subgroups like birds of prey. Other animals (mammals) are less well clustered but are still represented far from the birds. The clustering is good but could be better. However, these results vary with each training. Overall, the clustering is pretty good.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: We plotted the U-Matrix in the previous cell. What does it represent ? </p>
The U-matrix (Unified distance matrix) adds neurons on the map that are colored in function of the euclidean distance between the surrounding neurons. Dark dots show a big distance whereas light dits show a small distance. This allows us to see clusters as light areas, spearated by darker areas.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: What do the small stars represent ? What do the bigger circles represent ? </p>

The stars are the base neurons of the Kohonen map. The bigger circles are the added neurons to show the distance between neurons.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: What does the color in the big circles mean ? </p>

The color in the big circles means the distance between the two surrounding neurons.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: What does the color in the small stars mean ? </p>

The red stars are the closest neurons from each data input (animals). The blue stars are all the other neurons.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: Plot the learning rate and the neighborhood size. Why do you think we choose them like this? </p>

The learning rate is decreasing so the map will be subject to big changes at first but it will change less and less over time, so the map will end up stabilizing. The same applies to the neighborhood size: At first, a "winner" neuron will have a lot of effect on all its neighbours, even ones that are pretty far away. Them, as the epochs go, a "winner" neuron will have less and less influence over its neighbours, also to end up stabilizing the map.


<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: Observe the animals that are grouped together by K-Means and try different numbers of clusters: K=2,3,4, etc. </p>

With 2 clusters (K=2), the separation will always be brids/others, and it will be done perfectly. With more clusters, more arbitrary separations will appear, like separating birds of prey from the other ones, or more arbitrary groups between mammals, that don't make much sense from a human perspective. With 4 or more clusters, even more arbitrary groups are created. On a side note, with any K, a bird was never mixed with a mammal in tens of observations. It is also good to note that the results vary a lot between initializations.

<p style="background-color:#006600; color:#fff;padding:5px; font-weight:bold">Q: n_init is a parameter that automatically asks K-means to try different cluster initializations and selects the best result. init='random' asks K-means to randomly initialize the cluster centroids. Please, try init=’k-means++’ and modify n_init to 10 for example and observe the results. </p>

With K=2, again, birds and mammals are always separated from each other. However, now that we have specified some parameters for a more optimized initialization, results are much more consistants between different executions. For example, with K=3, we always have almost the same clusters: Birds; small mammals (fox, dog, wolf, cats) and bigger mammals. The clustering of mammals may vary a little but stays stable overall. With K=4, we keep the same separation between mammals, and add a cluster containing the birds of prey. Overall, the results are much more consistant and relevant that previously with those initialization parameters.
