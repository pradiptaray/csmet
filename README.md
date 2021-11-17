# csmet

******************************
******************************
0. CONTENTS
******************************
******************************

0. CONTENTS
I. TERMS OF USAGE
II. ADDRESS AND WEBPAGE
III. COMPILATION AND RUNNING
IV. SETTINGS FILE 
V. SUBSIDIARY INPUT FILE FORMAT DESCRIPTIONS
VI. OUTPUT FILES FOR CSMET


******************************
******************************
I. TERMS OF USAGE
******************************
******************************

CSMET is provided as a free software for academic and educational purposes. For other uses,
please contact epxing@cs.cmu.edu . CSMET is provided as-is and usage of the software is 
based on the understanding that the software is provided as-is without warranties or 
conditions of any kind. For derivative works, and redistribution, please contact 
epxing@cs.cmu.edu

Attribution is required if CSMET is used for research purposes. We would also be happy to hear
feedback from you, please send feedback to epxing@cs.cmu.edu or suyash@cs.cmu.edu or pray@cs.cmu.edu

******************************
******************************
II. ADDRESS AND WEBPAGE
******************************
******************************

Address :

SAILING LAB,
c/o E. P. Xing,
School of Computer Science,
Carnegie Mellon University,
5000 Forbes Avenue,
Pittsburgh, PA 15213

Webpage :

http://www.sailing.cs.cmu.edu/csmet/


******************************
******************************
III. COMPILATION AND RUNNING
******************************
******************************

To compile the code, simply type

 g++ csmet.cpp -o csmet -lm

at the terminal. Use the csmet.cpp and other .cpp, and .c files obtained in the /src directory

If you want to run CSMET on our simulation data, we have a code which uses the same algorithm, but is streamlined for performance
optimization on simulated data based on slightly different input formats. Please compile the csmet.cpp and other .cpp and .c files 
you would find in the /src/simulation directory

To run the program , type

 ./csmet [test|train] path_of_settings_file

at the terminal


******************************
******************************
IV. SETTINGS FILE
******************************
******************************

The settings file specifies which files are needed in the training and test phases.
Please write the settings file with care, as wrong path names or file formats may cause
the program to fail silently.

A sample settings file looks like this :

For a training run :

ATREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outall.tree
MTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outmtf.tree
BTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outbkg.tree
FTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outfun.tree
APARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outall.params
MPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outmtf.params
BPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outbkg.params
FPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outfun.params
ALIGNFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/train.fasta
TRUTHFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/train.truth
EMOUTFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/trainemissions.txt
TRANSITIONFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/transitions.txt
OUTFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/trainfullmat.txt
SUMMARYFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/trainsummary.txt
MOTIFFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/train.mtf
REVMOTIFFILE	/usr1/pray/cismet/src/experreal/ptcau/seq4/cismet_out/test.mtfr

For a testing run :

MTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outmtf.tree
BTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outbkg.tree
FTREEFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outfun.tree
MPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outmtf.params
BPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outbkg.params
FPARAMFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/outfun.params
ALIGNFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/test.fasta
EMOUTFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/testemissions.txt
TRANSITIONFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/transitions.txt
OUTFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/testfullmat.txt
SUMMARYFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/testsummary.txt
TRUTHFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/test.truth
MOTIFFILE	/usr1/pray/CSMET/src/training_exper_new/pt5/seq47/CSMET_out/test.mtf
REVMOTIFFILE	/usr1/pray/cismet/src/experreal/ptcau/seq4/cismet_out/test.mtfr

******************************
******************************
V. SUBSIDIARY INPUT FILES
******************************
******************************


The following are descriptions of the subsidiary input files :

For training phase only :
=========================
ATREEFILE 
Input file for training phase
Path of file containing the ML tree estimated over entire data during pre processing in Newick format, in unrooted binary tree form. 

APARAMFILE
Output file for training phase
Path of file containing ML tree parameters for the tree on all nucleotides

For training and testing phase :
================================

MTREEFILE 
Path of file containing rooted binary motif tree file in Newick format. 
Output file for training phase
Input file for test phase
Path of file containing the ML tree estimated over motif sites during pre processing in Newick format, in rooted binary tree form. 

BTREEFILE 
Path of file containing rooted binary background tree file in Newick format. 
Input and output file for training phase
Input file for test phase
This path is for the ML tree estimated on background sites.
For training phase, the tree is read into the program as an unrooted Newick format tree, and printed out again as a rooted Newick format tree.
For test phase, the tree is read in as a rooted Newick format tree

