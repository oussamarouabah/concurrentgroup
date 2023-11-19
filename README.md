# Concurrent group

concurrent group is a library that supports panic recovery and concurrency limiting.

## Example

```golang
group, _ := concurrentgroup.NewGroup(context.Background(), 10)
for i := 0; i < 150; i++ {
    group.Go(func() error {
        time.Sleep(2 * time.Second)
        fmt.Println("go test")
        return nil
    })
}
group.Wait()
```
