
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
>[WARNING] '/data/jwd08/main/099/080/99080105/working/./input.fasta'
contains 102 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd08/main/099/080/99080105/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **200** sequences, **1268** codons, and **1** partitions from `/data/jwd08/main/099/080/99080105/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd08/main/099/080/99080105/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd08/main/099/080/99080105/working/./input.fasta.FUBAR.cache_ and _/data/jwd08/main/099/080/99080105/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 78 zero-length internal branches: `Node1, Node102, Node106, Node11, Node111, Node120, Node121, Node124, Node125, Node128, Node129, Node130, Node131, Node134, Node139, Node143, Node155, Node158, Node159, Node16, Node164, Node165, Node166, Node167, Node17, Node170, Node171, Node172, Node173, Node176, Node18, Node185, Node186, Node187, Node189, Node2, Node200, Node201, Node203, Node206, Node208, Node214, Node216, Node219, Node223, Node23, Node24, Node27, Node28, Node3, Node302, Node31, Node34, Node35, Node36, Node4, Node40, Node41, Node42, Node45, Node48, Node49, Node5, Node54, Node56, Node60, Node64, Node77, Node81, Node85, Node87, Node9, Node90, Node91, Node92, Node93, Node94, Node98`
* Log(L) = -5871.58, AIC-c = 12367.42 (312 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.021
* Tree length (expected substitutions/site) for partition 1 :    0.021

### Computing the phylogenetic likelihood function on the grid 
* Determining appropriate tree scaling based on the best score from a  20 x 20 rate grid
* Best scaling achieved for 
	* synonymous rate =  1.227
	* non-synonymous rate =  0.857
* Computing conditional site likelihoods on a 20 x 20 rate grid

### Running an iterative zeroth order variational Bayes procedure to estimate the posterior mean of rate weights
* Using the following settings
	* Dirichlet alpha  : 0.5

### Tabulating site-level results
----
## FUBAR inferred no sites under subject to positive selection at posterior probability >= 0.9
