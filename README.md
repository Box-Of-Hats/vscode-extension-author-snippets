# vscode-extension-author-snippets README

A collection of snippets for writing extensions for VSCode.

## Snippets

### Get selected text

Get the currently selected text in the active document.

```typescript
let textEditor = vscode.window.activeTextEditor;

if (!textEditor) {
    vscode.window.showErrorMessage("No active text editor found.");
    return;
}
let selectedText = textEditor.document.getText(textEditor.selection);
```

### Create new file/document

Create a new file in a given language, with content.

```typescript
vscode.workspace
    .openTextDocument({
        language: "plaintext",
        content: "file contents here"
    })
    .then(doc => {
        vscode.window.showTextDocument(doc).then(e => {
            vscode.commands.executeCommand("editor.action.formatDocument");
        });
    });
```
