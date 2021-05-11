# goblin-benchmark-tests
This is a repository for benchmark tests of [golin](https://github.com/bmf-san/goblin).

# Benchmark
## Environment
|          key          |                             value                             |
| --------------------- | ------------------------------------------------------------- |
| version               | [1.0.0](https://github.com/bmf-san/goblin/releases/tag/1.0.0) |
| Model Name            | MacBook Air                                                   |
| Model Identifier      | MacBookAir8,1                                                 |
| Processor Name        | Dual-Core Intel Core i5                                       |
| Processor Speed       | 1.6 GHz                                                       |
| Number of Processors  | 1                                                             |
| Total Number of Cores | 2                                                             |
| Memory                | 16 GB                                                         |

## Test targets
Run a total of 203 static routes of GithubAPI.

- [beego/mux](https://github.com/beego/mux)
- [julienschmidt/httprouter](https://github.com/julienschmidt/httprouter)
- [dimfeld/httptreemux](https://github.com/dimfeld/httptreemux)
- [gin-gonic/gin](https://github.com/gin-gonic/gin)
- [go-chi/chi](https://github.com/go-chi/chi)

## How to run
```sh
cd benchmark
go test -bench . -benchmem
```

## Results
Date: Wed May 12 00:08:40 JST 2021

```
GithubAPI Routes: 203
   goblin: 96184 Bytes
   beego-mux: 108424 Bytes
   HttpRouter: 39264 Bytes
   httptreemux: 78800 Bytes
   gin: 59824 Bytes
   chi: 71624 Bytes
goos: darwin
goarch: amd64
pkg: github.com/bmf-san/goblin/benchmark
cpu: Intel(R) Core(TM) i5-8210Y CPU @ 1.60GHz
BenchmarkGoblin-4                            675           1555694 ns/op         1069449 B/op       3455 allocs/op
BenchmarkBeegoMux-4                          703           1894363 ns/op         1147723 B/op       3475 allocs/op
BenchmarkHttpRouter-4                        676           1491278 ns/op         1024065 B/op       2603 allocs/op
BenchmarkHttpTreeMux-4                       661           1514271 ns/op         1076138 B/op       3108 allocs/op
BenchmarkGin-4                               808           1426821 ns/op         1010568 B/op       2438 allocs/op
BenchmarkChi-4                               775           2088961 ns/op         1101483 B/op       3047 allocs/op
BenchmarkGoblinRequests-4                     30          40026919 ns/op          899394 B/op      11230 allocs/op
BenchmarkBeegoMuxRequests-4                   27          38580942 ns/op          978540 B/op      11255 allocs/op
BenchmarkHttpRouterRequests-4                 49          31815059 ns/op          852927 B/op      10373 allocs/op
BenchmarkHttpTreeMuxRequests-4                34          39901722 ns/op          906625 B/op      10897 allocs/op
BenchmarkHttpGinRequests-4                    38          28691349 ns/op          839147 B/op      10203 allocs/op
BenchmarkHttpChiRequests-4                    43          29239496 ns/op          930259 B/op      10815 allocs/op
PASS
ok      github.com/bmf-san/goblin/benchmark     20.365s
```
