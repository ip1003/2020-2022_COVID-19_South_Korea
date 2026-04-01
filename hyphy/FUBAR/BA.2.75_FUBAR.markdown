
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
>[WARNING] '/data/jwd07/main/099/080/99080101/working/./input.fasta'
contains 161 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/080/99080101/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **572** sequences, **1270** codons, and **1** partitions from `/data/jwd07/main/099/080/99080101/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/080/99080101/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/080/99080101/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/080/99080101/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 297 zero-length internal branches: `Node1000, Node1004, Node1005, Node1007, Node1012, Node107, Node108, Node109, Node11, Node110, Node113, Node115, Node119, Node12, Node127, Node129, Node13, Node131, Node132, Node137, Node138, Node141, Node145, Node146, Node147, Node148, Node152, Node157, Node158, Node173, Node174, Node175, Node176, Node18, Node181, Node184, Node188, Node19, Node197, Node2, Node20, Node204, Node205, Node209, Node21, Node212, Node216, Node219, Node220, Node221, Node222, Node225, Node23, Node231, Node237, Node239, Node24, Node242, Node247, Node248, Node25, Node250, Node259, Node26, Node260, Node264, Node268, Node269, Node274, Node277, Node28, Node280, Node281, Node282, Node283, Node286, Node289, Node297, Node298, Node3, Node301, Node303, Node31, Node312, Node315, Node316, Node317, Node319, Node322, Node324, Node328, Node330, Node334, Node339, Node34, Node346, Node349, Node351, Node364, Node369, Node371, Node374, Node377, Node378, Node379, Node380, Node381, Node382, Node387, Node389, Node392, Node396, Node398, Node399, Node403, Node404, Node406, Node41, Node410, Node412, Node414, Node415, Node418, Node421, Node436, Node439, Node44, Node440, Node453, Node455, Node469, Node470, Node477, Node478, Node482, Node483, Node486, Node488, Node492, Node496, Node50, Node500, Node501, Node502, Node505, Node51, Node512, Node513, Node514, Node515, Node516, Node517, Node519, Node530, Node532, Node535, Node536, Node539, Node54, Node540, Node541, Node550, Node554, Node555, Node557, Node558, Node563, Node564, Node568, Node57, Node571, Node572, Node578, Node582, Node583, Node586, Node59, Node593, Node596, Node598, Node60, Node600, Node603, Node604, Node610, Node611, Node614, Node62, Node620, Node623, Node627, Node628, Node629, Node63, Node630, Node631, Node633, Node640, Node648, Node651, Node652, Node661, Node663, Node667, Node677, Node678, Node679, Node680, Node681, Node686, Node689, Node691, Node697, Node700, Node711, Node713, Node714, Node726, Node733, Node739, Node741, Node743, Node749, Node750, Node752, Node753, Node756, Node759, Node762, Node765, Node766, Node770, Node771, Node776, Node777, Node782, Node787, Node788, Node789, Node79, Node790, Node791, Node792, Node794, Node795, Node80, Node809, Node81, Node811, Node814, Node816, Node82, Node821, Node822, Node828, Node83, Node831, Node832, Node834, Node835, Node84, Node841, Node842, Node852, Node854, Node857, Node858, Node859, Node86, Node863, Node865, Node866, Node867, Node872, Node874, Node877, Node885, Node886, Node889, Node892, Node896, Node898, Node901, Node906, Node909, Node910, Node913, Node915, Node919, Node929, Node932, Node937, Node94, Node96, Node98, Node998, Node999`
* Log(L) = -8303.05, AIC-c = 18651.07 (1022 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.086
* Tree length (expected substitutions/site) for partition 1 :    0.086

### Computing the phylogenetic likelihood function on the grid 
* Determining appropriate tree scaling based on the best score from a  20 x 20 rate grid
* Best scaling achieved for 
	* synonymous rate =  1.227
	* non-synonymous rate =  1.000
* Computing conditional site likelihoods on a 20 x 20 rate grid

### Running an iterative zeroth order variational Bayes procedure to estimate the posterior mean of rate weights
* Using the following settings
	* Dirichlet alpha  : 0.5

### Tabulating site-level results
|     Codon      |   Partition    |     alpha      |      beta      |Posterior prob for positive selection|
|:--------------:|:--------------:|:--------------:|:--------------:|:-----------------------------------:|
|      182       |       1        |        1.636   |       24.009   |       Pos. posterior = 0.9741       |
|      207       |       1        |        1.388   |       42.077   |       Pos. posterior = 0.9955       |
|      210       |       1        |        0.879   |       17.230   |       Pos. posterior = 0.9871       |
|      336       |       1        |        1.579   |       20.827   |       Pos. posterior = 0.9724       |
|      343       |       1        |        1.712   |       34.544   |       Pos. posterior = 0.9864       |
|      353       |       1        |        0.963   |       18.358   |       Pos. posterior = 0.9855       |
|      372       |       1        |        0.879   |       40.290   |       Pos. posterior = 0.9993       |
|      373       |       1        |        1.203   |       11.189   |       Pos. posterior = 0.9469       |
|      405       |       1        |        1.008   |       41.752   |       Pos. posterior = 0.9988       |
|      414       |       1        |        1.950   |       46.134   |       Pos. posterior = 0.9916       |
|      449       |       1        |        0.698   |       22.161   |       Pos. posterior = 0.9964       |
|      483       |       1        |        1.475   |       18.330   |       Pos. posterior = 0.9688       |
|      487       |       1        |        1.281   |       12.340   |       Pos. posterior = 0.9495       |
|      491       |       1        |        1.431   |       15.865   |       Pos. posterior = 0.9573       |
|      761       |       1        |        2.141   |       17.098   |       Pos. posterior = 0.9395       |
|      933       |       1        |        0.836   |       12.306   |       Pos. posterior = 0.9704       |
|      1218      |       1        |        1.904   |       13.722   |       Pos. posterior = 0.9336       |
----
## FUBAR inferred 17 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.45 are expected to be false positives (95% confidence interval of 0-2 )
