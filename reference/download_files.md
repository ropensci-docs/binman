# Download binaries

Download binaries from repository

## Usage

``` r
download_files(dllist, overwrite = FALSE)
```

## Arguments

- dllist:

  A named list of data.frames. The data.frame should contain the
  version, url and file to be processed, the directory to download the
  file to and whether the file already exists.

- overwrite:

  Overwrite existing binaries. Default value of FALSE

## Value

A data.frame indicating whether a file was downloaded for a platform.

## Examples

``` r
if (FALSE) { # \dontrun{
trdata <- system.file("testdata", "test_dlres.Rdata", package = "binman")
tldata <- system.file("testdata", "test_dllist.Rdata", package = "binman")
load(trdata)
load(tldata)
dllist <- assign_directory(test_dllist, "myapp")
testthat::with_mock(
  `httr::GET` = function(...) {
    test_llres
  },
  `base::dir.create` = function(...) {
    TRUE
  },
  dlfiles <- download_files(dllist)
)
} # }
```
