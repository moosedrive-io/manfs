manfs is a specification for describing filesystem contents using manifest
files. It's designed to be simple and flexible.

The name is sort of a portmanteau of **MAN**ifest and **F**ile**S**ystem.


# Schema

The base schema is very simple:

```json
{
  "type": String ("file" or "folder),
  "children": Object (of nested manfs instances)
  "appData": Object (arbitrary data for use by apps),
}
```

# Examples

file:

```json
{
  "type": "file",
  "appData": {
    "title": "Post Title",
    "format": "html",
    "publish": false,
  }
}
```

folder:

```json
{
  "type": "folder",
  "children": {
    "file1": {
      "type": "file",
      "appData": {
        "title": "Post 1 Title",
        "format": "html",
        "publish": false,
      }
    },
    "file2": {
      "type": "file",
      "appData": {
        "title": "Post 2 Title",
        "format": "markdown",
        "publish": true,
      }
    },
    "folder1": {
      "type": "folder",
      "children": {
        ...
      }
    }
  }
}
```
