
# DESCRIPTION
This project delves into the stochastic behavior of primary bets in craps using cutting-edge methods like reinforcement learning, value iteration, and probabilistic model checking. The dissertation, scoring 84% (A3), provides a solid introduction to these techniques and serves as a valuable resource for future analysis.

Implemented through meticulously crafted PRISM source code, the project explores the complexities of craps betting, revealing insights into the unpredictable nature of key bets. The findings offer strategic decision-making support and a deeper understanding of the game's dynamics.

This project has equipped me with indispensable tools to facilitate the development of valuable analysis techniques in future endeavors. By exploring the stochastic behavior of primary bets in craps through advanced methodologies such as reinforcement learning, value iteration, and probabilistic model checking, I have gained a solid foundation for conducting rigorous analyses.



# HOW TO RUN

Please refer to the PRISM manual on how to install PRISM on your machine: http://www.prismmodelchecker.org.

Once PRISM is installed, follow this link to open up the PRISM GUI: https://www.prismmodelchecker.org/manual/RunningPRISM/StartingPRISM

Once the GUI has opened, feel free to analyse the files for any more interesting trends. Also feel free to add more analysis files for different bets in the craps game! See the File structure section (down below) to identify where the prism and props files are located.

If you want to visualise the optimal strategies, please go to the command line and use the command below accordingly (depending on the file and props you want to analyse):

prism <"prism file path"> <"props file path"> -const <"const declarations"> -prop <"number of the prop you want to use to analyse"> -s -exportadvmdp tmp.tra -exportstates tmp.sta -exportlabels tmp.lab

The command above creates the individual states, lab and transition files. Please then use this command below to create the optimal strategy tmp file. Bear in mind, you can rename tmp to anything.:

prism -mdp -importtrans tmp.tra -importstates tmp.sta -importlabels tmp.lab -exporttransdotstates tmp.dot -fixdl

After the optimal tmp file is used, please use the dotview file command:

dotview tmp

This command will create the PDF, where you can visualise the optimal strategy and find any unique and interesting patterns.

# File Structure

The following shows the file structure of the Modelling and Analysis with the Main bets in Craps Project. Each section will state the file name and what it is for.

# DTMC Example Folder

This main folder includes all the files created when learning how to create DTMC's in PRISM.

### DTMC

This file holds the DTMC example created in the process of learning PRISM.

### DTMC properties

This file holds the DTMC properties to analyse the DTMC example model.

# MDP Example Folder

This main folder includes all the files created when learning how to create MDP's in PRISM.

### MDP.prism

This file holds the MDP example when in the process of learning PRISM.

### MDP-props.props

This file holds the MDP properties to analyse the MDP example model.

# Craps Folder

This main folder holds all the files used for the individual and combined analysis of the main bets in craps.

## DTMC's Folder

All files in this section hold the pass line and don't pass line DTMC's. As well as this, it holds the individual analysis for taking odds and laying odds.

### craps(Pass-Line DTMC).prism

This file holds the pass line DTMC.

### craps(pass DTMC odds-4-10).prism

This file holds the pass line odds 4 & 10 DTMC.

### craps(pass DTMC odds-5-9).prism

This file holds the pass line odds 5 & 9 DTMC.

### craps(pass DTMC odds-6-8).prism

This file holds the pass line odds 6 & 8 DTMC.

### craps(dontpass DTMC).prism

This file holds the don't pass line DTMC.

### craps(dont pass DTMC odds-4-10).prism

This file holds the don't pass line odds 4 & 10 DTMC.

### craps(dontpass DTMC odds-5-9).prism

This file holds the don't pass line odds 5 & 9 DTMC.

### craps(dontpass DTMC odds-6-8).prism

This file holds the don't pass line odds 6 & 8 DTMC.

## MDP's Folder

All files in this section hold the pass line and don't pass line MDP's as well as the Odds MDP for Laying Odds with point values 6 and 8, and Taking Odds with 5 and 9.

### crapsMDP.prism

This file holds the pass line and don't pass line MDP.

### crapsMDPodds.prism

This file holds the taking odds and laying odds MDP with point values 6 and 8, and 5 and 9.

## MDP-Probability-Step-Verification Folder

### ProbVerificationEvenSteps.prism

This file holds the verification required for the probabilistic reachability optimality criteria (breaking even). This is specific to craps sessions with an even number of games, and the optimal result is compared to the optimal results of the crapsMDP.prism file (located in the MDP folder).

### ProbVerificationOddSteps.prism

This file holds the verification required for the probabilistic reachability optimality criteria (breaking even). This is specific to craps sessions with an odd number of games, and also is compared to the optimal results of the crapsMDP.prism file (located in the MDP folder).

## Property-Specification Folder

### PropertySpecification.props

This file holds the properties file to specify the optimality criteria for all models (probability of breaking even/profit and expected reward).

### onegamechances.props

This file holds the properties file to identify the probability of winning, losing or drawing a game of craps with the Pass Line and Don't Pass Line bets. Bear in mind, the push (draw) property is only used for the Don't Pass Line bet.

