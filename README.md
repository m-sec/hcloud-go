你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
# hcloud: A Go library for the Hetzner Cloud API

[![GitHub Actions status](https://github.com/hetznercloud/hcloud-go/workflows/Continuous%20Integration/badge.svg)](https://github.com/hetznercloud/hcloud-go/actions)
[![GoDoc](https://godoc.org/github.com/hetznercloud/hcloud-go/hcloud?status.svg)](https://godoc.org/github.com/hetznercloud/hcloud-go/hcloud)

Package hcloud is a library for the Hetzner Cloud API.

The library’s documentation is available at [GoDoc](https://godoc.org/github.com/hetznercloud/hcloud-go/hcloud),
the public API documentation is available at [docs.hetzner.cloud](https://docs.hetzner.cloud/).

## Example

```go
package main

import (
    "context"
    "fmt"
    "log"

    "github.com/hetznercloud/hcloud-go/hcloud"
)

func main() {
    client := hcloud.NewClient(hcloud.WithToken("token"))

    server, _, err := client.Server.GetByID(context.Background(), 1)
    if err != nil {
        log.Fatalf("error retrieving server: %s\n", err)
    }
    if server != nil {
        fmt.Printf("server 1 is called %q\n", server.Name)
    } else {
        fmt.Println("server 1 not found")
    }
}
```

## License

MIT license
