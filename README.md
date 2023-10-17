# Protein-Secondary-Structure-using-RNN-and-LSTM
Protein secondary structure can be calculated based on its atoms' 3D coordinates once the protein's 3D structure is solved using X-ray crystallography or NMR. Commonly, DSSP is the tool used for calculating the secondary structure and assigns one of the following secondary structure types (https://swift.cmbi.umcn.nl/gv/dssp/index.html) to every amino acid in a protein.

C: Loops and irregular elements (corresponding to the blank characters output by DSSP)
E: β-strand
H: α-helix
B: β-bridge
G: 3-helix
I: π-helix
T: Turn
S: Bend
However, X-ray or NMR is expensive. Ideally, we would like to predict the secondary structure of a protein based on its primary sequence directly, which has had a long history. A review on this topic is published recently, Sixty-five years of the long march in protein secondary structure prediction: the final stretch?.

For the purpose of secondary structure prediction, it is common to simplify the aforementioned eight states (Q8) into three (Q3) by merging (E, B) into E, (H, G, I) into E, and (C, S, T) into C. The current accuracy for three-state (Q3) secondary structure prediction is about ~85% while that for eight-state (Q8) prediction is <70%. The exact number depends on the particular test dataset used.

#DATASET

#Dataset LINK   https://www.kaggle.com/datasets/alfrandom/protein-secondary-structure

The main dataset lists peptide sequences and their corresponding secondary structures. It is a transformation of https://cdn.rcsb.org/etl/kabschSander/ss.txt.gz downloaded at 2018-06-06 from RSCB PDB into a tabular structure. If you download the file at a later time, the number of sequences in it will probably increase.

Description of columns:

pdb_id: the id used to locate its entry on https://www.rcsb.org/
chain_code: when a protein consists of multiple peptides (chains), the chain code is needed to locate a particular one.
seq: the sequence of the peptide
sst8: the eight-state (Q8) secondary structure
sst3: the three-state (Q3) secondary structure
len: the length of the peptide
has_nonstd_aa: whether the peptide contains nonstandard amino acids (B, O, U, X, or Z).

#I tried rmsprop optimizer but it is giving only 72% accuracy so i tried "adam" its giving 96% accuracy.


