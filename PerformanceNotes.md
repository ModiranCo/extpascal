# Performance Notes on ExtPascal Samples. #

## Environment Description ##

  * Sever:
    * Processor: Intel Pentium 4 (Prescott) 3.2 GHz
    * Memory: 1GB DDR1
  * Client:
    * Processor: Intel Pentium 4 (Prescott) 3.0 GHz
    * Memory: 1GB DDR1
  * Network:
    * Ethernet 100 Mbps.
    * Server and Client on the same segment.
    * No significant traffic.
  * Server OSes:
    * Windows 2003 Service Pack 1
    * Linux Fedora 9
  * Client OS:
    * Windows XP Service Pack 2
  * WebServer:
    * Apache 2.2.8
  * Compilers:
    * Turbo Delphi 2006
    * FreePascal 2.2.2 (linux and windows)
  * Benchmark software:
    * ab.exe - ApacheBench, Version 2.0.40-dev <$Revision: 1.146 $>
  * Command:
    * ab -v 0 -n 1000 -c 10
  * Webserver Comunication Protocol:
    * Fastcgi
  * HTTP compression
    * Deflate activated


|Legend | |
|:------|:|
|# |Number of the execution of Apache Benchmark(ab) with parameters specified in top line |
|Errors | Number of errors occurred in execution of ab |
|RPS | Requests Per Second – Average number of requests attended by the server during execution of ab |
|Mem | Total Physical Memory used by server (reported by Task Manager in Windows e Top in Linux) |
|T | Time in seconds that the service takes to attend the demand |
|<sup>*</sup> | means that all calls to ab was made consecutively without interval to take notes |

## Server Windows 2003 – Delphi generated code – 1,000 requests / 10 concurrents ##

|#|Errors|RPS|Mem (KB)|T(s)|
|:|:-----|:--|:-------|:---|
|01|1 |333| 9032|3.0|
|02|1 |344| 9128|2.9|
|03|0 |276|15272|3.6|
|04|4 |344| 9120|2.9|
|05|0 |274|15296|3.6|
|06|1 |271|15492|3.6|
|07|0 |227|21456|4.4|
|08|0 |275|18984|3.6|
|09|1 |257|19056|3.9|
|10|1 |275|18992|3.6|
|<sup>*11..15</sup>|0 |186|27904|5.3|
|<sup>*16..25</sup>|0 |120|35892|7.7|

## Server Windows 2003 – Delphi generated code – 10,000 requests / 10 concurrents ##

|#|Errors|RPS|Mem (KB)|T(s)|
|:|:-----|:--|:-------|:---|
|1 |4 |149|52524|66.9|
|2 |0 |135|55464|74.1|
|3 |2 |148|48512|67.3|
|4 |0 |140|58532|71.5|
|5 |0 |131|55672|76.1|



## Server Windows 2003 – Free Pascal generated code – 1,000 requests / 10 concurrents ##

| # |Errors|RPS|Mem (KB)|T(s)|
|:--|:-----|:--|:-------|:---|
|  1|0 |252| 40992|3.0|
|  2|0 |229| 75300|2.9|
|  3|0 |213|113072|3.6|
|  4|0 |180|150744|2.9|
|  5|0 |199|180288|3.6|
|  6|0 |192|213780|3.6|
|  7|0 |177|250776|4.4|
|  8|0 |175|284600|3.6|
|  9|0 |202|314912|3.9|
| 10|0 |202|348536|3.6|
|<sup>*</sup>11..15|0 |122|529332|5.3|
|<sup>*</sup>16..25|0 |110|728420|7.7|

## Server Windows 2003 – Free Pascal generated code – 10,000 requests / 10 concurrents ##

|#|Errors|RPS|Mem (KB)|T(s)|
|:|:-----|:--|:-------|:---|
|1 |0 |124|357596|80.32|
|2 |0 |120|699356|83.78|
|3 |0 |109|901044|91.78|
|4 |0 |113|892768|88.17|
|5 |0 |110|907120|91.93|


## Server Linux Fedora 9 – Free Pascal generated code – 1,000 requests / 10 concurrents ##

| # |Errors|RPS|Mem (KB)|T(s)|
|:--|:-----|:--|:-------|:---|
|  1|0 |397| 7852|2.5|
|  2|0 |402| 9780|2.5|
|  3|0 |355|16000|2.8|
|  4|0 |304|22000|3.4|
|  5|0 |296|23000|3.4|
|  6|0 |296|25000|3.4|
|  7|0 |296|25000|3.4|
|  8|0 |293|26000|3.4|
|  9|0 |271|27000|3.7|
| 10|0 |296|27000|3.4|
|<sup>*</sup>11..15|0 |197|50000|5.6|
|<sup>*</sup>16..25|0 |136|79000|7.3|

## Server Linux Fedora 9 – Free Pascal generated code – 10,000 requests / 10 concurrents ##

|#|Errors|RPS|Mem (KB)|T(s)|
|:|:-----|:--|:-------|:---|
|1 |0 |191| 70000|52.34|
|2 |0 |200| 81000|49.86|
|3 |0 |198| 89000|50.29|
|4 |0 |169|104000|59.14|
|5 |0 |156|111000|63.84|