# List app versions

List app versions by platform

## Usage

``` r
list_versions(appname, platform = c("ALL"))
```

## Arguments

- appname:

  A character string giving the name of the application

- platform:

  A character vector of platforms to list. Defaults to "ALL"

## Value

A list of platforms with version directories

## Examples

``` r
if (FALSE) { # \dontrun{
appdir <- app_dir("superduperapp", FALSE)
platforms <- LETTERS[1:4]
versions <- LETTERS[5:7]
mkdirs <- file.path(appdir, outer(platforms, versions, file.path))
chk <- vapply(mkdirs, dir.create, logical(1), recursive = TRUE)
expect_true(all(chk))
res <- list_versions("superduperapp")
unlink(appdir, recursive = TRUE)
} # }
```
