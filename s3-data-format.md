# S3 Data Format

## Top Level

```
$ s3cmd ls
2024-08-22 18:11  s3://0l-fyi-data-01
2024-08-24 12:31  s3://0l-fyi-data-01-v5
2024-08-24 12:31  s3://0l-fyi-data-01-v6
```

### Bucket Layout

```
$ s3cmd ls s3://0l-fyi-data-01-v5/
                          DIR  s3://0l-fyi-data-01-v5/parquets/
                          DIR  s3://0l-fyi-data-01-v5/transactions/
$ s3cmd ls s3://0l-fyi-data-01-v6/
                          DIR  s3://0l-fyi-data-01-v6/parquets/
                          DIR  s3://0l-fyi-data-01-v6/transactions/
$ s3cmd ls s3://0l-fyi-data-01/
                          DIR  s3://0l-fyi-data-01/parquets/
                          DIR  s3://0l-fyi-data-01/transactions/
```

### Directory Layout
#### V5

```
$ s3cmd ls s3://0l-fyi-data-01-v5/parquets/ | head
                          DIR  s3://0l-fyi-data-01-v5/parquets/0-99900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100000-199900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/1000000-1099900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/10000000-10099900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100000000-100099900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100100000-100199900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100200000-100299900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100300000-100399900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100400000-100499900/
                          DIR  s3://0l-fyi-data-01-v5/parquets/100500000-100599900/
```

