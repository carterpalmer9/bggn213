Class12
================

We want to download a PDB structure and produce a protein only and ligand only PDB files

``` r
library(bio3d)
```

    ## Warning: package 'bio3d' was built under R version 3.4.4

``` r
get.pdb("1hsg") 
```

    ## Warning in get.pdb("1hsg"): ./1hsg.pdb exists. Skipping download

    ## [1] "./1hsg.pdb"

Once we have the pdb we need to select the protein and ligand as their own pdb files

``` r
pdb <- read.pdb("1hsg.pdb")
protein <- (atom.select(pdb, 'protein', value = TRUE))
ligand <- (atom.select(pdb, 'ligand', value = TRUE))

write.pdb (protein, file = "1hsg_protein.pdb")
write.pdb (ligand, file = "1hsg_ligand.pdb")
```
