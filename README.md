# diversity indexes
Calculation of basic ecological diversity indexes from a list of values

This script calculates Richness (S), Evenness, Menhinick richness index (DMn) and the
diversity indexes Shannon (H), Simpson (1-D), and Berger-Parker dominance index (1/d).

# Installation

Just download the script ([latest release](https://github.com/GenomicaMicrob/diversity_indexes/releases/tag/v0.0.1)) and make it executable ```chmod +x div_index.v0.0.1.sh```, it does not need any special dependencies appart from those already found in any common linux distribution (Ubuntu).

# Usage

```./div_index.v0.0.1.sh file```

You will need a file with just the values of the OTUs in a column.

Example of a useful file:
```
6
5
1
3
12
7
```

# Indexes calculated

**Richness (S)** is just the number of species or OTUs in the sample.

**Simpson measure of evenness (E)** for Simpson's measure of heterogeneity,
maximum diversity is obtained when all abundances are equal (p = 1/S) in a very
large population. Formula: E=(1/D)/S.
This index ranges from 0 to 1 and is relatively unaffected by the rare species in the
sample.

**Menhinick richness index** considers the influence on diversity of the analysis
scale, therefore the index value is not taking into account class frequencies.

##### DIVERSITY INDEXES

**Simpson diversity index (1-D)** represents the probability that two individuals
randomly selected from a sample will belong to different species. It is a measure
of diversity which takes into account both Richness (the number of species per
sample) and Evenness (the relative abundance of the different species making up
the richness of an area). Formula: 1-D=1-SUM(n/N)2.
The results can be from 0 (less diverse, only one OTU) to 1 (most diverse).

**Shannon diversity index (H)** is a measure of the average degree of uncertainty
in predicting to what species and individual a chosen at random from a collection of
species and individuals will belong. Formula: H=-SUM(Pi * ln Pi)
The values can range from 0 (less diverse, only one OTU) to ln(1/S), but usually they
will fall between 1.5 and 3.5, and rarely above 5. 

**Berger-Parker dominance index (1/d)** the number of individuals in the
dominant taxon relative to n. Its value does not take into account the number of
classes but it is highly influenced by the equity. It is a simple measure of the
numerical importance of the most abundant species. Formula: 1/d=Nmax/N.
An increase in the value of the index accompanies an increase in diversity and a
reduction in dominance.

# Results

The script will send to the screen the results:
```
Number of individuals (N):           34
Number of OTUs (Richness S):         6
Menhinick's richness index (D):      1.029
--- DIVERSITY ---
Shannon diversity index (H):         1.599
Simpson diversity index (1-D):       0.772
Berger-Parker dominance index (1/d): 0.353
Simpsons evenness (E):               0.216
```
