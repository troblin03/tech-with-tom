# JSON

JSON stands for JavaScript Object Notation and is a lightweight data-interchange format. As with YAML, it is designed to be easy for humans to both read and write as well as being easy for machines to parse and generate.

In comparison to YAML, JSON doesn't care about indentation which can make it more forgiving to write with.

The first thing to be aware of is an 'object' which is an unordered set of key: value pairs enclosed by curly brackets { & }

```
{"Monday": "day", "January", "month"}
```

This is the equivalent of the YAML dictionary.

A YAML list is named an 'array' in JSON format and is an ordered collection of values seperated by commas but enclosed in square brackets [ & ]

```
[ "day", "day", "month", "day"]
```

Combining this in a JSON document may look like this:

```
{
  "monday" : {
    "mood" : ["sad", "angry"]
    "numhoursworked" : "6"
  }
  "tuesday" : {
    "mood" : "mixed"
    "numhoursworked" : "4"
  }
  "wednesday" : {
    "mood" : "excited"
    "numhoursworked" : "5"
  }
  "thursday" : {
    "mood" : "impatient"
    "numhoursworked" : "2"
  }
}
```

It's worth noting that in AWS, JSON has an advantage over YAML in that it can be used for _both_ CloudFormation templates and identitiy policy documents, as opposed to just CloudFormation templates.
