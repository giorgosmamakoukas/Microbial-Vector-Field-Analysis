# Data Dictionary for VMBData_clean

Each row corresponds to one sample. For each sample, the columns are:

- day_relative_to_study_start: The day the sample was taken. Day 1 is the first day of the first year of the study. Samples taken in year 2 will start with a number >350. Study was carried out for approximately 10 weeks each year with one week of spring break during which (most) participants did not collect samples.
- meta_Participant: This is a persistent subject ID that carries forward year to year. Note that originally, the data was recorded and de-identified separately between year 1 and year 2.
- meta_Year: This is the year of the study during which the samples were collected. Note there is a strong batch effect in the sequencing between years 1 and 2. In particular, there is a marked change in diversity.
- meta_StudyDay: This is the day relative to the study start in that year.
- blast_XXX: These are taxa identifications made using blast. This was done as a way to hand-engineer the taxa features in a way that was meaningful for the vaginal microbiome while reducing dimensionality. In particular, note that we separated out specific species of Lactobacilli while grouping other genuses together more broadly. And anything we did not care to highlight we put in the "other" categorgy. This is the primary data we are making predictions on.
- otu_XXX: Operational taxanomic unit for XXX. This is a sequence-based method for clustering 16S rRNA data into approximate species using an unsupervised clustering method that is groups sequences together within approximatelly consistent hamming distances.

Some additional notes for those outside the field:
- The species concept is a somewhat arbitrary in microbiology because they replicate asexually.
- Taxa levels are not consistently applied from the viewpoint of sequence evolution. A species might be a single 16S rRNA mutation away form another one, or a species might contain many mutations. As an upper bound, is generally accepted that if two species >3% different in 16S rRNA sequence are definitely different species.
