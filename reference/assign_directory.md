# Assign directory

Assign directory to download list

## Usage

``` r
assign_directory(dllist, appname)
```

## Arguments

- dllist:

  A named list of data.frames. The name indicates the platform. The
  data.frame should contain the version, url and file to be processed.

- appname:

  Name to give the app

## Value

A named list of data.frames. The data.frame should contain the version,
url and file to be processed, the directory to download the file to and
whether the file already exists.

## Examples

``` r
if (FALSE) { # \dontrun{
tdata <- system.file("testdata", "test_dllist.Rdata", package = "binman")
load(tdata)
assign_directory(test_dllist, "myapp")
} # }
```
