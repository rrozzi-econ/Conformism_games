# Conformism_games
SImulations for "Conformism across games"

This code refers to simulations of Hawk-Dove games where more and less intelligent agents interact. This project is part of a chapter of my PhD thesis.

The code part must be insert in the dedicated part of NetLogo, while the in the interface part I insert the commands to setup the interface functional to the code. Other plots and monitors are optional.

The general aim of the code is calculate the composition of the population (how many non intelligent players and how many intelligent ones) and their strategies after they interact repeatedly over Hawk-Dove games. At each period, with a probability (G_1_like) a Hawk-Dove with mild conflict is played and with another probability a Hawk-DOve with harsh conflict is played. A first process determines how non intelligent players and intelligent players behave: non intelligent players conform to what the majority is doing at a given step, while intelligent players best reply at each step to the current distribution of strategies (this procedures are called respectively, conform and playMBR). Importantly, intelligent players distinguish between the two types of games (that s they adapt their strategy depending on whether there is a Hawk-Dove with mild or harsh conflict), while non intelligent ones only react to changes in the distribution of strategies.

As usually done in evolutionary game theory models, only a small fraction of players revise their strategy at each step, the others keep playing the strategy they were playing the previous period (such an assumption is called inertia, and it is specified in the code by the global prob-revision). Also in line with standard works in the literature, I assume that agents play randomly occasionally (mist-prob). In the so called evolutionary process, I evaluate the fitness of each type of player over the last "fit-mem" periods: the type of players that have the highest fitness replicates of 100 units, while the other decreases of 100 units. Importantly, since playing intelligently requires an effort, intelligent players pay a cognitive cost in their fitness (kappa). The assessment of the fitnesses happens each 100 periods, but one can choose different length, as long as the assessment of fitnesses happens at a slower rate than the change of strategies (that happens each period). This assumption is justified by the fact that changing the way a player behave requires a further cognitive step than just changing their strategy.

Further details on the model can be find in the paper.

*******************************************************************************

For "Conformism across games" readers

Note 1: the code was originally thought for a conflict game, but in the current version of the paper titled "Conformism across games", the game studied analytically could both be of conflict or anti-coordination. Results still hold also by considering an anit-coordination game.

Note 2: the payoffs were originally thought for an Hawk-Dove game with payoffs c=1 and v variable. Specifically, the code allows for studying the results when at each period there is a probability "p" that a Hawk-Dove game with harsh conflict is played (1-p is the probability of playing a mild conflict Hawk-Dove game). Coherently, in the code I refer to v_1 as the value for v in the harsh conflict game and v_2 as the value for confrlict in the mild conflict game. For the simulations, in the paper, I used v_1 = 0.6 and v_2 = 0.4. These values are equivalent to using p = 0.6 and q = 0.1 or 0.3 (as described in the paper). It is sufficient to set the probability of each game equal to 0 or 1 at every period constantly throughout the simulation to obtain the simulations for a game with "a=0.4" or $a=0.6$ (adopting the notation in "Conformism across games").
