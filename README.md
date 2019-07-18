# USB-SATA
USB to SATA converter

# License
Hardware is with CERN OHL v1.2 license

Software is with GPL3 license

Documentation is with CC BY-SA 4.0 license

# USB-SATA Benchmark

[Reference](https://www.thomas-krenn.com/en/wiki/Linux_I/O_Performance_Tests_using_dd)


## Commands
### Streaming I/O
    dd if=/dev/zero of=/mnt/testfile bs=1G count=1 oflag=direct
    dd if=/dev/zero of=/mnt/testfile bs=512M count=1 oflag=direct
    dd if=/dev/zero of=/mnt/testfile bs=256M count=1 oflag=direct

### Latency
    hdparm -W0 /dev/sdx
    dd if=/dev/zero of=/mnt/testfile bs=512 count=1000 oflag=direct
    


## Results

| Board     | Streaming I/O |   Latency  |
| ----------|--------------:| ----------:|
| PC        |     30.2 MB/s | 37.3938 ms |
| A20-MICRO |     28.4 MB/s | 30.5117 ms |
| A10-LIME  |      7.6 MB/s | 33.1223 ms |
| A13-OLXn  |     30.0 MB/s |     -      |
| A64-OLXn  |     31.5 MB/s | 36.6841 ms |


### PC
#### Streaming I/O
    1073741824 bytes (1.1 GB, 1.0 GiB) copied, 35.5515 s, 30.2 MB/s
** 30.2 MB/s **
### Latency
    512000 bytes (512 kB, 500 KiB) copied, 37.3938 s, 13.7 kB/s
** 37.3938 ms **

## A20-OLinuXino-MICRO
### Streaming I/O
    536870912 bytes (537 MB) copied, 18.9142 s, 28.4 MB/s
** 28.4 MB/s **
### Latency
    512000 bytes (512 kB) copied, 30.5117 s, 16.8 kB/s
** 30.5117 ms ** 

## A10-Lime
### Streaming I/O
    268435456 bytes (268 MB) copied, 35.4505 s, 7.6 MB/s
** 7.6 MB/s **
### Latency
    512000 bytes (512 kB) copied, 33.1223 s, 15.5 kB/s
** 33.1223 ms ** 

## A13-OLinuXino
### Streaming I/O
    268435456 bytes (268 MB) copied, 8.96246 s, 30.0 MB/s
** 30.0 MB/s **

## A64-OLinuXino
### Streaming I/O
    536870912 bytes (537 MB, 512 MiB) copied, 17.0416 s, 31.5 MB/s
** 31.5 MB/s **
### Latency
    512000 bytes (512 kB, 500 KiB) copied, 36.6841 s, 14.0 kB/s
** 36.6841 ms ** 
