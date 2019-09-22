# vscode-extension-author-snippets README

A collection of snippets for writing extensions for VSCode.

## Snippets

### Get selected text

```typescript
let textEditor = vscode.window.activeTextEditor;

if (!textEditor) {
    vscode.window.showErrorMessage("No active text editor found.");
    return;
}
let selectedText = textEditor.document.getText(textEditor.selection);
```
