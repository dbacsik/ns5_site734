# Zika Virus IFN Antagonism
This repo analyzes a single-site (D734) saturation mutagenesis experiment in the Zika Virus NS5 protein.

The analysis happens in the `codon_analysis.py.ipynb` notebook. This notebook calculates the enrichment of each codon in each sequencing sample compared to the `"Mut_NS5_Sample"`.

The steps involved in analysis are:  
* Open each FASTQ file
* Parse the site 734 codon
* Save the parsed codons to `codon_counts.csv.gz`
* Perform quality control
* Calculate the enrichment compared to reference
* Plot the results

The following files are required for input:
* `ns5.fasta` gives the coding sequence of the NS5 gene as supplied on the source plasmid.
* `samplesheet.csv` gives the sequencing samples and paths to FASTQ files on the Hutch server.
* `codon_lookup_table.csv` is a table containing codons and amino acid symbols.
