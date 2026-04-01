
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
>[WARNING] '/data/jwd07/main/099/080/99080093/working/./input.fasta'
contains 107 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/080/99080093/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **509** sequences, **1271** codons, and **1** partitions from `/data/jwd07/main/099/080/99080093/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/080/99080093/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/080/99080093/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/080/99080093/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 278 zero-length internal branches: `Node1, Node103, Node106, Node107, Node108, Node109, Node11, Node110, Node111, Node114, Node116, Node119, Node12, Node122, Node124, Node125, Node126, Node127, Node128, Node129, Node130, Node135, Node146, Node150, Node153, Node154, Node155, Node156, Node157, Node158, Node159, Node176, Node177, Node178, Node179, Node19, Node2, Node208, Node209, Node21, Node217, Node218, Node221, Node222, Node224, Node229, Node234, Node235, Node247, Node248, Node252, Node254, Node260, Node264, Node268, Node27, Node270, Node28, Node281, Node283, Node286, Node289, Node292, Node293, Node296, Node3, Node302, Node311, Node319, Node32, Node320, Node321, Node323, Node324, Node325, Node326, Node329, Node332, Node333, Node334, Node337, Node339, Node34, Node341, Node344, Node354, Node356, Node359, Node360, Node363, Node367, Node380, Node381, Node382, Node383, Node384, Node385, Node386, Node389, Node397, Node399, Node4, Node40, Node402, Node407, Node408, Node409, Node413, Node415, Node420, Node425, Node426, Node427, Node431, Node433, Node434, Node435, Node445, Node45, Node453, Node455, Node46, Node463, Node464, Node469, Node47, Node472, Node473, Node474, Node475, Node477, Node48, Node481, Node482, Node483, Node487, Node492, Node498, Node499, Node5, Node500, Node501, Node503, Node508, Node51, Node512, Node515, Node516, Node517, Node523, Node524, Node525, Node526, Node534, Node535, Node536, Node538, Node54, Node540, Node559, Node567, Node568, Node569, Node57, Node570, Node572, Node575, Node576, Node584, Node586, Node588, Node590, Node594, Node597, Node60, Node600, Node604, Node605, Node606, Node61, Node612, Node616, Node62, Node620, Node630, Node631, Node637, Node638, Node64, Node646, Node648, Node651, Node655, Node660, Node661, Node662, Node664, Node67, Node677, Node68, Node682, Node685, Node686, Node688, Node69, Node690, Node693, Node701, Node703, Node709, Node712, Node713, Node714, Node715, Node716, Node717, Node718, Node72, Node721, Node728, Node73, Node74, Node740, Node741, Node744, Node75, Node757, Node760, Node762, Node764, Node767, Node77, Node772, Node779, Node78, Node780, Node781, Node785, Node788, Node79, Node794, Node795, Node797, Node805, Node808, Node809, Node811, Node813, Node815, Node818, Node824, Node825, Node83, Node831, Node832, Node834, Node838, Node839, Node840, Node841, Node847, Node848, Node85, Node850, Node852, Node861, Node862, Node864, Node866, Node868, Node874, Node875, Node878, Node880, Node91, Node92, Node97, Node99`
* Log(L) = -7275.16, AIC-c = 16419.23 (934 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.058
* Tree length (expected substitutions/site) for partition 1 :    0.058

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
|      142       |       1        |        2.707   |       49.700   |       Pos. posterior = 0.9909       |
|      231       |       1        |        2.752   |       21.400   |       Pos. posterior = 0.9282       |
|      253       |       1        |        2.537   |       28.901   |       Pos. posterior = 0.9587       |
|      948       |       1        |        3.521   |       45.156   |       Pos. posterior = 0.9747       |
----
## FUBAR inferred 4 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.15 are expected to be false positives (95% confidence interval of 0-1 )
