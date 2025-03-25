## 1. Non-deterministic (networkx.maximal_independent_set)
```
# %%
import pandas as pd 
import hail as hl 
import networkx as nx
import matplotlib.pyplot as plt
import numpy as np

# %%
#---------------------------------------------------
# Import data, build, and plot relationship graph
# ---------------------------------------------------
rel_df = pd.read_table("./first_degree_2023_1_1.0_GRCh37.tsv")
rel_df.info()
rel_df.to_numpy()
rel_df

# %%
rel_samples = rel_df[['ID1', 'ID2']]
rel_samples

# %%
rel_list = [tuple(r) for r in rel_df[['ID1', 'ID2']].to_numpy()]
rel_list

# %%
G = nx.Graph(rel_list)  # create a graph from an edge list
list(G.edges())

# %%
#plot first degree relationships as a graph
print(f"First Degree Relationships: {G}")

fig1 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" for n in G],
    ax=fig1.add_subplot()
)

fig1.savefig("first_degree_graph.png")   # Save plot to file


# %%


#-----------------------------------------------------
# Calculate maximal independent set and plot it
#Uses .approximation.maximum_independent_set instead
#-------------------------------------------------------
maxlen = 0

for i in range(0, 1000):

    max_ind_set = nx.approximation.maximum_independent_set(G)
    this_len = len(max_ind_set)

    if  this_len > maxlen:
        final_set = max_ind_set
        maxlen= this_len

print("Max set length: ", maxlen)
#final_set.sort()
print("Set:", list(final_set))

# %%
#Plot and save maximal independant set as graph
print(f"Maximal Independent set: {final_set}")

fig2 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" if n in final_set else "tab:blue" for n in G],
    ax=fig2.add_subplot()
)

fig2.savefig("max_ind_graph.png")   # Save plot to file

# %%

#--------------------------------------------------------
# Create lists of sample sets and graph information
#--------------------------------------------------------

filter_list = list(set(G.nodes) - set(final_set))
filter_list

# %%
#write graph information to file
with open('./graph_info', mode='wt', encoding='utf-8') as myfile:
    myfile.write('Number of nodes: ' + str(G.number_of_nodes()))
    myfile.write('\nNumber of first degree relationships (edges): ' + str(G.number_of_edges()) + '\n')
  

#write independent set to file
with open('./max_ind_set.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(final_set))

#write samples to filter to file
with open('./rel_samples_to_filter.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(filter_list))

# %%




[stephanie.petrone@gpcc-node01 independent_set]$ cat calc_independent_set.py 
# %%
import pandas as pd 
import hail as hl 
import networkx as nx
import matplotlib.pyplot as plt
import numpy as np

# %%
#---------------------------------------------------
# Import data, build, and plot relationship graph
# ---------------------------------------------------
rel_df = pd.read_table("./first_degree_2023_1_1.0_GRCh37.tsv")
rel_df.info()
rel_df.to_numpy()
rel_df

# %%
rel_samples = rel_df[['ID1', 'ID2']]
rel_samples

# %%
rel_list = [tuple(r) for r in rel_df[['ID1', 'ID2']].to_numpy()]
rel_list

# %%
G = nx.Graph(rel_list)  # create a graph from an edge list
list(G.edges())

# %%
#plot first degree relationships as a graph
print(f"First Degree Relationships: {G}")

fig1 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" for n in G],
    ax=fig1.add_subplot()
)

fig1.savefig("first_degree_graph.png")   # Save plot to file


# %%


#-----------------------------------------------------
# Calculate maximal independent set and plot it
#-------------------------------------------------------
maxlen = 0

for i in range(0, 1000):

    max_ind_set = nx.maximal_independent_set(G)
    this_len = len(max_ind_set)

    if  this_len > maxlen:
        final_set = max_ind_set
        maxlen= this_len

print("Max set length: ", maxlen)
final_set.sort()
print("Set:", list(final_set))

# %%
#Plot and save maximal independant set as graph
print(f"Maximal Independent set: {final_set}")

fig2 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" if n in final_set else "tab:blue" for n in G],
    ax=fig2.add_subplot()
)

fig2.savefig("max_ind_graph.png")   # Save plot to file

# %%

#--------------------------------------------------------
# Create lists of sample sets and graph information
#--------------------------------------------------------

filter_list = list(set(G.nodes) - set(final_set))
filter_list

# %%
#write graph information to file
with open('./graph_info', mode='wt', encoding='utf-8') as myfile:
    myfile.write('Number of nodes: ' + str(G.number_of_nodes()))
    myfile.write('\nNumber of first degree relationships (edges): ' + str(G.number_of_edges()) + '\n')
  

#write independent set to file
with open('./max_ind_set.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(final_set))

#write samples to filter to file
with open('./rel_samples_to_filter.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(filter_list))

# %%
def plot_3d(independent, filter_out, G):
    # 3d spring layout
    pos = nx.spring_layout(G, dim=3, seed=779)
    # Extract node and edge positions from the layout
    node_ind_xyz = np.array([pos[v] for v in sorted(independent)])
    node_filter_xyz = np.array([pos[v] for v in sorted(filter_out)])
    edge_xyz = np.array([(pos[u], pos[v]) for u, v in G.edges()])

    # Create the 3D figure
    fig = plt.figure(figsize=(48,36), dpi=80)
    ax = fig.add_subplot(111, projection="3d")

    # Plot the nodes - alpha is scaled by "depth" automatically
    ax.scatter(*node_ind_xyz.T, s=100, ec="w", c='red')
    ax.scatter(*node_filter_xyz.T, s=100, ec="w", c='blue')

    # Plot the edges
    for vizedge in edge_xyz:
        ax.plot(*vizedge.T, color="tab:gray")


    def _format_axes(ax):
        """Visualization options for the 3D axes."""
        # Turn gridlines off
        ax.grid(False)
        # Suppress tick labels
        for dim in (ax.xaxis, ax.yaxis, ax.zaxis):
            dim.set_ticks([])
        # Set axes labels
        ax.set_xlabel("x")
        ax.set_ylabel("y")
        ax.set_zlabel("z")


    _format_axes(ax)
    fig.tight_layout()
    fig2.savefig("3d_max_ind_graph.png") 
    plt.show()

# %%
plot_3d(final_set, filter_list, G)

```
## 2. Deterministic (networkx.approximate.maximum_independent_set)
```# %%
# %%
import pandas as pd 
import hail as hl 
import networkx as nx
import matplotlib.pyplot as plt
import numpy as np

# %%
#---------------------------------------------------
# Import data, build, and plot relationship graph
# ---------------------------------------------------
rel_df = pd.read_table("./first_degree_qc_filtered_2023_1_1.0_GRCh37.tsv")
rel_df.info()
rel_df.to_numpy()
rel_df

# %%
rel_samples = rel_df[['ID1', 'ID2']]
rel_samples

# %%
rel_list = [tuple(r) for r in rel_df[['ID1', 'ID2']].to_numpy()]
rel_list

# %%
G = nx.Graph(rel_list)  # create a graph from an edge list
list(G.edges())

# %%
#plot first degree relationships as a graph
print(f"First Degree Relationships: {G}")

fig1 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" for n in G],
    ax=fig1.add_subplot()
)

fig1.savefig("first_degree_graph.png")   # Save plot to file


# %%


#-----------------------------------------------------
# Calculate maximal independent set and plot it
#Uses .approximation.maximum_independent_set instead
#-------------------------------------------------------
maxlen = 0

for i in range(0, 1000):

    max_ind_set = nx.approximation.maximum_independent_set(G)
    this_len = len(max_ind_set)

    if  this_len > maxlen:
        final_set = max_ind_set
        maxlen= this_len

print("Max set length: ", maxlen)
#final_set.sort()
print("Set:", list(final_set))

# %%
#Plot and save maximal independant set as graph
print(f"Maximal Independent set: {final_set}")

fig2 = plt.figure(figsize=(48,36), dpi=80)

pos = nx.spring_layout(G, seed=39299899)
nx.draw(
    G,
    pos=pos,
    with_labels=True,
    node_color=["tab:red" if n in final_set else "tab:blue" for n in G],
    ax=fig2.add_subplot()
)

fig2.savefig("max_ind_graph.png")   # Save plot to file

# %%

#--------------------------------------------------------
# Create lists of sample sets and graph information
#--------------------------------------------------------

filter_list = list(set(G.nodes) - set(final_set))
filter_list

# %%
#write graph information to file
with open('./graph_info', mode='wt', encoding='utf-8') as myfile:
    myfile.write('Number of nodes: ' + str(G.number_of_nodes()))
    myfile.write('\nNumber of first degree relationships (edges): ' + str(G.number_of_edges()) + '\n')
  

#write independent set to file
with open('./max_ind_set.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(final_set))

#write samples to filter to file
with open('./rel_samples_to_filter.tsv', mode='wt', encoding='utf-8') as myfile:
    myfile.write('\n'.join(filter_list))

# %%


```