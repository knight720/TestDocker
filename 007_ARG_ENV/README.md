```
docker build -t arg_env --build-arg ARG1=1 --build-arg ARG3=3  .
```

## 結論
- ${:-} 變數未定義時提供預設值 Default
- ${:+} 變數已定義時會覆寫 Overwirte

## Reference
[Dockerfile - ENV與ARG參數](https://peihsinsu.gitbooks.io/docker-note-book/content/dockerfile-env-vs-arg.html)