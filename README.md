## Introduction
This repository contains several scripts for bioinformatics.


## Usage
- approximate_cnv.py is a script for approximating CNV (Copy Number Variation) with read depth.
```shell
approximate_cnv.py -bam <bam_list_file> -g <genome_size> -l <read_length> -bed <bed_file> -o <out_file> [-t <thread_nums>]

Usage:
  -bam: a list file, each line is the full path of a bam file
  -g: the size of genome, integer
  -l: the length of read, integer
  -bed: bed file contain 4 columns: chromosome, start position, end position, gene name, seperate with tab
  -o: result file
  -t: threads, integer
```
- average_fpkm.py is a script for calculating average of fpkm values.
```shell
# Dependencies
# Python modules: numpy
average_fpkm.py <in_fpkm> <out_avg>
```
- blast2heatmap.py is a script for drawing heatmap with blast file of format 6.
```shell
# Dependencies
# Software: R, bedtools
# R modules: pheatmap
blast2heatmap.py <ref_fasta> <blast_file> <window_size> <out_name> <threshold_identify> <threshold_match>
```
- calc_gap_cnt.py is a script for calculating gap count of all sequences.
```shell
calc_gap_cnt.py <in_fa>
```
- calc_gene_ovlp_te.py is a script for calculating overlap ratio of genes with TE regions.
```shell
calc_gene_ovlp_te.py <gene_gff3> <TE_gffs> <ovlp_stat>
Usage:
  ovlp_stat: is the output file.
```
- convert_collinearity_from_MCScanX_to_Circos.py is a script for converting collinearity file from MCScanX result to link file for Circos
```shell
convert_collinearity_from_MCScanX_to_Circos.py <collinearity_file> <gff_file> <out_file>
```
- convert_gbff_to_fasta.py is a script for converting NCBI GBFF file to fasta file.
```shell
convert_gbff_to_fasta.py <in_gbff> <out_fasta>
```
- convert_QTL_info.py is a script for converting QTL information of contig-level to chromosome-level with agp file.
```shell
convert_QTL_info.py <in_QTL> <in_agp> <out_QTL>
```
- convert_simple_for_circos.py is a script for converting JCVI simple file to link file for circos.
```shell
convert_simple_for_circos.py <in_simple> <in_gff3_files> <out_link>
```
- dup_dotplot.pl is a script for plotting dotplot with monoploid and polyploid.
```shell
dup_dotplot.pl -g reference_genome -r ref_id -q query_id -n number_of_dup -t threads
Usage:
    ref_id: reference cds and bed name, like: Sb, Sb.cds and Sb.bed must exist
    query_id: query cds and bed name, like: Os
    number_of_dup: number of duplications
    threads: default 1
```
- eval_filled_gaps.py is a script for evaluating status that gaps been filled
```shell
eval_filled_gaps.py <ref_fasta> <query_fasta> <result_file>
```
- extract_all_sv_from_nucmer_delta.py is a script for extracting SV from delta file generated by nucmer.
```shell
extract_all_sv_from_nucmer_delta.py <in_delta> <out_pre>
```
- extract_gene_from_gff.py is a script for extracting genes from gff3 file with gene id list and generating a bed file.
```shell
extract_gene_from_gff.py <in_list> <in_gff> <out_bed>
```
- extract_vcf.py is a script for extracting vcf with bed file
```shell
extract_vcf.py <in_vcf> <in_bed> <out_vcf>
```
- filter_cds.py is a script for removing invalided CDS sequences.
```shell
filter_cds.py <in_cds> <out_cds>
```
- find_gff_ovlp_regions.py is a script for getting overlap regions from gff3 file.
```shell
find_gff_ovlp_regions.py <in_gff3> <out_bed>
```
- get_chr_len.py is a script for calculating length of chromosomes in fasta file
```shell
get_chr_len.py <fasta_file> <output_file> <T/F chr only>
```
- get_genes_from_range.py is a script for getting genes with bed file.
```shell
get_genes_from_range.py <gff3_file> <bed_file> <output_file> <threshold>
```
- get_genes_region_from_gff.py is a script for getting gene regions from gff3 file.
```shell
get_genes_region_from_gff.py <gene_list> <in_gff> <out_bed>
```
- get_gff_with_list.py is a script for extracting gff3 file with gene IDs.
```shell
get_gff_with_list.py <in_gff> <in_list> <out_gff>
```
- get_seq_from_range.py is a script for extracting sequence fragments with bed file.
```shell
get_seq_from_range.py <in_fasta> <in_bed> <out_fasta>
```
- group_exon_and_intron.py is a script for classifying vcf positions to exon and intron.
```shell
group_exon_and_intron.py <input_gff> <input_vcf> <output_file>
```
- group_SNP_exon_and_intron.py is a script for classifying SNP positions to exon and intron.
```shell
group_SNP_exon_and_intron.py <input_gff> <input_snp> <output_file>
```
- merge_bed_regions.py is a script for merging bed files based on distance
```shell
merge_bed_regions.py <in_bed> <out_bed> <max_distance>
```
- modify_geno_with_snp_mummer.py is a script for modifying columns in geno file with snp result generated by show-snps of mummer
```shell
modify_geno_with_snp_mummer.py <in_geno> <in_snp> <col> <out_geno>
```
- nucmer_extract_all_sv.py is a script for running nucmer and extracting all SV.
```
# Dependencies
# Software: nucmer
nucmer_extract_all_sv.py <ref_fasta> <query_fasta> <out_pre> <threads>
```
- nucmer_statistics.py & nucmer_statistics_all_sv.py are scripts for running nucmer and generating statistics.
```shell
nucmer_statistics.py <ref_fasta> <query_fasta> <out_pre> <threads>
nucmer_statistics_all_sv.py <ref_fasta> <query_fasta> <out_pre> <threads>
```
- quick_extract_fastx.py is a script for extracting fasta or fastq file with list.
```shell
quick_extract_fastx.py <in_fastx|gz> <in_list> <out_fastx|gz>
```
- quick_mask_genome.py is a script for masking genome with bed file.
```shell
quick_mask_genome.py <in_fasta> <in_bed> <out_fasta> <threshold> <threads>
```
- remove_region_by_blast_result.py is a script for removing regions in chromosomes with blast results.
```shell
remove_region_by_blast_result.py <blast_results> <chr_len> <out_bed>
Usage:
  <blast_results> is a list of blast files seperated with comma
```
- rename_ID.py is a script for sorting and renaming id with in_gff file, and renaming id in fasta files.
```shell
rename_ID.py <chr_prefix> <in_gff> <out_gff> <in_fasta> <out_fasta>
```
- SeqStat.py is a script for generating statistics with fasta|fastq|bam file.
```shell
SeqStat.py <in_file> [out_stat]
```
- SimContigs.py & SimCollapse.py are scripts for simulating collapsed contigs.
```shell
usage: SimContigs.py [-h] [--min MIN] [--max MAX] [-n N50] -i INPUT -o OUTPUT

options:
  -h, --help            show this help message and exit
  --min MIN             minimum length of contig, default: 15k, you can use both number or string end with k,m
  --max MAX             minimum length of contig, default: 5m, you can use both number or string end with k,m
  -n N50, --n50 N50     size of N50, default: 500k, you can use both number or string end with k,m
  -i INPUT, --input INPUT
                        origin fasta file of genome
  -o OUTPUT, --output OUTPUT
                        filename of simulated data


usage: SimCollapse.py [-h] -a A_CONTIGS -b B_CONTIGS -p PREFIX -o OUTPUT -s BLAST [-c COLLAPSE]

options:
  -h, --help            show this help message and exit
  -a A_CONTIGS, --a_contigs A_CONTIGS
                        first fasta file contain contigs generated by SimContigs.py
  -b B_CONTIGS, --b_contigs B_CONTIGS
                        second fasta file contain contigs generated by SimContigs.py
  -p PREFIX, --prefix PREFIX
                        prefix of contig file a and contig file b, divided by comma, like: HA, HB
  -o OUTPUT, --output OUTPUT
                        filename of simulated data
  -s BLAST, --blast BLAST
                        blast file with format 6, must use first file of input as query and second file as database
  -c COLLAPSE, --collapse COLLAPSE
                        persentage of collapse region size, like 5 means 5%, default: 10
```
- simple_ANGSD.py & simple_ANGSD_without_errorCorrect.py are script for running ANGSD.
```shell
simple_ANGSD.py -l <species.list> -anc <outgroup.fasta> -r <region> [-out <out_group_name> -p <bam_path> -ref <ref.fasta>]
simple_ANGSD_without_errorCorrect.py -l <species.list> -r <region> [-out <out_group_name> -p <bam_path>]
Notice:
  -p: path of bam files, default is current path
  -out: name of outgroup, default is "Outgroup"
```
- simple_JBrowser.py is a script for generating file for JBrowser
```shell
# J.conf is a default config file for simple_JBrowser.py
simple_JBrowser.py -f <fasta_file> [--gff <gff_file> --bed <bed_file> --bam <bam_file> --bw <bigwig_file> --conf <config_file>]
```
- SimSID.py is a script for simulating SNP, Insertions and Deletions.
```shell
usage: SimSID.py [-h] [-s SNP] [-i INSERTION] [--insert_length INSERT_LENGTH] [-d DELETION] [--delete_length DELETE_LENGTH] [--random_length] [-v] -r REF -o OUT

options:
  -h, --help            show this help message and exit
  -s SNP, --snp SNP     snp ratio of whole genome, percentage, default: 0.01
  -i INSERTION, --insertion INSERTION
                        insertion ratio of whole genome, percentage, default: 0.01
  --insert_length INSERT_LENGTH
                        max length of insertion, default: 10
  -d DELETION, --deletion DELETION
                        delection ratio of whole genome, percentage, default: 0.01
  --delete_length DELETE_LENGTH
                        max length of deletion, default: 10
  --random_length       use this argument for generate random length of indels
  -v, --verbose         print detail information
  -r REF, --ref REF     origin fasta file of genome
  -o OUT, --out OUT     prefix of simulated data
```
- split_cmd_with_parts.py is a script for splitting cmd file.
```shell
split_cmd_with_parts.py <in_cmd_file> <num_parts> <out_str> <threads>
```
- split_ctg_with_agp.py is a script for convert chromosome file to contig file with agp file.
```shell
split_ctg_with_agp.py <in_fa> <in_agp> <out_dir>
```
- split_fasta_by_chr.py is a script for splitting fasta into several files contain single chromosome.
```shell
split_fasta_by_chr.py <in_fasta> <out_dir>
```
- split_fasta_by_count.py is a script for splitting fasta to several files with file size or sequence counts.
```shell
split_fasta_by_count.py <in_fasta> <S/F> <count> <out_dir>
```
- split_fasta_by_id.py is a script for splitting fasta with id.
```shell
split_fasta_by_id.py <in_fasta> <out_dir>
```
- StatAgp.py & StatAgpDetail.py are scripts for generating statistic with agp file.
```shell
StatAgp.py <in_agp>
StatAgpDetail.py <in_agp> <out_csv>
```
- subVCF.py is a script for extracting vcf file with list file, default missing rate 0.4.
```shell
subVCF.py <in_vcf> <in_list> <out_vcf> [<missing_rate>]
```
- transfer_gff3_with_agp.py is a script for transferring positions with old agp and new agp file.
```shell
transfer_gff3_with_agp.py <in_gff3> <in_old_agp> <in_new_agp> <out_gff3>
```
- vcf2geno.py is a script for converting vcf file to geno file for ABBABABAwindows.py.
```shell
vcf2geno.py -i <input_vcf> -o <output_vcf> -q/--quality <min_qual> -f/--filter <filter_type> <min_value>
```