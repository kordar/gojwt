# gojwt

对 `github.com/golang-jwt/jwt` 的简单封装（HS256）。

## 安装

```bash
go get github.com/kordar/gojwt
```

## 使用

```go
package main

import (
	"fmt"
	"github.com/golang-jwt/jwt"
	gjwt "github.com/kordar/gojwt"
)

func main() {
	claims := jwt.MapClaims{"uid": 123}
	token, err := gjwt.GenTokenE(claims, "secret")
	if err != nil {
		panic(err)
	}

	out, err := gjwt.ParseToken(token, "secret")
	if err != nil {
		panic(err)
	}
	fmt.Println(out["uid"])
}
```
