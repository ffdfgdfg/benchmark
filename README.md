# Benchmark
A simple benchmark testing tool implemented in golang, the basic functions refer to wrk and ab, added some small features based on personal needs.
## Why use Benchmark?
- http and socks5 proxy support
- good performance as wrk(some implements in golang not work well)
- simple code, easy to change
## Building

```
git clone git://github.com/cnlh/benchmark.git
cd benchmark
go build
```
## usage

basic usage is quite simple:
```
benchmark [flags] url
```

with the flags being
```
    -b string
      	the body of request
    -c int
      	the number of connection (default 1000)
    -cpu int
      	the number of cpu used
    -h string
      	request header, split by \r\n
    -host string
      	the host of request
    -m string
      	request method (default "GET")
    -n int
      	the number of request (default 100000)
    -t int
      	request/socket timeout in ms (default 3000)
    -proxy string
    	proxy of request
```
for example
```
benchmark -c 1100 -n 1000000  http://127.0.0.1/
```

## Example Output
```shell script
Running 1000000 test @ 127.0.0.1:80 by 1100 connections
1000000 requests in 5.73s, 4.01GB read, 33.42MB write
Requests/sec: 174420.54
Transfer/sec: 721.21MB
Error       : 0
Percentage of the requests served within a certain time (ms)
    50%				5
    65%				6
    75%				7
    80%				7
    90%				9
    95%				13
    98%				19
    99%				23
   100%				107
```