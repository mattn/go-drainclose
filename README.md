# go-drainclose

Make it 4x faster for your app

See https://github.com/google/go-github/pull/317

## Usage

### Before

```go
resp, err := http.Get(blah)
if err != nil {
	return err
}
defer resp.Body.Close()
```

### After

```go
resp, err := http.Get(blah)
if err != nil {
	return err
}
defer drainclose.Close(resp.Body)
```

## License

MIT

## Author

Yasuhiro Matsumoto (a.k.a mattn)
