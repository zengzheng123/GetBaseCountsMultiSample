# GetBaseCountsMultiSample

##### Calculate the base counts in multiple BAM files for all the sites in a given VCF file or MAF file


### Install:
Run "make" in the program directory to compile


### Usage:
```
[REQUIRED ARGUMENTS]

--fasta                 <string>        Input reference sequence file
--bam                   <string>        Input bam file, in the format of SAMPLE_NAME:BAM_FILE. This paramter need to be specified at least once
                                        e.g: --bam s_EV_crc_007:Proj_4495.eta_indelRealigned_recal_s_EV_crc_007_M3.bam.
--maf                   <string>        Input variant file in TCGA maf format. --maf or --vcf need to be specified at least once. But --maf and --vcf are mutually exclusive
--vcf                   <string>        Input variant file in vcf-like format(the first 5 columns are used). --maf or --vcf need to be specified at least once. But --maf and --vcf are mutually
--output                <string>        Output file

[OPTIONAL ARGUMENTS]
--omaf                                  Output the result in maf format
--thread                <int>           Number of thread. Default 1
--maq                   <int>           Mapping quality threshold. Default 20
--baq                   <int>           Base quality threshold, Default 0
--filter_duplicate      [0, 1]          Whether to filter reads that are marked as duplicate. 0=off, 1=on. Default 1
--filter_improper_pair  [0, 1]          Whether to filter reads that are marked as improperly paired. 0=off, 1=on. Default 0
--filter_qc_failed      [0, 1]          Whether to filter reads that are marked as failed quality control. 0=off, 1=on. Default 0
--filter_indel          [0, 1]          Whether to filter reads that contain indels. 0=off, 1=on. Default 0
--filter_non_primary    [0, 1]          Whether to filter reads that are marked as non primary alignment. Default 0
--positive_count        [0, 1]          Whether to output positive strand read counts DPP/RDP/ADP. 0=off, 1=on. Default 1
--fragment_count        [0, 1]          Whether to output fragment read counts DPF/RDF/ADF. 0=off, 1=on. Default 0
--suppress_warning      <int>           Only print a limit number of warnings for each type. Default 3
--help                                  Print command line usage



[ADVANCED ARGUMENTS, CHANGING THESE ARGUMENTS MAY SIGNIFICANTLY AFFECT MEMORY USAGE AND RUNNING TIME. USE WITH CAUTION]

--max_block_size        <int>           The maximum number of variant chunks that can be processed at once per thread. Default 10,000
--max_block_dist        <int>           The longest spanning region (bp) of variant chunks that can be processed at once per thread. Default 100,000
--generic_counting                      Use the newly implemented generic counting algorithm. Works better for complex variants. You may get different allele count result from the default counting algorithm
```

```
### FAQ:

```






``` 

### This software uses the following library

bamtools https://github.com/pezmaster31/bamtools
