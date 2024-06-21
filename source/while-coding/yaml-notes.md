# YAML notes

## what is YAML
YAML = YAML ain't markup language

Main website: https://yaml.org/

YAML is a data serialisation language designed to be directly writable and readable by humans.

It’s a strict superset of JSON, with the addition of syntactically significant newlines and indentation, like Python.

a yaml document is a map of key and values. `key: value`.

YAML needs a parser to create serialized stream of bits from YAML document. You can also convert a YAML into Java objects using [snakeyaml engine](https://bitbucket.org/snakeyaml/snakeyaml-engine/src/master/README.md), or [jackson yaml](https://github.com/FasterXML/jackson-dataformats-text/tree/master/yaml) (which again uses snakeyaml underneath). A good understanding of YAML processing is given [here](https://tutorialreference.com/yaml/yaml-processes#yaml-process-flow)

All the parsers will interpret the content of a yaml file with reference to [yaml spec](https://yaml.org/spec/1.2.2/). 

## syntax 

Good place to learn syntax: https://learnxinyminutes.com/docs/yaml/

yaml comments start with `#`. And yaml only supports single line comments.




