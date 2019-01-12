# Song Mashups and Mixes with DJ MARKOV
Created by Alex Gao, Andrew Kim, and Brian Yang

## What's in the repo:
1. A final report going into detail about the code, methodology, etc
2. Input and output midi files for you to groove to
3. The code itself, if you want to mess around and generate your own stuff
4. This readme, for a high-level summary of the project
5. An encouraging message from DJ Markov

## High level summary:
This project had two primary goals.

1. Generate original songs based off source material
2. Combine those original songs into a smooth and original mash-up/remix, simulating a DJ at a party

To accomplish the first goal, we parsed musical notes and calculated note transition frequencies from Midi files to generate discrete time Markov Chain (DTMC) representations for single songs. We extended on the vanilla DTMC approach with an n-gram featurization, simulating higher order Markov Chains and better allowing us to capture local dependencies and phrasings beyond just the previous note.

This gave us the starting point of original compositions to mix together for the second, more interesting, goal. This second goal involved two major barriers.

First, we needed to make sure that DJ MARKOV's mixes were smooth and connected rather than arbitrary concatenations of songs. The n-gram state space of the DTMC helped us accomplish this by allowing us to compare the similarity of longer musical phrases in songs. The precise value of the parameter 'n' also allowed DJ MARKOV to 'improvise' more or less in its compositions.

Second, we wanted DJ MARKOV to mix together similar-sounding compositions more frequently. To accomplish this, we created a continuous time Markov chain (CTMC) based on song similarity to mediate the transitions between different songs in the mix. This was made possible through the n-gram featurization; without it, we would not have had a musically valid way of representing song similarity (other ideas, such as stationary distribution analysis, were explored but didn't work). 

We implemented the higher order DTMC and CTMC models from scratch to solidify our understanding of the material. With this framework and some other clever music representations, DJ MARKOV was able to generate songs that were recognizably derived from the source material and mix them together (somewhat) smoothly. 

## An encouraging message from DJ MARKOV:
Life is a dance floor. Have fun with it :^)
<a href="http://www.youtube.com/watch?feature=player_embedded&v=Bjt7mDVCLtk
" target="_blank"><img src="http://img.youtube.com/vi/Bjt7mDVCLtk/0.jpg" 
alt="groove" width="240" height="180" border="10" /></a>

