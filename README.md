It seems there was an issue with generating the README.md file. Let me create the content for you directly here:

```markdown
# Clipboard Script for Google AppSheet

This project provides a simple HTML and JavaScript snippet that enables a Google AppSheet app to write to the clipboard. The script reads a 'text' parameter from the URL and copies it to the clipboard, supporting both modern and fallback methods.

## Features

- Copies text to clipboard using the modern `navigator.clipboard` API if available.
- Falls back to using a temporary `textarea` element for older browsers.
- Displays an alert to confirm that the text has been copied.
- Automatically closes the window after copying the text.

## Usage

1. Include the HTML and JavaScript snippet in your project.
2. Pass the text to be copied as a URL parameter named `text`.

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Clipboard Script</title>
</head>
<body>
    <script>
        function copyToClipboard(text) {
            if (navigator.clipboard) {
                navigator.clipboard.writeText(text).then(function() {
                    alert("Copied to clipboard: " + text);
                    window.close();
                }).catch(function(err) {
                    console.error("Failed to copy: ", err);
                });
            } else {
                var dummy = document.createElement("textarea");
                document.body.appendChild(dummy);
                dummy.value = text;
                dummy.select();
                document.execCommand("copy");
                document.body.removeChild(dummy);
                alert("Copied to clipboard: " + text);
                window.close();
            }
        }

        // Get the text parameter from the URL
        const urlParams = new URLSearchParams(window.location.search);
        const textToCopy = urlParams.get('text');

        // Copy the text to clipboard
        if (textToCopy) {
            copyToClipboard(textToCopy);
        }
    </script>
</body>
</html>
```

## License

This project is licensed under the MIT License.
```
