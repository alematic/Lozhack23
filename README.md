# Lozhack23

##Idea: Create a model to see whether a chemical moiety would be uptaken by different cell types according to transporter expression.
For a drug to act, it needs to go up to its therapeutic target. Some of those target are inside the cells, in this case the drug needs to be uptaken by the cell to reach its target. To go within a cell, two paths are available: through a transporter or directly through the plasma membrane by diffusion. Transporters are not present on all cells (liver cells, kidney cells ...) and their presence can be determinant for drug effect. These transporters and their expression is different between mice and human, making some successful pre-clinical studies fail when passing to humans.The model would be to combine database of differents transporters (e.g. https://transportal.compbio.ucsf.edu/index/ ), models of drug-protein interactions to predict what chemical would be the target of what transporter, and cell-type/tissue RNA-sequencing data in human ( https://www.ebi.ac.uk/gxa/home) to know what cells would uptake the chemical agent. 

## Actual Achievement
We built a program to compare if one list of molecules has similarity to known drugs for several transporters. This comparison returns scores for every molecule from the test dataset which is compared with the drugs that are known to function for a certain transporter.
Finally, we obtain an output which shows all drugs, which have a chemical similarity score of a threshold above 0.6, that potentially can be applied to other transporters.
This process is repeatable for every SMILES - dataframe which can be fed into the 'similar()' function.
Access m2m_comparison for the results.

### Sources
- Database used for fething the transporters:    http://varidt.idrblab.net/data/transporter/details/dtd0003  SMILES codes were incosistent and were replaced with SMILES entries from PubChem, if there was any.
- similar() function by @zealseeker:             https://gist.github.com/zealseeker/9910056                  https://pubs.acs.org/doi/full/10.1021/ci0496797
