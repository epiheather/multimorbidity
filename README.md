
<!-- README.md is generated from README.Rmd. Please edit that file -->

# multimorbidity

<!-- badges: start -->
<!-- badges: end -->

The goal of `multimorbidity` is to create as single package which can
take original claims data, clean and organize them to a simple format,
which can then be immediately used to obtain any of a number of
comorbidity, frailty, and multimorbidity measures. This package is meant
to be a simple and transparent one-stop-shop for those working with
claims or other administrative health care data. The measures included
in this package have been developed by other researchers and are
detailed in depth below.

This package is meant to be both user-friendly and transparent. An
individual should feel comfortable understanding what’s ‘under the hood’
with these various metrics. Given this, this function has been written
in a way that makes the code and specific diagnosis codes accessible.

## Installation

There is currently no released version of `multimorbidity` on CRAN.

The development version can be downloaded from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("WYATTBENSKEN/multimorbidity")
```

## Citation Information

In addition to citing this R Package, we ask that you please cite the
original manuscripts which developed these algorithms. Portions of this
package, specifically, the Elixhauser and Charlson diagnoses codes, were
adapted from another package,
[`comorbidity`](https://github.com/ellessenne/comorbidity).

## Included Algorithms and Indices

### Elixhauser Comorbidities and Index

The Elixhauser Comorbidities and Comorbidity Index are a widely-used set
of comorbidities originally developed in 1998 by
[Elixhauser](https://pubmed.ncbi.nlm.nih.gov/9431328/), with two indices
for mortality and readmission created in 2017 by [Moore et
al.](https://pubmed.ncbi.nlm.nih.gov/28498196/)

In this package, we used the codes provided in the format programs by
the Agency for Healthcare Research and Quality for
[ICD-9](https://www.hcup-us.ahrq.gov/toolssoftware/comorbidity/comorbidity.jsp),
[ICD-10
Beta](https://www.hcup-us.ahrq.gov/toolssoftware/comorbidityicd10/comorbidity_icd10_archive.jsp),
and
[ICD-10](https://www.hcup-us.ahrq.gov/toolssoftware/comorbidityicd10/comorbidity_icd10.jsp).
The ICD-10 data contain a larger set of comorbidities and, as of this
writing, no calculator for the indices has been released, and thus when
data contain both ICD-9 and ICD-10, we will use the ICD-9 comorbidities
with the Beta code. Finally, the original algorithm takes into account
DRG, which this package currently does not accommodate.

### Charlson Comorbidities and Index

The Charlson Comorbidities and Index are, similarly, a widely-used set
of comorbidities. First developed in 1987 by [Charlson et
al.](https://pubmed.ncbi.nlm.nih.gov/3558716/), they’ve been modified a
number of times. This algorithm employs the [Deyo et
al.](https://pubmed.ncbi.nlm.nih.gov/1607900/) list of 17 comorbidities,
with the adaptations included in [Quan et
al.](https://pubmed.ncbi.nlm.nih.gov/16224307/)

### Claims Frailty Index

The Claims Frailty Index (CFI) is based off of work by [Kim et
al.](https://pubmed.ncbi.nlm.nih.gov/29244057/) in 2018. This algorithm
uses ICD-9, ICD-10, and procedure codes to establish the frailty score
for each patient. The code included in this package is largely developed
from publicly-available code which can be found on the [Harvard
dataverse](https://dataverse.harvard.edu/dataverse/cfi). As the original
algorithms included HCPCS/CPT procedure codes, so does this.

### Multimorbidity Weighted Index

The Multimorbidity Weighted Index (MWI) was created by [Wei et
al.](https://pubmed.ncbi.nlm.nih.gov/31917465/) in 2020. This uses ICD-9
codes (note: ICD-10 is not yet available for MWI) to establish a
multimorbidity index for each individual. The R code used in this
package was developed based on the supplement included in the previously
linked manuscript.
