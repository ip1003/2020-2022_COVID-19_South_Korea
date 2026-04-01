
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
>[WARNING] '/data/jwd07/main/099/080/99080097/working/./input.fasta'
contains 413 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/080/99080097/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **508** sequences, **1273** codons, and **1** partitions from `/data/jwd07/main/099/080/99080097/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/080/99080097/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/080/99080097/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/080/99080097/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 84 zero-length internal branches: `Node1, Node111, Node112, Node113, Node114, Node12, Node120, Node123, Node124, Node125, Node126, Node127, Node128, Node131, Node133, Node138, Node144, Node145, Node146, Node149, Node150, Node153, Node155, Node158, Node159, Node176, Node181, Node183, Node184, Node19, Node199, Node2, Node200, Node201, Node202, Node203, Node204, Node205, Node208, Node21, Node212, Node213, Node22, Node222, Node228, Node233, Node234, Node235, Node236, Node241, Node242, Node243, Node244, Node255, Node256, Node257, Node259, Node267, Node269, Node27, Node3, Node33, Node35, Node37, Node53, Node606, Node610, Node612, Node63, Node64, Node66, Node68, Node7, Node71, Node75, Node76, Node77, Node78, Node79, Node81, Node89, Node90, Node91, Node97`
* Log(L) = -6042.56, AIC-c = 13341.54 (628 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.025
* Tree length (expected substitutions/site) for partition 1 :    0.025

### Computing the phylogenetic likelihood function on the grid 
* Determining appropriate tree scaling based on the best score from a  20 x 20 rate grid
* Best scaling achieved for 
	* synonymous rate =  1.227
	* non-synonymous rate =  0.786
* Computing conditional site likelihoods on a 20 x 20 rate grid

### Running an iterative zeroth order variational Bayes procedure to estimate the posterior mean of rate weights
* Using the following settings
	* Dirichlet alpha  : 0.5

### Tabulating site-level results
|     Codon      |   Partition    |     alpha      |      beta      |Posterior prob for positive selection|
|:--------------:|:--------------:|:--------------:|:--------------:|:-----------------------------------:|
|      631       |       1        |        2.759   |       20.178   |       Pos. posterior = 0.9133       |
----
## FUBAR inferred 1 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.09 are expected to be false positives (95% confidence interval of 0-1 )
