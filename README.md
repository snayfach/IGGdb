# IGGdb: integrated genomes from the gut microbiome and other environments

The current dataset is part of a pre-publication release.

We constructed the IGGdb using data from a number of domains, including PATRIC, IMG, and MAGs assembled from number of publicly available human gut metagenomes from the NCBI SRA. If this repository is useful, please consider additionally citing the individual sources of the data.

Note that many of the genomes in this repository were assembled from metagenomes. Lower quality genomes and MAGs need to be treated with special care to avoid issues with missingness, contamination, and short contigs. When in doubt, restrict your analysis to the high-quality genome sets.

After download, all datasets can be unpacked using: `tar -xjvf <dataset>.tar.gz`

And please do not download more data than is necessary. Thank you.
 
## Dataset of Human Gut Mags (HGMs) derived from globally-distributed human gut metagenomes

MAGs were assembled from 3810 human gut metagenomes from 15 different studies from geographically and phenotypically diverse human subjects. Metagenomes were assembled with MegaHIT and MAGs were constructed by binning contigs per-sample on the basis of nucleotide composition and read-depth. This was performed using four existing tools: Maxbin, MetaBAT, CONCOCT, DAS Tool. MAGs were screened for contamination using a [custom pipeline](link).

<b>High quality MAGs (N=24345)</b>   
[download link](http://bit.ly/HGM_hq_24345_fna)

* High quality mags meet the following criterea:
	* 	>=90% estimated completeness
	*  <=5% estimated contamination
	*  <=500 contigs
	*  >=10kb contig N50
	*  >=5x read depth over >=90% of contigs

<b>High and medium quality MAGs (N=60664)</b>   
[download link](http://bit.ly/HGM_all_60664_fna)

* All MAGs are estimated to be >=50% complete and <=10% contamintion

## Integrated gut genomes database (IGGdb)

The 60,006 genomes from the HGM dataset were integrated together with 148,656 reference genomes from PATRIC and IMG, which include 16,525 publicly available MAGs from other studies. All 209,320 genomes met the MIMAG medium quality draft genome standard of >=50% completeness and <=10% contamination. Genomes were clustered into 23,790 species-level OTUs based on 95% genome-wide average nucleotide identity.  

<b>Representative genomes for all species (N=23,790)</b>  
[download link](http://bit.ly/IGG_all_23790_fna)

* The representative genome is the high-quality genome that is most-closely related to other genomes in the same species
* The selection was based on: completeness, contamination, N50, % DNA identity to other genomes, and % DNA alignment to other species
* High-quality genomes are picked as representatives whenever possible

<b>Representative genomes for species with a high-quality genome (N=16,136)</b>  
[download link](http://bit.ly/IGG_hq_16136_fna)  

* This is a more conservative, higher-quality set of genomes 

<b>Representative genomes for human gut species (N=4,558)</b>  
[download link](http://bit.ly/IGG_gut_4558_fna)  

* Gut species were defined on the basis of 3 critera:  
	1) Contain a genome from an organism isolated from the gut (N=955), or  
	2) Contain a MAG from the HGM dataset (N=2,962), or  
	3) Were detected in a human gut metagenome based on read-mapping to conserved species-specific marker genes using [IGGsearch](https://github.com/snayfach/IGGsearch) (N=4,347)

<b>Representative genomes for human gut species with a high-quality genome (N=2,935)</b>  
<i> coming soon...</i>  
	
	
## Metadata for the HGM dataset and the IGGdb

<i> coming soon...</i>	
