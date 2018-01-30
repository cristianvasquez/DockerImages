# docker-tabula-java

A minimal Docker image for running the [tabula-java](https://github.com/tabulapdf/tabula-java) from a Docker container. Based on [java:openjdk-8-jre-alpine](https://hub.docker.com/_/java/).

## Run a batch process

You can mount a Directory file available at `/data` to the docker container by using the `-v` option to the `docker run` command:

```
docker run --user `id -u` -v `pwd`/data:/data tabula-java:latest -b /data -f JSON -l

```

To get tabula help:

```
docker run --rm tabula-java:latest --help

usage: tabula [-a <AREA>] [-b <DIRECTORY>] [-c <COLUMNS>] [-d] [-f
       <FORMAT>] [-g] [-h] [-i] [-l] [-n] [-o <OUTFILE>] [-p <PAGES>] [-r]
       [-s <PASSWORD>] [-t] [-u] [-v]

Tabula helps you extract tables from PDFs

 -a,--area <AREA>           Portion of the page to analyze
                            (top,left,bottom,right). Example: --area
                            269.875,12.75,790.5,561. Default is entire
                            page
 -b,--batch <DIRECTORY>     Convert all .pdfs in the provided directory.
 -c,--columns <COLUMNS>     X coordinates of column boundaries. Example
                            --columns 10.1,20.2,30.3
 -d,--debug                 Print detected table areas instead of
                            processing.
 -f,--format <FORMAT>       Output format: (CSV,TSV,JSON). Default: CSV
 -g,--guess                 Guess the portion of the page to analyze per
                            page.
 -h,--help                  Print this help text.
 -i,--silent                Suppress all stderr output.
 -l,--lattice               Force PDF to be extracted using lattice-mode
                            extraction (if there are ruling lines
                            separating each cell, as in a PDF of an Excel
                            spreadsheet)
 -n,--no-spreadsheet        [Deprecated in favor of -t/--stream] Force PDF
                            not to be extracted using spreadsheet-style
                            extraction (if there are no ruling lines
                            separating each cell)
 -o,--outfile <OUTFILE>     Write output to <file> instead of STDOUT.
                            Default: -
 -p,--pages <PAGES>         Comma separated list of ranges, or all.
                            Examples: --pages 1-3,5-7, --pages 3 or
                            --pages all. Default is --pages 1
 -r,--spreadsheet           [Deprecated in favor of -l/--lattice] Force
                            PDF to be extracted using spreadsheet-style
                            extraction (if there are ruling lines
                            separating each cell, as in a PDF of an Excel
                            spreadsheet)
 -s,--password <PASSWORD>   Password to decrypt document. Default is empty
 -t,--stream                Force PDF to be extracted using stream-mode
                            extraction (if there are no ruling lines
                            separating each cell)
 -u,--use-line-returns      Use embedded line returns in cells. (Only in
                            spreadsheet mode.)
 -v,--version               Print version and exit.

```