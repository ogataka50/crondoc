# crondoc

generate crontab document tool


## Description

- crondoc is tool what generate crontab document from crontab or stdin
- Grouping up to line break

## Usage

```
$ crodoc /etc/crontab
$ crontab -l | crodoc -s
```

```
usage: crondoc [OPTIONS] <args> crontab_path

argument
	[crontab_path] generate crontab document

Available options are:
	-v --version	print versions
	-h --help		print help
	-s --stdin		generate crontab document from stdin
```

## document example

it will be such an output ....

```bash
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root
HOME=/

# @title monday.sh
# @author hoge
# @param env[dev|stg|prod]
# start every monday
0 10 * * 1 sh /home/hoge/happy_monday.sh prod
```

↓↓↓

### Environment variable
 - SHELL=/bin/bash
 - PATH=/sbin:/bin:/usr/sbin:/usr/bin
 - MAILTO=root,hoge@mail.co.jp
 - HOME=/

## monday.sh

- Author : hoge
- param : env[dev|stg|prod]
- start every monday

| min|hour|day|month|day week|command |
|:---|:---|:---|:---|:---|:---|
| 0| 10| *| *| Mon| `sh /home/hoge/happy_monday.sh prod`|

***

## document format

only markdown now ....

## document tags

- @title
- @author
- @param

## Install

### Just want the binary?

Go to the [releases page](https://github.com/ogataka50/crondoc/releases)

To install, use `go get`:

```bash
$ go get -d github.com/ogasawara_takahiro/crondoc
```

## Contribution

1. Fork ([https://github.com/ogataka50/crondoc/fork](https://github.com/ogataka50/crondoc/fork))
1. Create a feature branch
1. Commit your changes
1. Rebase your local changes against the master branch
1. ~~Run test suite with the `go test ./...` command and confirm that it passes~~
1. Run `gofmt -s`
1. Create a new Pull Request

## TODO

- Selectable output format
- Add many types of tags


## License

[MIT](https://github.com/ogataka50/crondoc/blob/master/LICENSE)

## Author

[ogataka50](https://github.com/ogataka50/)
