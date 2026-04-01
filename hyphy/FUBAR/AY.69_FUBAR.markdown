
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
>[WARNING] '/data/jwd07/main/099/079/99079528/working/./input.fasta'
contains 85 duplicate sequences. Identical sequences do not contribute
any information to the analysis and only slow down computation. Please
consider removing duplicate or 'nearly' duplicate sequences, e.g. using
https://github.com/veg/hyphy-analyses/tree/master/remove-duplicates
prior to running selection analyses
-------
/data/jwd07/main/099/079/99079528/working/input.nhx
input.nhx

>Loaded a multiple sequence alignment with **686** sequences, **1271** codons, and **1** partitions from `/data/jwd07/main/099/079/99079528/working/./input.fasta`
Save FUBAR cache to : 
>cache => /data/jwd07/main/099/079/99079528/working/./input.fasta.FUBAR.cache
> FUBAR will write cache and result files to _/data/jwd07/main/099/079/99079528/working/./input.fasta.FUBAR.cache_ and _/data/jwd07/main/099/079/99079528/working/./input.fasta.FUBAR.json_, respectively 


> Number of grid points per dimension (total number is D^2) (permissible range = [5,50], default value = 20, integer): 
>grid => 20

>method => Variational-Bayes
> The concentration parameter of the Dirichlet prior (permissible range = [0.001,1], default value = 0.5): 
>concentration_parameter => 0.5

>non-zero => No


### Obtaining branch lengths and nucleotide substitution biases under the nucleotide GTR model

>kill-zero-lengths => Yes

### Deleted 383 zero-length internal branches: `Node1, Node1001, Node1008, Node1013, Node1016, Node1020, Node1021, Node1023, Node1026, Node1027, Node1035, Node1043, Node1045, Node1046, Node1048, Node105, Node1052, Node1053, Node1054, Node1055, Node1056, Node106, Node1063, Node1064, Node1065, Node1068, Node107, Node1070, Node1078, Node1085, Node1086, Node1105, Node1106, Node1123, Node1130, Node1131, Node1133, Node1134, Node1141, Node1142, Node1143, Node1145, Node1146, Node1148, Node1152, Node1153, Node1165, Node1185, Node1187, Node1189, Node1193, Node1194, Node12, Node121, Node1212, Node1214, Node1216, Node1217, Node1219, Node1220, Node1222, Node1223, Node1225, Node123, Node1238, Node1240, Node1242, Node1244, Node1256, Node1257, Node1262, Node1264, Node1272, Node128, Node1287, Node1289, Node129, Node130, Node131, Node138, Node142, Node143, Node145, Node147, Node149, Node15, Node151, Node155, Node156, Node16, Node160, Node164, Node165, Node169, Node17, Node172, Node174, Node176, Node18, Node181, Node183, Node184, Node194, Node2, Node20, Node203, Node205, Node206, Node207, Node211, Node216, Node220, Node221, Node223, Node229, Node232, Node233, Node234, Node239, Node246, Node248, Node251, Node254, Node26, Node260, Node266, Node271, Node276, Node277, Node278, Node28, Node282, Node285, Node288, Node289, Node297, Node3, Node30, Node300, Node307, Node308, Node310, Node311, Node319, Node323, Node324, Node33, Node335, Node336, Node337, Node338, Node347, Node348, Node35, Node350, Node352, Node354, Node356, Node357, Node358, Node363, Node372, Node373, Node374, Node376, Node377, Node379, Node383, Node384, Node385, Node386, Node388, Node390, Node394, Node395, Node397, Node399, Node4, Node40, Node402, Node406, Node41, Node410, Node415, Node420, Node426, Node427, Node428, Node441, Node442, Node444, Node446, Node449, Node450, Node452, Node453, Node455, Node458, Node460, Node466, Node467, Node468, Node469, Node470, Node471, Node473, Node475, Node483, Node490, Node491, Node493, Node499, Node5, Node500, Node501, Node502, Node504, Node510, Node511, Node512, Node513, Node515, Node516, Node52, Node522, Node523, Node524, Node525, Node526, Node527, Node529, Node531, Node535, Node537, Node540, Node541, Node542, Node550, Node559, Node561, Node562, Node567, Node569, Node570, Node573, Node574, Node575, Node583, Node586, Node587, Node588, Node591, Node592, Node595, Node596, Node598, Node6, Node604, Node606, Node608, Node61, Node614, Node617, Node619, Node622, Node629, Node63, Node633, Node634, Node636, Node638, Node642, Node646, Node648, Node65, Node662, Node663, Node668, Node670, Node672, Node675, Node676, Node680, Node681, Node684, Node687, Node690, Node692, Node7, Node70, Node701, Node702, Node703, Node712, Node713, Node714, Node715, Node717, Node728, Node729, Node730, Node731, Node775, Node776, Node777, Node778, Node785, Node789, Node790, Node791, Node793, Node795, Node8, Node802, Node805, Node811, Node814, Node815, Node817, Node822, Node824, Node830, Node831, Node834, Node835, Node838, Node839, Node842, Node845, Node846, Node847, Node848, Node849, Node857, Node859, Node861, Node862, Node864, Node868, Node870, Node874, Node875, Node877, Node879, Node882, Node883, Node884, Node886, Node888, Node890, Node895, Node896, Node9, Node907, Node908, Node914, Node921, Node927, Node929, Node931, Node933, Node936, Node938, Node943, Node944, Node945, Node946, Node950, Node952, Node972, Node973, Node975, Node977, Node983, Node985, Node987, Node989, Node992, Node993, Node995, Node996, Node997, Node999`
* Log(L) = -8230.03, AIC-c = 19059.36 (1299 estimated parameters)
* 1 partition. Total tree length by partition (subs/site)  0.087
* Tree length (expected substitutions/site) for partition 1 :    0.087

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
|       5        |       1        |        1.529   |       20.791   |       Pos. posterior = 0.9737       |
|       61       |       1        |        4.122   |       30.537   |       Pos. posterior = 0.9289       |
|      142       |       1        |       17.095   |       49.897   |       Pos. posterior = 0.9020       |
|      148       |       1        |        1.236   |       11.275   |       Pos. posterior = 0.9170       |
|      184       |       1        |        1.227   |       11.532   |       Pos. posterior = 0.9505       |
|      207       |       1        |        1.480   |       12.823   |       Pos. posterior = 0.9450       |
|      232       |       1        |        1.217   |       23.402   |       Pos. posterior = 0.9848       |
|      287       |       1        |        1.827   |       11.971   |       Pos. posterior = 0.9264       |
|      444       |       1        |        1.409   |       11.892   |       Pos. posterior = 0.9437       |
|      948       |       1        |        2.537   |       20.877   |       Pos. posterior = 0.9422       |
----
## FUBAR inferred 10 sites subject to diversifying positive selection at posterior probability >= 0.9
Of these,  0.59 are expected to be false positives (95% confidence interval of 0-2 )
