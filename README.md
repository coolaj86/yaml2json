yaml2json
=========

A command-line utility to convert YAML to JSON (meaning a `.yml` file to a `.json` file)

The purpose of this utility is to minify YAML as JSON.
(ignore the misnomer, YAML is actually an Object Notation, not a Markup Language)

Installation
===

```bash
npm install -g yaml2json
```

Usage
===

Specify a file:

```bash
yaml2json ./example.yml

json2yaml ./example.json | yaml2json
```

Or pipe from stdin:

```bash
curl -s http://foobar3000.com/echo/echo.json | json2yaml | yaml2json

wget -qO- http://foobar3000.com/echo/echo.json | json2yaml | yaml2json
```

Example
===

```yaml
---
  foo: bar
  baz:
    - qux
    - quxx
  corge: null
  grault: 1
  garply: true
  waldo: "false"
  fred: undefined
```

becomes

```javascript
{
  "foo": "bar",
  "baz": [
    "qux",
    "quxx"
  ],
  "corge": null,
  "grault": 1,
  "garply": true,
  "waldo": "false",
  "fred": "undefined"
}
```

*Note*: JSON is a proper subset of YAML.
The difference is that YAML can use whitespace instead of syntax, which is more human-readable.
Also, YAML supports comments.

Alias
===

`yaml2json` has the following aliases:

  * `yml2json`
  * `yamltojson`
  * `ymltojson`
