
# for NIPS review

Collaborative Similarity Embedding

# Developed Environment
- g++ > 4.9 (In macOS, it needs OpenMP-enabled compilers. or try installing lateast version of gcc)

# Compilation
```
$ git clone https://github.com/cnclabs/codes.cse.rec
$ cd codes.cse.rec
$ make
```

# Task
Given a network input **net.txt**:
```txt
userA itemA 3
userA itemC 5
userB itemA 1
userB itemB 5
userC itemA 4
```
and a input for specifying the fields **field.txt**:
```
userA u
userB u
userC u
itemA i
itemB i
itemC i
```
The model learns the representations of each vertex:
```
6 5
userA 0.0815412 0.0205459 0.288714 0.296497 0.394043
itemA -0.207083 -0.258583 0.233185 0.0959801 0.258183
itemC 0.0185886 0.138003 0.213609 0.276383 0.45732
userB -0.0137994 -0.227462 0.103224 -0.456051 0.389858
itemB -0.317921 -0.163652 0.103891 -0.449869 0.318225
userC -0.156576 -0.3505 0.213454 0.10476 0.259673
```

# Command Line Interface
Directly call the execution file to see the usage like:
```
./cli/nemf   # for RATE-CSE
./cli/nerank $ for RANK-CSE
```
then you will see the options description like:
```
[CSE]
        command nerank interface for proNet-core

Options Description:
        -train <string>
                Train the Network data
        -save <string>
                Save the representation data
        -field <string>
                Field data
        -dimensions <int>
                Dimension of vertex representation; default is 64
        -sample_times <int>
                Number of training samples *Million; default is 10
        -walk_steps <int>
                Walk steps; default is 5
        -threads <int>
                Number of training threads; default is 1
        -alpha <float>
                Init learning rate; default is 0.025
Usage:

[NERANK]
./nerank -train net.txt -field field.txt -walk_steps 2 -save rep.txt -dimensions 64 -sample_times 10 -alpha 0.025 -threads 1
```

