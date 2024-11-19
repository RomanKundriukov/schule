# HTML Seite.
## Basis Konstruktion

Hier siehst du ein Beispiel, wie eine HTML-Seite aussieht:

```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Name der Seite</title>
</head>
<body>
    <!-- Hier befindet sich dein Inhalt -->
    <p>Hier wird dein Content angezeigt, wie Tabellen oder anderes.</p>
</body>
</html>
```

# Tabellen

<div style="display: flex; gap: 20px;">
<div>

    ```html

    <style>
        table {
            border: 1px solid black;
            border-collapse: collapse;
        }
        td, th {
            border: 1px solid black;
            padding: 5px;
        }
    </style>

    <table>
        <tr>
            <th>
                Row 1 --> Col 1
            </th>
            <th>
                Row 1 --> Col 2
            </th>
        </tr>
        <tr>
            <td>
                Row 2 --> Col 1
            </td>
            <td>
                Row 2 --> Col 2
            </td>
        </tr>
    </table>
    ```

</div>
<div>
    <style>
        table {
            border: 1px solid black;
            border-collapse: collapse;
        }
        td, th {
            border: 1px solid black;
            padding: 5px;
        }
    </style>
    <table>
        <tr>
            <th>
                Row 1 --> Col 1
            </th>
            <th>
                Row 1 --> Col 2
            </th>
        </tr>
        <tr>
            <td>
                Row 2 --> Col 1
            </td>
            <td>
                Row 2 --> Col 2
            </td>
        </tr>
    </table>
</div>
</div>


