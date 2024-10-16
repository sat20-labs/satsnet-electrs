# Electrum

* Snapshot DB after successful indexing - and run queries on the latest snapshot
* Update height to -1 for txns with any [unconfirmed input](https://electrumx.readthedocs.io/en/latest/protocol-basics.html#status)

# Rust

* Use [bytes](https://carllerche.github.io/bytes/bytes/index.html) instead of `Vec<u8>` when possible
* Use generators instead of vectors
* Use proper HTTP parser for JSONRPC replies over persistent connection

# Performance

* Consider https://github.com/facebook/rocksdb/wiki/RocksDB-Tuning-Guide#difference-of-spinning-disk


# note

curl --user jacky:_RZekaGRgKQJSIOYi6vq0_CkJtjoCootamy81J2cDn0 --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnetworkinfo", "params": []}' -H 'content-type: text/plain;' http://192.168.10.101:8332/

curl --user jacky:_RZekaGRgKQJSIOYi6vq0_CkJtjoCootamy81J2cDn0 --data-binary '{"jsonrpc": "1.0", "id": "1", "method": "getblockcount", "params": []}' -H 'content-type: text/plain;' --cacert ./rpc.cert https://192.168.10.102:8337/