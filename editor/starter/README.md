# Kinglet starter

Plan a full or single-range HTTP response against a known representation size.

Open the extracted folder in VS Code. With Blyx 0.2.1 and its host toolchain installed, choose **Terminal → Run Task → Run Kinglet** or run the following command in this directory.

```sh
blyxc native-run main.blyx
```

Expected output

```text
206
90
10
100
```

The vendor directory contains the framework source for 0.1.0 and its license texts. [Read the API guide](https://www.blyx-lang.space/packages/kinglet) · [View the release](https://github.com/Rahulchaube1/blyx-kinglet/releases/tag/v0.2.0)

## Scale example

Map a checkpoint tensor slice to exact, shard-local byte ranges for storage or HTTP range readers. Install this compiler and run the editable example from the starter directory.

~~~sh
cargo install --locked --git https://github.com/Rahulchaube1/blyxxxx --rev 120d6b6ec6df09ff018d7c18752fb3297b5e629d blyxc
blyxc native-run scale_example.blyx
~~~
