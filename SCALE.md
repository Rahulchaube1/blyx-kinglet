# Checkpoint slices across shard boundaries

Pass the tensor length in elements, element width in bytes, maximum elements per file, first requested element, element count and zero-based part number. The CLI prints the number of affected shards, the shard index and the local first byte, byte length and inclusive last byte. Query each part and concatenate its bytes in that order.

## Try the native command

Extract the archive for your platform from the [Kinglet 0.2.0 release](https://github.com/Rahulchaube1/blyx-kinglet/releases/tag/v0.2.0). Add its directory to PATH or use the executable’s full path. Run the fixture commands from the extracted directory.

~~~sh
kinglet range 2199023255552 2 1073741824 1099511627774 5 0
kinglet range 2199023255552 2 1073741824 1099511627774 5 1
~~~

## Scope and input contract

Shards are consecutive, headerless, fixed-width payloads with a possibly shorter last file. Add your format’s payload offset before reading a containerized file. The command calculates intervals and leaves storage I/O and integrity checks to the caller. File-relative byte counts must fit signed 64-bit integers.

## Import in Blyx

The executable includes its runtime. To compile the source example, install the tested compiler revision and a host linker, then run these commands from the tagged source tree.

~~~sh
cargo install --locked --git https://github.com/Rahulchaube1/blyxxxx --rev 120d6b6ec6df09ff018d7c18752fb3297b5e629d blyxc
blyxc native-run scale_example.blyx
~~~

~~~blyx
use checkpoint_ranges;

fn main() {
    let elements = 2199023255552;
    let first = 1099511627774;
    let shard = 1073741824;
    println!(kinglet_checkpoint_range(elements,2,shard,first,5,0,0));
    println!(kinglet_checkpoint_range(elements,2,shard,first,5,0,3));
    println!(kinglet_checkpoint_range(elements,2,shard,first,5,1,3));
}
~~~

## Verification

The ten requested bytes occupy bytes 2,147,483,644 through 2,147,483,647 in shard 1023 and bytes 0 through 5 in shard 1024. The reference test reassembled 32 slices from actual local files and compared the bytes with the unsharded fixture. [Study, raw timings and reproduction instructions](https://www.blyx-lang.space/articles/training-in-factors)
