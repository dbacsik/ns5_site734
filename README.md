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
* `permitted_codons.csv` which lists the codons designed to be the mutagenized library.
* `STAT2_luciferase_results.csv` which contains luciferase assay results (FLUC/RLUC values) for each amino acid in the library.
* `codon_lookup_table.csv` is a table containing codons and amino acid symbols.

The following files are output:
* `codon_analysis.py.ipynb` contains the analysis code.
* `codon_analysis.py.html` contains an HTML copy of the notebook with outputs stored inline.
* `codons_parsed.csv.gz` contains the unfiltered, parsed codons for every read. This file is not stored on GitHub because it is too large.
* `results/codon_counts.csv` contains the count and frequency of each codon in each sample **after filtering**.
* `results/tolerance.csv` contains the codon tolerance calculated by taking the enrichment of each codon in the unselected cell sample ("Mut_NS5_Sample") compared to the mutant plasmid library ("Mut_Plasmid").
* `results/enrichment_Rnd1_IFN_neg.csv` contains the enrichment of each codon in the IFN- population ("Rnd1_IFN_neg") compared to the unselected cell sample ("Mut_NS5_Sample").