## MDP-Full-Odds-Attempt(FutureWork)

In this folder, there are all the files for the attempt with the analysis for the MDP with all odd point values with Taking Odds and Laying Odds. This is related to the future work section.

# Pass-dontpass-mdp-reward-dot-graphs Folder

In this folder, there are many examples of the synthesised optimal policy dot files, relative to maximising the expected reward for the crapsMDP.prism file (located in the CRAPS MDP folder).

# Pass-dontpass-mdp-probability-dot-graphs Folder

In this folder, there are many examples of optimal policy dot files, relative to maximising the probabilistic reachability for breaking-even, for the crapsMDP.prism file. There are examples which show both odd and even steps.

# Taking-Laying-Odds-MDP-dot-graphs Folder

In this folder, there are many examples of optimal policy dot files, relative to maximising the expected reward for the crapsMDPodds.prism file (located in the CRAPS MDP folder).

#Taking-Odds-DTMC-Graphs Folder
This main folder highlights the individual DTMC analysis of taking odds with different odds combinations.

## Doubling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 1x odds for all odds combinations.

## Doubling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 3x odds for all odds combinations.

## Tripling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 1x odds for all odds combinations.

## Tripling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 3x odds for all odds combinations.

#Laying-Odds-DTMC-Graphs Folder
This main folder highlights the individual DTMC analysis of laying odds with different odds combinations.

## Doubling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 1x odds for all odds combinations.

## Doubling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 3x odds for all odds combinations.

## Tripling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 1x odds for all odds combinations.

## Tripling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 3x odds for all odds combinations.

# Taking-Odds-Laying-Odds-Combined-Graphs Folder

This main folder highlights the comparison of each odds point combination. Each graph file shows the probabilistic reachability comparison for laying odds and taking odds 4 & 10 in one seperate file, 5 & 9 in one seperate file and 6 & 8 in one seperate file. This is done for both 1x and 3x odds.

## Doubling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 1x odds.

## Doubling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for doubling the initial balance with 3x odds.

## Tripling-Initial-Balance(1xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 1x odds.

## Tripling-Initial-Balance(3xodds) Folder

This contains all the probability reachability graphs for tripling the initial balance with 3x odds.

#Taking-Odds-DTMC-Combined-Graphs Folder

## Doubling-Initial-Balance(1xodds)

This contains the combined graphs showing the trends in the "doubling the initial balance" files in the Taking-Odds-DTMC-Graphs Folder. So therefore this file shows the probabilistic reachability trends for the DTMC taking odds analysis for odds 4 & 10, 5 & 9 and 6 & 8, in 1 graph. This graph represents the players probabilistic chances of doubling their initial balance at 1x odds.

## Tripling-Initial-Balance(3xodds)

This contains the combined graphs showing the trends in the "tripling the initial balance" files in the Taking-Odds-DTMC-Graphs Folder. So therefore this file shows the probabilistic reachability trends for the DTMC taking odds analysis for odds 4 & 10, 5 & 9 and 6 & 8, in 1 graph. This graph represents the players probabilistic chances of tripling their initial balance at 3x odds.

#Laying-Odds-DTMC-Combined-Graphs Folder

## Doubling-Initial-Balance(1xodds)

This contains the combined graphs showing the trends in the "doubling the initial balance" files in the Laying-Odds-DTMC-Graphs Folder. So therefore this file shows the probabilistic reachability trends for the DTMC laying odds analysis for odds 4 & 10, 5 & 9 and 6 & 8, in 1 graph. This graph represents the players probabilistic chances of doubling their initial balance at 1x odds.

## Tripling-Initial-Balance(3xodds)

This contains the combined graphs showing the trends in the "tripling the initial balance" files in the Laying-Odds-DTMC-Graphs Folder. So therefore this file shows the probabilistic reachability trends for the DTMC laying odds analysis for odds 4 & 10, 5 & 9 and 6 & 8, in 1 graph. This graph represents the players probabilistic chances of tripling their initial balance at 3x odds.

#Dont-Pass-Line-DTMC-Probability-Graphs Folder
In this folder, there are two folders showing the probabilistic reachability graphs for breaking even and generating profit only, with different buy in and initial balance combinations. All files show the probabilistic trends for the Dont Pass Line DTMC.

# Pass-Line-DTMC-Probability-Graphs Folder

In this folder, there are two folders showing the probabilistic reachability graphs for breaking even and generating profit only, with different buy in and initial balance combinations. All files show the probabilistic trends for the Pass Line DTMC.

# Taking-Odds-Expected-Reward-Combined-Graphs Folder

In this folder, there is the graph for the expected reward for Taking odds with point values 4 and 10, 5 and 9, and 6 and 8 in a single graph.

# Laying-Odds-Expected-Reward-Combined-Graphs Folder

In this folder, there is the individual graph file (.gra) for the expected reward for Laying odds with point values 4 and 10, 5 and 9, and 6 and 8 in a single graph.

# Dotview

This is the executable file to convert the synthesised policies into visual format (PDF).
