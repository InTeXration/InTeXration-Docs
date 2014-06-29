# API

## Hooks
Both call return a list of blueprint objects.

### All Hooks
```
/hook/:owner/:repo
```

### Hooks by Owner & Repo
```
/hook/:owner/:repo
```
```javascript
[{
    "owner": "InTeXration",
    "repo": "TexExample",
    "url": "https://github.com/InTeXration/TexExample",
    "pusher": "JDevlieghere",
    "message": "Update main.tex",
    "_id": "53a5e07e8fa22b120e0e937b",
    "__v": 0,
    "timestamp": "2014-06-21T19:43:58.713Z"
}]
```
## Builds
Completed builds. Returns a list of build objects.

```
/build
```

```
/build/:owner/:repo
```

```javascript
[{
    "_id": "53a5baeb8bca181e0be769d1",
    "documents": [{
        "name": "main",
        "_id": "53a5baeb8bca181e0be769d2",
        "files": [{
            "type": "pdf",
            "name": "main.pdf",
            "dir": "public/InTeXration/TexExample/main",
            "_id": "53a5baeb8bca181e0be769d4"
        }, {
            "type": "log",
            "name": "main.log",
            "dir": "public/InTeXration/TexExample/main",
            "_id": "53a5baeb8bca181e0be769d3"
        }]
    }],
    "timestamp": "2014-06-21T17:03:36.546Z",
    "__v": 0,
    "blueprint": {
        "owner": "InTeXration",
        "repo": "TexExample",
        "url": "https://github.com/InTeXration/TexExample",
        "pusher": "JDevlieghere",
        "message": "Update main.tex",
        "timestamp": "2014-06-21T17:03:36.522Z"
    }
}]
```

## Files

### PDF
```
/file/:owner/:repo/:name/pdf
```

### Log
```
/file/:owner/:repo/:name/log
```

### Error & Warning Data

```
/file/:owner/:repo/:name/data
```

```javascript
{
    "errors": [" LaTeX Error: Missing \\begin{document}.\n", " I can't find file `main.aux'.\n\\enddocument ...keatletter \\@@input \\jobname .aux \n                                                  \\fi \\@dofilelist \\ifdim \\f...\nl.11 \\end{document}\n                   \n(Press Enter to retry, or Control-D to exit)\nPlease type another input file name\n! Emergency stop.\n\\enddocument ...keatletter \\@@input \\jobname .aux \n                                                  \\fi \\@dofilelist \\ifdim \\f...\nl.11 \\end{document}\n                   \n*** (job aborted, file error in nonstop mode)\n", "  ==> Fatal error occurred, no output PDF file produced!\n"],
    "warnings": []
}
```