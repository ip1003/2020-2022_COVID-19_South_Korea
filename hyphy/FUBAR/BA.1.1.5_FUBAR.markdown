
Analysis Description
--------------------
Perform a Fast Unbiased AppRoximate Bayesian (FUBAR) analysis of a
coding sequence alignment to determine whether some sites have been
subject to pervasive purifying or diversifying selection. v2.1
introduces two more methods for estimating the posterior distribution of
grid weights: collapsed Gibbs MCMC (faster) and 0-th order Variation
Bayes approximation (fastest). Please note that a FUBAR analysis
generates a cache and a results JSON file in the same directory as
directory as the original alignment. HyPhy needs to have write
privileges to this directory. For example if the original file is in
/home/sergei/FUBAR/data/pol.nex then at the end of a FUBAR run, there
will also exist FUBAR-generated files
/home/sergei/FUBAR/data/pol.nex.FUBAR.json,
/home/sergei/FUBAR/data/pol.nex.fubrar.cache. They also provide
checkpointing so that a partially completed analysis can be restarted.

- __Requirements__: in-frame codon alignment (possibly partitioned) and a phylogenetic tree
(one per partition)

- __Citation__: FUBAR: a fast, unconstrained bayesian approximation for inferring
selection (2013), Mol Biol Evol. 30(5):1196-205

- __Written by__: Sergei L Kosakovsky Pond

- __Contact Information__: spond@temple.edu

- __Analysis Version__: 2.2


>code => Universal

-------
>[WARNING] '/data/jwd08/main/099/080/99080099/working/./input.fasta'
contains 429 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd08/main/099/080/99080099/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **520** sequences, **1270** codons, and **1** partitions from `/data/jwd08/main/099/080/99080099/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd08/main/099/080/99080099/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd08/main/099/080/99080099/working/./input.fasta.FUBAR.cache_ and _/data/jwd08/main/099/080/99080099/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 93 zero-length internal branches: `Node1, Node12, Node151, Node153, Node157, Node158, Node161, Node162, Node163, Node164, Node166, Node167, Node168, Node17, Node18, Node19, Node2, Node20, Node231, Node232, Node234, Node236, Node243, Node244, Node245, Node247, Node248, Node249, Node251, Node252, Node255, Node256, Node257, Node259, Node261, Node266, Node269, Node27, Node271, Node272, Node28, Node3, Node318, Node322, Node324, Node325, Node340, Node343, Node348, Node351, Node358, Node368, Node372, Node375, Node379, Node381, Node386, Node393, Node396, Node399, Node402, Node406, Node407, Node408, Node546, Node551, Node556, Node557, Node558, Node564, Node566, Node568, Node569, Node572, Node580, Node585, Node586, Node587, Node588, Node589, Node591, Node594, Node602, Node603, Node604, Node613, Node615, Node618, Node622, Node624, Node626, Node627, Node8`
* Log(L) = -5471.69, AIC-c = 12225.80 (641 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.009
* Tree length (expected substitutions/site) for partition 1 :    0.009

### Computing the phylogenetic likelihood function on the grid 
* Determining appropriate tree scaling based on the best score from a  20 x 20 rate grid
* Best scaling achieved for 
	* synonymous rate =  1.227
	* non-synonymous rate =  0.714
* Computing conditional site likelihoods on a 20 x 20 rate grid

### Running an iterative zeroth order variational Bayes procedure to estimate the posterior mean of rate weights
* Using the following settings
	* Dirichlet alpha  : 0.5

### Tabulating site-level results
|     Codon      |   Partition    |     alpha      |      beta      |Posterior prob for positive selection|
|:--------------:|:--------------:|:--------------:|:--------------:|:-----------------------------------:|
|      414       |       1        |        5.007   |       43.516   |       Pos. posterior = 0.9441       |
----
## FUBAR inferred 1 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.06 are expected to be false positives (95% confidence interval of 0-1 )