FTREEFILE 
Path of file containing rooted binary annotation tree file in Newick format. 
Output file for training phase
Input file for test phase
Path of file containing the ML tree for functional annotations in Newick format, in rooted binary tree form. 

MPARAMFILE
Output file for training phase
Input file for test phase
Path of file containing the ML parameters of the ML tree for motif nucleotides.
 
BPARAMFILE
Output file for training phase
Input file for test phase
Path of file containing the ML parameters of the ML tree for background nucleotides.

FPARAMFILE
Output file for training phase
Input file for test phase
Path of file containing the ML parameters of the ML tree for functional annotations.

ALIGNFILE
Input file for training phase
Input file for test phase
MultiFASTA file specifying the aligned sequences. The ordering for aligned sequences need to correspond 
to an inorder traversal of each of the three tree files. 

EMOUTFILE
Output file for training phase
Output file for test phase
This file contains block emission probabilities used as input for the HMM for each aligned block in the sequence. In the training phase, it simply contains the emission parameters for inference run on the training sequence. In test phase, it contains the emission probabilities for inference
run on the test sequence as log likelihoods.

TRANSITIONFILE
Input file for training phase
Input file for test phase
Please note that parameters for the transition probability matrix for the HMM are not estimated inside the CSMET code but taken care of during 
preprocessing. Log probabilities of the transitions are provided.

OUTFILE
Output file for training phase
Output file for test phase
This file prints out the predicted functional annotation for each species for each site. The indicator variables vary by species 
inside a row, and by site across rows. For training phase, this shows the predictions on the training sequence, and for test phase it shows the 
predictions on the test sequence

SUMMARYFILE
Output file for training phase
Output file for test phase
This file prints out the predicted functional annotation  for the common ancestor for each site - this is the same as the prediction of the state of the HMM. 

TRUTHFILE
Input file for training phase
Input file for evaluator in test phase
This file contains the gold standard functional annotation for each species. It is of the same format as OUTFILE, the prediction file for functional
annotation

MOTIFFILE
Input file for training phase
Input file for evaluator in test phase
This file contains the gold standard positional location for each motif block on the forward strand. It also contains the length of the aligned sequence, and the width of the motif.

REVMOTIFFILE
Input file for training phase
Input file for evaluator in test phase
This file contains the gold standard positional location for each motif block on the reverse strand. It also contains the length of the aligned sequence, and the width of the motif.

************************************************************
************************************************************
V. INPUT / INTERMEDIATE FILE FORMAT DESCRIPTIONS
************************************************************
************************************************************


NEWICK FORMAT TREE FILES
========================

Sister lineages are parenthesized and branch lengths of the branch from which a node is hanging is specified after the parenthesis or sequence 
name as a floating point number. The in order traversal of all the tree files should match with each other and should produce the same ordering 
as the sequence of species in the multiple alignment from top to bottom.

No line breaks or new lines should be present in the files. No whitespaces should be present preferably. A tree of the form 


                            a
                       ----------- Species1
                  b    | 
          -------------+
          |            |       d
----------+            --------------- Species2
          |        c
          ------------------- Species3

would be represented as a rooted tree as :
((Species1:a,Species2:d):b,Species3:c):0;

and as an unrooted tree as :
(Species1:a,Species2:d,Species3:x):0;

where x = b + c


Example of unrooted tree :
(((((sequence11: 0.040780,(sequence10: 0.014272,sequencen9: 0.004583): 0.017864): 0.023027,(sequencen8: 0.051451,sequencen7: 0.039911): 0.027026): 0.101963,sequencen6: 0.199530): 0.139373,(sequencen5: 0.022191,sequencen4: 0.014206): 0.244400): 0.388700,(sequencen2: 0.210565,sequencen3: 0.128102): 0.039597,sequencen1: 0.202271):0.0;

Example of rooted tree :
(((sequencen2:0.210565,sequencen3:0.128102):0.039597,sequencen1:0.202271):0.194350,((((sequence11:0.040780,(sequence10:0.014272,sequencen9:0.004583):0.017864):0.023027,(sequencen8:0.051451,sequencen7:0.039911):0.027026):0.101963,sequencen6:0.199530):0.139373,(sequencen5:0.022191,sequencen4:0.014206):0.244400):0.194350):0.000000;


