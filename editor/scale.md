# Read a checkpoint slice

Pass the tensor length in elements, element width in bytes, maximum elements per file, first requested element, element count and zero-based part number. The CLI prints the number of affected shards, the shard index and the local first byte, byte length and inclusive last byte. Query each part and concatenate its bytes in that order.

The ten requested bytes occupy bytes 2,147,483,644 through 2,147,483,647 in shard 1023 and bytes 0 through 5 in shard 1024. The reference test reassembled 32 slices from actual local files and compared the bytes with the unsharded fixture.

[Native commands and compiler installation](https://github.com/Rahulchaube1/blyx-kinglet/blob/v0.2.0/SCALE.md)
