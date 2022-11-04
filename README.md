# gorelaser1

[GoReleaser](https://goreleaser.com/)の練習

```
$ goreleaser -v
goreleaser version 1.12.3
commit: e27e6a9e8c66ec5d2bbcafb1c047068bcf250269
built at: 2022-10-20T12:30:56Z
built by: goreleaser
goos: linux
goarch: amd64
module version: v1.12.3, checksum: h1:sTJXdkGQO9eAP6pwEUazaD6ERJewZ7yzQexWEGPUVg4=

https://goreleaser.com

$ go version
go version go1.18.1 linux/amd64
```

[Quick Start](https://goreleaser.com/quick-start/)通りにやると動かない。


```bash
mkdir gorelaser1 ; cd gorelaser1
```

[Quick Start](https://goreleaser.com/quick-start/)にあるmain.goを作る。

```bash
go mod init main
goreleaser init
goreleaser --snapshot --rm-dist
```

`error=couldn't guess project_name, please add it to your config` とエラーが出るので、
[Project Name](https://goreleaser.com/customization/project/)
にある通り、`.goreleaser.yaml`の一番上のレベルに project_name を追加。

再び
```bash
goreleaser --snapshot --rm-dist
```

とりあえず./dist以下に tarballができた。

- 386いらない -> done
- Macもいらない -> done
- tar.gzよりzipがいい -> Windowsはzip, Linuxはtar.gzにした。

ここでいったんgitをinitial. goreleaserの作る.gitignoreは./distが入ってるだけなので、

```bash
curl -L -o .gitignore https://www.toptal.com/developers/gitignore/api/go,visualstudiocode,emacs
```

`go build`した場合に備えて、最後に `gorelease1` を追加。

...修正
