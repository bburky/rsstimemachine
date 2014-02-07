# RSS Time Machine

From a given domain, try to discover as many old archived RSS feeds as possible using the Internet Archive's [Wayback Machine](https://archive.org/web/).

The RSS feeds are discovered by searching the Wayback Machine using the [CDX Server API](https://github.com/internetarchive/wayback/tree/master/wayback-cdx-server). RSS and ATOM feeds are discovered by searching by MIME type and using regular expressions for RSS URLs.

An undocumented `id_` flag is used to download unmodified original files as [described here](http://www.willglynn.com/2014/01/26/exporting-from-the-wayback-machine/).

This may be useful for finding many links and creation dates for content on arbitrary domains.

## Usage

Each found URL will be printed on standard output on its own line. You may feed this directly into something like `wget`.

Example usage:

    ./rsstimemachine.py example.com | wget --force-directories --input-file=-

## TODO

*  BUG: The program may find other XML files that are not feeds
*  Possibly handle non-200 status codes better
*  Merge RSS feeds using an external tool or write it myself
