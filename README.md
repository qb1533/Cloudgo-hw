# cloudgo

## curl 结果

```
*   Trying ::1...
* TCP_NODELAY set
* Connected to localhost (::1) port 9090 (#0)
> GET /hello/Mensu HTTP/1.1
> Host: localhost:9090
> User-Agent: curl/7.54.0
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Type: application/json; charset=utf-8
< Date: Tue, 25 Dec 2018 11:06:49 GMT
< Content-Length: 29
<
{
    "Test": "Hello Mensu"
* Connection #0 to host localhost left intact
}
```

### log

```
[GIN] 2018/12/26 - 15:47:08 | 200 |      34.506µs |             ::1 | GET      /hello/Mensu
```

## ab 测试

```
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 100 requests
Completed 200 requests
Completed 300 requests
Completed 400 requests
Completed 500 requests
Completed 600 requests
Completed 700 requests
Completed 800 requests
Completed 900 requests
Completed 1000 requests
Finished 1000 requests


Server Software:
Server Hostname:        localhost
Server Port:            9090

Document Path:          /hello/Mensu
Document Length:        29 bytes

Concurrency Level:      100
Time taken for tests:   0.188 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      152000 bytes
HTML transferred:       29000 bytes
Requests per second:    5323.54 [#/sec] (mean)
Time per request:       18.785 [ms] (mean)
Time per request:       0.188 [ms] (mean, across all concurrent requests)
Transfer rate:          790.21 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    7   3.6      6      15
Processing:     1   11   3.9     12      23
Waiting:        1    8   3.3      8      21
Total:          6   18   4.9     18      30

Percentage of the requests served within a certain time (ms)
  50%     18
  66%     21
  75%     22
  80%     22
  90%     25
  95%     26
  98%     27
  99%     29
 100%     30 (longest request)

```



            min最小  mean期望[+/-sd]标准差 median中位数   max最大
Connect:    连接时间
Processing: 处理时间
Waiting:    等待时间
Total:      总时间
```

- Percentage of the requests served within a certain time (ms) 

```
  50%     N    N 毫秒内服务了50%的请求
  ...
 100%     M    M 毫秒内服务了100%的请求(最长请求)
```
- Server Port:            服务器端口
- Server Hostname:        服务器主机名
- Server Software:        服务器使用的软件
- Document Length:        文档长度
- Document Path:          文档路径
- Concurrency Level:      并发数
- Time taken for tests:   测试时间
- Complete requests:      完成请求数
- Failed requests:        失败请求数
- Total transferred:      传输字节数
- Requests per second:    平均每秒的请求数
- HTML transferred:       传输HTML报文体字节数
- Time per request:       平均每个请求花费的时间
- Transfer rate:          平均每秒传输的千字节数

- Connection Times (ms) 

```