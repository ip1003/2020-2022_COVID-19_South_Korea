
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
>[WARNING] '/data/jwd06/main/099/080/99080095/working/./input.fasta'
contains 381 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd06/main/099/080/99080095/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **421** sequences, **1270** codons, and **1** partitions from `/data/jwd06/main/099/080/99080095/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd06/main/099/080/99080095/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd06/main/099/080/99080095/working/./input.fasta.FUBAR.cache_ and _/data/jwd06/main/099/080/99080095/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 38 zero-length internal branches: `Node1, Node2, Node3, Node315, Node318, Node319, Node320, Node322, Node327, Node333, Node334, Node337, Node338, Node349, Node357, Node360, Node361, Node362, Node367, Node368, Node379, Node380, Node383, Node384, Node4, Node432, Node435, Node436, Node437, Node440, Node441, Node444, Node445, Node446, Node448, Node451, Node467, Node7`
* Log(L) = -5558.04, AIC-c = 12070.35 (477 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.011
* Tree length (expected substitutions/site) for partition 1 :    0.011

### Computing the phylogenetic likelihood function on the grid 
* Determining appropriate tree scaling based on the best score from a  20 x 20 rate grid
* Best scaling achieved for 
	* synonymous rate =  1.000
	* non-synonymous rate =  1.000
* Computing conditional site likelihoods on a 20 x 20 rate grid

### Running an iterative zeroth order variational Bayes procedure to estimate the posterior mean of rate weights
* Using the following settings
	* Dirichlet alpha  : 0.5

### Tabulating site-level results
|     Codon      |   Partition    |     alpha      |      beta      |Posterior prob for positive selection|
|:--------------:|:--------------:|:--------------:|:--------------:|:-----------------------------------:|
|       54       |       1        |        3.598   |       29.099   |       Pos. posterior = 0.9293       |
|      580       |       1        |        4.311   |       32.833   |       Pos. posterior = 0.9262       |
----
## FUBAR inferred 2 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.14 are expected to be false positives (95% confidence interval of 0-1 )
