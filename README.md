# KMeansSuperTreeClustering
A new fast method for clustering phylogenetic trees using K-means and inferring multiple supertrees

# About
	=> =============================================================================================================================
	=> Program   : KMeansSuperTreeClustering - 2019
	=> Authors   : Nadia Tahiri and Vladimir Makarenkov (Université du Québec a Montréal)
	=> This program clusters phylogenetic trees using the k-means partitioning algorithm.
	=> These trees may have the same or different, but mutually overlapping, sets of leaves (the multiple supertree problem).
	=> Phylogenetic trees must be given in the Newick format (program input).
	=> A partitioning of the input trees in K clusters of trees is returned as output. 
	=> The optimal number of clusters can be determined either by the Calinski-Harabasz (CH) or by the Ball-Hall (BH) cluster 
	=> validity index adapted for tree clustering.
	=> A supertree can then be inferred for each cluster of trees.
	=> The Robinson and Foulds topological distance is used in the objective function of K-means.
	=> The list of the program parameters is specified below. =============================================================================================================================

# Installation
	$ git clone https://github.com/TahiriNadia/KMeansSuperTreeClustering.git
	$ make
	or
	$ make install

	clean project
	$ make clean

# Help
	$ make help

# Examples
	Please execute the following command line:
	=> For trees: ./KMSTC -tree input_file cluster_validity_index \alpha Kmin Kmax

	=> input_file: the input file for the program
	=> cluster_validity_index: the cluster validity index used in K-means (1 for Calinski-Harabasz and 2 for Ball-Hall)
	=> \alpha: is the penalty parameter for species overlap in phylogenetic trees (must be between 0 and 1)
	=> Kmin: is the minimum number of clusters in K-means. 
        	- For CH, Kmin>=2,
        	- For BH, Kmin>=1.
	=> Kmax: the maximum number of clusters in K-means. 
        	- Kmax must be less or equal to N-1 (where N is the number of input trees).

	Command line execution (input_file = data/all_trees_woese.txt, cluster_validity_index = CH, alpha = 1, Kmin = 2, Kmax = 10):
	./KMSTC -tree data/all_trees_woese.txt 1 1 2 10

# Input
	=> The data set is located in the folder "data"
	Phylogenetic gene trees in the Newick format from the paper by Woese et al. (2000, Microbiology and Molecular Biology Reviews)
	(data file: data/all_trees_woese.txt)

# Output
	=> See the folder "output"
	The output is in the following files:
	1) stat.csv - for the clustering statistics;
	2) output.txt - for the cluster content.
