# Vegeta

Vegeta is a versatile HTTP load testing tool built out of a need to drill
HTTP services with a constant request rate.
It can be used both as a command line utility and a library.

https://github.com/tsenart/vegeta

### Homebrew on Mac OS X

You can install Vegeta using the [Homebrew](https://github.com/Homebrew/homebrew/) package manager on Mac OS X:

```shell
$ brew update && brew install vegeta
```

### Source

You need `go` installed and `GOBIN` in your `PATH`. Once that is done, run the
command:

```shell
$ go install github.com/tsenart/vegeta@latest
```

### Targets list file

Create a `target.list` file with the list of endpoint you want to attack, like this:

```
GET https://apple.com
GET https://google.com
```

You can send baerer token:

```
GET https://apple.com
Authorization: Bearer Bearer 80|22yg7oQ4TWlP6DgIFoYclfagdgdi4r1slV0NPvSX
```

### Usage Manual

```console
Usage: vegeta [global flags] <command> [command flags]
```

This example prints the result of 10 requests for each second, during 5 seconds: 

```console
vegeta attack -duration=5s -rate=10 -targets=target.list | tee results.bin | vegeta report
```
