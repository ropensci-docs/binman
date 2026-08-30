# Remove application version

Remove application version for a given platform

## Usage

``` r
rm_version(appname, platform, version = c("ALL"))
```

## Arguments

- appname:

  A character string giving the name of the application

- platform:

  A character string indicating the platform.

- version:

  A character vector of versions to remove. Defaults to "ALL"

## Value

Returns a logical vector indicating whether the removal of version was
successful. Return is invisible.

## Examples

``` r
if (FALSE) { # \dontrun{
appdir <- app_dir(appname, FALSE)
platforms <- LETTERS[1:4]
versions <- LETTERS[5:7]
mkdirs <- file.path(appdir, outer(platforms, versions, file.path))
chk <- vapply(mkdirs, dir.create, logical(1), recursive = TRUE)
appver <- list_versions(appname)
rm_version(appname, platforms[2], versions[1:2])
unlink(appdir, recursive = TRUE)
} # }
```
