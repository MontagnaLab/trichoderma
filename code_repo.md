### **markdown for manuscript: "A hidden interkingdom competition underlies plant-insect interactions."**

-------------------------------------------------------------------------------------------

# *1. In Vivo Bioassays*

#### In Vivo Bioassay - SOFTWARE:

- [PRISM](https://www.graphpad.com/scientific-software/prism/) 

#### In Vivo Bioassay - INPUTS AND INTERMEDIATE FILES:

-  raw data in ```raw_data/1_In_Vivo_Bioassay/In_Vivo_Bioassay.xlsx```.

#### In Vivo Bioassay - OUTPUTS:

- Fig. 1a
- Fig. 1b
- Fig. 1c
- Fig. 1d
- Fig. 1e
- Fig. 1f
- Fig. 5a
- Fig. 5b 
- Fig. 5c
- Fig. 5d 
- Fig. 5e 
- Supplementary Figure 6
- Supplementary Figure 7
- Supplementary Table 1
- Supplementary Table 6

#### In Vivo Bioassay - COMMANDS: Log-rank test in Fig. 1a Fig. 1d, Fig. 5a and Fig. 5b (PRISM)

```
1. Open the program 
2. From the Welcome or New Table dialog in the program Prism 6, choose the Survival tab and chose on the right the option “Start with an empty data table”, than “Create”.
3. Enter the time (Day) until censoring or the event of interest (death) in the X column. Name the column with the name of the treatments you have realized in the experiments.
4. Enter “1” into the Y column for rows in which the subject experienced the event of interest (death)  at the time and enter “0” into rows where the subject was alive at this time. Note that every row must have either a 0 or a 1 in a single Y column. 
5. After insert data press on “Curve comparison” under Survival data to have the results.
```

#### In Vivo Bioassay - COMMANDS: Student’s t-test of Fig. 1b, Fig. 1e, Fig. 1c, Fig. 1f, Supplementary Fig. 1 and Supplementary table 1 (PRISM)

```
1.	From the Welcome (or New Table and graph) dialog, choose the “Column” tab and choose “Student’s test – Unpaired” and “Create”.
2.	Enter the data for each group into a separate column.
3.	Select “Analyze” then “Column analysis” and “Column Statistics”.
4.	In “Column statistics” select the “Shapiro-Wilk normality test” under “Test if the values come from a Gaussian distribution”.
5.	Then return to data-set selecting “Unpaired t test data” and select against “Analyze”, “Column analysis” and “t-test (and nonparametric)”.
6.	Because the data are normal select “Experimental design”, select “Unpaired”; under “Assume Gaussian distribution” select “Yes. Use parametric test”; under “Chose test” select “Unpaired t test. Assume both populations have the same SD”.
7.	Select “Ok” to have statistical results, including the homoscedasticity  anlysis.
```

#### In Vivo Bioassay - COMMANDS: One Way ANOVA and Kruskal-Wallis test (nonparametric ANOVA) of Fig.5c, Fig.5d, Fig. 5e, Supplementary Fig. 6 and Supplementary Fig. 7 (PRISM)

```
1.	From the Welcome (or New Table and graph) dialog, choose the Column tab and choose “One-way ANOVA” and “Create”.
2.	Enter the data for each group into a separate column.
3.	Select “Analyze” then “Column analysis” and “Column Statistics”
4.	In “Column statistics” select under “Test if the values come from a Gaussian distribution” the “Shapiro-Wilk normality test”.
5.	Then return to data-set select against “Analyze” and under Column statistics select “One-way ANOVA (and nonparametric)” and “OK”. 
6.	Select “Experimental design”, select “No matching or pairing”; under “Assume Gaussian distribution” select “Yes. Use ANOVA” if the data are normal or “No. Use nonparametric test” if the data are not normal; select ok, Select “Ok” to have statistical results, including the homoscedasticity anlysis.
7.	If assumption of normality and equal SD are met the results for ONE WAY ANOVA can be considered.
8.	If the normality condition are not respected and the populations have different SDs come back to point 6 and select “No. Use nonparametric test” and ok to perform Kruskal-Wallis test.
```

#### In Vivo Bioassay - COMMANDS: Plot results or t-tests, One Way ANOVA and Kruskal-Wallis tests (PRISM)

```
1.	From the Welcome (or New Table and graph) dialog, choose the “Column” tab and choose in “Enter/import data” the option “Enter and plot values already calculated elsewhere”, then in “Enter:” chose “Mean & SEM”. Chose “OK”
2.	Insert the name of the treatment in the column as “Title”
3.	Insert for every group the Mean and SEM in the corrispondent column 
4.	On the left chose from the list in the folder “Graphs” the “Data” sheet.
```

-------------------------------------------------------------------------------------------

## *2. Digestive_Enzymes_Assays_and_Quantification_of_Glycogen_Deposits*

#### Digestive_Enzymes_Assays_and_Quantification_of_Glycogen_Deposits - SOFTWARE:

- [R](https://www.R-project.org/) - R Core Team (2021). R: A language and environment for statistical computing (version 4.0.4). R Foundation for Statistical Computing.

#### Digestive_Enzymes_Assays_and_Quantification_of_Glycogen_Deposits - INPUTS AND INTERMEDIATE FILES:

- raw data in ```raw_data/2_Digestive_Enzyme_Assays_and_Quantification_of_Glycogen_Deposits/Digestive_Enzyme_Assays_and_Quantification_of_Glycogen_Deposits.xls```.

#### Digestive_Enzymes_Assays_and_Quantification_of_Glycogen_Deposits - OUTPUTS:

- Fig. 2k
- Fig. 2l
- Fig. 2m
- Fig. 2p

#### Digestive_Enzymes_Assays_and_Quantification_of_Glycogen_Deposits - CODE: barplots in Fig. 2k, 2l, 2m and 2p (R AND PRISM)

Statistical analysis for Total Proteolytic Activity (Fig. 2k).

```
C_larvae=c(1.4,3.7,3.3) #data input (C-larvae)
T22_larvae=c(3.0,2.1,2.3) #data input (T22-larvae)
shapiro.test(C_larvae) #checking the normality assumption
shapiro.test(T22_larvae) # checking the normality assumption
t.test(C_larvae, T22_larvae,paired = F) # performing Welch Two Sample t-test
```

Statistical analysis for Aminopeptidase N Activity (Fig. 2l).

```
C_larvae=c(0.538,0.570,0.620,0.602,0.633) #data input (C-larvae)
T22_larvae=c(0.756,0.543,0.576,0.551,0.595,0.551) #data input (T22-larvae)
shapiro.test(C_larvae) #checking the normality assumption
shapiro.test(T22_larvae) # checking the normality assumption
# nonparametric test was performed since the normality assumption was rejected
wilcox.test (C_larvae, T22_larvae, paired = F) # performing Wilcoxon rank sum test with continuity correction
```

Statistical analysis for α-amylase activity (Fig. 2m).

```
C_larvae=c(1.6,2.2,3.3,2.0,1.2) #data input (C-larvae)
T22_larvae=c(2.0,2.1,3.9,2.5,1.4) #data input (T22-larvae)
shapiro.test(C_larvae) #checking the normality assumption
shapiro.test(T22_larvae) # checking the normality assumption
t.test(C_larvae, T22_larvae,paired = F) # performing Welch Two Sample t-test
```

Statistical analysis for quantification of glycogen deposits (Fig. 2p).

```
C_larvae=c(5.86,5.74,7.69,6.96,6.69) #data input (C-larvae)
T22_larvae=c(15.75,16.51,18.33,12.98,25.44) #data input (T22-larvae)
shapiro.test(C_larvae) #checking the normality assumption
shapiro.test(T22_larvae) # checking the normality assumption
t.test(C_larvae, T22_larvae,paired = F) # performing Welch Two Sample t-test
```

Subsequently all plots have been produced using PRISM:

```
1.	From the Welcome (or New Table and graph) dialog, choose the “Column” tab and choose in “Enter/import data” the option “Enter and plot values already calculated elsewhere”, then in “Enter:” chose “Mean & SEM”. Chose “OK”
2.	Insert the name of the treatment in the column as “Title”
3.	Insert for every group the Mean and SEM in the corrispondent column 
4.	On the left chose from the list in the folder “Graphs” the “Data” sheet.
```

-------------------------------------------------------------------------------------------

## *3. Midgut Gene Differential Expression Analyses*

#### Midgut Gene Differential Expression Analyses - SOFTWARE:

- [STAR v2.7.10a](https://github.com/alexdobin/STAR) - Dobin, A. et al. STAR: ultrafast universal RNA-seq aligner. Bioinformatics 29, 15–21 (2013).
featureCounts - Liao, Y., Smyth, G. K. & Shi, W. featureCounts: an efficient general purpose program for assigning sequence reads to genomic features. Bioinformatics 30, 923–930 (2014).
- [DESeq2](https://bioconductor.org/packages/release/bioc/html/DESeq2.html) - Love, M. I., Huber, W. & Anders, S. Moderated estimation of fold change and dispersion for RNA-seq data with DESeq2. Genome Biol. 15, 1–21 (2014).

#### Midgut Gene Differential Expression Analyses - INPUTS AND INTERMEDIATE FILES:

- raw reads have been deposited under the accessions SRR17054439 - SRR17054444 (BioProject: PRJNA784009)
- normalized counts - ```intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_normalized_counts.csv```
- differential expression results - ```intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_results.csv```
- digestion target genes - *.txt files in the folder ```intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/genes differential_expression_target_genes/```
- proportion of differentially expressed genes among digestion-associated cathegories - ```intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_target_genes.csv```

#### Midgut Gene Differential Expression Analyses - OUTPUTS:

 - Supplementary Table 2
 - Fig. 2j
 - Supplementary Fig. 8a and 8b

#### Midgut Gene Differential Expression Analyses - CODE: gene expression quantification (BASH)

```
fastqc -t 10 -o FastqcOutput/ *.fastq.gz

cutadapt -m 25 --cores 8 -a adapter -A Adapter -o outFile/$trim_R1_001.fastq.gz -p outFile/$trim_R2_001.fastq.gz $_R1_001.fastq.gz $_R2_001.fastq.gz};

STAR --genomeDir $genomeDir --sjdbGTFfile $GTFfile --readFilesIn outFile/$trim_R1_001.fastq.gz outFile/$trim_R2_001.fastq.gz --runThreadN 10 \
     --outSAMtype BAM SortedByCoordinate --readFilesCommand zcat --outFileNamePrefix $outFile/
	 
featureCounts --tmpDir $tmp -F GFF -p -T 10 -s 2 -g ID -a $GTFfile -o $outFile/ $BAM
```

#### Midgut Gene Differential Expression Analyses - CODE: gene differential expression for Supplementary Table 2 (R)

```
setwd("Analisi_Diff2")

require(DESeq2)
Count <- read_excel("Count.xlsx")
matrice=as.data.frame(Count)
sampleFiles <-as.character(colnames(matrice))
sample <- read_excel("sample.xlsx")
sampleCondition=as.data.frame(sample)
sampleTable<-data.frame(sampleName=colnames(matrice), fileName=as.character(sampleFiles), condition=sampleCondition)

dds <- DESeqDataSetFromMatrix(countData = matrice,
                              colData = sampleTable,
                              design = ~ condition)
colData(dds)$condition<-factor(colData(dds)$condition, levels=colnames(sampleCondition))
keep <- rowSums(counts(dds)) >= 10
dds <- dds[keep,]
dds<-DESeq(dds)


res=results(dds, contrast=c("condition",))
res<-res[order(res$padj),]
m=as.data.frame(res)
write.table(m, file="Comparison.txt")
```

#### Midgut Gene Differential Expression Analyses - CODE: multivariate analyses in Supplementary Fig. 8a and 8b (R)

```
# requirements and inputs

library(tidyverse)
library(ggplot2)

theme<-theme(panel.background = element_blank(),panel.border=element_rect(fill=NA),panel.grid.major = element_blank(),panel.grid.minor = element_blank(),strip.background=element_blank(),axis.text.x=element_text(colour="black"),axis.text.y=element_text(colour="black"),axis.ticks=element_line(colour="black"),plot.margin=unit(c(1,1,1,1),"line"))

norm_counts <- as.data.frame(read_tsv("intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_normalized_counts.tsv", col_names = TRUE))

# intro

head(norm_counts,0)
dim(norm_counts)
rownames(norm_counts) <- norm_counts[,1]

# PCA - Fig. 8a

df_pca <- prcomp(sqrt(t(norm_counts[,-1])), center = TRUE, scale = FALSE) 


df_out <- as.data.frame(df_pca$x)
df_out$group <- c("control","control","control","T22","T22","T22")


percentage <- round(df_pca$sdev / sum(df_pca$sdev) * 100, 2)
percentage <- paste( colnames(df_out), "(", paste( as.character(percentage), "%", ")", sep="") )

# clustering Fig. 8b

p <-ggplot(df_out,aes(x=PC1,y=PC2, fill=group)) + coord_fixed() 
p <-p+geom_point(shape=23, size=7, alpha=1) + scale_fill_manual(values = c("white","black"))
p + theme + xlab((summary(df_pca)$importance[2,]*100)[1]) + ylab((summary(df_pca)$importance[2,]*100)[2]) + theme(aspect.ratio=1) +
  stat_ellipse(type = "norm", linetype = 2)

het <- heatmap(as.matrix(t(norm_counts[,-1])), clustering_distance_rows = "pearson",
               clustering_method_rows = "complete", na.rm = TRUE, scale = "column", show_col_names = FALSE,
               gp = gpar(fontsize = 19), col= colorRampPalette(brewer.pal(2, "Blues"))(5))
```


-------------------------------------------------------------------------------------------


#### Midgut Gene Differential Expression Analyses - CODE: target genes analyses in Main Fig. 2j (BASH and R)

- Target genes list were manually curated  from S. littoralis genome and can be found in the folder ```intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_target_genes```.
- DE results relative to target genes were obtained using the following BASH script, for example: ```sh ./extract_target_genes.sh differential_expression_target_genes/lipases.lst.txt```.

```
baseout=$(echo $1 | awk -F '/' '{print $NF}' |  awk -F '.' '{print $1}')
ggrep XP $1 | awk '{print $1}' | sort -u > $baseout"_features.pep_names.tmp"
echo "peptide\ttranscript\t4_padj\t4_logFC\t6_padj\t6_logFC\tproduct" > $baseout".out.tsv"
while read line; 
	do 
	tr=$(ggrep $line enrichment_GCF_002706865.1_ASM270686v1_Spodoptera_littoralis.gtf | ggrep transcript_id | head -1 | awk '{print $12}' | tr -d '";'); 
	padj=$(ggrep $tr Comparison_4Tvs4C.txt | awk '{print $NF}'); if [ -z "$padj" ]; then padj=NA; fi;
	logFC=$(ggrep $tr Comparison_4Tvs4C.txt | awk '{print $3}'); if [ -z "$logFC" ]; then logFC=NA; fi;
	product=$(ggrep "$tr" GCF_002706865.1_ASM270686v1_genomic.gtf | head -1 | awk -F "product" '{print $2}' | awk -F ";" '{print $1}' | tr -d '"')
	echo "$line\t$tr\t$padj\t$logFC\t$product" >> $baseout".out.tsv"; 
done < $baseout"_features.pep_names.tmp"
rm $baseout"_features.pep_names.tmp"
```

Then we used the used the ```differential_expression_target_genes.csv``` to visualize results in R:

```
# requirements and inputs

library(ggplot2)
library(tidyr)
df <- read.table("intermediate_files/3_Midgut_Gene_Differential_Expression_Analyses/differential_expression_target_genes.csv",header=TRUE, sep = ";")

#

long <- df %>% gather(de, nonde, -c(class))

ggplot(long, aes(fill=de, y=class, x=nonde)) + 
  geom_bar(position="fill", stat="identity", width = 0.75) +
  scale_fill_manual(values = c("darkgray", "lightgray")) +
  theme_minimal() +
  theme(panel.grid.major = element_blank(), panel.grid.minor = element_blank(),
        panel.background = element_blank(), axis.line = element_line(colour = "black"))
```

-------------------------------------------------------------------------------------------

## *4. Midgut DE genes GO enrichment*

#### Midgut DE genes GO enrichment - SOFTWARE: 

- [PANNZER2](http://ekhidna2.biocenter.helsinki.fi/sanspanz/) - Törönen, P., Medlar, A. & Holm, L. PANNZER2: a rapid functional annotation web server. Nucleic Acids Res. 46, W84–W88 (2018).
- [TopGO](https://bioconductor.org/packages/release/bioc/html/topGO.html) - Alexa, A. & Rahnenführer, J. TopGO: enrichment analysis for gene ontology. R package version 2.46.0 (2021).
- [REVIGO](http://revigo.irb.hr/) - Supek, F., Bošnjak, M., Škunca, N. & Šmuc, T. REVIGO summarizes and visualizes long lists of gene ontology terms. PloS One 6, e21800 (2011).


#### Midgut DE genes GO enrichment - INPUTS AND INTERMEDIATE FILES: 

- _S. littoralis_ proteome - ```intermediate_files/4_Midgut_DE_genes_GO_enrichment/GCF_002706865.1_ASM270686v1_Spodoptera_littoralis_proteome.faa```
- _S. littoralis_ PANNZER output - ```intermediate_files/4_Midgut_DE_genes_GO_enrichment/enrichment_Spodoptera_littura_PANNZER_output.txt```
- _S. littoralis_ gtf annotation - ```intermediate_files/4_Midgut_DE_genes_GO_enrichment/GCF_002706865.1_ASM270686v1_Spodoptera_littoralis.gtf```
- Upregulated genes - ```intermediate_files/4_Midgut_DE_genes_GO_enrichment/differential_expression_UP_genes.lst```

#### Midgut DE genes GO enrichment - OUTPUTS:

- Fig. 2i
- Supplementary Fig. 3

#### Midgut DE genes GO enrichment - CODE: GOterms functional annotation (online and BASH)

_S. littoralis_ proteome has been uploaded to PANNZER2 webserver. 

Results were initially formatted using the following bash lines:

```
cd intermediate_files/4_Midgut_DE_genes_GO_enrichment/

for i in $(awk '{print $1}' enrichment_Spodoptera_littura_PANNZER_output.txt | sort -u);
	do 
	GO=$(grep $i GO_Spodoptera_littura.txt | awk '{print $3}' | tr '\n' ' ');
	echo -e "\n"; echo $i $GO | sed 's/ / GO:/g';
done > GO_Spodoptera_littura.ref
```

Then to convert protein ids to gene ids :
 
```
while read line; 
	do 
	protein=$(echo $line | awk '{print $1}'); 
	nucleotide=$(ggrep "$protein" GCF_002706865.1_ASM270686v1_Spodoptera_littoralis.gtf | \
	head -1 |  sed -n -e's/^.*transcript_id //p' | awk '{print $1}' | tr -d "\";"); 
	go=$(echo $line | awk '{$1=""; sub("  ", " "); print}'  | sed 's/ /, /g'); 
	echo $nucleotide $go; 
done < GO_Spodoptera_littura_IEA.ref  | sed $'s/ , /\t/g' > Spodoptera_littura_GeneUniverse_TopGO
```

#### Midgut DE genes GO enrichment - CODE: enrichment anlysis with TopGO and REVIGO in Main Fig. 2i and Supplementary Fig. 3 (R):

```
# requirements and inputs

require(ggplot2)
library(tidyr)
library(topGO)

geneID2GO <- readMappings(file = "intermediate_files/4_Midgut_DE_genes_GO_enrichment/enrichment_spodoptera_littura_GeneUniverse_TopGO")
genesOfInterest <- read.table("intermediate_files/4_Midgut_DE_genes_GO_enrichment/enrichment_expression_UP_genes.lst.txt",header=FALSE)

# intro

geneUniverse <- names(geneID2GO)
genesOfInterest <- as.character(genesOfInterest$V1)
geneList <- factor(as.integer(geneUniverse %in% genesOfInterest))
names(geneList) <- geneUniverse
myGOdata <- new("topGOdata", description="My project", ontology="BP", allGenes=geneList,  annot = annFUN.gene2GO, gene2GO = geneID2GO, nodeSize=3)
myGOdata

# Biological_Processes - Main Fig. 2i

BP_UP_classic_fisher <- runTest(myGOdata, algorithm="classic", statistic="fisher")
BP_UP_allRes <- GenTable(myGOdata, 
                                Classic_Fisher = BP_UP_classic_fisher,
                                orderBy = "Classic_Fisher", topNodes=1000)
BP_UP_allRes$Classic_Fisher <- as.numeric(BP_UP_allRes$Classic_Fisher)
BP_UP_allRes <- subset(BP_UP_allRes, Classic_Fisher < 0.01)
BP_UP_allRes$n=(BP_UP_allRes$Significant)
BP_UP_allRes <- subset(BP_UP_allRes, select=-c(Significant,Expected))
BP_UP_allRes$n=(round(BP_UP_allRes$n,2))
BP_UP_allRes$Classic_Fisher=(round(-log10(as.numeric(BP_UP_allRes$Classic_Fisher)),2))
BP_UP_allRes <- BP_UP_allRes[c("GO.ID","Term","Annotated","n","Classic_Fisher")]
colnames(BP_UP_allRes) <- c("id","Upregulated Terms (BP) in 4th instar","Total","DE","-log10p")
write.csv(BP_UP_allRes,"intermediate_files/4_Midgut_DE_genes_GO_enrichment/BP_UP.csv", row.names = FALSE)

### TopGO output is uploaded to REVIGO and the generated plot is plotted using ggplot2

revigo.names <- c("term_ID","description","frequency_%","plot_X","plot_Y","plot_size","value","uniqueness","DE");
revigo.data <- rbind(c("GO:0006690","icosanoid metabolic process",0.035,-6.588,-0.117,0.699,2.300,0.951,2),
                     c("GO:0008152","metabolic process",41.999,4.500,-3.172,3.678,2.600,1.000,44),
                     c("GO:0009617","response to bacterium",2.159,5.157,3.285,2.391,4.620,0.493,7),
                     c("GO:0044419","biological process involved in interspecies interaction",3.816,4.233,-4.834,2.637,2.270,1.000,7),
                     c("GO:0055114","oxidation-reduction process",100.000,-3.844,-3.796,2.818,4.720,1.000,18),
                     c("GO:0006629","lipid metabolic process",4.803,-4.640,5.900,2.737,2.140,0.922,10),
                     c("GO:0008202","steroid metabolic process",0.485,-1.533,7.817,1.748,2.130,0.935,3),
                     c("GO:0006508","proteolysis",7.825,-3.671,4.406,2.949,3.720,0.920,16),
                     c("GO:0009607","response to biotic stimulus",3.551,4.777,4.995,2.606,2.900,0.768,7),
                     c("GO:0019731","antibacterial humoral response",0.247,5.292,2.562,1.462,2.270,0.560,2));

one.data <- data.frame(revigo.data);
names(one.data) <- revigo.names;
one.data <- one.data [(one.data$plot_X != "null" & one.data$plot_Y != "null"), ];
one.data$plot_X <- as.numeric( as.character(one.data$plot_X) );
one.data$plot_Y <- as.numeric( as.character(one.data$plot_Y) );
one.data$plot_size <- as.numeric( as.character(one.data$plot_size) );
one.data$value <- as.numeric( as.character(one.data$value) );
one.data$frequency <- as.numeric( as.character(one.data$frequency) );
one.data$uniqueness <- as.numeric( as.character(one.data$uniqueness) );
one.data$DE <- as.numeric(as.character(one.data$DE));

BP_UP <- ggplot(data = one.data,aes(plot_X, plot_Y, size=DE, color = value));
BP_UP <- BP_UP + geom_point(alpha=I(1),show.legend = TRUE) + scale_size_area();
BP_UP <- BP_UP + scale_colour_gradient(low = "orange", high = "red")
BP_UP <- BP_UP + scale_size(range=c(5, 30)) + theme_bw();
ex <- one.data [ one.data$frequency > 0,];
BP_UP <- BP_UP + geom_text( data=ex,aes(plot_X, plot_Y,label = description),size = 5,hjust="inward", color="black");
#BP_UP <- BP_UP + theme(legend.key=element_blank()) ;
one.x_range = max(one.data$plot_X) - min(one.data$plot_X);
one.y_range = max(one.data$plot_Y) - min(one.data$plot_Y);
BP_UP <- BP_UP + xlim(min(one.data$plot_X)-one.x_range/10,max(one.data$plot_X)+one.x_range/10);
BP_UP <- BP_UP + ylim(min(one.data$plot_Y)-one.y_range/10,max(one.data$plot_Y)+one.y_range/10);
BP_UP <- BP_UP + xlim(-8, 8) + ylim(-8, 8) + coord_fixed()

## Molecular_Functions - Supplementary Fig. 3

genesOfInterest <- read.table("differential_expression_UP_genes.lst",header=FALSE)
genesOfInterest <- as.character(genesOfInterest$V1)
geneList <- factor(as.integer(geneUniverse %in% genesOfInterest))
names(geneList) <- geneUniverse
myGOdata <- new("topGOdata", description="My project", ontology="MF", allGenes=geneList,  annot = annFUN.gene2GO, gene2GO = geneID2GO, nodeSize=3)
myGOdata
BP_UP_classic_fisher <- runTest(myGOdata, algorithm="classic", statistic="fisher")
BP_UP_allRes <- GenTable(myGOdata, 
                                Classic_Fisher = BP_UP_classic_fisher,
                                orderBy = "Classic_Fisher", topNodes=1000)
BP_UP_allRes$Classic_Fisher <- as.numeric(BP_UP_allRes$Classic_Fisher)
BP_UP_allRes <- subset(BP_UP_allRes, Classic_Fisher < 0.01)
BP_UP_allRes$n=(BP_UP_allRes$Significant)
BP_UP_allRes <- subset(BP_UP_allRes, select=-c(Significant,Expected))
BP_UP_allRes$n=(round(BP_UP_allRes$n,2))
BP_UP_allRes$Classic_Fisher=(round(-log10(as.numeric(BP_UP_allRes$Classic_Fisher)),2))
BP_UP_allRes <- BP_UP_allRes[c("GO.ID","Term","Annotated","n","Classic_Fisher")]
colnames(BP_UP_allRes) <- c("id","Upregulated Terms (MF) in 4th instar","Total","DE","-log10p")
write.csv(BP_UP_allRes,"./intermediate_files/4_Midgut_DE_genes_GO_enrichment/MF_UP.csv", row.names = FALSE)

### TopGO output is uploaded to REVIGO and the generated plot is plotted using ggplot2

revigo.names <- c("term_ID","description","frequency","plot_X","plot_Y","log_size","value","uniqueness","DE");
revigo.data <- rbind(c("GO:0003824","catalytic activity",36.0641373871901,0.0234793999859198,-5.44743244737403,3.61458086699749,11.21,1,53),
                     c("GO:0004252","serine-type endopeptidase activity",2.42705686497853,3.17366483114428,4.77173807584345,2.44404479591808,9.28,0.490171722841365,14),
                     c("GO:0004364","glutathione transferase activity",0.350477525628669,-4.28196826132176,5.07494675373861,1.61278385671974,3.42,0.646953634323536,3),
                     c("GO:0016787","hydrolase activity",15.8941557872601,0.180607715402115,6.14385167899786,3.25887662937213,5.92,0.656676449724219,32),
                     c("GO:0016825","hydrolase activity, acting on acid phosphorus-nitrogen bonds",0.0438096907035836,6.11472336050376,4.69328089661152,0.778151250383644,8.52,0.685674572158385,14),
                     c("GO:0016491","oxidoreductase activity",5.78287917287304,0.277589562258674,7.79533236360951,2.82020145948564,4.4,0.69633831958126,17),
                     c("GO:0102756","very-long-chain 3-ketoacyl-CoA synthase activity",0.175238762814335,-4.31929038118813,2.07701460727189,1.32221929473392,3.07,0.594578202565494,3),
                     c("GO:0004806","triglyceride lipase activity",0.499430474020853,4.34738977576005,2.08225356359957,1.76342799356294,4.19,0.516603817095553,5),
                     c("GO:0008194","UDP-glycosyltransferase activity",0.96381319547884,-3.17294056228571,4.49418309035638,2.04532297878666,2.91,0.556248273882106,4),
                     c("GO:0016765","transferase activity, transferring alkyl or aryl (other than methyl) groups",0.595811793568737,-3.4983186726064,3.70923410018904,1.83884909073726,2.2,0.631480535811859,3),
                     c("GO:0017171","serine hydrolase activity",3.13677385437659,2.60788836370135,3.51439788655886,2.55509444857832,8.52,0.547258988206564,14),
                     c("GO:0016788","hydrolase activity, acting on ester bonds",4.608779462017,2.43875753458385,4.1789563609817,2.72181061521255,5.04,0.529167419529517,15),
                     c("GO:0016298","lipase activity",0.849907999649522,4.06884400962198,2.92438949261325,1.99122607569249,3.05,0.532669893772496,5),
                     c("GO:0102336","3-oxo-arachidoyl-CoA synthase activity",0.136040618500602,-4.51465919983889,1.56524660451144,1.20411998265592,3.07,0.601409832019768,3),
                     c("GO:0102337","3-oxo-cerotoyl-CoA synthase activity",0.136040618500602,-4.86180913138599,2.24141297668935,1.20411998265592,3.07,0.601409832019768,3),
                     c("GO:0102338","3-oxo-lignoceronyl-CoA synthase activity",0.136040618500602,-4.97832299381935,2.82252440497418,1.20411998265592,3.07,0.601409832019768,3),
                     c("GO:0052689","carboxylic ester hydrolase activity",1.27924296854464,3.48657639074235,2.45761679174962,2.16731733474818,11.51,0.516469566490386,14),
                     c("GO:0008970","phospholipase A1 activity",0.00876193814071673,5.52957819259176,0.759144742180937,0.301029995663981,2.82,0.629339434751816,16));

one.data <- data.frame(revigo.data);
names(one.data) <- revigo.names;
one.data <- one.data [(one.data$plot_X != "null" & one.data$plot_Y != "null"), ];
one.data$plot_X <- as.numeric( as.character(one.data$plot_X) );
one.data$plot_Y <- as.numeric( as.character(one.data$plot_Y) );
one.data$plot_size <- as.numeric( as.character(one.data$plot_size) );
one.data$value <- as.numeric( as.character(one.data$value) );
one.data$frequency <- as.numeric( as.character(one.data$frequency) );
one.data$uniqueness <- as.numeric( as.character(one.data$uniqueness) );
one.data$DE <- as.numeric( as.character(one.data$DE));

MF_UP <- ggplot(data = one.data,aes(plot_X, plot_Y, size=DE, color = value));
MF_UP <- MF_UP + geom_point(alpha=I(1),show.legend = TRUE) + scale_size_area();
MF_UP <- MF_UP + scale_colour_gradient(low = "orange", high = "red")
MF_UP <- MF_UP + scale_size(range=c(5, 30)) + theme_bw();
ex <- one.data [ one.data$frequency > 0,];
MF_UP <- MF_UP + geom_text( data=ex,aes(plot_X, plot_Y,label = description),size = 5,hjust="inward", color="black");
one.x_range = max(one.data$plot_X) - min(one.data$plot_X);
one.y_range = max(one.data$plot_Y) - min(one.data$plot_Y);
MF_UP <- MF_UP + xlim(min(one.data$plot_X)-one.x_range/10,max(one.data$plot_X)+one.x_range/10);
MF_UP <- MF_UP + ylim(min(one.data$plot_Y)-one.y_range/10,max(one.data$plot_Y)+one.y_range/10);
MF_UP <- MF_UP + xlim(-8, 8) + ylim(-8, 8) + coord_fixed()
```

-------------------------------------------------------------------------------------------

## *5. Targeted Metagenome Taxonomy Analyses*

#### Targeted Metagenome Taxonomy Analyses - SOFTWARE:

- [QUIME2 v2020.8](https://github.com/qiime2/qiime2) - Bolyen, E. et al. Reproducible, interactive, scalable and extensible microbiome data science using QIIME 2. Nat Biotechnol. 37, 852–857 (2019).

#### Targeted Metagenome Taxonomy Analyses - INPUTS AND INTERMEDIATE FILES

- raw reads have been deposited under the accessions SRR17050410 - SRR17050419 (BioProject: PRJNA784009).
- tab-separated values file reporting the path to the fastq files obtained for each sample - ```intermediate_files/5_Targeted_Metagenome_Taxonomy_Analyses/ manifest.tsv```
- tab-separated values file reporting the type of plants on which larvae of each sample were reared (control = C-larvae, T22 = T22-larvae) - ```intermediate_files/5_Targeted_Metagenome_Taxonomy_Analyses/metadata.tsv"```
- Reference database (16S rRNA SILVA database release 138):
  - [silva-138-99-seqs.qza](https://data.qiime2.org/2020.8/common/silva-138-99-seqs.qza) reference sequences 
  - [silva-138-99-tax.qza](https://data.qiime2.org/2020.8/common/silva-138-99-tax.qza) taxonomic assignments of the reference sequences

#### Targeted Metagenome Taxonomy Analyses - OUTPUT:

- Main Fig. 3a
- Supplementary Fig. 8
- Supplementary Table 4

#### Targeted Metagenome Taxonomy Analyses - CODE: import data (BASH)

```
qiime tools import \
  --type 'SampleData[PairedEndSequencesWithQuality]' \
  --input-path manifest.tsv \
  --output-path seqs.qza \
  --input-format PairedEndFastqManifestPhred33
```

#### Targeted Metagenome Taxonomy Analyses - CODE: denoising and filtering with dada2 (BASH)

```
qiime dada2 denoise-paired \
  --i-demultiplexed-seqs seqs.qza \
  --p-trim-left-f 17 \
  --p-trim-left-r 21 \
  --p-trunc-len-f 250 \
  --p-trunc-len-r 250 \
  --p-max-ee-f 2 \
  --p-max-ee-r 2 \
  --p-trunc-q 2 \
  --p-pooling-method independent \
  --p-chimera-method consensus \
  --p-min-fold-parent-over-abundance 1.0 \
  --p-n-reads-learn 1000000 \
  --o-table table.qza \
  --o-representative-sequences rep-seqs.qza \
  --o-denoising-stats denoising-stats.qza
```

#### Targeted Metagenome Taxonomy Analyses - CODE: taxonomic assignment (BASH)

Trim the full length 16S rRNA reference sequences to the region actually amplified.

```
qiime feature-classifier extract-reads \
  --i-sequences silva-138-99-seqs.qza \
  --p-f-primer CCTACGGGNGGCWGCAG \
  --p-r-primer GACTACHVGGGTATCTAATCC \
  --p-identity 0.8 \
  --p-min-length 150 \
  --p-max-length 500 \
  --o-reads silva-138-99_V3V4-ref-seqs.qza
```

Generate class weights to increase classification accuracy with the q2-clawback plugin.

```
qiime feature-classifier fit-classifier-naive-bayes \
  --i-reference-reads silva-138-99_V3V4-ref-seqs.qza \
  --i-reference-taxonomy silva-138-99-tax.qza \
  --o-classifier NBclassifier_silva-138-99_V3V4.qza

qiime feature-classifier classify-sklearn \
  --i-classifier NBclassifier_silva-138-99_V3V4.qza \
  --i-reads rep-seqs.qza \
  --p-confidence=disable \ 
  --o-classification no-confidence-classification.qza

qiime clawback generate-class-weights \
  --i-reference-taxonomy silva-138-99-tax.qza \ 
  --i-reference-sequences silva-138-99_V3V4-ref-seqs.qza \ 
  --i-samples table.qza \
  --i-taxonomy-classification no-confidence-classification.qza \
  --o-class-weight weights.qza
```

Train the naive Bayes classifier and use it for the taxonomic classification.

```
qiime feature-classifier fit-classifier-naive-bayes \
  --i-reference-reads silva-138-99_V3V4-ref-seqs.qza \
  --i-reference-taxonomy silva-138-99-tax.qza \
  --i-class-weight weights.qza \
  --o-classifier weighted-classifier.qza

qiime feature-classifier classify-sklearn \
  --i-classifier weighted-classifier.qza \
  --i-reads rep-seqs.qza \
  --p-confidence=0.95 \
  --o-classification taxonomy_weighted.qza
```

#### Targeted Metagenome Taxonomy Analyses - CODE: filter out ASVs assigned to mitochondria and chloroplasts (BASH)

```
qiime taxa filter-table \
  --i-table table.qza \
  --i-taxonomy taxonomy_weighted.qza \
  --p-exclude mitochondria,chloroplast \
  --p-mode contains \
  --o-filtered-table table-filt.qza

qiime taxa filter-seqs \
  --i-sequences rep-seqs.qza \
  --i-taxonomy taxonomy_weighted.qza \
  --p-exclude mitochondria,chloroplast \
  --p-mode contains \
  --o-filtered-sequences rep-seqs-filt.qza
```

#### Targeted Metagenome Taxonomy Analyses - CODE: make one ASV table for each group of samples (BASH)

```
qiime feature-table filter-samples \
  --i-table table-filt.qza \
  --m-metadata-file metadata.tsv \
  --p-where "[Group]='control'" \
  --o-filtered-table table-filt-control.qza
  
qiime feature-table filter-samples \
  --i-table table-filt.qza \
  --m-metadata-file metadata.tsv \
  --p-where "[Group]='T22'" \
  --o-filtered-table table-filt-T22.qza
```

#### Targeted Metagenome Taxonomy Analyses - CODE: export results (BASH)

```
# tables
qiime tools export \
  --input-path table-filt.qza \
  --output-path exported
biom convert -i exported/feature-table.biom -o exported/feature-table.tsv --to-tsv

qiime tools export \
  --input-path table-filt-T22.qza \
  --output-path exported
biom convert -i exported/feature-table.biom -o exported/feature-table-T22.tsv --to-tsv

qiime tools export \
  --input-path table-filt-control.qza \
  --output-path exported
biom convert -i exported/feature-table.biom -o exported/feature-table-control.tsv --to-tsv

# taxonomy
qiime tools export \
  --input-path taxonomy_weighted.qza \
  --output-path exported

# sequences
qiime tools export \
  --input-path rep-seqs-filt.qza \
  --output-path exported
```

-------------------------------------------------------------------------------------------

## *6. Targeted Metagenome Diversity Analyses*

#### Targeted Metagenome Diversity Analyses - SOFTWARE:

- [R](https://www.R-project.org/) - R Core Team (2021). R: A language and environment for statistical computing (version 4.0.4). R Foundation for Statistical Computing.

    Libraries:
    - [iNEXT](http://johnsonhsieh.github.io/iNEXT/)
    - [ggplot2](https://github.com/tidyverse/ggplot2)

#### Targeted Metagenome Diversity Analyses - INPUTS AND INTERMEDIATE FILES:

- ASV tables by group - ```intermediate_files/6_Targeted_Metatgenome_Diversity_Analyses/feature-table-T22.tsv``` and ```intermediate_files/6_Targeted_Metatgenome_Diversity_Analyses/feature-table-control.tsv```

#### Targeted Metagenome Diversity Analyses - OUTPUTS:

- Fig. 3b

#### Targeted Metagenome Diversity Analyses - CODE: Hills numbers (R)

Install and load required libraries.

```
install.packages("iNEXT")
install.packages("ggplot2")

library(iNEXT)
library(ggplot2)
```

Import tables 

NB: removed the first comment line of the files before importing them in R.

```
data <- list("control"=read.table("exported/feature-table-control.tsv",
                                  row.names=1, header = TRUE, sep="\t", stringsAsFactors = F),
             "T22"=read.table("exported/feature-table-T22.tsv",
                              row.names=1, header = TRUE, sep="\t", stringsAsFactors = F))
```

Convert data to presence-absence.

```
for (i in 1:length(data)) {
  data[[i]][data[[i]]>0] <- 1
}
```

Estimate Hill numbers and plot results.

```
est <- estimateD(data, datatype = "incidence_raw", base="coverage")

ggplot(est, aes(x=as.character(order), y=qD, group=site)) + 
  geom_errorbar(aes(ymin=qD.LCL, ymax=qD.UCL), width=.1, size=.6) +
  scale_x_discrete(labels = c("q=0","q=1","q=2")) +
  geom_point(aes(shape=site),size=c(2.5,2.5,2.5,4,4,4)) +
  scale_shape_manual(values=c(5,18), labels = c("C-larvae","T22-larvae")) +
  xlab("") + ylab("Diversity") +
  theme_classic() +
  theme(legend.position=c(0.32,0.1), legend.direction = "horizontal", legend.background = element_blank(),
        legend.title = element_blank(), 
        legend.text = element_text(size=12),
        legend.key.size = unit(10,unit="pt"),
        axis.text=element_text(size=12), axis.title=element_text(size=14)) +
  scale_y_continuous(limits=c(0,200), breaks = seq(0, 200, by = 50)) 
```

-------------------------------------------------------------------------------------------

## *7. Midgut Metatranscriptome Analyses*

#### Midgut Metatranscriptome Analyses - SOFTWARE:

- [HUMAnN 2.0](https://huttenhower.sph.harvard.edu/humann2/) - Franzosa EA, McIver LJ, Rahnavard G, Thompson LR, Schirmer M, Weingart G, Schwarzberg Lipson K, - Knight R, Caporaso JG, Segata N, Huttenhower C. Species-level functional profiling of metagenomes and metatranscriptomes. Nat Methods 15: 962-968 (2018).
- [MaAsLin2](https://huttenhower.sph.harvard.edu/maaslin) - Mallick H, Rahnavard A, McIver LJ, Ma S, Zhang Y, Nguyen LH, Tickle TL, Weingart G, Ren B, Schwager EH,  Chatterjee S. Multivariable association discovery in population-scale meta-omics studies. PLoS Comput. Biol. 17(11):.e1009442 (2021).

#### Midgut Metatranscriptome Analyses - INPUTS AND INTERMEDIATE FILES:

- raw reads have been deposited under the accessions SRR17050383 - SRR17050387 (BioProject: PRJNA784009)
- metadata ```intermediate_files/7_Midgut_Metatranscriptome_Analyses/metatrascriptomics_metadata.tsv```
- CPM normalized counts - ```intermediate_files/7_Midgut_Metatranscriptome_Analyses/metatranscriptomics_path_abundance_CPM.tsv```

#### Midgut Metatranscriptome Analyses - OUTPUTS:

- Main Fig. 3c
- Supplementary Fig. 4
- Supplementary Fig. 5a and 5b

#### Midgut Metatranscriptome Analyses - CODE: Humann2 analysis (BASH)

```
metaphlan --force --bowtie2_build $PATH:bowtie2-build --nproc 8 .fastq --input_type fastq -o *profiled_metagenome.txt

humann2 --threads 14 --diamond $PATH:diamond --nucleotide-database $PATH:chocophlan --protein-database $PATH:uniref --taxonomic-profile *profiled_metagenome.txt -i *.fastq -o Output/
```

#### Midgut Metatranscriptome Analyses - CODE: Maaslin2 analysis in Main Fig. 3c (R and BASH)

Maaslin2 analysis:

```
# requirements and inputs

require(Maaslin2)

df_input_data = read.table(file = "intermediate_files/7_Midgut_Metatranscriptome_Analyses/metatranscriptomics_path_abundance_CPM.tsv", header = TRUE, sep = "\t",
                           row.names = 1,
                           stringsAsFactors = FALSE)

df_input_metadata = read.table(file = "intermediate_files/7_Midgut_Metatranscriptome_Analyses/metatrascriptomics_metdata.tsv", header = TRUE, sep = "\t",
                               row.names = 1,
                               stringsAsFactors = FALSE)

#

keep_pathways <-function(df_input_data){
  temp = df_input_data[!grepl("\\|",rownames(df_input_data)),]
  return(temp)
}

clean_input <- keep_pathways(df_input_data)

fit_data = Maaslin2(
  input_data = clean_input, 
  input_metadata = df_input_metadata, 
  output = "./intermediate_files/7_Midgut_Metatranscriptome_Analyses/Maaslin2_results",
  transform = "AST",
  analysis_method = "LM",
  fixed_effects = c("Condition"))
```

Subset CPMs to significant pathways with a first kind of formatting:

```
cd intermediate_files/7_Midgut_Metatranscriptome_Analyses/

head -1 metatranscriptomics_path_abundance_CPM.tsv | sed "1s/^/# Pathway /" | awk -F "Pathway" '{print $1"Pathway\t"$2}' \
| tr -d "\"" > significant_results_path_abundance_CPM.tsv

for i in $(awk '{print $2}' Maaslin2_results/significant_results.tsv); do grep $i \
metatranscriptomics_path_abundance_CPM.tsv; done >> significant_results_path_abundance_CPM.tsv
```

Generate tiles and rank pathways based on cumulative abundance in the control microbiota:

```
# requirements and inputs

library(ggplot2)
library(tidyverse)

humann2_pathways <- as.data.frame(read_tsv("intermediate_files/7_Midgut_Metatranscriptome_Analyses/significant_results_path_abundance_CPM.tsv"))

# tiles
humann2_pathways_long <- 
  humann2_pathways %>% 
  #Rename  `# Pathway` as pathway
  rename(pathway = `# Pathway`) %>%
  #Gather cmp by pathway and sampleID
  gather(sampleID, cpm, -pathway) %>% 
  #Separate by sampleID and drop any extra values without warning
  separate(sampleID, "sampleID", sep = "_", extra = "drop") %>% 
  #Separate pathways from organisms using |
  separate(pathway, c("pathway", "organism"), sep = "\\|", fill = "right")

# generate pathway table with no organism stratifications
humann2_pathways_no_stratifications_long <-
  humann2_pathways_long %>%
  filter(is.na(organism)) %>%
  select(-organism) %>%
  filter(!(grepl("^UN", pathway))) 

plot <- ggplot(humann2_pathways_no_stratifications_long, aes(sampleID, pathway, fill= cpm)) + 
  geom_tile(color = "black", size = 0.5, width=0.7, height=0.7) + 
  scale_fill_gradient2(low="#afd9e5", mid="white", high="#fca428", limits=c(0,1200)) +
  coord_equal() + theme_minimal()

# ranking

humann2_pathways_no_stratifications_long_C <- subset(humann2_pathways_no_stratifications_long, sampleID == "C")
humann2_pathways_no_stratifications_long_C <- humann2_pathways_no_stratifications_long_C %>% group_by(pathway) %>%summarize(cpm = sum(cpm))
humann2_pathways_no_stratifications_long_C <- humann2_pathways_no_stratifications_long_C[order(humann2_pathways_no_stratifications_long_C$cpm),]

```

Subset CPMs to significant pathways with a second kind of formatting:

```

a=$(head -1 metatranscriptomics_path_abundance_CPM.tsv | tr -d "\""); echo -e "# Pahtway\tstrata\t$a" > significant_results_path_abundance_CPM_alternative.tsv

for i in $(awk '{print $2}' Maaslin2_results/significant_results.tsv); do grep $i \
metatranscriptomics_path_abundance_CPM.tsv; done | grep "g__" | awk -F "|" '{print $1"\t"$2}' >> \
significant_results_path_abundance_CPM_alternative.tsv

sed -i 's/\"//g' significant_results_path_abundance_CPM_alternative.tsv

```

Generate piecharts:

```
# requirements and inputs

library(tidyverse)
library(ggplot2)

DE_pathways_stage_strata_abundances <- as.data.frame(read_tsv("./intermediate_files/7_Midgut_Metatranscriptome_Analyses/significant_results_path_abundance_CPM_alternative.tsv"))

#

colnames(DE_pathways_stage_strata_abundances) 

DE_pathways_stage_strata_abundances$mean_control<- rowMeans(DE_pathways_stage_strata_abundances[,6:8])
DE_pathways_stage_strata_abundances$mean_treatment<- rowMeans(DE_pathways_stage_strata_abundances[,3:5])

DE_pathways_stage_strata_abundances <- DE_pathways_stage_strata_abundances[,-(3:8)]

colnames(DE_pathways_stage_strata_abundances) <- c("Pathway", "strata", "mean_control", "mean_treatment")

DE_pathways_stage_strata_abundances_total_control <- aggregate(DE_pathways_stage_strata_abundances$mean_control, by=list("Pathway"=DE_pathways_stage_strata_abundances$Pathway), FUN=sum)
colnames(DE_pathways_stage_strata_abundances_total_control) <- c("Pathway", "mean_control_total")

DE_pathways_stage_strata_abundances_total_treatment <- aggregate(DE_pathways_stage_strata_abundances$mean_treatment, by=list("Pathway"=DE_pathways_stage_strata_abundances$Pathway), FUN=sum)
colnames(DE_pathways_stage_strata_abundances_total_treatment) <- c("Pathway", "mean_treatment_total")

DE_pathways_stage_strata_abundances_total_ <- merge(DE_pathways_stage_strata_abundances_total_treatment, DE_pathways_stage_strata_abundances_total_control, by="Pathway")

colnames(DE_pathways_stage_strata_abundances)
colnames(DE_pathways_stage_strata_abundances_total_)


DE_pathways_stage_strata_abundances <- DE_pathways_stage_strata_abundances %>% left_join(DE_pathways_stage_strata_abundances_total_, by="Pathway")

colnames(DE_pathways_stage_strata_abundances)

DE_pathways_stage_strata_abundances$perc_control <- DE_pathways_stage_strata_abundances$mean_control/DE_pathways_stage_strata_abundances$mean_control_total*100
DE_pathways_stage_strata_abundances$perc_treatment <- DE_pathways_stage_strata_abundances$mean_treatment/DE_pathways_stage_strata_abundances$mean_treatment_total*100

DE_pathways_stage_strata_abundances_control <- subset(DE_pathways_stage_strata_abundances, mean_control > 0)
c <- ggplot(DE_pathways_stage_strata_abundances_control, aes(fill=strata, y=mean_control, x="")) + 
  geom_bar(stat = "identity", position = position_fill()) + theme_void() + 
  scale_fill_manual("legend", values = c("g__Enterococcus.s__Enterococcus_casseliflavus"="#23CE6B",
                                         "g__Propionibacterium.s__Propionibacterium_acnes"="#EB5E55",
                                         "g__Enterococcus.s__Enterococcus_mundtii"="#235789",
                                         "g__unclassified"="#F1D302")) +
  coord_polar(theta = "y") +
  facet_wrap(~ Pathway)  +
  theme(axis.title.x = element_blank(),
        axis.title.y = element_blank()) + 
  theme(legend.position='top') + guides(fill=guide_legend(nrow=2, byrow=TRUE)) +
  theme(strip.text.x = element_text(size = 5)) + ggtitle('control')


DE_pathways_stage_strata_abundances_treatment <- subset(DE_pathways_stage_strata_abundances, mean_treatment > 0)
t <- ggplot(DE_pathways_stage_strata_abundances_treatment, aes(fill=strata, y=mean_treatment, x="")) + 
  geom_bar(stat = "identity", position = position_fill()) + theme_void() +
  scale_fill_manual("legend", values = c("g__Enterococcus.s__Enterococcus_casseliflavus"="#23CE6B",
                                         "g__Propionibacterium.s__Propionibacterium_acnes"="#EB5E55",
                                         "g__Enterococcus.s__Enterococcus_mundtii"="#235789",
                                         "g__unclassified"="#F1D302",
                                         "g__Sanguibacter.s__Sanguibacter_keddieii"="#F1D302",
                                         "g__Staphylococcus.s__Staphylococcus_caprae_capitis"="#F1D302",
                                         "g__Enhydrobacter.s__Enhydrobacter_aerosaccus"="#F1D302",
                                         "g__Kocuria.s__Kocuria_rhizophila"="#F1D302")) +
  coord_polar(theta = "y") + 
  facet_wrap(~ Pathway)  +
  theme(axis.title.x = element_blank(),
        axis.title.y = element_blank()) + 
  theme(legend.position='top') + guides(fill=guide_legend(nrow=2, byrow=TRUE)) +
  theme(strip.text.x = element_text(size = 5)) + ggtitle('treatment')
```

-------------------------------------------------------------------------------------------

#### Midgut Metatranscriptome Analyses - CODE: Multivariate analyses in Supplementary Fig. 5a and 5b (R)

```
# requirements and inputs

library(tidyverse)
library(ComplexHeatmap)
library(RColorBrewer)

theme<-theme(panel.background = element_blank(),panel.border=element_rect(fill=NA),panel.grid.major = element_blank(),panel.grid.minor = element_blank(),strip.background=element_blank(),axis.text.x=element_text(colour="black"),axis.text.y=element_text(colour="black"),axis.ticks=element_line(colour="black"),plot.margin=unit(c(1,1,1,1),"line"))

humann2_pathways = read.table(file = "./intermediate_files/7_Midgut_Metatranscriptome_Analyses/metatranscriptomics_path_abundance_CPM.tsv", header = TRUE, sep = "\t",
                              row.names = 1,
                              stringsAsFactors = FALSE)

# PCA - Fig. 5a

keep_pathways <-function(df_input_data){
  temp = df_input_data[!grepl("\\|",rownames(df_input_data)),]
  return(temp)
}

humann2_pathways <- keep_pathways(humann2_pathways)
humann2_pathways <- humann2_pathways[-1, ]
humann2_pathways <- humann2_pathways[-1, ]
df_pca <- prcomp(sqrt(t(humann2_pathways)), center = TRUE, scale = FALSE)
df_out <- as.data.frame(df_pca$x)
df_out$group <- c("T22","T22","T22","control","control","control")
percentage <- round(df_pca$sdev / sum(df_pca$sdev) * 100, 2)
percentage <- paste( colnames(df_out), "(", paste( as.character(percentage), "%", ")", sep="") )

p <-ggplot(df_out,aes(x=PC1,y=PC2, fill=group)) + coord_fixed() 
p <-p+geom_point(shape=23, size=7, alpha=1) + scale_fill_manual(values = c("white","black"))
p + theme + xlab((summary(df_pca)$importance[2,]*100)[1]) + ylab((summary(df_pca)$importance[2,]*100)[2]) + theme(aspect.ratio=1) +
  stat_ellipse(type = "norm", linetype = 2)

# clustering - Fig. 5B

heatmap(as.matrix(t(humann2_pathways)), clustering_distance_rows = "pearson",
        clustering_method_rows = "complete", na.rm = TRUE, scale = "column", show_col_names = FALSE,
        gp = gpar(fontsize = 5), col= colorRampPalette(brewer.pal(2, "Blues"))(5))
```

-------------------------------------------------------------------------------------------

## *8. Metabolomics Analyses*

#### Metabolomics analyses - SOFTWARE:
  
- [MSConvertGUI](https://proteowizard.sourceforge.io/tools.shtml) - Chambers, M., Maclean, B., Burke, R. et al. A cross-platform toolkit for mass spectrometry and proteomics. Nat Biotechnol 30, 918–920 (2012).  
- [XCMSOnline](https://xcmsonline.scripps.edu/landing_page.php?pgcontent=mainPage) - Tautenhahn, R., Patti, G. J., Rinehart, D. & Siuzdak, G. XCMS Online: a web-based platform to process untargeted metabolomic data. Anal Chem. 84, 5035–5039 (2012).
- [ggplot2](https://ggplot2.tidyverse.org/) - Wickham, H. ggplot2: Elegant Graphics for Data Analysis (Springer, 2016)..

#### Metabolomics analyses - INPUTS AND INTERMEDIATE FILES:

- mzML files - ```intermediate_files/```
- table of differentially accumulated metabolites (DAMs) - ```intermediate_files/8_Metabolomics_Analyses/metabolomics_differential_abundance_results.csv```
- table of metabolites abundances - ```intermediate_files/8_Metabolomics_Analyses/8_Metabolomics_Analyses/metabolomics_all_data_PCA.csv```

#### Metabolomics analyses - OUTPUTS:

- Main Fig. 4a and 4b
- Supplementary Table 5

#### Metabolomics analyses - COMMANDS (MSConvertGUI and XCMSOnline)

```
- Conversion of 12 raw files, 6 for each condition ( 4th instar C-larvae, C_L4,  and 4th instar T22-larvae, T22_L4)  into mzML files with MSConvertGUI (ProteoWizard).
- Converted files have been processed with XCMS Online as following:
	1. Create a Job;
	2. Choose “Pairwise” as the experimental design;
	3. Upload the Datasets (Dataset 1 is the C_L4 and Dataset 2 is the T22_L4) ;
	4. Select Parameter Set.  XCMX Online predefined parameter has been used: UPLC/Q-exactive (3110).
	5. Submit the Job.

The DAMs final list was manually curated from the “Results table” as following: 
- select and delete all the repeated m/z;
- filter the m/z on the basis of p-value ≤ 0.05
```

#### Metabolomics analyses - CODE: visualyze results in Main Fig. 4b (R)
  
```
# requirements and inputs

library(ggplot2)
library(tidyverse)

theme<-theme(panel.background = element_blank(),panel.border=element_rect(fill=NA),panel.grid.major = element_blank(),panel.grid.minor = element_blank(),strip.background=element_blank(),axis.text.x=element_text(colour="black"),axis.text.y=element_text(colour="black"),axis.ticks=element_line(colour="black"),plot.margin=unit(c(1,1,1,1),"line"))
df <- read.csv(file="intermediate_files/8_Metabolomics_Analyses/metabolomics_differential_abundance_results.csv", sep=";", header=T)

## barplot - Main Fig. 4b

df <- df[,c(12,17,18)]

df <- df %>% arrange(New.Metabolic.Classes)

df <- subset(df, New.Metabolic.Classes != "nd")

filter <- table(df$New.Metabolic.Classes)
filter <- data.frame(filter)
filter <- subset(filter, Freq > 4)
filter$id <- seq(1,nrow(filter))

df <- df[df$New.Metabolic.Classes %in% filter$Var1, ]

df_up <- df[which(df$Regulation=='UP'),][,2:3]
df_up$direction <- "UP"
df_up$value <- 1

df_dn <- df[which(df$Regulation=='DOWN'),][,2:3]
df_dn$direction <- "DN"
df_dn$value <- -1

df <- rbind(df_dn,df_up)

  ggplot(df, aes(x = forcats::fct_rev(New.Metabolic.Classes), y = value, fill = Origin)) +
  geom_col(width=0.7) + coord_flip() +
  theme_minimal() + 
    geom_hline(yintercept=0, color = "black", size=1) +
    geom_hline(yintercept=10, color = "gray", size=0.1) +
    geom_hline(yintercept=-10, color = "gray", size=0.1) +
    geom_hline(yintercept=20, color = "gray", size=0.1) +
    geom_hline(yintercept=-20, color = "gray", size=0.1) +
    ggtitle("metabolites") + scale_fill_manual(values = c("darkorchid1","burlywood4","slateblue","mediumvioletred","darkgoldenrod1","forestgreen","indianred1","gray")) +
    theme(plot.title = element_text(hjust = 0.5)) + theme(plot.title = element_text(size=22)) + 
    theme(legend.position="bottom") +  
    theme(axis.title.x=element_blank()) +
    theme(axis.title.y=element_blank()) +
    theme(axis.text.y   = element_text(size=14),
          axis.text.x   = element_text(size=18),
          axis.title.y  = element_text(size=0),
          axis.title.x  = element_text(size=0),
          panel.background = element_blank(),
          #panel.grid.major = element_blank(), 
          #panel.grid.minor = element_blank(),
          axis.line = element_line(colour = "black"),
          panel.border = element_rect(colour = "black", fill=NA, size=1)
    ) + theme(legend.text=element_text(size=18)) +
    theme(legend.title = element_text(size=0))
```

#### Metabolomics analyses - CODE: visualyze bubbleplot in Main Fig. 4a (R)

```
# requirements and inputs

library(ggplot2)
library(tidyverse)

df <- read.csv(file="intermediate_files/8_Metabolomics_Analyses/metabolomics_significant_bubbleplot.csv", sep=";", header=T)
annot <- read.csv(file="intermediate_files/8_Metabolomics_Analyses/metabolomics_differential_abundance_results.csv", sep=";", header=T)

theme<-theme(panel.background = element_blank(),panel.border=element_rect(fill=NA),panel.grid.major = element_blank(),panel.grid.minor = element_blank(),strip.background=element_blank(),axis.text.x=element_text(colour="black"),axis.text.y=element_text(colour="black"),axis.ticks=element_line(colour="black"),plot.margin=unit(c(1,1,1,1),"line"))

# bubbleplot - Main Fig. 4a

df <- as.data.frame(df)
annot <- as.data.frame(annot)

df <- df %>% 
  full_join(annot, by = c("featureidx")) 

df <- df[,c(1,2,16,23,24,25)]

df$log2.FOLD <- as.numeric(gsub(",", ".", gsub("\\.", "", df$log2.FOLD)))
df$RT <- as.numeric(gsub(",", ".", gsub("\\.", "", df$RT)))
df$p.value <- as.numeric(gsub(",", ".", gsub("\\.", "", df$p.value)))
df$p.value <- (-log10(df$p.value))
df$p.value <- round(df$p.value,3)
colnames(df) <- c("featureidx", "m.z.x","RT", "log2.FOLD", "neg_log10p", "Regulation")

df_dn <- subset(df, Regulation == "DOWN")
df_up <- subset(df, Regulation == "UP")
df_dn$m.z.x <- df_dn$m.z.x * -1

df <- rbind(df_dn,df_up)

ggplot(data = df, mapping=aes(x=RT, y=m.z.x, size=abs(neg_log10p), fill=log2.FOLD)) + 
  geom_point(pch=21, alpha = 1) + theme +
  scale_size(range = c(.01, 30)) + scale_fill_gradient2(low="blue", mid="white",high="red") +
  coord_fixed(ratio=-0.005)+
  ylim(-1400, 1000) + geom_hline(yintercept=0, linetype="dashed", color = "black", size=0.5)

```

-------------------------------------------------------------------------------------------

## *9. Taxonomic identification of isolated Enterococcus*

#### Taxonomic identification of isolated Enterococcus - SOFTWARE:

- [blast online](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE=Nucleotides&PROGRAM=blastn&BLAST_PROGRAMS=megaBlast&PAGE_TYPE=BlastSearch&DBSEARCH=true) - 

#### Taxonomic identification of isolated Enterococcus - INPUTS AND INTERMEDIATE FILES:

- chromatogram files in .ab1 format are in - ```raw_data/9_Taxonomic_Identification_of_Isolated_Enterococcus/```
- sequence files in .fasta format are in - ```raw_data/9_Taxonomic_Identification_of_Isolated_Enterococcus/```

#### Taxonomic identification of isolated Enterococcus - OUTPUTS:

- molecular identification presented in the main text

#### Taxonomic identification of isolated Enterococcus - COMMANDS:

```
1. For each gene fragment, reverse and forward .ab1 files were visually inspected and subsequenyly converted into a consensus sequence using Geneious 10.2.
2. The .fasta files were uploaded on the blast online platform, checking the "Sequences from type material" box.
```

-------------------------------------------------------------------------------------------
