# Remove application platform

Remove application files/directories for a given platform

## Usage

``` r
rm_platform(appname, platform = c("ALL"))
```

## Arguments

- appname:

  A character string giving the name of the application

- platform:

  A character vector indicating the platform to remove. Defaults to
  "ALL"

## Value

Returns a logical vector indicating whether the removal of platform was
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
rm_platform(appname, platforms[2:3])
unlink(appdir, recursive = TRUE)
} # }
```
