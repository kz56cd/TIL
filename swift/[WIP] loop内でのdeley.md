# loop内でのdeley

## overview


## usage

### 1

```
for i in 1...5 {
    DispatchQueue.main.asyncAfter(deadline: .now() + Double(i)) {
        // do something
    }
}
```

### 2

```
for i in 1...5 {
	// do something
	sleep(1)
}
```



## ref

- https://stackoverflow.com/questions/39207398/create-delay-in-swift-3-inside-a-loop
- http://marycore.jp/prog/objective-c/sleep-process/