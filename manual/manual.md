Manual
======

## Obtaining an API Key

API Keys are stored in the MongoDB database as api-key records. Use the MongoDB CLI to add records.

## The .intexration File

The .intexration file is a JSON file containing build information about your document. The example below shows a project with two latex files, `main.tex` and `print.tex`, both located in the root of the repository. They share the same Bibtex file but have a separate index. For each document, the `name` field is required while the others are optional.

```javascript
{
  "documents": [
    {
      "name": "main",
      "dir": "/",
      "bib": "main.bib",
      "idx": "main.idx"
    },
    {
      "name": "print",
      "dir": "/",
      "bib": "main.bib",
      "idx": "print.idx"
    }
  ]
}
```

## Setting up the Hook

To add InTeXration to your project, navigate to *Webhooks & Services* under the repository preferences. Click the `Add webhook` button in the upper right corner. The payload url contains your API key as shown below. The *content type* is the default `application/json`.
```
http://intexration.com/hook/[API KEY]
```

If the web hook is setup successfully the server will respond with a simple JSON message.
```javascript
{"message":"WebHook Setup Successful"}
```