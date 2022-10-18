# JSON-Pointer
This document serves as an easy to read explanation of the [JSON Pointer Specification](https://www.rfc-editor.org/rfc/rfc6901).

JSON Pointer syntax allows the access of a specific element within a JSON document.

---

A path points to the desired element.

- The path begins with `/`
- Keys are separated by `/`
- A key is either an object key or an array index

Given a JSON object:

```json
{
   "colors": ["red", "green"],
   "": 0,
   "a/b": 1,
   "c%d": 2,
   "e^f": 3,
   "g|h": 4,
   "i\\j": 5,
   "k\"l": 6,
   " ": 7,
   "m~n": 8
}
```

Below are the JSON pointer paths to each element:

```c++
""           	// the whole document
"/colors"    	["red", "green"]
"/colors/0"  	"red"
"/"          	0
"/a~1b"      	1
"/c%d"       	2
"/e^f"       	3
"/g|h"       	4
"/i\\j"      	5
"/k\"l"      	6
"/ "         	7
"/m~0n"      	8
```

`~` is delimited with `~0`

`/` is delimited with `~1`

### Nested Example

```json
{
  "grandparent": {
    "parent": {
      "child": {
        "name": "bob"
      }
    }
  }
}
```

The path to `"bob"` is `"/grandparent/parent/child/name"`.
