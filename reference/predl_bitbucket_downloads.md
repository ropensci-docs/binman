# Pre download bitbucket downloads

Pre download bitbucket downloads template function

## Usage

``` r
predl_bitbucket_downloads(
  url,
  platform,
  history,
  appname,
  platformregex = platform,
  versionregex = "\\d+(?:\\.\\d+)+"
)
```

## Arguments

- url:

  A url giving the bitbucket download JSON for a project. As an example
  https://bitbucket.org/ariya/phantomjs/downloads the phantomjs project
  has an asset JSON available at
  https://api.bitbucket.org/2.0/repositories/ariya/phantomjs/downloads?pagelen=100

- platform:

  A character vector of platform names

- history:

  The maximum number of files to get for a platform

- appname:

  Name of the app

- platformregex:

  A filter for platforms. Defaults to the platform

- versionregex:

  A regex for retrieving the version.

## Value

A named list of data.frames. The name indicates the platform. The
data.frame should contain the version, url and file to be processed.
Used as input for
[`download_files`](https://docs.ropensci.org/binman/reference/download_files.md)
or an equivalent.

## Examples

``` r
if (FALSE) { # \dontrun{
bbdata <- system.file("testdata", "test_bitbucketdl.json",
  package = "binman"
)
platform <- c("linux64", "linux32", "windows", "macosx")
platformregex <- c("linux-x86_64", "linux-i686", "windows", "macosx")
bbdllist <-
  predl_bitbucket_downloads(
    url = bbdata, platform, history = 3L,
    appname = "binman_chromedriver",
    platformregex
  )
} # }
```
