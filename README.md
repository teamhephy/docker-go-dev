# hephy/go-dev

[![Build Status](https://github.com/teamhephy/docker-go-dev/actions/workflows/docker-publish.yml/badge.svg)](https://hub.docker.com/r/hephy/go-dev/tags)

A [Go][] language development toolbox.

This image is intended to be useful to any Go developer. Please help make hephy/go-dev better by
creating [issues][] and submitting [pull requests][].

## Image Contents

* based on [Ubuntu 20.04][]
* [delve][]: debugger for the Go programming language
* [Docker][]: Docker binaries to be able to bind mount /var/run/docker.sock in the dev environment container
* [ginkgo][]: BDD testing framework for Go
* [go-bindata][]: converts any file into Go source code
* [golangci-lint][]: concurrent runner for Go linting tools
* [goss][]: YAML-based tool for validating a server's configuration
* [gox][]: simple Go cross-compiling tool
* [helm][]: Kubernetes package manager
* [jq][]: command-line JSON processor
* [jwt][]: tool for creating and parsing JSON Web Tokens
* [k][]: automatically run the correct version of `kubectl` every time
* [kubectl][]: Kubernetes command-line client
* [ruby][]: ruby scripting language
* [shellcheck][]: static analysis for shell scripts
* [shfmt][]: shell script parser, formatter, and interpreter
* [shyaml][]: YAML access from the command line
* [test-cover.sh][]: test coverage for multiple Go packages
* [unzip][]: list, test, and extract files from ZIP archives
* [upx][]: executable packer
* [vim][]: text editor
* [wamerican][]: American English dictionary words for /usr/share/dict

## Usage

Mount your local Go code into a container's `$GOPATH` to run any `go` command or one of the
included tools or scripts. Here's an example of running `ginko` for teamhephy/builder:

```console
$ docker run --rm \
  --volume $GOPATH/src/github.com/teamhephy/builder:/go/src/github.com/teamhephy/builder \
  --workdir /go/src/github.com/teamhephy/builder \
  hephy/go-dev:latest \
  ginkgo -r
```

## Releases

The latest hephy/go-dev Docker image is available at:

* [Docker Hub][]
  ```
  docker pull hephy/go-dev
  ```

To publish a new release of hephy/go-dev, use the [deisrel][] tool:

```console
$ deisrel release docker-go-dev v1.28.7
Doing a dry run of the component release...

Creating changelog for docker-go-dev with tag v1.28.6 through commit 1a69c5502ef1bca014fbd3581451d1421829a42f


### v1.28.6 -> v1.28.7
...
```

If the CHANGELOG contents look correct, run the same command again but add the argument `--dry-run=false`.
You will be prompted to confirm again before any tag or release is written to GitHub.


[deisrel]: https://github.com/teamhephy/deisrel
[delve]: https://github.com/go-delve/delve
[Docker Hub]: https://hub.docker.com
[Docker]: http://www.docker.com
[gen-changelog.sh]: https://github.com/teamhephy/docker-go-dev/tree/master/rootfs/usr/local/bin/gen-changelog.sh
[ginkgo]: https://github.com/onsi/ginkgo
[go-bindata]: https://github.com/jteeuwen/go-bindata
[Go]: https://golang.org/
[golangci-lint]: https://github.com/golangci/golangci-lint
[goss]: https://github.com/aelsabbahy/goss
[gox]: https://github.com/mitchellh/gox
[helm]: https://github.com/kubernetes/helm
[issues]: https://github.com/teamhephy/docker-go-dev/issues
[jq]: https://stedolan.github.io/jq/
[jwt]: https://github.com/dgrijalva/jwt-go
[k]: https://github.com/jakepearson/k
[kubectl]: https://kubernetes.io/docs/user-guide/kubectl-overview/
[pull requests]: https://github.com/teamhephy/docker-go-dev/pulls
[ruby]: https://www.ruby-lang.org/
[shellcheck]: https://github.com/koalaman/shellcheck
[shfmt]: https://github.com/mvdan/sh
[shyaml]: https://github.com/0k/shyaml
[test-cover.sh]: https://github.com/teamhephy/docker-go-dev/tree/master/rootfs/usr/local/bin/test-cover.sh
[Ubuntu 20.04]: https://hub.docker.com/_/ubuntu/
[unzip]: https://linux.die.net/man/1/unzip
[upx]: http://upx.sourceforge.net/
[vim]: http://www.vim.org/
[ruby]: https://www.ruby-lang.org/
[wamerican]: https://packages.ubuntu.com/xenial/wamerican
