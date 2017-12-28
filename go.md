## unit for go 

#### build unit env (from source)

```

1. git clone https://github.com/nginx/unit.git $PATH/unit

2. cd $PATH/unit

3. ./configure

4. set GOPATH=$GOAPTH

5. ./configure go

6. make all

7. make go-install # unit for go dependency source will install $GOPATH

8. cd $GOPATH

9. go build nginx/unit

10. go install nginx/unit

11. copy follow go http server to file

    package main

    import (
        "fmt"
        "net/http"
            "nginx/unit"
    )

    func handler(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hi there, I love %s!", r.URL.Path[1:])
    }

    func main() {
        http.HandleFunc("/", handler)
        unit.ListenAndServe(":10000", nil)
    }
    
12. go build

13. Done & play unit have fun

```
