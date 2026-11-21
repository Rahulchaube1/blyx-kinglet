<img src="assets/logo.png" width="112" height="112" alt="Kinglet logo">

# Kinglet

Plan a full or single-range HTTP response against a known representation size. This Blyx workflow framework is part of the graphql, rpc and http collection.

An inclusive last byte becomes a read length with a plus one. Handle suffixes, empty resources and unsatisfied offsets explicitly. [IETF RFC 9110, byte ranges](https://www.rfc-editor.org/rfc/rfc9110.html#section-14.1.2)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-kinglet.git
cd blyx-kinglet
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-kinglet) · [Package page](https://www.blyx-lang.space/packages/kinglet) · [Handbook](https://doc.blyx-lang.space/guide/kinglet)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-kinglet.git vendor/kinglet
```

```blyx
use vendor::kinglet::kinglet;

fn main() {
    let size = 100.0;
    let mode = 1.0;
    let first = 90.0;
    let last = 200.0;
    let result = kinglet_respond(size, mode, first, last);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
206
90
10
100
```

## API

`kinglet_respond(size, mode, first, last)`

Returns [status, body offset, body length, full length]. Mode 0 sends the full body, 1 uses first/last, 2 uses first as a suffix count. Header parsing and multipart ranges belong to the host. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| size | A nonnegative exact integer |
| mode | A nonnegative exact integer |
| first | A nonnegative exact integer |
| last | A exact signed integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- 100 1 90 200
```

## Libraries

- [ByteRange](https://github.com/Rahulchaube1/blyx-byterange/tree/v0.1.0) — Resolve a single inclusive HTTP byte range to an offset and length.
- [SuffixRange](https://github.com/Rahulchaube1/blyx-suffixrange/tree/v0.1.0) — Resolve an HTTP suffix-byte specification without negative offsets.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-kinglet/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The package artwork uses [Lucide icons](https://lucide.dev/license); see [artwork notices](assets/NOTICE.txt).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
