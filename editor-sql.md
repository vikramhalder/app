```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <title>SQL Editor</title>
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/codemirror.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/theme/material.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/addon/hint/show-hint.min.css">
      <style>
         #editor {
         height: 200px;
         }
         #results {
         margin-top: 20px;
         }
      </style>
   </head>
   <body>
      <h1>SQL Editor</h1>
      <textarea id="editor"></textarea>
   </body>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/codemirror.min.js"></script>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/mode/sql/sql.min.js"></script>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/addon/hint/show-hint.min.js"></script>
   <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/addon/hint/sql-hint.min.js"></script>
   <script>
      var editor = CodeMirror.fromTextArea(document.getElementById("editor"), {
      	mode: 'text/x-sql',
      	theme: 'material',
      	lineNumbers: true,
      	extraKeys: { "Ctrl-Space": "autocomplete" },
      	hintOptions: {
      		tables: {
      			users: ["name", "score", "birthDate"],
      			countries: ["name", "population", "size"]
      		}
      	}
      });
          
      editor.on("keyup", function (cm, event) {
      	 if (!cm.state.completionActive && 
      		 event.keyCode != 13) {
      		 CodeMirror.commands.autocomplete(cm, null, {completeSingle: false});
      	 }
       }); 
   </script>
</html>
```
