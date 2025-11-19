## How to reproduce

### 1. Install dependencies

```sh
npm install
```

### 2. Run @tailwindcss/cli to compare results

```sh
npm run compile
```

This runs

<table>
    <tbody>
        <tr>
            <td>
```sh
npx @tailwindcss/cli -i ./working-input.css -o ./working-output.css
```
            </td>
            <td>
```sh
npx @tailwindcss/cli -i ./failing-input.css -o ./failing-output.css
```
            </td>
        </tr>
    </tbody>
</table>

### 3. Compare output CSS files and see that the colors end up with different names

Here's the diff of [the output I expect](./working-output.css) and [the output that I get](./failing-output.css):

```diff
 @layer utilities {
-  .text-camelCased {
+  .text-camel-cased {
-    color: var(--color-camelCased);
+    color: #ffffff;
   }
 }
```

