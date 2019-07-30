# Deep-learning-project-milestone

This repository contains the code for the Digital Sudoku SatNet project and it primarily refers to the ICML 2019 SatNet paper [https://icml.cc/Conferences/2019/Schedule?showEvent=3947]
We played with the number of parameters and get the model output printed.

** **Background: What is SATNet?** **

SATNet is a differentiable (smoothed) maximum satisfiability (MAXSAT) solver that can be integrated into the loop of larger deep learning systems. Our (approximate) solver is based upon a fast coordinate descent approach to solving the semidefinite program (SDP) associated with the MAXSAT problem.


** **What do these experiments do? ** **

These experiments show that, by integrating the SATNet solver into end-to-end learning systems, we can learn the logical structure of challenging problems in a minimally supervised fashion. 
In particular, this file will show you some sample output of the SatNet-based mode to play 9×9 Sudoku (original and permuted) solely from examples.

** **The Sudoku Dataset** **

The 10K 9x9 Sudoku boards (9K test/1K train) used in this project was from [https://github.com/Kyubyong/sudoku]

** **The SatNet-based model** **

This model presents a differentiable optimization-based MAXSAT solver, namely an SDP relax-ation of MAXSAT,  and demonstrate  that SATNet can be integrated into larger deep network architecture for end toend training. 

In both forward and backward pass they use similar coor-dinate descent approach, which has similar fast convergence properties. This procedure enables the model to compute the desired gradients without needing to maintain intermediate Jacobians explicitly.

Here is a picture of the Forward Pass of the MAXSAT Layer.

![](images/model-architecture.png)
(Image Source: SATNet: Bridging deep learning and logical reasoning usinga differentiable satisfiability solver, Wang et al, ICML 2019)


** **Experiment procedure** **

After we trained the model with the training set, we test its performance with the test dataset.

First, the game started with an unsolved Sudoku, with several initially filled digits. An example from the test:
![](images/initialSudoku.jpeg)

After the initially unsolved Sudoku went through the SatNet-based model, we printed out the output to visualize the performance of the model. 

For illustration, we painted the model generated digits in green and red. 

If the digits are correctly generated, we painted it green. 
If the digits are wrong, we painted it red. 

We checked the result up until 20 epochs for the first sample in our test set, and found that starting from 4 until 20 epochs, the model does a perfect job in generating the right answer. 

For convenience, we decided to attach only the first 4 epochs results for the first sample in our test set as a demonstration.

![](images/epoch1.jpeg)

![](images/epoch2.jpeg)

![](images/epoch3.jpeg)

![](images/epoch4.jpeg)
