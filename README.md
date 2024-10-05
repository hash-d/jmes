
# jmes

(name subject to change)

A command line JMESPath processor for YAML and JSON (plus limited CSV handling, experimental TOML, and ouput-only table format).

# Examples

## Data

    list of dicts:
    - ordinal: first
      cardinal: one
      number: 1
    - ordinal: second
      cardinal: two
      number: 2
    - number: 3
      ordinal: third
      cardinal: three

## Conversions

### To JSON

    $ jmes -J @ test/data/sample.yaml
    {
      "list of dicts": [
        {
          "ordinal": "first",
          "cardinal": "one",
          "number": "1"
        },
        {
          "ordinal": "second",
          "cardinal": "two",
          "number": "2"
        },
        {
          "number": "3",
          "ordinal": "third",
          "cardinal": "three"
        }
      ]
    }

### To table

    $ jmes --table @ test/data/sample.yaml
        ordinal    cardinal      number
    --  ---------  ----------  --------
     0  first      one                1
     1  second     two                2
     2  third      three              3
