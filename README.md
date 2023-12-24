# 2-bit-Counter-for-branch-prediction

The aim of this project is to create a 2-bit saturating up-down counter (referred to as Automaton A2 in the paper) and another variation, Automaton A3. Additionally, the project involves evaluating and contrasting the performance of these two distinct states in a two-level branch prediction system. This initiative also serves to acquaint individuals with zsim, a Pin-based x86-64 simulator that models an out-of-order issue processor with a comprehensive memory hierarchy designed for large-scale multicore architectures.

A2 is used in zsim already, we need to add codes to implement the A3 state diagram. We will need to modify ooo core.h to implement the state diagram

<img width="503" alt="image" src="https://github.com/Rajat5991/2-bit-Counter-for-branch-prediction/assets/154459536/15084541-bb70-427d-b0c4-84f22a7265e9">


Paper Link: https://dl.acm.org/doi/pdf/10.1145/146628.139709

# System Requirement

Linux operating system is required in order to use the zsim. Do not use Cygwin, Mac OS X is not supported.

# Environemnt setup
Everytime you want to build or run zsim, you need to setup the environment variables first.

$ source setup_env

# Compile zsim

$ cd zsim

$ scons -j4

# Launch a test to run

./build/opt/zsim tests/simple.cfg

# Run the following benchmarks using ZSim
   blackschoels, bodytrack, canneal, dedup, fluidanimate, freqmine, streamcluster, swaptions, x264
   1. Use branchpredictorscript to run the benchmarks

      Note: The config files and runscript must be in the casim/zsim.

      $ ./branchpredictorscript <benchmark> <automaton>

      Example: $ ./hw2runscript blackscholes A2
   2. Check the results in outputs directory (zsim.out)

