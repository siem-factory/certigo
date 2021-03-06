# certigo

[![license](http://img.shields.io/badge/license-apache_2.0-blue.svg?style=flat)](https://raw.githubusercontent.com/square/certigo/master/LICENSE)
[![build](https://travis-ci.org/square/certigo.svg?branch=master)](https://travis-ci.org/square/certigo)
[![report](https://goreportcard.com/badge/github.com/square/certigo)](https://goreportcard.com/report/github.com/square/certigo)

Certigo is a utility to examine and validate certificates in a variety of formats.

### Install

To install certigo, simply use:

    go get -u github.com/square/certigo

Note that certigo requires Go 1.6 or later to build.

### Develop

We use [glide][1] for managing vendored dependencies.

[1]: https://glide.sh

### Usage

Certigo can read certificates/keystores in various formats and dump them to stdout.

Currently supported formats are DER, PEM, JCEKS/JKS and PKCS12. Certigo will display information in a human-readable way, and print warnings for common mistakes (such as small key sizes or weak signatures/hash functions). Certigo can also convert any input to a series of PEM blocks, which is useful if you want to e.g. dump the contents of PKCS12/JCEKS keystores into something more useful.

```
usage: certigo [<flags>] <command> [<args> ...]

A command line certificate examination utility.

Flags:
  --help     Show context-sensitive help (also try --help-long and --help-man).
  --version  Show application version.

Commands:
  help [<command>...]
    Show help.

  dump [<flags>] [<file>...]
    Display information about a certificate from a file/stdin.

  connect [<flags>] [<server:port>]
    Connect to a server and print its certificate(s).
```

### Examples

Display information about a certificate (from a file, or from stdin):

<img src="https://cdn.rawgit.com/square/certigo/142ea7a63126d1366194cf0eb746abbac2eb3f09/examples/example_1.svg" width="100%" height="100%">

Export certificates/keys from a keystore into PEM blocks:

<img src="https://cdn.rawgit.com/square/certigo/142ea7a63126d1366194cf0eb746abbac2eb3f09/examples/example_2.svg" width="100%" height="100%">

Display information about a certificate from a remote server:

<img src="https://cdn.rawgit.com/square/certigo/142ea7a63126d1366194cf0eb746abbac2eb3f09/examples/example_3.svg" width="100%" height="100%">
