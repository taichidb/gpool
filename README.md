## GPool

goroutine pool implemented using channel

## Example

```go
import (
    "gopkg.in/taichidb/gpool.v1"
)

func foobar() {
    pool := gpool.NewPool(10)
    for i := 0; i < 100; i++ {
        pool.Add(1)
        go func(i int) {
            // do something
            pool.Done()
        }(i)
    }
    pool.Wait()
}
```
