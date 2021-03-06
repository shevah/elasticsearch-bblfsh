# elasticsearch-bblfsh

"Code as data" can be a powerful idea, but I don't think there are many concrete examples. To explore this concept, I used [bblfshd](https://bblf.sh) to analyze the Elasticsearch code base to get a full list of all the configurable settings in Elasticsearch.

[Take a look at the generated settings here.](https://nickcanzoneri.com/elasticsearch-settings/)

## The problem space

Elasticsearch has a lot of configurable settings and they aren't fully listed anywhere. Some are dynamic, some are not. I wanted to explore how to get **all** of the settings and their properties to see what I could do. 

## The main tech

This analysis is powered by [bblfshd](https://bblf.sh) (pronounced babelfish). It's takes code and produces a "universal abstract syntax tree" (uast) of the code and supports a number of languages. Elasticsearch is written in Java which is one of the provided languages.

## Getting up and running

### Prereqs

* Is written in go, so you need to have go installed
* Assumes bblfshd is running on localhost:9432, see [their docs on getting started](https://doc.bblf.sh/user/getting-started.html)
* Need to have a checkout of the [Elasticsearch codebase](https://github.com/elastic/elasticsearch) somewhere on disk

### Building and running

* `cd` into `cmd/elasticsearch-bblfsh`
* `go build` will make the `elasticsearch-bblfsh` executable
* `./elasticsearch-bblfsh` will create `elasticsearchSettings.json` with all of the settings found 

## Caveats

This was a fun experiment for me. I'm very new at writing go code and it's probably all wrong. Use at your own risk.
