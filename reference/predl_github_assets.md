# Pre download Github assets

Pre download Github assets template function

## Usage

``` r
predl_github_assets(
  url,
  platform,
  history,
  appname,
  fileregex = "",
  platformregex = platform,
  versionregex = c("", "")
)
```

## Arguments

- url:

  A url giving the github asset JSON for a project. As an example
  https://github.com/mozilla/geckodriver/releases the geckodriver
  project has an asset JSON available at
  https://api.github.com/repos/mozilla/geckodriver/releases

- platform:

  A character vector of platform names

- history:

  The maximum number of files to get for a platform

- appname:

  Name of the app

- fileregex:

  A filter for files

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
gadata <- system.file("testdata", "test_gitassets.json",
  package = "binman"
)
platform <- c("linux64", "win64", "macos")
gadllist <- predl_github_assets(
  url = gadata, platform, history = 3L,
  appname = "binman_chromedriver"
)
} # }
```
