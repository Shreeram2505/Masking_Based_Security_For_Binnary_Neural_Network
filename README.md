This repo contains the RTL generator codes and its respective RTL codes and the test benches for testing.

#Three kinds of masked  BNN model generators have been created
1) Iterative Model ( Reuses the same adder trees and the lut components for the computations of ball the layers which is controlled by a controller): Reduced Area but bad Througput
2) Pipellined Model ( Uses unique adder tree and components for the respective layer computations ) :Faster Througput but Huge Area overhead
3) Pipellined Model  without B2A ( Uses unique adder tree and components for the respective layer computations  without the use of binary to arithmetic converters ) :Faster Througput but Huge Area overhead


RESULTS FROM SYNOPSYS DESIGN COMPILER : ALL GENERAL MODEL COMPARISION

                         area overhead:             data arrival time (ns): data required time (ns):      total power :

iterative1: compile ultra: 20030.863664                 2.46                     10                         2.30e+03
            compile: 28235.3675                         4.51                     10                         2.74e+03

iterative2: compile ultra: 82117.922495                 2.97                     10                        9.58e+03
            compile: 115145.279871                      4.64                     10                        1.13e+04

iterative3:  compile ultra: 328551.755885               3.06                     10                        3.93e+04
             compile: 459013.847446                     4.99                     9.96                      4.54e+04

------------------------------------------------------------------------------------------------------------------------------
pipellined1: compile ultra: 20117.579645               2.42                      9.96                       2.74e+03
             compile: 28496.31348                      4.16                      9.96                       3.42e+03

pipellined2: compile ultra: 83624.014498               2.57                      9.96                       1.18e+04
             compile: 118005.046007                    4.47                      9.96                       1.46e+04

pipellined3: compile ultra: 343536.333655              2.69                      9.96                        4.09e+04
             compile:481591.927634                     4.75                      9.96                        6.03e+04
----------------------------------------------------------------------------------------------------------------------------------
unmasked 1: compile ultra: 4992.021915                 2.16                      9.96                        649.550
            compile:      5928.607904                  2.12                      9.96                        722.941

unmasked 2: compile ultra: 21568.609610               2.36                      9.96                         2890.00
             compile: 25247.123564                    2.34                      9.96                         3190.00

unmasked 3: compile ultra: 89715.946325               2.47                      9.96                         1.21e+04
             compile:104471.232147                    2.63                      9.96                         1.34e+04

------------------------------------------------------------------------------------------------------------------------------
Difference between Iterative And pipellined :

increase in area percentage:         decrease in data arrival percentage:

1) 0.4329  0.924                     1.62    7.76
2) 1.834   2.48                      13.46   3.66
3) 4.56    4.91                      12.09    4.80

----------------------------------------------------------------------------------------------------------------------------
