## Exercises Ensembl genome browser and Biomart

1. Find your favorite organism

  Go to http://ensemblgenomes.org and try to find the ensembl entry page of your favorite species. If your favorite species is not 
  in ensembl go to you related species.

2. Go through one of the worked example (either [Human](worked_example_Human.pdf) or [Arabidopsis](workedExample_Arabidopsis.pdf) )

  Pages (also called ‘views’) in Ensembl are organised under a number of tabs, i.e. ‘Species’, ‘Location’, ‘Gene’, ‘Transcript’, 
  ‘Variation’ and ‘Regulation’. The various available pages under each tab are listed in the left-hand side menu.

### BioMart 'Data Mining'

Remember that each BioMart query consists of 4 steps:
  1. Dataset: choose database & species
  2. Filters: what you know
  3. Attributes: what you want to know
  4. Results: table / sequences  


#### Exercises using Ensembl Plants

1. Get description for a gene list / Convert IDs

  The gene list we use here is a list of significantly up-regulated genes in the met1 background in Arabidopsis thaliana defective in methylation maintenance (PMID:18423832).
(obtained from Table S2 from the publication [PMID:23146178](http://onlinelibrary.wiley.com/doi/10.1111/tpj.12070/abstract) 

  - Download gene list (from browser or using `wget`) 
  https://raw.githubusercontent.com/milchmolch/BIO634_NGS2_2015/master/GENE_LISTS/Lister_met1_up.txt

  - Go to EnsemblPlants http://plants.ensembl.org and Start BioMart

  - Select in **Dataset**: 'Arabidopsis thaliana (TAIR10)'

  - Select in **Filters**: 'GENE', check 'ID list limit' and upload your file containing the list of genes

  - Select in **Attributes**: 'Features', and under **Gene Attributes**: 'Gene stable ID', 'Gene name' and 'Gene description'

  - Get the results by clicking on the 'Results' box in the upper left corner of the screen

  - Note that you can modify **Attributes** by clicking on the box **Attributes** in the left panel

  - Download the table to your local computer in Excel format (xls). Note that in the Excel file IDs are clickable.
  
  
  Similarly, we can use BioMart for gene ID conversion if we select as attributes the IDs we want to compare.


2. Get orthologs in Brassica oleracea for genes on the list

  - Modify **Attributes** by clicking on the box **Attributes** in the left panel

  - Unfold 'ORTHOLOGS' and select in **Brassica oleracea Orthologs**: 'gene stable ID', 'Homology type', '% identity' and 'Orthology confidence'  

  - Hit the 'Results' box to get the results

3. Download the sequences of all promoter sequences for gene list 

  - Under **Atributes** select 'Sequence'

  ...

4. Retrieve known SNPs for a list of genes leading to frameshifts

  - Modify the **Filters** by clicking on the **Attributes** in the left panel

  - Unfold 'VARIATION' at the bottom, under 'Variation type' select 'frameshift_variant'

  - Under **Attributes** select 'Variation' and then under 'GERMLINE VARIATION INFORMATION':
    'Reference ID', 'Source', 'Distance to transcript', 'Consequence type', 'Consequence specific allele', 'SIFT prediction'  
  
5. Explore the possibilities of BioMart
  There are many more possibilites to annotate genes and retrieve features/sequences. 
  E.g. under **Filters**  you can filter genes according to their genomic location, protein domains, Gene Ontology description, microarray probes... 
  
  You can also access BioMart/ensembl from R using the `biomaRt` package


## Further tutorials / coursebooks

- [Browsing Bacterial Genomes with Ensembl](http://pedagogix-tagc.univ-mrs.fr/allbio/teaching_material/ensembl_material/Ensembl%20Bacteria%20Coursebook.pdf)

- Recent Presentations and Worked examples  
  ftp://ftp.sanger.ac.uk/pub/resources/coursesandconferences/
    
- Worked example Human                             
  ftp://ftp.sanger.ac.uk/pub/resources/coursesandconferences/Mammalian_2016/Browsers_2016.pdf
  
- Variation in Human  
  ftp://ftp.sanger.ac.uk/pub/resources/coursesandconferences/Mammalian_2016/Variation_2016.pdf
