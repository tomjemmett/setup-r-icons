# setup-r-icons

This action downloads and installs the [`{icons}`](https://github.com/mitchelloharawild/icons) package and then optionally downloads individual icon libraries. It then caches whatever font's have been installed to improve future runtimes.

This action needs R to have previously been setup (e.g. with [`r-lib/actions/setup-r`](https://github.com/r-lib/actions/tree/master/setup-r)).

## Inputs

* `cache-version` - default `1`. If you need to invalidate the existing cache pass any other number and a new cache will be used.
* `icon-sets` - default ''. Comma separated list of the font's to download, see below for further details

## Fonts

The font set's that are available to download can be found in the `{icons}` package, named as `download_*()`. Currently available are:
* `bioicons`
* `feather_icons`
* `fontawesome`
* `google_material`
* `ionicons`
* `octicons`
* `simple_icons`

## Usage

``` yaml
steps:
- uses: actions/checkout@v2
- uses: r-lib/actions/setup-r@v1
- uses: tomjemmett/setup-r-icons@main
  with:
    icon-sets: fontawesome,simple_icons
```
