# Do not post process

Do not post process dlfiles

## Usage

``` r
noproc_dlfiles(dlfiles)
```

## Arguments

- dlfiles:

  A data.frame of files by platform and indicating whether they were
  processed

## Value

Returns a list of character vectors indicating files processed

## Examples

``` r
if (FALSE) { # \dontrun{
ymlfile <- system.file("exdata", "sampleapp4.yml", package = "binman")
trdata <- system.file("testdata", "test_dlres.Rdata", package = "binman")
load(trdata)
testthat::with_mock(
  `httr::GET` = function(...) {
    test_llres
  },
  `base::dir.create` = function(...) {
    TRUE
  },
  procyml <- process_yaml(ymlfile)
)
procyml
} # }
```
