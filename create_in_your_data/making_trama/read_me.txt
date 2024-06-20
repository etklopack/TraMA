Updated 1-9-24
Eric Klopack

This folder contains R scripts and data needed to calculate a TraMA score from log2 counts per million RNAseq data. You need to add your log2cpm matrix, with rows representing genes and columns representing observations. Data to be QC'd, normalized, etc. Row names should be ensemble IDs, and column names should be observation IDs. Replace the .txt file name in line 131, "l2cpm <- read.table('fake_data_complete.txt')", with your log2cpm matrix. You also need a .csv file with a column of IDs called "Subject.ID" and a column of your subjects' ages.

The file "replication.Rmd" is an R markdown file that will calculate TraMA scores.

This folder also contains example files "fake_data_complete.txt" and "fake_data_missing.txt" which contain randomly generated data for 10 imaginary subjects that are complete and are missing 2 needed genes, respectively, as well as "age_col.csv" containing randomly generated ages for those subjects.

The file "trama_coef.csv" contains the ensemble IDs and weights for genes needed to calculate TraMA scores.

The file "trama_hrs_ref_panel_means.csv" contains means from the HRS data for each gene. The replication.Rmd file will impute genes that are missing for all participants using the mean from the HRS data. This is to keep means and standard deviations meaningful if you are missing genes. If you do not wish to use a reference panel, remove the ref_panel option from line 149 or set this value to NULL. You may also want to use a diferent reference panel that is more representative of your population. Note the HRS sample is of older adults in the US and may not be applicable to your sample.