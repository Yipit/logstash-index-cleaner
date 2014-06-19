logstash-index-cleaner
======================

THIS PROJECT IS DEPRECATED! USE elasticsearch-curator: https://github.com/elasticsearch/curator
-------------------------------------------------------------------------------------------------------------------




Delete logstash indexes older than n days from ElasticSearch.

::

  $ logstash-index-cleaner -h
  usage: logstash-index-cleaner [-h] [-v] [--host HOST] [--port PORT]
                                [-t TIMEOUT] [-p PREFIX] [-s SEPARATOR]
                                [-H HOURS_TO_KEEP] [-d DAYS_TO_KEEP] [-n]

  Delete old logstash indices from Elasticsearch.

  optional arguments:
    -h, --help            show this help message and exit
    -v, --version         show program's version number and exit
    --host HOST           Elasticsearch host.
    --port PORT           Elasticsearch port
    -t TIMEOUT, --timeout TIMEOUT
                          Elasticsearch timeout
    -p PREFIX, --prefix PREFIX
                          Prefix for the indices. Indices that do not have this
                          prefix are skipped.
    -s SEPARATOR, --separator SEPARATOR
                          Time unit separator
    -H HOURS_TO_KEEP, --hours-to-keep HOURS_TO_KEEP
                          Number of hours to keep.
    -d DAYS_TO_KEEP, --days-to-keep DAYS_TO_KEEP
                          Number of days to keep.
    -n, --dry-run         If true, does not perform any changes to the
                          Elasticsearch indices.



Project history
---------------

This is a fork of https://github.com/crashdump/logstash-elasticsearch-scripts.

Since ElasticSearch 0.90 all fields are compressed, and some benchmarks show that
nothing improves optimizing those already compressed indices. That's why this fork
does not include the original `logstash_index_optimize.py`


Optimizations references:

* https://github.com/logstash/logstash/wiki/Elasticsearch-Storage-Optimization
* https://github.com/jordansissel/experiments/tree/master/elasticsearch/disk
