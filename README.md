<a href='https://datashield.org'><img src='https://i0.wp.com/datashield.org/wp-content/uploads/2024/07/DS-logo-A4.png' alt='DataSHIELD logo' align='right' height=70px/></a>

# DataSHIELD packages tests’ Dashboard

<!-- badges: start -->
<!-- badges: end -->

This repository contains scripts to aggregate
([source/parse_test_report.R](source/parse_test_report.R)) results from
[`{testthat}`](https://cran.r-project.org/package=testthat) and
[`{covr}`](https://cran.r-project.org/package=covr) packages (see the
workflow: [.github/workflows/dsbase-test-suite.yaml](.github/workflows/dsbase-test-suite.yaml) 
OR [.github/workflows/dsbaseclient-test-suite.yaml](.github/workflows/dsbasclient-test-suite.yaml)). 

There is a script to render ([source/build_site.R](source/build_site.R)) the results
committed by the pipeline to the [logs/](logs/) directory. This script generates
a Quarto webpage using the files in [site](site).

To configure additional branches, commits or releases to be tested, please modify
the config files inside [.github](.github):

- dsBase: [.github/dsbase-refs.txt](.github/dsbase-refs.txt)
- dsBaseClient: [.github/dsbaseclient-refs.txt](.github/dsbaseclient-refs.txt)

----------

The workflow follows the following steps:

`Run unit tests & coverage [GHA]` \>\>\> `Parse results` \>\>\>
 \>\>\> `Render Quarto webpage`  \>\>\> `Publish site [GitHub pages]`
