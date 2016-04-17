### University of Zurich
### URPP Evolution in Action
![URPP logo](Logo_URPP_kl2.png)

Stefan Wyder & Heidi Lischer

stefan.wyder@uzh.ch  
heidi.lischer@ieu.uzh.ch


## Genomic Data visualization
  
  

Topic             | Software | Person 
----------------- | -------- | ------------------
Genome browsers | Ensembl project, BioMart, UCSC | Stefan
Genome viewers | IGV & co | Heidi
Visualization in a circular layout | circos, OmicCircos | Heidi
  
  
Heidi's parts: [Presentation](URPP_Tutorial_GenomicVisual_HL.pdf) | [Exercises](Exercises_GenomicVisualiz_HL.pdf)  
  
Stefan's [presentation](URPP_Tutorial_GenomicVisual_SW.pdf)  
  
  
### Ensembl
- hub of reference and baseline data
- construct annotation (also manual)
- all data public
- 4-5 updates (versions/freezes) a year
- archived version
  
  
### 4 types of resources:  
1. gene annotation 
2. variation resources 
3. regulatory resources
4. comparative genomics resources  
  orthology
  whole-genome alignments  
  
  
### Ensembl Tools

Name | Description
---- | --------
VEP (Variant Effect Prediction) | Analyse your own variants and predict the functional consequences of known and unknown variants via our Variant Effect Predictor (VEP) tool.
| available as webtool and standalone perl script [see previous tutorial](https://github.com/milchmolch/URPP_Tutorials/blob/master/NGS/URPP_Tutorial_NGS_Part3_SW.pdf)
HMMER | Quickly search our genomes for your protein sequence
BLAST/BLAT | Search our genomes for your DNA or protein sequence.
BioMart (+ biomaRt via R) | Use this data-mining tool to export custom datasets from Ensembl.
Assembly converter | Map (liftover) your data's coordinates to the current assembly.
ID History converter | Convert a set of Ensembl IDs from a previous release into their current equivalents.

  
- attach standard bioinformatic data formats (incl. BigBED, BigWig, VCF, BAM)
- export pictures in high-quality (pdf png svg formats)
- all views are customizable
  
## Sources / Links
  
**Tutorials / Courses**    
- [Tutorials](http://www.ensembl.org/info/website/tutorials/index.html)
- [Online Course (7hrs)](http://www.ebi.ac.uk/training/online/course/ensembl-browser-webinar-series-2016)
  
**More info**  
- [Ensembl Roadmap](http://www.ensembl.info/roadmap/)
  
  
## Exercises

### Ensembl genome browser

1. Find your favorite organism

Go to http://ensemblgenomes.org and try to find the ensembl entry page of your favorite species. If your favorite species is not 
in ensembl go to you related species.

2. Find 

Go to the Ensembl homepage (http://www.ensembl.org/) and select the mouse and search for the gene "ABCD1".
  
The search result shows an ABCD1 gene and several transcripts (splice variants).  
  
Click on ‘ABCD1 (Mouse Gene)’ (the first hit)
  
This leads us to the ‘Gene summary’ page under the ‘Gene’ tab.
  
**The Gene tab**  
  
Pages (also called ‘views’) in Ensembl are organised under a number of tabs, i.e. ‘Species’, ‘Location’, ‘Gene’, ‘Transcript’, ‘Variation’ and ‘Regulation’. The various available pages under each tab are listed in the left-hand side menu.


3. 
http://www.ensembl.org/Ovis_aries/Gene/Summary?db=core;g=ENSOARG00000007049;r=X:77653929-77668081;t=ENSOART00000007672



### BioMart 'Data Mining'

Remember that each BioMart query consists of 4 steps:
  1. Dataset: choose database & species
  2. Filters: what you know
  3. Attributes: what you want to know
  4. Results: table / sequences  


1. Get description for a gene list / Convert IDs

  The gene list we use here is a list of significantly up-regulated genes in the met1 background in Arabidopsis thaliana defective in methylation maintenance (PMID:18423832).
(obtained from Table S2 from the publication [PMID:23146178](http://onlinelibrary.wiley.com/doi/10.1111/tpj.12070/abstract) 

  - Download gene list
  wget https://raw.githubusercontent.com/milchmolch/BIO634_NGS2_2015/master/GENE_LISTS/Lister_met1_up.txt

  - Go to EnsemblPlants http://plants.ensembl.org and Start BioMart

  - Select in **Dataset**: <Arabidopsis thaliana (TAIR10)

  - Select in **Filters**: <GENE>, check <ID list limit> and upload your file containing the list of genes

  - Select in **Attributes**: <Features>, and under **Gene Attributes**: <Gene stable ID>, <Gene name> and <Gene description>

  - Get the results by clicking on the <Results> box in the upper left corner of the screen

  - Note that you can modify **Attributes** by clicking on the box **Attributes** in the left panel

  - Download the table to your local computer in Excel format (xls). Note that in the Excel file IDs are clickable.
  
  
  Similarly, we can use BioMart for gene ID conversion if we select as attributes the IDs we want to compare.


2. Get orthologs in Brassica oleracea for genes on the list

  - Modify **Attributes** by clicking on the box **Attributes** in the left panel

  - Unfold <ORTHOLOGS> and select in **Brassica oleracea Orthologs**: <gene stable ID>, <Homology type>, <% identity> and <Orthology confidence>  

  - Hit the <Results> box to get the results

3. Download the sequences of all promoter sequences for gene list 

  - Under **Atributes** select <Sequence>
XXX

4. Retrieve all the known sequence variants leading to frameshifts for a gene list

XXX  - Modify the **Filters** by clicking on the **Attributes** in the left panel

  - Unfold <VARIATION> at the bottom, under <Variation type> select <frameshift_variant>

  - Under **Attributes** select <Variation> and then under <GERMLINE VARIATION INFORMATION>:
    <Reference ID>, <Source>, <Distance to transcript>, <Consequence type>, <Consequence specific allele>, <SIFT prediction>  
  
5. Explore the possibilities of BioMart
  There are many more possibilites to annotate genes and retrieve features/sequences. 
  E.g. under **Filters**  you can filter genes according to their genomic location, protein domains, Gene Ontology description, microarray probes... 
  
  You can also access BioMart/ensembl from R using the "biomaRt" package


## Further tutorials / coursebooks

- [Browsing Bacterial Genomes with Ensembl](http://pedagogix-tagc.univ-mrs.fr/allbio/teaching_material/ensembl_material/Ensembl%20Bacteria%20Coursebook.pdf)

- [Recent Presentations and Worked examples](ftp://ftp.sanger.ac.uk/pub/resources/coursesandconferences/)
