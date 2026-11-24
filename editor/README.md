# Blyx Kinglet

Plan a full or single-range HTTP response against a known representation size.

This extension includes the Blyx Kinglet 0.2.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Checkpoint slices across shard boundaries

Map a checkpoint tensor slice to exact, shard-local byte ranges for storage or HTTP range readers. [Commands and worked example](https://github.com/Rahulchaube1/blyx-kinglet/blob/v0.2.0/SCALE.md) · [Measurements and source data](https://www.blyx-lang.space/articles/training-in-factors)

## Run in the editor

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

## Use Kinglet in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/kinglet`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-kinglet-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyx-kinglet/releases/download/v0.2.0/blyx-kinglet-starter-0.2.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/kinglet) · [Framework source](https://github.com/Rahulchaube1/blyx-kinglet/tree/v0.2.0) · [Report an issue](https://github.com/Rahulchaube1/blyx-kinglet/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
