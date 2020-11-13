---
layout: post
title: "Python Tips and Tricks"
subtitle: "Various tips and tricks for python"
categories: coding
tags: python
comments: true
---
# 1. General
## How to check the version of python module
```markdown
pip freeze
```

# 2. JSON tips and tricks
## To serialize into json
```python
import json

python_object = dict()

json_dump = json.dumps(python_object)

```

### To json file

```python
def to_file(file_name, data):
    with open(file_name,  'w', encoding="utf-8") as json_file:
        json_file.write(data)
```

## To deserialize from json
```python
import json

json_string = "{}"

json_object = json.loads(json_string)

```

### From a json file
```python
import json

def from_file(path):
    try:
        f = open(path, "r", encoding="utf-8")
        data = json.load(f)
        f.close()
        return data

    except Exception as ex:
        print(ex)
```