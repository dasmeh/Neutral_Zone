# Neutral_Zone

Population Genetics Simulations of the antibiotic resistance evolution


The distribution of mutational effects (DMEs) of wtVIM-2 for ampicillin resistance (EC50) was experimentally obtained in our previous deep mutational scanning (DMS) study of VIM-2 (https://www.nature.com/articles/s41559-022-01675-5). We also obtained the relationship between EC50 and the fitness of E. coli harbouring VIM variants. 

![Screen Shot 2023-02-28 at 9 28 57 AM](https://user-images.githubusercontent.com/6492012/221796879-1981d043-f998-420f-88b4-17d4efc1d491.png)

(Equation 1)

Where, average fitness of mutant VIM-2 variants was estimated by the calculation of the bacterial growth rate (g) was modelled by a Hill function of the MIC concentration of ampicillin, the relative growth rate in the absence of ampicillin (g0) the Hill-coefficient (n), the concentration of the antibiotic at which selection is performed [C], and finally the concentration at which 50% of growth of a single population is inhibited (EC50). We used the parameters of Equation 1 from our previous study in which we determined the empirical fitness landscape of VIM-2 populations3.   In this study, using the correlations between the enrichment scores of each single point mutant of wtVIM-2 under ampicillin selection with the EC50 level of each single point mutant, the Hill-coefficient (n) was estimated to be 5. Using the DME of wtVIM-2 and the empirically obtained the fitness-phenotype-environment relationships, a population genetic simulations reflecting neutral drift experiments VIM-2 variants were conducted to obtain the physiological fitness landscape of antibiotic resistance in our model system. 

We first divided the phenotype space of EC50 values into n= 1,000 different states, ranging from EC50=0 to EC50=10,000. We assumed that a VIM-2 variant occupies one of these states and can transition from one to another by single point mutations. We then took an approach akin to Discrete Time Markov Chain simulations to simulate the evolutionary trajectory of VIM-2 in our experiments1. We constructed a 1,000 by 1,000 matrix that represents the transition probability matrix for transitions between different states, and simulated evolution of 1,000 Markov chains, each representing a VIM-2 variant in the population. All these Markov chains were initially in the same state and evolved to other states according to our transition probabilities. 
The transition probability between each two states (i, and j) is the product of two probabilities, one that represents mutations, P_mutation (i →j), and the other that represents selection, P_selection (i →j):

![Screen Shot 2023-02-28 at 9 31 06 AM](https://user-images.githubusercontent.com/6492012/221797097-7ef832bf-5d64-4203-97eb-d687d3413ea3.png)

(Equation 2)

We calculated P_mutation (i →j), i.e., the probability that VIM-2 transition from the state ith to jth with single point mutations, from experimentally determined DME distribution47,49. The second term, P_selection (i →j), shows the fixation probability of such mutations. To estimate this probability, we related EC50 to fitness (Equation 1), and calculated the selection coefficient of any arising mutation on the wtVIM-2 background as:

![Screen Shot 2023-02-28 at 9 31 49 AM](https://user-images.githubusercontent.com/6492012/221797621-00898d2c-cfcf-438b-a120-8ddc5d6251d1.png)

(Equation 3)

Here, [C] is the concentration of ampicillin in the media which takes the values of 10 µg/ml and 1000 µg/ml, corresponding to weak and strong selection experiments, respectively. We then used the probability of fixation of arising mutations in a monoclonal haploid population from the Kimura formula4:

![Screen Shot 2023-02-28 at 9 32 34 AM](https://user-images.githubusercontent.com/6492012/221797488-f0b495aa-b732-4624-b090-d4ce324935b1.png)

(Equation 4)

where Neff is the effective population size and is 104 in our simulations which is ~ equal to the number of colonies sampled from LB-agar plates in each generation. We started the simulations with 104 Markov chains all starting from a single state (i.e., initial EC50 value), and let these states evolve according to the transition probabilities and recorded their states after 100 rounds of mutation and selection.

(©2023 Pouria Dasmeh, Center for Human Genetics, Marburg University, dasmeh@staff.uni-marburg.de)
(Department of Chemistry and Chemical Biology, Harvard University, dasmeh@fas.harvard.edu)


