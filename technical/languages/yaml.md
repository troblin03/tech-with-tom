# YAML

YAML stands for YAML ain't markup language and is a language for defining data or configurations that is _human-readable_. It is often used as a language for Infrastructure as Code (IaC) in the cloud and otherwise.

A YAML document is an **unordered** collection of key:value pairs, each key having a value.

```
key: value
key: value
key: value
```

YAML supports strings, numbers, floating points, boolean, and null.

YAML also allows arrays or lists as an _ordered_ set of values.

```
daysofweek: ["Monday", "Tuesday", "Wednesday"]
```

This is known as inline format but we can also represent lists in another way:

```
daysofweek:
  - "Monday"
  - "Tuesday"
  - "Wednesday"
```

In YAML, indentation matters. This is because it shows that things are within the same structure (e.g. the same list in the above example).

IN YAML, a dictionary is a collection of key value pairs. This allows us to create richer, more complex data structures. For example:

```
daysofweek:
  - name: "Monday"
    mood: [sad, angry]
  - name: "Tuesday"
    mood: "mixed"
  - name: "Wednesday"
    mood: "happy"
    numhoursworked: 4
```

An example of where YAML may be used is, as mentioned, in provisioning cloud infrastructure as code. An example template is below for an S3 bucket:

```
Resources:
  s3bucket:
    Type: "AWS::S3::Bucket"
    Properties:
      BucketName: "trmoodboard"
```

The 'Resources' dictionary contains within it a key, 's3bucket' which is in itself a dictionary. The dictionary contains 'Type' and 'Properties' keys where 'Type' is a string value and 'Properties is a dictionary containing 'BucketName', a key with the value "trmoodboard".
