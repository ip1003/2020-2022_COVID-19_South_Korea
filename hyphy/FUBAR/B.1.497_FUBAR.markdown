
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
>[WARNING] '/data/jwd07/main/099/080/99080096/working/./input.fasta'
contains 432 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/080/99080096/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **531** sequences, **1273** codons, and **1** partitions from `/data/jwd07/main/099/080/99080096/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/080/99080096/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/080/99080096/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/080/99080096/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 94 zero-length internal branches: `Node1, Node10, Node27, Node28, Node32, Node351, Node352, Node353, Node354, Node355, Node358, Node362, Node363, Node364, Node365, Node37, Node372, Node38, Node39, Node392, Node396, Node397, Node399, Node4, Node400, Node402, Node41, Node410, Node413, Node414, Node415, Node421, Node423, Node424, Node425, Node426, Node429, Node439, Node440, Node441, Node442, Node45, Node450, Node451, Node452, Node453, Node459, Node465, Node468, Node469, Node470, Node476, Node479, Node481, Node486, Node487, Node49, Node491, Node492, Node497, Node498, Node5, Node501, Node51, Node513, Node514, Node516, Node518, Node520, Node521, Node523, Node53, Node531, Node532, Node582, Node587, Node592, Node598, Node599, Node6, Node60, Node604, Node617, Node619, Node62, Node621, Node629, Node631, Node64, Node640, Node644, Node7, Node8, Node9`
* Log(L) = -6199.79, AIC-c = 13732.03 (666 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.029
* Tree length (expected substitutions/site) for partition 1 :    0.029

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
|       5        |       1        |        2.276   |       17.371   |       Pos. posterior = 0.9186       |
|       98       |       1        |        2.316   |       18.872   |       Pos. posterior = 0.9239       |
|      243       |       1        |        2.341   |       19.889   |       Pos. posterior = 0.9273       |
|      1079      |       1        |        2.258   |       16.487   |       Pos. posterior = 0.9150       |
|      1083      |       1        |        2.652   |       22.046   |       Pos. posterior = 0.9277       |
----
## FUBAR inferred 5 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.39 are expected to be false positives (95% confidence interval of 0-2 )
