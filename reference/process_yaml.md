# Process a yaml file

Process a yaml file. The file defines the pre-download function, the
download function and the post download function.

## Usage

``` r
process_yaml(ymlfile, verbose = TRUE)
```

## Arguments

- ymlfile:

  A file in a YAML format defining the pre-download/ download and post
  download functions together with their arguments.

- verbose:

  If TRUE, include status messages (if any)

## Value

A list of files processed (downloaded and post processed)

## Examples

``` r
if (FALSE) { # \dontrun{
ymlfile <- system.file("exdata", "sampleapp.yml", package = "binman")
trdata <- system.file("testdata", "test_dlres.Rdata", package = "binman")
load(trdata)
testthat::with_mock(
  `httr::GET` = function(...) {
    test_llres
  },
  `base::dir.create` = function(...) {
    TRUE
  },
  `utils::unzip` = function(zipfile, ...) {
    zipfile
  },
  procyml <- process_yaml(ymlfile)
)
procyml
} # }
```
