# Pre-Download Google Storage

Pre-Download Google Storage template function

## Usage

``` r
predl_google_storage(
  url,
  platform,
  history,
  appname,
  fileregex = "\\.zip$",
  platformregex = platform,
  versionregex = c(paste0("(.*)/.*", fileregex), "\\1")
)
```

## Arguments

- url:

  A url giving the JSON bucket listings for a project. For example:
  http://chromedriver.storage.googleapis.com/index.html lists the
  chromedriver files but
  https://www.googleapis.com/storage/v1/b/chromedriver/o/ is the JSON
  listings for the project.

- platform:

  A character vector of platform names

- history:

  The maximum number of files to get for a platform

- appname:

  Name of the app

- fileregex:

  A filter for files

- platformregex:

  A filter for platforms. Defaults to the platform names.

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
gsdata <- system.file("testdata", "test_googstor.json",
  package = "binman"
)
platform <- c("linux64", "win32", "mac64")
gsdllist <- predl_google_storage(
  url = gsdata, platform, history = 5L,
  appname = "binman_chromedriver"
)
} # }
```
