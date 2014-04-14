LCurl
=====

## LCurl - a command line tool for Loganis API

* This project provides a sample command line application for Loganis API
* Curl is used as an http-client

## Usage

* Register a [Loganis Account](https://ldash.loganis.com)
* Add one or more Channels to your Loganis Account.
  * ch0 Channel name used in LCurl samples
* Obtain an API token first for your Loganis Account.
* More info can be found at [Loganis Docs](http://docs.loganis.com) site
* Check out this project and copy `lqs` script into ~/bin

```bash
git clone https://github.com/loganis/LCurl.git
cd LCurl
cp lqs ~/bin
chmod +x ~/bin/lqs
```

* Put your token to a file ex. `~/.my-token`
  * format: `token=your_token_characters`
* Query file format:
  * first line: `query=` then a valid Loganis query without comment
  * Check out [GA dimensions and metrics overview](http://docs.loganis.com/articles/GA_dim_met.html)
* Try a query file from `samples` sub-directory

```bash
lqs ~/.my-token samples/query-csv-gzip
"date","ch0:ga:visits"
"2014-03-31",49
"2014-04-01",39
"2014-04-02",38
"2014-04-03",31
"2014-04-04",18
"2014-04-05",9
...
```

## Output format :fmt

* Default output format of a query is JSON with Unix time
* To change output format, put a :fmt tag in your query
  * `:fmt "csv"` CSV with YYYY-MM-DD time
  * `:fmt "csz"` CSV with YYYY-MM-DD time using Gzipped transport
  * `:fmt "jsz"` JSON with Unix time using Gzipped transport

## Saving responses

* `lqs` script writes to STDOUT, you can save it to a file:

```bash
lqs ~/.my-token samples/query-csv-gzip > my-result.csv
```

## License

* LCurl can be distributed under [MIT License](https://raw.githubusercontent.com/loganis/LSheet/master/LICENSE)

## Copyright

* LSheet is Copyright (c) 2014 Loganis - iWebMa Ltd.
