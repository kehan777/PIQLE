# PIQLE

<h2>Protein-protein Interface Quality Estimation with Deep Graph Learning of Multimeric Geometries</h2>

### Environment
PIQLE is tested on x86_64 Linux system in the following Python environment<br/>
1. python 3.6.13 <br/>
2. dgl 0.9.0 <br/>
3. torch 1.10.2 <br/>

### Download and installation
PIQLE can be downloaded and installed by typing
```
$ git clone https://github.com/Bhattacharya-Lab/PIQLE.git
$ cd PIQLE
$ python config.py
```

### Dependencies
<b>Multiple sequence alignment (MSA) generator:</b> we use DMPfold to generate MSAs which can be downloaded and installed from https://github.com/psipred/DMPfold

### Usage
To run PIQLE, type
```
$ python PIQLE.py
```
You will see the following output
```
usage: PIQLE.py [-h] [--tgt TARGETNAME] [--seq FASTAFILE] [--dec DECOYDIR]
                [--ch CHAINFILE] [--msa1 INMSA1] [--msa2 INMSA2]
                [--a3m1 INA3M1] [--a3m2 INA3M2] [--out OUTDIR]

Arguments:
  -h, --help        show this help message and exit
  --tgt TARGETNAME  Target name
  --seq FASTAFILE   Fasta file. IMPORTANT: Should be exactly in the same order
                    as the chain order in the PDB
  --dec DECOYDIR    Complex decoy directory
  --ch CHAINFILE    Chain file. Only one line with chain ids seperated by
                    space. IMPORTANT: Should be exactly in the same order as
                    the chain order in the PDB
  --msa1 INMSA1     MSA1: Multiple Sequence Alignment of chain 1
  --msa2 INMSA2     MSA2: Multiple Sequence Alignment of chain 2
  --a3m1 INA3M1     A3M of chain1
  --a3m2 INA3M2     A3M of chain2
  --out OUTDIR      Output directory
```
<b>Example commands to run PIQLE</b><br/><br/>
<b>IMPORTANT:</b> Please provide absolute path for all the input files including the output directory
```
python PIQLE.py --tgt example --seq absolute_path/git/example/example.fasta --dec example/decoys/ --ch absolute_path/git/example/example.chain --msa1 absolute_path/git/example/msa/example_A.aln --msa2 absolute_path/example/msa/example_B.aln --a3m1 absolute_path/git/example/msa/example_A.a3m --a3m2 absolute_path/example/msa/example_B.a3m --out absolute_path/example_out/
```
<b>Argument descriptions</b><br/><br/>
* --tgt TARGETNAME: name of the target without any extension <br/>
* --seq FASTAFILE: fasta file containing both of the sequences of the complex. As a reference please see ```example/example.fasta``` <br\>
