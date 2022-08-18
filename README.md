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
   "foo": ["bar", "baz"],
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

Below are shown the JSON pointer paths to each element:

```c++
""           // the whole document
"/foo"       ["bar", "baz"]
"/foo/0"     "bar"
"/"          0
"/a~1b"      1
"/c%d"       2
"/e^f"       3
"/g|h"       4
"/i\\j"      5
"/k\"l"      6
"/ "         7
"/m~0n"      8
```
