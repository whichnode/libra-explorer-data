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


