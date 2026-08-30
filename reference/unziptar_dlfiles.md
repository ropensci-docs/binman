# Unzip/Untar downloaded files

Unzip/Untar downloaded files. Keeps the original zip file

## Usage

``` r
unziptar_dlfiles(dlfiles, chmod = FALSE)
```

## Arguments

- dlfiles:

  A data.frame of files by platform and indicating whether they were
  processed

- chmod:

  change the mode of the unarchived file/files to "755" so they are
  executable on unix like systems.

## Value

Returns a list of character vectors indicating files processed

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
