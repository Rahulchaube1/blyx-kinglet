## Serve a byte range at end of file

Returns [status, body offset, body length, full length]. Mode 0 sends the full body, 1 uses first/last, 2 uses first as a suffix count. Header parsing and multipart ranges belong to the host. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `kinglet-demo.blyx`.
2. Type `blyx-kinglet-demo` and select **Kinglet — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
206
90
10
100
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-kinglet)
