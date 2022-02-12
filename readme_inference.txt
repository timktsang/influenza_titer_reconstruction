Demo Data and R syntax for the following paper:
Tim K. Tsang, Ranawaka A. P. M. Perera, Vicky J. Fang, Jessica Y. Wong, Eunice Y. Shiu, Hau Chi So, Dennis K. M. Ip, J. S. Malik Peiris1,, Gabriel M. Leung, Benjamin J. Cowling, Simon Cauchemez

Reconstructing antibody dynamics to estimate the risk of influenza virus infection

+---------------------------------------------+
| System requirements and installation guide  |
+---------------------------------------------+

Please install R software, and install the used package, including 
1. Rcpp
2. RcppParallel
3. RcppArmadillo

Install time should be less than 10 mins
For windows user, Rtools 4.0 is required


+--------------------------------+
|  Demo and instruction for use  |
+--------------------------------+

[data_analysis.zip] contains all codes related to the results of data analysis

[inference_demo.zip] contains the file for doing statistical inference

[Figure_table_code.zip] contains all codes to replicate the tables/figures in the manuscript.

[simulation_result.zip] contains all results of simulation

File needed:

A. [data_demo.csv] This data file contains demo data from the kiddivax study at 2009-2010. 
1. Household ID
2. hosuehold member i.d
3. age group (0: children, 1: adults, 2: older adults)
4. the time for collection for the first serum sample in a season
5. the time for collection for the last serum sample in a season
6. the time for collection for serum sample 1
7. the time for collection for serum sample 2
8. the time for collection for serum sample 3
9. the HAI titer for serum sample 1
10. the HAI titer for serum sample 2
11. the HAI titer for serum sample 3
12. the indicator for season
	0 for epidemics 1
	1 for epidemics 2
	2 for epidemics 3
	3 for epidemics 4
	4 for epidemics 5
	5 for epidemics 6
13. the indicator for flu type of season
	0 for H1N1
	1 for H3N2
14. the indicator for boosting type
	0 for H1N1 with strain change
	1 for H1N1 without strain change.
	2 for H3N2 with strain change
	3 for H3N2 without strain change

[dataSX.csv] for X = 1, 2, ... 6
This is the same format for the data_demo.csv 

B. [ILILAB.csv] The influenza proxy used in the analysis. The first column is H1N1 and second column is H3N2

C. [crossprotection.cpp] The file that are used by [crossprotection.R].

D. [crossprotection.R] The file for running the data-augmentation MCMC to obtain the main results in the paper


Run instruction:

1. Please install R and the required package. 
2. open the crossprotection.R
3. Following the instruction in crossprotection.R. 
4. Please remember set the link to the depository.
5. The expected run time is 15 hours for the whole dataset with 9000+ observation. Therefore, please consider to do a subset of data with 500 observation for testing.

Expected output:
1. The posterior samples for all parameters, they are stored in tt[[1]], tt[[2]] and tt[[3]]
2. The augmented infection status and infection time, they are stored in tt[[13]] and tt[[14]]
3. The augmented boosting, waning and HAI titer to reconstruct HAI titer, they are stored in tt[[15]],tt[[16]] and tt[[17]]

Run the code for your data
If you have your own data, please clean the data in the format of data_demo.csv, then you can apply it.



