# IGGdb: integrated genomes from the gut microbiome and other environments

We constructed the IGGdb using data from a number of domains, including PATRIC, IMG, and MAGs assembled from 3,810 publicly available human gut metagenomes from the NCBI SRA. If this repository is useful, please consider additionally citing the individual sources and studies the data was derived from.

Note that many of the genomes in this repository were assembled from metagenomes. Lower quality genomes and MAGs need to be treated with special care to avoid issues with missingness, contamination, and short contigs. When in doubt, restrict your analysis to the high-quality genome sets.

After download, all datasets can be unpacked using: `tar -xjvf <dataset_name>`
 
## Human Gut MAG (HGM) dataset

MAGs were assembled from 3,810 human gut metagenomes from 15 different studies from geographically and phenotypically diverse human subjects. Metagenomes were assembled with MegaHIT and MAGs were constructed by binning contigs per-sample on the basis of nucleotide composition and read-depth. This was performed using four existing tools: Maxbin, MetaBAT, CONCOCT, DAS Tool. MAGs were screened for contamination using a [custom pipeline](https://github.com/snayfach/MAGpurify).

<b>High quality MAGs (N=24345)</b>   
download from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/HGM_v1.0_hq_24345_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/HGM_v1.0_hq_24345_fna.tar.bz2`  

* High quality MAGs meet the following criterea:
	*  \>=90% estimated completeness
	*  <=5% estimated contamination
	*  <=500 contigs
	*  \>=5kb average contig length
	*  \>=10kb contig N50
	*  \>=5x read depth over >=90% of contigs

<b>High and medium quality MAGs (N=60664)</b>   
download from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/HGM_v1.0_all_60664_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/HGM_v1.0_all_60664_fna.tar.bz2` 

* All MAGs are estimated to be >=50% complete and <=10% contaminated

## Integrated genomes from the gut and other environments dataset (IGG)

Note: this set includes non-gut genomes

The 60,664 genomes from the HGM dataset were integrated together with 145,917 reference genomes from PATRIC and IMG, which include 16,525 publicly available MAGs from other studies <b> as well as genomes from other non-gut environments </b>. All 206,581 genomes met the MIMAG medium quality draft genome standard of >=50% completeness and <=10% contamination. Genomes were clustered into 23,790 species-level OTUs based on 95% genome-wide average nucleotide identity. 

<b>Representative genomes for all species (N=23,790)</b>  
download from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_all_23790_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_all_23790_fna.tar.bz2`

* The representative genome is the highest quality genome that is most closely related to other genomes in the same species
* The selection was based on: completeness, contamination, N50, and % DNA identity  and % DNA alignment to other genomes in the same species
* High-quality genomes are picked as representatives when available

<b>Representative genomes for species with a high-quality genome (N=16,136)</b>  
download via from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_hq_16136_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_hq_16136_fna.tar.bz2`

* This is a more conservative, higher-quality set of representative genomes 

<b>Representative genomes for human gut species (N=4,558)</b>  
download from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_gut_4558_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_gut_4558_fna.tar.bz2`  

* Gut species were defined on the basis of 3 criteria:  
	1) Contain a genome from an organism isolated from the gut (N=955), or  
	2) Contain a MAG from the HGM dataset (N=2,962), or  
	3) Were detected in a human gut metagenome based on read-mapping to conserved species-specific marker genes using [IGGsearch](https://github.com/snayfach/IGGsearch) (N=4,347)
* 2,058 (45%) gut species are new while 2,500 (55%) contain a reference genome

<b>Representative genomes for human gut species with a high-quality genome (N=2,935)</b>  
download from your browser: [download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_gut_2935_fna.tar.bz2)  
download via wget: `wget https://portal.nersc.gov/cfs/m342/HGM/IGG_v1.0_gut_2935_fna.tar.bz2` 

* 684 (23%) gut species are new while 2,251 (77%) contain a reference genome


## Phylogenome trees

Phylogenetic trees were constructed for all Bacterial and Archaeal species in the IGGdb using concatenated alignments of conserved, single-copy marker gene families from the PhyEco database (N=88 for Bacteria and 100 for Archaea). Protein-based multiple sequence alignment was performed using FAMSA v1.2.5, which is designed for fast and accurate alignment of thousands of sequences. Gene alignments were concated together, columns with >15% gaps were dropped, and seuqneces with >70% gaps and were removed (N=39). FastTree2 was used to build a maximum likelihood phylogeny.

<b>All Bacterial species (N=22,515)</b>  
[download alignments](https://portal.nersc.gov/cfs/m342/HGM/IGG_bact_22515_msa)  
[download tree](https://portal.nersc.gov/cfs/m342/HGM/IGG_bact_22515_tre)

<b>All Archaeal species (N=1,236)</b>  
[download alignments](https://portal.nersc.gov/cfs/m342/HGM/IGG_arch_1236_msa)   
[download tree](https://portal.nersc.gov/cfs/m342/HGM/IGG_arch_1236_tre)


## Metadata for the HGM and IGG datasets

<b>Reference genomes and MAGs from HGM dataset (N=206,581)</b>  
[download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_genome_info_206581.tsv)

* Contains rich metadata on all reference genomes and MAGs, including quality information and habitat
* Completeness and contamination estimates were made using [CheckM](https://github.com/Ecogenomics/CheckM)

<b>All species from the IGGdb (N=23,790)</b>  
[download link](https://portal.nersc.gov/cfs/m342/HGM/IGG_species_info_23790.tsv)  

* Contains rich metadata on each species, including taxonomic information
* Species were taxonomically annotated based on the [Genome Taxonomy Database](https://github.com/Ecogenomics/GTDBTk)
* Additionaly, species were assigned to an operational taxonomy based on phylogenetic clustering using rank-specific distance cutoffs
