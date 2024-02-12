Welcome to NEMATOR! 

Analyzing Soil Nematode Communities

----------------------------------------------------------------------
Version 1.0 
----------------------------------------------------------------------

## Overview

Nemator is an R script developed for the comprehensive analysis of soil nematode communities. 
It calculates a wide range of metrics and indices for nematode analyses.
This tool is designed to assist researchers in understanding the biodiversity, structure, and function of nematode communities in soil ecosystems.

## Requirements
- R (version 3.5 or higher recommended).
- R packages: ape, asbio, picante, vegan, FD, dplyr, tidyr, hillR, funrar, rotl, CommEcol, betapart, zetadiv

## Installation
1. Install R from [CRAN](https://cran.r-project.org).
2. Install the required R packages.

## Databases
Community Data: A table with nematode taxa (columns) and their abundances across different samples (rows). I recommand using absolute abundances for taxa.
Nemaffilitation : A table with information on the diet [1], life cycle [2,3], and other relevant traits of the nematode taxa from NEMAPLEX (http://nemaplex.ucdavis.edu/).

## Output Description
The script generates several output files including:
nemator.alpha.data.csv: Comprehensive dataset with all calculated metrics and indices in columns and site in rows refering to ALPHA diversity.
nemator.beta.data.csv: Comprehensive dataset with all calculated metrics in columns and site in rows refering to BETA diversity.
nemator.zeta.data.csv: Comprehensive dataset with order and Zeta values. 
UiRi.csv: Comprehensive dataset with functional uniqueness (columns) and geographical restrictedness (columns) of taxa (rows).

## NEMATOR steps
1. Install R: Ensure R is installed on your system. Visit CRAN to download and install it.
2. Required Packages: Install the necessary R packages by running the following command in NEMATOR
3. Prepare Your Data: Format your nematode community data aaccording to the NEMATOR requirements.
4. Run the script in R or RStudio
5. After cleaning the community data by removing taxa and sites with zero counts, NEMATOR checks taxa affilitation using NEMAFFILITATION database.
6. NEMATOR then compute abundance and diversity metrics (see METRICS)
7. Output files including calculated indices and diversity metrics will be saved automatically in csv format.

## Metrics and references
NEMATOR computed the following metrics (the numbers in brackets [] refer to bibliographic references for more information):
#For nemator.alpha.data (in order of appearance)
-Ab.tot : Total abundance of nematodes 
-B.ab.tot : Absolute abundance of bacterivores
-F.ab.tot : Absolute abundance of fongivores
-P.ab.tot : Absolute abundance of predators
-O.ab.tot : Absolute abundance of omnivores
-H.ab.tot : Absolute abundance of herbivores
-SE.ab.tot : Absolute abundance of sedentary endoparasites
-ME.ab.tot : Absolute abundance of migratory endoparasites
-SM.ab.tot : Absolute abundance of semi-endoparasites
-EC.ab.tot : Absolute abundance of ectoparasites
-RA.ab.tot : Absolute abundance of root associated herbivores
-B.ab.rel : Relative abundance of bacterivores to total abundance
-F.ab.rel : Relative abundance of fongivores to total abundance
-P.ab.rel : Relative abundance of predators to total abundance
-O.ab.rel : Relative abundance of omnivores to total abundance
-H.ab.rel : Relative abundance of herbivores to total abundance
-SE.ab.rel : Relative abundance of sedentary endoparasites to total herbivore abundance
-ME.ab.rel : Relative abundance of migratory endoparasites to total herbivore abundance
-SM.ab.rel : Relative abundance of semi-endoparasites to total herbivore abundance
-EC.ab.rel : Relative abundance of ectoparasites to total herbivore abundance
-RA.ab.rel : Relative abundance of root associated herbivores to total herbivore abundance
-cp1.ab.tot : Absolute abundance of cp1 free-living nematodes
-cp2.ab.tot : Absolute abundance of cp2 free-living nematodes
-cp3.ab.tot : Absolute abundance of cp3 free-living nematodes
-cp4.ab.tot : Absolute abundance of cp4 free-living nematodes
-cp5.ab.tot : Absolute abundance of cp5 free-living nematodes
-pp2.ab.tot : Absolute abundance of pp2 herbivores
-pp3.ab.tot : Absolute abundance of pp3 herbivores
-pp4.ab.tot : Absolute abundance of pp4 herbivores
-pp5.ab.tot : Absolute abundance of pp5 herbivores
-Shannon : Shannon-Weiner diversity computed for the whole community using the function "alpha.div" from the {asbio} function alpha.div [5,6]
-Simpson : Simpson's diversity computed for the whole community using the function "alpha.div" from the {asbio} function alpha.div [5,6]
-J : Pielou's J Eveness for the whole community [5,6] 	
-q0.all : Hill number with order q = 0 to get species richnes for the whole community [7,8]	
-q1.all : Hill number with order q = 1 to get shannon entropy for the whole community [7,8]
-q2.all : Hill nummber with order q = 2 to get inverse Simpson for the whole community [7,8]
-q0.B : Hill number q = 0 for bacterivores [7,8]
-q1.B : Hill number q = 1 for bacterivores [7,8]
-q2.B : Hill number q = 2 for bacterivores [7,8]
-q0.F : Hill number q = 0 for fongivores [7,8]
-q1.F :	Hill number q = 1 for fongivores [7,8]
-q2.F : Hill number q = 2 for fongivores [7,8]
-q0.P : Hill number q = 0 for predators [7,8]
-q1.P : Hill number q = 1 for predators [7,8]
-q2.P : Hill number q = 2 for predators [7,8]
-q0.O : Hill number q = 0 for omnivores [7,8]
-q1.O : Hill number q = 1 for omnivores [7,8]
-q2.O : Hill number q = 2 for omnivores [7,8]
-q0.H : Hill number q = 0 for herbivores [7,8]
-q1.H : Hill number q = 1 for herbivores [7,8]
-q2.H : Hill number q = 2 for herbivores [7,8]
-q0.FL : Hill number q = 0 for free-living forms [7,8]	
-q1.FL : Hill number q = 1 for free-living forms [7,8]	
-q2.FL : Hill number q = 2 for free-living forms [7,8]	
-NCR : Nematode Channel Ratio [9]
-MI : The Maturity Index [2-4] 	
-MI25 :	The Maturiy Index for cp2-5 [2,10]
-PPI : The Plant Parasite Index [2,11]
-PPI.MI : The PPI:MI ratio [11]	
-BI : The Basal Fauna Index [12]	
-EI : The Enrichment Index [12]	
-SI : The Structure Index [12]
-Mean.mass : The mean body mass in the community in dry µg [13]	
-Mean.prod : The mean daily C assimilated in the community in ng-C [13]	
-Mean.resp : The mean daily C respired in the community in ng-C	[13]
-Mean.budget : The mean daily C used for total budget in the community in ng-C [13]
-Mean.CUE : The mean carbon use:efficiency of the whole community [13]	
-Sum.mass : The total biomass of the community in dry µg [13]	
-Sum.prod : The total daily C assimilated in the community in ng-C [13]
-Sum.resp : The total daily C respired in the community in ng-C [13]
-Sum.budget : The total daily C used for total budget in the community in ng-C [13]
-Mean.mass.FL : The mean body mass for the free-living nematodes in dry µg [13]	
-Mean.budget.FL : The mean daily C used for total budget for the free-living nematodes in ng-C [13]		
-Mean.CUE.FL :	The mean carbon use:efficiency of the free-living nematodes [13]
-Sum.mass.FL :	The total biomass of the free-living nematodes in dry µg [13]
-Sum.budget.FL : The total daily C used for total budget of the free-living nematodes in ng-C [13]	
-Mean.mass.EI :	The mean body mass for the Enrichment Fauna in dry µg [13]	
-Mean.budget.EI : The mean daily C used for total budget of the Enrichment Fauna in ng-C [13]	
-Sum.mass.EI : The total biomass of the Enrichment Fauna in dry µg [13]	
-Sum.budget.EI : The total daily C used for total budget of the Enrichment Fauna in ng-C [13]	
-Mean.mass.SI : The mean body mass of the Structure Fauna in ng-C [13]
-Mean.budget.SI : The mean daily C used for total budget of the Structure Fauna in ng-C [13]	
-Sum.mass.SI : The total biomass of the Structure Fauna in dry µg [13]
-Sum.budget.SI : The total daily C used for total budget of the Structure Fauna in ng-C [13]	
-FRic : Functional Richness computed with the "dbFD" function from {FD}	[14-26]
-FEve : Functional Eveness computed with the "dbFD" function from {FD} [14-26]	
-FDisp : Functional Dispersion computed with the "dbFD" function from {FD} [14-26]	
-FDiv : Functional Divergence computed with the "dbFD" function from {FD} [14-26]	
-RaoQ : Rao's quadratic entropy computed with the "dbFD" function from {FD} [14-26]	
-FGR : Functional Group Richness computed with the "dbFD" function from {FD} [14-26] 	
-CWM.mass The Community-Level Means of body masscomputed with the "dbFD" function from {FD} [14-26]	
-Ui : Functional Uniqueness computed using the function "uniqueness" from {funrar} [27]
-Ri : Geographical Restrictedness computed using the function "restrictedness" from {funrar} [27]
-Di..taxa : Functional Distinctiveness for each taxa compute from the function "distinctiveness" from {funrar} [27]
-PD : Faith's Phylogenetic Diversity computed using the function pd from {picante} [28]	
-SR : Specific Richness	computed using the function pd from {picante} [28]

#For nemator.beta.data (in order of appearance)
-Taxonomic Sorensen dissimilarity indice between pairs of sites using the function "dis.chao" from {CommEcol} [29]
-Taxonomic Turnover dissimilarity using the function "beta.pair" from {betapart} [30]
-Taxonomic nestedness dissimilarity using the function "beta.pair" from {betapart} [30]
-Beta Functional diversity using the function "hclust" from {stats} and "treedive" from {vegan} [31-35]
-Beta Phylogenetic diversity using the "phylosor" function from {picante} [36]

#For nemator.zeta.data (in order of appearance)
-order : Range of order using the function "Zeta.decline.mc" from {zetadiv} [37]
-zeta.value : Zeta Diveristy values using the function "Zeta.decline.mc" from {zetadiv} [37]

## References
[1] G.W. Yeates, T. Bongers, R.G.M. de Goede, D. Freckman, S. Georgieva. (1993) J. Nematol. 25, 315-331.
[2] T. Bongers. (1990) Oecologia 83, 14-19. 
[3] Bongers, T., Goede, R. D., Korthals, G. W., Yeates, G. W. (1995). Proposed changes of cp classification for nematodes. Russian Journal of Nematology, no. 3, 61-62.
[4] T. Bongers, H. Ferris. (1999) Trends Ecol. Evol. 14, 224-228.
[5] Simpson, E. H. (1949) Nature. 163: 688.
[6] MacArthur, R. H., and MacArthur J. W. (1961) Ecology. 42: 594-598.
[7] Chao, Anne, Chun-Huo Chiu, and Lou Jost. (2014) Annual Review of Ecology, Evolution, and Systematics 45, no. 1: 297–324.
[8] Jost, Lou. (2006) Oikos 113, no. 2: 363-375.
[9] Yeates, G. W. (2003) Biology and Fertility of Soils, 37, 199-210.
[10] T. Bongers, G. Korthals. (1994) Proc. 22nd Int. Symp. Eur. Soc. Nematol., Ghent, Belgium, p. 39.
[11] T. Bongers, H. van der Meulen, G. Korthals. (1997) Appl. Soil. Ecol. 6, 195-199.
[12] H. Ferris, T. Bongers, R.G.M. de Goede. (2001) Appl. Soil. Ecol. 18, 13-29.
[13] H. Ferris. (2010) Eur. J. Soil. Biol. 46, 97-104.
[14] Anderson, M. J., K. E. Ellingsen, and B. H. McArdle. (2006) Multivariate dispersion as a measure of beta diversity. Ecology Letters 9:683-693.
[15] Botta-Dukát, Z. (2005) Rao's quadratic entropy as a measure of functional diversity based on multiple traits. Journal of Vegetation Science 16:533-540.
[16] Cailliez, F. (1983) The analytical solution of the additive constant problem. Psychometrika 48:305-310.
[17] Calinski, T., and J. Harabasz. (1974) A dendrite method for cluster analysis. Communications in Statistics 3:1-27.
[18] Gower, J. C. (1971) A general coefficient of similarity and some of its properties. Biometrics 27:857-871.
[19] Laliberté, E., and P. Legendre. (2010) A distance-based framework for measuring functional diversity from multiple traits. Ecology 91:299-305.
[20] Lavorel, S., et al. (2008) Assessing functional diversity in the field - methodology matters! Functional Ecology 22:134-147.
[21] Legendre, P., and M. J. Anderson. (1999) Distance-based redundancy analysis: testing multispecies responses in multifactorial ecological experiments. Ecological Monographs 69:1-24.
[22] Legendre, P., and L. Legendre. (1998) Numerical Ecology. 2nd English edition. Amsterdam: Elsevier.
[23] Lingoes, J. C. (1971) Some boundary conditions for a monotone analysis of symmetric matrices. Psychometrika 36:195-203.
[24] Podani, J. (1999) Extending Gower's general coefficient of similarity to ordinal characters. Taxon 48:331-340.
[25] Sokal, R. R., and C. D. Michener. (1958) A statistical method for evaluating systematic relationships. The University of Kansas Scientific Bulletin 38:1409-1438.
[26] Villéger, S., N. W. H. Mason, and D. Mouillot. (2008) New multidimensional functional diversity indices for a multifaceted framework in functional ecology. Ecology 89:2290-2301.
[27] Grenié, M., Denelle, P., Tucker, C. M., Munoz, F., & Violle, C. (2017) Diversity and Distributions, 23(12), 1365-1371.
[28] Faith, D.P. (1992) Conservation evaluation and phylogenetic diversity. Biological Conservation, 61, 1-10.
[29] Chao, A., R.L. Chazdon, R.K. Colwell, & T. Shen. (2005) A new statistical approach for assessing similarity of species composition with incidence and abundance data. Ecology Letters 8: 148-159.
[30] Baselga, A. (2010) Partitioning the turnover and nestedness components of beta diversity. Global Ecology and Biogeography 19:134-143.
[31] Baselga, A. (2012) The relationship between species replacement, dissimilarity derived from nestedness, and nestedness. Global Ecology and Biogeography 21, 1223-1232.
[32] Lozupone, C., and Knight, R. (2005) Applied and Environmental Microbiology 71, 8228–8235.
[33] Petchey, O.L., and Gaston, K.J. (2002). Ecology Letters 5, 402–411.
[34] Petchey, O.L., and Gaston, K.J. (2006). Ecology Letters 9, 741–758.
[35] Podani, J., and Schmera, D. (2006) On dendrogram-based methods of functional diversity. Oikos 115, 179–185.
[36] Bryant, J.B., Lamanna, C., Morlon, H., Kerkhoff, A.J., Enquist, B.J., Green, J.L. (2008). Proceedings of the National Academy of Sciences 105 Supplement 1: 11505-11511.
[37] Hui, C., & McGeoch, M.A. (2014). Zeta diversity as a concept and metric that unifies incidence-based biodiversity patterns. The American Naturalist, 184, 684-694.

## For more information about the interpretation of nematofaunal indices, see the following references:
Du Preez et al. Nematode-based indices in soil ecology: Application, utility, and future directions. Soil Biology and Biochemistry, 2022, vol. 169, p. 108640.
H. Ferris, T. Bongers, Indices for analysis of nematode assemblages, in: M. Wilson, T. Kakouli-Duarte (Eds.), Nematodes as Environmental Bioindicators, CABI, Wallingford, 2009, pp. 124e145. 
M. Rutgers, A.J. Schouten, J. Bloem, N. van Eekeren, R.G.M. de Goede, G.A.J.M. Jagers op Akkerhuis, et al., Biological measurements in a nationwide soil monitoring network, Eur. J. Soil Sci. 60 (2009) 820e832.
M. Vervoort, J. Arie Vonk, P. Mooijman, S. van den Elsen, H. van Megen, P. Veenhuizen, et al., SSU ribosomal DNA-based monitoring of nematode assemblages reveals distinct seasonal fluctuations within evolutionary heterogeneous feeding guilds, PLoS One 7 (2012) 1e13. 
C. Campbell, J. Bay, A. Hellkamp, G. Hess, M. Munster, K. Nauman, et al., Environmental Monitoring and Assessment Program: Agroecosystem Pilot
Field Program Report e 1992, 1994. 
D.W. Freckman, C.H. Ettema, Assessing nematode communities in agroecosystems of varying human intervention, Agric. Ecosyst. Environ. 45 (1993) 239e261.
H. Ferris, M.M. Matute, Structural and functional succession in the nematode fauna of a soil food web, Appl. Soil. Ecol. 23 (2003) 93e110.
J. Andrassy, Die Rauminhalt and Gewichtsbestimmung der Fadenwürmer (Nematoden), Acta Zool. Acad. Sci. Hung. 2 (1956) 1e15.
T. Bongers, R. Alkemade, G.W. Yeates, Interpretation of disturbance-induced maturity decrease in marine nematode assemblages by means of the Maturity Index, Mar. Ecol. Prog. Ser. 76 (1991) 135e142.
T. Bongers, R.G.M. de Goede, G. Korthals, G.W. Yeates, Proposed changes of cp classification for nematodes, Russ. J. Nematol. 3 (1995) 61e62.
G.W. Yeates, Modification and qualification of the nematode maturity index, Pedobiologia (Jena) 38 (1994) 97e101. 

## Contribtuions
I warmly welcome contributions from the community, be it in the form of bug reports, code enhancements, documentation improvements, or feature suggestions.
If you have an idea for a new feature or an improvement, please share it with me through the Issue Tracker by creating a 'feature request'.

## Support & Contact
For questions, suggestions, or collaborations, please contact Jean Trap at :
Email: jean.trap@ird.fr
UMR Eco&sols, Montpellier, France

## License
This script is provided "as is", without warranty of any kind. 
This is free and unencumbered R script released into the public domain.
Anyone is free to copy, modify, publish, use, compile this script, either in source code form or as a compiled binary, for any purpose.
Users are free to use and modify it for their research or work.