```
 s3cmd ls s3://0l-fyi-data-01-v5/parquets/ | wc -l
1417
```
```
 s3cmd ls s3://0l-fyi-data-01-v5/parquets/68100000-68199900/
2024-08-24 12:58          957  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/burn.parquet.tar.gz
2024-08-24 12:58         1602  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/create_account.parquet.tar.gz
2024-08-24 12:58         2010  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/mint.parquet.tar.gz
2024-08-24 12:58       923170  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/new_block.parquet.tar.gz
2024-08-24 12:58        34325  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/received_payment.parquet.tar.gz
2024-08-24 12:58         8336  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/sent_payment.parquet.tar.gz
2024-08-24 12:58     73636292  s3://0l-fyi-data-01-v5/parquets/68100000-68199900/user_transaction.parquet.tar.gz
```
```
$ s3cmd ls s3://0l-fyi-data-01-v5/transactions/ | head
2024-08-24 12:34     26146300  s3://0l-fyi-data-01-v5/transactions/0-99900.tgz
2024-08-24 12:34     20073521  s3://0l-fyi-data-01-v5/transactions/100000-199900.tgz
2024-08-24 12:34     14137074  s3://0l-fyi-data-01-v5/transactions/1000000-1099900.tgz
2024-08-24 12:34     63657491  s3://0l-fyi-data-01-v5/transactions/10000000-10099900.tgz
2024-08-24 12:34     68759959  s3://0l-fyi-data-01-v5/transactions/100000000-100099900.tgz
2024-08-24 12:34    143598008  s3://0l-fyi-data-01-v5/transactions/100100000-100199900.tgz
2024-08-24 12:34    111745514  s3://0l-fyi-data-01-v5/transactions/100200000-100299900.tgz
2024-08-24 12:34     73999597  s3://0l-fyi-data-01-v5/transactions/100300000-100399900.tgz
2024-08-24 12:34    156861818  s3://0l-fyi-data-01-v5/transactions/100400000-100499900.tgz
2024-08-24 12:34    147345421  s3://0l-fyi-data-01-v5/transactions/100500000-100599900.tgz
```
```
$ s3cmd ls s3://0l-fyi-data-01-v5/transactions/ | wc -l
1417
```
#### V6
```
$ s3cmd ls s3://0l-fyi-data-01-v6
                          DIR  s3://0l-fyi-data-01-v6/parquets/
                          DIR  s3://0l-fyi-data-01-v6/transactions/
```
```
$ s3cmd ls s3://0l-fyi-data-01-v6/parquets/ | head
                          DIR  s3://0l-fyi-data-01-v6/parquets/0-9900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10000-19900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/100000-109900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/1000000-1009900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10000000-10009900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10020000-10029900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10030000-10039900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10040000-10049900/
                          DIR  s3://0l-fyi-data-01-v6/parquets/10050000-10059900/
```
```
$ s3cmd ls s3://0l-fyi-data-01-v6/parquets/10010000-10019900/
2024-08-24 14:45       867650  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/block_metadata_transaction.parquet.tar.gz
2024-08-24 14:45         3347  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/coin_balance.parquet.tar.gz
2024-08-24 14:45       357237  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/event.parquet.tar.gz
2024-08-24 14:45         1538  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/slow_wallet.parquet.tar.gz
2024-08-24 14:45       524252  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/state_checkpoint_transaction.parquet.tar.gz
2024-08-24 14:45          860  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/total_supply.parquet.tar.gz
2024-08-24 14:45       106030  s3://0l-fyi-data-01-v6/parquets/10010000-10019900/user_transaction.parquet.tar.gz
```
#### V7
```
$ s3cmd ls s3://0l-fyi-data-01/parquets/ | head
2024-09-04 13:38      5604050  s3://0l-fyi-data-01/parquets/0-9900.tar.gz
2024-09-04 13:38      1768895  s3://0l-fyi-data-01/parquets/10000-19900.tar.gz
2024-09-04 13:38      1766397  s3://0l-fyi-data-01/parquets/100000-109900.tar.gz
2024-09-04 13:38      1768153  s3://0l-fyi-data-01/parquets/1000000-1009900.tar.gz
2024-09-04 13:38      1787490  s3://0l-fyi-data-01/parquets/10000000-10009900.tar.gz
2024-09-04 13:38      1785162  s3://0l-fyi-data-01/parquets/10010000-10019900.tar.gz
2024-09-04 13:38      1787845  s3://0l-fyi-data-01/parquets/10020000-10029900.tar.gz
2024-09-04 13:38      1788267  s3://0l-fyi-data-01/parquets/10030000-10039900.tar.gz
2024-09-04 13:38      1788081  s3://0l-fyi-data-01/parquets/10040000-10049900.tar.gz
2024-09-04 13:38      1787984  s3://0l-fyi-data-01/parquets/10050000-10059900.tar.gz
```
```
$ s3cmd ls s3://0l-fyi-data-01/transactions/ | head
2024-08-24 10:30     27839983  s3://0l-fyi-data-01/transactions/0-9900.tgz
2024-08-24 10:30      2366919  s3://0l-fyi-data-01/transactions/10000-19900.tgz
2024-08-24 10:30      2649689  s3://0l-fyi-data-01/transactions/100000-109900.tgz
2024-08-24 10:30      2479753  s3://0l-fyi-data-01/transactions/1000000-1009900.tgz
2024-08-24 10:30      2526967  s3://0l-fyi-data-01/transactions/10000000-10009900.tgz
2024-08-24 10:30      2519739  s3://0l-fyi-data-01/transactions/10010000-10019900.tgz
2024-08-24 10:30      2542199  s3://0l-fyi-data-01/transactions/10020000-10029900.tgz
2024-08-24 10:30      2539767  s3://0l-fyi-data-01/transactions/10030000-10039900.tgz
2024-08-24 10:30      2511337  s3://0l-fyi-data-01/transactions/10040000-10049900.tgz
2024-08-24 10:30      2543799  s3://0l-fyi-data-01/transactions/10050000-10059900.tgz
```
## File Formats

### Parquet Files

