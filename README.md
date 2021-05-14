# PepOcalypse
A new module for proteomics' pipelines

### * The module would be released upon the publication.

This repository contains the implemention of a new module for proteomics pipelines. Current methods search raw MS/MS spectrums against a theoretical database of peptides to finally identify proteins in that sample. One of the most important sources of error is that there are non-unique peptides that could match to more than one protein which makes protein identification step error prone. PepOcalypse removes non-unique peptides from output of search engine to eliminate this source of error.

This module currently works with [Trans-Proteomic Pipeline (TPP)](http://tools.proteomecenter.org/software.php) in which the first step is using the Comet proteomics search engine. After this step the other parts of the pipeline are carried out by PepOcalypse module.

PepOcalypse uses [pepx](https://github.com/calipho-sib/pepx) to check for uniqueness of each peptide. This module is fully automated and the operator should only specify the folder of Comet output and the destination for final results. Coedes are written in Python 3 and the wrapper is written in Bash.

Tasks that PepOcalypse does are:

1. Extract peptides (target and decoy) from Comet output
2. Check the uniqueness of each peptide (target and decoy seperatly)
3. Remove non-unique peptides from Comet output file
4. Run ProteinProphet and ProteinProphet (from TPP) on edited files
5. Extract and filter proteins from ProteinProphet output
