# go-drainclose

Make your app 4x faster.

See https://github.com/google/go-github/pull/317

## Usage

### Before

```go
resp, err := http.Get(blah)
if err != nil {
	return err
}
defer resp.Body.Close()
json.NewDecoder(resp.Body).Decode(&data)
```

### After

```go
resp, err := http.Get(blah)
if err != nil {
	return err
}
defer drainclose.Close(resp.Body)
json.NewDecoder(resp.Body).Decode(&data)
```

## License

MIT

## Author

Yasuhiro Matsumoto (a.k.a mattn)
