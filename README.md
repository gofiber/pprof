# PPROF

![Release](https://img.shields.io/github/release/gofiber/pprof.svg)
[![Discord](https://img.shields.io/badge/discord-join%20channel-7289DA)](https://gofiber.io/discord)
![Test](https://github.com/gofiber/pprof/workflows/Test/badge.svg)
![Security](https://github.com/gofiber/pprof/workflows/Security/badge.svg)
![Linter](https://github.com/gofiber/pprof/workflows/Linter/badge.svg)

Special thanks to [Matthew Lee (@mthli)](https://github.com/mthli)

### Install
```
go get -u github.com/gofiber/fiber
go get -u github.com/gofiber/pprof
```
### Example
```go
package main

import (
  "github.com/gofiber/fiber"
  "github.com/gofiber/pprof"
  // pprofh "github.com/gofiber/pprof"
)

func main() {
  app := fiber.New()
  
  app.Use(pprof.New())
  // http://localhost:3000/debug/pprof/
  // http://localhost:3000/debug/pprof/cmdline
  // http://localhost:3000/debug/pprof/profile?seconds=30
  // http://localhost:3000/debug/pprof/symbol
  // http://localhost:3000/debug/pprof/trace?seconds=5
  // http://localhost:3000/debug/pprof/allocs
  // http://localhost:3000/debug/pprof/block
  // http://localhost:3000/debug/pprof/goroutine
  // http://localhost:3000/debug/pprof/heap
  // http://localhost:3000/debug/pprof/mutex
  // http://localhost:3000/debug/pprof/threadcreate

  app.Get("/", func(c *fiber.Ctx) {
    c.Send("Hello, World!")
  })
  
  app.Listen(3000)
}
```
