---
title: DevReplay
layout: default
subtitle: A linter based on developer own coding convention.
---

# Quick start

You can install DevReplay using [npm](https://nodejs.org) or yarn:

```sh
npm install -g devreplay
# or
yarn global add devreplay
```

You should then make a `devreplay.json` file.
Here is the example.
```json
[
    {
        "before": [
            "tmp = $1",
            "$1 = $2",
            "$2 = tmp"
        ],
        "after": [
            "$1, $2 = $2, $1"
        ]
    }
]
```

Fix the your source file.
```sh
devreplay --fix yourfile.py > yourfile.py
```

```diff
- tmp = a
- a = b
- b = a
+ a, b = b, a
```
Check out [the full usage guide](https://devreplay.github.io/docs.html) to learn more.