Stored as compressed tar containing one .parquet file which
can be decoded with [pqrs](https://github.com/manojkarthick/pqrs):

```
$ s3cmd get s3://0l-fyi-data-01-v5/parquets/68100000-68199900/new_block.parquet.tar.gz
$ tar zxvf new_block.parquet.tar.gz
$ pqrs cat out/68100000-68199900/new_block.parquet | head

#############################################
File: out/68100000-68199900/new_block.parquet
#############################################

{version: 68100000, timestamp_usecs: 1663139714059953, round: 119273, proposer: [106, 159, 15, 160, 182, 189, 104, 127, 67, 67, 216, 136, 11, 64, 246, 151], proposed_time: 1663139714059953, gas_used: 100000000}
{version: 68100001, timestamp_usecs: 1663139714417004, round: 119274, proposer: [226, 100, 2, 51, 66, 180, 26, 204, 219, 182, 26, 25, 11, 108, 178, 167], proposed_time: 1663139714417004, gas_used: 100000000}
{version: 68100002, timestamp_usecs: 1663139714831376, round: 119275, proposer: [217, 110, 137, 226, 112, 165, 39, 61, 148, 188, 138, 183, 149, 55, 84, 249], proposed_time: 1663139714831376, gas_used: 100000000}
{version: 68100003, timestamp_usecs: 1663139715234628, round: 119276, proposer: [153, 9, 246, 237, 178, 160, 104, 74, 222, 205, 123, 68, 139, 152, 158, 79], proposed_time: 1663139715234628, gas_used: 100000000}
```

### Trancactions Files

Compressed tar containing a json file:

```
$ s3cmd get s3://0l-fyi-data-01-v5/transactions/100200000-100299900.tgz
$ tar zxvf 100200000-100299900.tgz
$ file 100233000-100233999.json
100233000-100233999.json: ASCII text, with very long lines (65536), with no line terminators
$ cat 100233000-100233999.json | jq | head -30
[
  {
    "timestamp_usecs": 1678488645070370,
    "version": 100233000,
    "transaction": {
      "type": "user",
      "sender": "ba249b81eac4279bb7f4be9fbc1b5889",
      "signature_scheme": "Scheme::Ed25519",
      "signature": "bb9c3904a2eee1c81d78cade57335eee2a2ca9e7f3940edeb3bf7c276d7286ff3c249afdb23c40ffe204c1d9a084a5fcee36f1e44a34fff45427a3148774250b",
      "public_key": "81bea5a9665bce56a05eaf7d8e07e8455ec2e6828d24ba28a879b344fced3e31",
      "secondary_signers": [],
      "secondary_signature_schemes": [],
      "secondary_signatures": [],
      "secondary_public_keys": [],
      "sequence_number": 12651,
      "chain_id": 1,
      "max_gas_amount": 100000,
      "gas_unit_price": 1,
      "gas_currency": "GAS",
      "expiration_timestamp_secs": 1678493595,
      "script_hash": "0000000000000000000000000000000000000000000000000000000000000000",
      "script_bytes": "0000000000000000000000000000000111546f776572537461746553637269707473116d696e657273746174655f636f6d6d69740004212005d34d7c8fe6af441cc718df2582287438dcb7c90708c756c4d8a68a85e2322aec0aea0a000fef88dc3406e2b358dc38f85fb9fa42cf41f373515c629ac39b64f6a3d4920100004c60e7f0722557b0a6b072cf42049852d58f7ee4e796238a85ef730aa2e925004207763710bf8abb5c8d4e223c6f33c2ea206ccf50e5c232d5244d80d5083b22003c4659c156e262f4932a32eaa07441c5c9897bda1bae48f0a0aaf84f5fba3f45004e87aab5d20c2bf83f0b305dcfb020e6f6b992c1a480767c36f9a1e835b85818ffd89499efd5e3d87657782c34bbce23afaf8e8e950a7022655ea641e288c0fcbb0009f5f683696845de282b5bd136faba530b100bed32699c48214d214ce737a1f600060805dfcc5bef9d9f41ab21a9581e5b8e68f655fd05d341356af015e2d3b5dd005a9e35acc7e4a35c04cf8ace394c6d019ab8a7f65296c5cf9079e2944388b1a2ffc8716006e9052f7b77c78d82d88f91a196fd84c3d3016b0e122a79404a03e5d3000ae849c8ad53dc8ceb0046307798cf3c481dd661f0a1a0e3095b327af7d2077dfffa8b5c5c38a8a1deafef5016551c4198c76166dca0866b63f48bf80dfa010e8d0051ddc40ebb2f5a47f4fff09ae25fd93feb720fbe6a71d2d490342b1465247686ffef8caf0047f8c2fd8615a97347b987744f7b5733e90dbd3260d5ef03b5421131001714cfa3b5b85144a159d77e6dea7ed6e46d7f6bdcc3b7cc280bae630918d366fffa3f5841288d6e250bf9bd76971cdc61e8d3d7e87997f74bf8a4d8e25d84995b005db6d5dd0994a88a0b4b9ed3a00d2ea751b85bb56b820ce49e78f49acbc67650ffd5a40d25213f17df8ee5bf0b767d95e5f83280a9a698f5843d4777b700eaa6cb00442f5a01237c164f00460bf02e48c2e09031300d9f2b4293f03ca1757f86fc650009ae06419722e90ca7ebb39839b252edaae0656c144465994e0531766c99fad3005c58df686ae5f574a11189662497459407f9a13d5de2a4b909f9632ae0f545a20031b8c9ab93957460598a01d6dec82f3215edaef215043d18c0c6f48a206fb067004f0ae9371f23c84d0a68c4487934f52ee83fcc46ed53482dfba8247171b1daea001fbedee448e4e71d84db6d33f83d259ee0c7c6ebea6810e37521a802a91e1cf5005ee87fd36b896865545e0dcc9153b3b8cb8d34e126a4ff420e8c2c137a4a8387ffc651886b468ffe1e3effe11d1de978b43a6a7c72b338bb94ebbfe33ebe5046c30001b509758c6e89cab94f45f0a7610c8a5ca932f56be07bdb79cae1b74375163bfffef07f2382fbadbeef4bcfc4eab3022ecb30c6f64a4be00401f3c78c56f9953d005733ba34e7005107aabe563684e0e465a46c2716c11e91665b759337a21d90b900287fefc3df366bc5f79aacd020dde04f76994a18d27123a714ca107bfa6e5beb0030deeb8032dc92e5cd1e452f817cf0bb7fc23fe08de879077f4dd05c7108cf0efffcbfee2ce9cf747f48746dd53ebba22bb286692574b9cfc224762028da1d5ed5005b3ac1ac0a29faae4900006503ddb6f2cd5a38f471490c1ad800c28e169619ae0034b0241263581c7b4a525599e5aa4001e2a98c6a2cc8bcaba29595de473b12a7000266635db5c76f890e4cd247b95eb554789fc95b13a1c5415f15f9b569f8eb4cffff1838c4cad4d06a4afb3efda1c7a71606f4af9368747da10566b5b47fd84c6b000f2f69046ac0b03b01c9774c32e9d0dbf6b0dc5c6be3cf6af1b5cd3ffd18af1c00013ae2340f72c91cac2a38f9a9aaa9bda506c28e4b6746b4ff70f9b47604eec50057162af09304fe903f01ecfa24aac4231a696b7abb5e04f660a71cacea00f96cffaa42ed9fee7734f64d0c1063934d61a4baa6473e110bc11ca79598c52411fef3001b7de95a28619c3ddc7c47529009d1d930bbdc131016fd878727159813d0578000162f60b5f4d70992a51884306520b540db4009327d21ff6ae9a6b3e040e5e70b08000e270700000000080002000000000000",
      "script": {
        "type": "script_function",
        "arguments_bcs": [
          "2005d34d7c8fe6af441cc718df2582287438dcb7c90708c756c4d8a68a85e2322a",
          "ea0a000fef88dc3406e2b358dc38f85fb9fa42cf41f373515c629ac39b64f6a3d4920100004c60e7f0722557b0a6b072cf42049852d58f7ee4e796238a85ef730aa2e925004207763710bf8abb5c8d4e223c6f33c2ea206ccf50e5c232d5244d80d5083b22003c4659c156e262f4932a32eaa07441c5c9897bda1bae48f0a0aaf84f5fba3f45004e87aab5d20c2bf83f0b305dcfb020e6f6b992c1a480767c36f9a1e835b85818ffd89499efd5e3d87657782c34bbce23afaf8e8e950a7022655ea641e288c0fcbb0009f5f683696845de282b5bd136faba530b100bed32699c48214d214ce737a1f600060805dfcc5bef9d9f41ab21a9581e5b8e68f655fd05d341356af015e2d3b5dd005a9e35acc7e4a35c04cf8ace394c6d019ab8a7f65296c5cf9079e2944388b1a2ffc8716006e9052f7b77c78d82d88f91a196fd84c3d3016b0e122a79404a03e5d3000ae849c8ad53dc8ceb0046307798cf3c481dd661f0a1a0e3095b327af7d2077dfffa8b5c5c38a8a1deafef5016551c4198c76166dca0866b63f48bf80dfa010e8d0051ddc40ebb2f5a47f4fff09ae25fd93feb720fbe6a71d2d490342b1465247686ffef8caf0047f8c2fd8615a97347b987744f7b5733e90dbd3260d5ef03b5421131001714cfa3b5b85144a159d77e6dea7ed6e46d7f6bdcc3b7cc280bae630918d366fffa3f5841288d6e250bf9bd76971cdc61e8d3d7e87997f74bf8a4d8e25d84995b005db6d5dd0994a88a0b4b9ed3a00d2ea751b85bb56b820ce49e78f49acbc67650ffd5a40d25213f17df8ee5bf0b767d95e5f83280a9a698f5843d4777b700eaa6cb00442f5a01237c164f00460bf02e48c2e09031300d9f2b4293f03ca1757f86fc650009ae06419722e90ca7ebb39839b252edaae0656c144465994e0531766c99fad3005c58df686ae5f574a11189662497459407f9a13d5de2a4b909f9632ae0f545a20031b8c9ab93957460598a01d6dec82f3215edaef215043d18c0c6f48a206fb067004f0ae9371f23c84d0a68c4487934f52ee83fcc46ed53482dfba8247171b1daea001fbedee448e4e71d84db6d33f83d259ee0c7c6ebea6810e37521a802a91e1cf5005ee87fd36b896865545e0dcc9153b3b8cb8d34e126a4ff420e8c2c137a4a8387ffc651886b468ffe1e3effe11d1de978b43a6a7c72b338bb94ebbfe33ebe5046c30001b509758c6e89cab94f45f0a7610c8a5ca932f56be07bdb79cae1b74375163bfffef07f2382fbadbeef4bcfc4eab3022ecb30c6f64a4be00401f3c78c56f9953d005733ba34e7005107aabe563684e0e465a46c2716c11e91665b759337a21d90b900287fefc3df366bc5f79aacd020dde04f76994a18d27123a714ca107bfa6e5beb0030deeb8032dc92e5cd1e452f817cf0bb7fc23fe08de879077f4dd05c7108cf0efffcbfee2ce9cf747f48746dd53ebba22bb286692574b9cfc224762028da1d5ed5005b3ac1ac0a29faae4900006503ddb6f2cd5a38f471490c1ad800c28e169619ae0034b0241263581c7b4a525599e5aa4001e2a98c6a2cc8bcaba29595de473b12a7000266635db5c76f890e4cd247b95eb554789fc95b13a1c5415f15f9b569f8eb4cffff1838c4cad4d06a4afb3efda1c7a71606f4af9368747da10566b5b47fd84c6b000f2f69046ac0b03b01c9774c32e9d0dbf6b0dc5c6be3cf6af1b5cd3ffd18af1c00013ae2340f72c91cac2a38f9a9aaa9bda506c28e4b6746b4ff70f9b47604eec50057162af09304fe903f01ecfa24aac4231a696b7abb5e04f660a71cacea00f96cffaa42ed9fee7734f64d0c1063934d61a4baa6473e110bc11ca79598c52411fef3001b7de95a28619c3ddc7c47529009d1d930bbdc131016fd878727159813d0578000162f60b5f4d70992a51884306520b540db4009327d21ff6ae9a6b3e040e5e70b",
          "000e270700000000",
          "0002000000000000"
        ],
```

