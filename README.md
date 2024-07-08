# corgi  
[![Go](https://github.com/keepchen/corgi/actions/workflows/go.yml/badge.svg)](https://github.com/keepchen/corgi/actions/workflows/go.yml)  [![CodeQL](https://github.com/keepchen/corgi/actions/workflows/codeql.yml/badge.svg)](https://github.com/keepchen/corgi/actions/workflows/codeql.yml)  [![Go Report Card](https://goreportcard.com/badge/github.com/keepchen/corgi/v3)](https://goreportcard.com/report/github.com/keepchen/corgi)  
A distributed lock via redis written in Go.

### Requirement
```text
go version >= 1.19
```

### Installation
```shell
go get -u github.com/keepchen/corgi
```  

### Features
- [x] Lock
- [x] Unlock
- [x] Renewal automatically

### Examples  
#### Initialization
```go
corgi.SetRedisProviderStandalone(...)

//or
corgi.SetRedisProviderCluster(...)

//or
corgi.SetRedisProviderFailOver(...)
```  
#### Lock
```go
corgi.Wakeup().TryLock(ctx, key)
```  
#### Unlock
```go
corgi.Wakeup().Unlock(ctx, key)
```  
#### Release  
```go
corgi.Asleep()
```
