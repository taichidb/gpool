## GPool

goroutine pool implemented using channel

## Example

```go
{
    pool := NewPool(10)
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
