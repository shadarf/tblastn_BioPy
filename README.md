# tblastn using BioPython

This code is provided as is, and there is no guarantee based on that, users take their responsibility of the terms of usage in publications.  
if you are using this code for a publication purpose please refernce Biopython as they developed the library, mentioning my name would also be nice :) 

by: Shad Arif Mohammed 22.01.2022, University of Sulaimani, college of science, Biology Department. 


The code has been tried using jupyter notebook, minor changes might be needed if you use other IDE or plain text files! 
How to run tblastn using biopython ? 
to be able to use biopython you would need to install it firts, using: 
```
!pip install biopython
```

# import required libraries
```
import pandas as pd
import numpy as np 
import Bio
from Bio.Seq import Seq   # import sequence object.
```
# check version of your biopython

mine is 1.79

```
print("Biopython version is %s"%Bio.__version__)
```
download a sample *.FASTA file from NCBI, iam using this sample for this example: 
dUTP diphosphatase [Lactobacillales] NCBI Reference Sequence: WP_000701992.1

https://www.ncbi.nlm.nih.gov/protein/WP_000701992.1

for the purpose of this walkthrough I named the file as dUTP_prot.fasta

# Explore the contents: 
```
from Bio import SeqIO 
for seq_record in SeqIO.parse("dUTP_prot.fasta", "fasta"):
    print(seq_record.id)
    print(repr(seq_record.seq))
    print(len(seq_record))
```
# Read the file from the fasta file and assign it to variable: 
```
fasta_string = open ("dUTP_prot.fasta").read(); fasta_string
```

# Run tblastn programme: 
```
from Bio.Blast import NCBIWWW
result_handle = NCBIWWW.qblast("tblastn", "nt", fasta_string); result_handle
```
# View the results: 
```
print(result_handle.read())
```
enjoy waiting for the outputs :) 

# Example output: 

![image](https://user-images.githubusercontent.com/50680034/150646665-6690ee03-3a25-419c-92a6-37a975f42c24.png)

![image](https://user-images.githubusercontent.com/50680034/150646672-80c55a4e-7bba-4aea-8d49-2b2acaa5c34e.png)