MULTIFASTA FILES
================
The sequence for a single species in the 
alignment has to be present in a single line after the species name is specified with a ">" on the line before it. 
Characters allowed in the input alignment are a,t,g,c,A,T,G,C,N,n and - . - stands for gaps, and N / n for any character.
All sequences should have the same number of characters, and the entire sequence for a single species should be present on the same line.
The ordering for aligned sequences need to correspond to an inorder traversal of each of the three tree files.


For eg,
>sequence10
CATGACCGCTTCAATACCNNNNNNTGCTTCACAG
>sequence9
CATGAC----TCAATATCAAGCGTTGTTTCACAG
>sequence8
CATGACCGCTTCAATATCAAGCGTTGTTTCACAG
>sequence7
CATGACCGCTTCAATACCAGGCGTTGCTTCTCAG
>sequence6
CATGATCGCTTCAATACCAGGCGTTGCTTCACAG
>sequence5
CACGGCATTCTCAGGACCAAGTTTTACATTATGG
>sequence4
CGTGACGATTCCAGCGCTAATGGTTACATCATTG
>sequence3
CATGACGATTCCAGCGCTAATGGTTACCTCATTG
>sequence1
TGTGGTGGTCATAGTAACGACCACTACGGCGACT
>sequence2
AATGGTGGTTATGGTAAGGACCACTTTGGGGAGC
>sequence0
TATGATTGTCCTGGTAACAACCACTACGACTAGT



TREE PARAMETER FILES
====================
Tree parameter files are ASCII files with whitespace separated parameter values. 

For eg,
0.20 0.25 4 11 0.6 0.3 0.05 0.05  0.6 0.3 0.05 0.05

<transition/transversion ratio> <mutation rate> <number of alphabets which evolve over the phylogeny> <number of species> 
<Prob of A at Position 1> <Prob of T at Position 1> <Prob of G at Position 1> <Prob of C at Position 1>
<Prob of A at Position 2> <Prob of T at Position 2> <Prob of G at Position 2> <Prob of C at Position 2>
...


GOLD STANDARD FUNCTIONAL ANNOTATION FILE
========================================

This file contains the gold standard functional annotation indicator variable for each species for each site. The indicator variables vary by species inside a row, and by site across rows. 1 indicates presence of motif and 0 indicates absence of motif.

eg for 5 species and an alignment of 17 sites (10 blocks for a motif of size 8), the annotation would be of the form :
0 0 0 0 0
1 1 0 0 1
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 1 1 0
0 0 0 0 0
0 0 0 0 0

where species 1,2, and 5 are predicted to have a motif starting at site 2, and species 3 and 4 
are predicted to have a motif starting at site 8.


MOTIF LOCATION FILES
====================
These are of the form of whitespace separated integers specifying the length of the alignment, width of the motif, and index of the starting 
position for each of the motifs. The starting positions are 0-indexed with respect to the start (i.e. a motif starting at the first site of the alignment would have a position of "0", not "1". Motif files specifying motifs on reverse strands contain the indices of the ending positions of 
the motifs.

eg For an alignment containing 5 instances of a motif of length 8 in an alignment of 300 nucleotides, the motif file would look like
300
8
21
142
66
45
278


i.e. the format is as follows 
<length of alignment>
<width of motif>
<position of instance 1 of motif>
<position of instance 2 of motif>
<position of instance 3 of motif>
...

******************************
******************************
CSMET OUTPUT FILES
******************************
******************************


Functional Annotation Predictions
=================================
Name : As specified by OUTNAME in the settings file
FOrmat : This file prints out the predicted functional annotation indicator variable for each species for each site. The indicator variables vary by species inside a row, and by site across rows. 1 indicates presence of motif and 0 indicates absence of motif.

eg for 5 species and an alignment of 17 sites (10 blocks for a motif of size 8), the annotation would be of the form :
0 0 0 0 0
1 1 0 0 1
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 0 0 0
0 0 1 1 0
0 0 0 0 0
0 0 0 0 0

where species 1,2, and 5 are predicted to have a motif starting at site 2, and species 3 and 4 
are predicted to have a motif starting at site 8.

Summary State Predictions
=========================
Name : As specified by SUMMARYFILE in the settings file
Format : It prints out the ML prediction for the functional annotation of the common ancestor for each aligned block.
1 indicates starting position of motif on the forward strand, 2 indicates ending position of motif on the reverse strand, and 
0 indicates absence of a motif.

eg for 5 species and an alignment of 17 sites (10 blocks for a motif of size 8), the annotation would be of the form :
0 1 0 0 0 0 0 0 2 0 0

which represents that the common ancestral sequence possessed a motif on the forward strand at site no. 2,
and on the reverse strand on site no. 8.

