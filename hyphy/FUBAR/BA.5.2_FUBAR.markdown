
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
>[WARNING] '/data/jwd07/main/099/080/99080106/working/./input.fasta'
contains 119 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/080/99080106/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **211** sequences, **1268** codons, and **1** partitions from `/data/jwd07/main/099/080/99080106/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/080/99080106/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/080/99080106/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/080/99080106/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 80 zero-length internal branches: `Node1, Node104, Node113, Node114, Node117, Node121, Node126, Node128, Node129, Node13, Node130, Node131, Node134, Node136, Node137, Node138, Node141, Node142, Node15, Node153, Node155, Node157, Node163, Node167, Node18, Node189, Node191, Node196, Node2, Node20, Node200, Node201, Node203, Node204, Node211, Node218, Node22, Node222, Node226, Node227, Node229, Node233, Node234, Node236, Node240, Node243, Node245, Node249, Node252, Node253, Node26, Node260, Node261, Node262, Node263, Node266, Node267, Node269, Node270, Node273, Node274, Node277, Node285, Node286, Node287, Node291, Node295, Node297, Node299, Node3, Node301, Node302, Node306, Node309, Node313, Node4, Node6, Node7, Node8, Node9`
* Log(L) = -5803.15, AIC-c = 12254.57 (324 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.019
* Tree length (expected substitutions/site) for partition 1 :    0.019

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
|     Codon      |   Partition    |     alpha      |      beta      |Posterior prob for positive selection|
|:--------------:|:--------------:|:--------------:|:--------------:|:-----------------------------------:|
|       75       |       1        |        3.371   |       32.564   |       Pos. posterior = 0.9434       |
|      341       |       1        |        4.506   |       33.433   |       Pos. posterior = 0.9238       |
|      1015      |       1        |        2.912   |       27.568   |       Pos. posterior = 0.9379       |
----
## FUBAR inferred 3 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.19 are expected to be false positives (95% confidence interval of 0-1 )
