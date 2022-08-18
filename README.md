# JSON-Pointer
This document serves as an easy to read explanation of the [JSON Pointer Specification](https://json-schema.org/draft/2019-09/relative-json-pointer.html).

JSON Pointer syntax allows the access of a specific element within a JSON document.

---

A path points to the desired element.

- The path begins with `/`
- Cues are separated by `/`
- A cue is either an object key or an array index

Given a JSON object:

```json
{
  "colors": ["red", "green", "blue"],
  "arg": "x";
  "": 0,
}
```

Below are shown the JSON pointer paths to each element:

```c++
<empty>			// the entire object is returned
/colors			["red", "green", "blue"]
/colors/0		"red"
/						0 // the key is treated as an empty string
```

