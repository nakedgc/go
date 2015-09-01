# Naked Go Compiler

**Currently up to date with [go1.5](https://github.com/golang/go/tree/release-branch.go1.5)**

**You want to be sure we didn't sneak any malicious code into the compiler? [Here you go.](https://github.com/golang/go/compare/release-branch.go1.5...nakedgc:master)**

This is a complete fork of the [go repo](https://go.googlesource.com/go/), but it only changes *gc*, the Go Compiler. This version of gc is friendlier than the default version, as you can tell it to shut up about certain errors (like unused variables).

This project aims to provide a drop-in replacement for the standard 'go' executable.

We currently turn errors about unused variables and unused packages into warnings when the flag `-Wno-error` is passed.

Example:

	go build -Wno-error unused_vars.go
	...
	./unused_vars.go:7: [WARNING] a declared and not used
	...
	Hello world!

If you still don't get it, there are [more examples](https://github.com/nakedgc/etc).

	[23:01] <johto> there are several ways of enforcing that people don't go out naked
	in public. Go's way is makign sure everyone showers clothed. I prefer the world
	where I can choose to shower naked, so long as I put something on before I leave 
	my front door

## [gb](https://github.com/constabulary/gb) instructions

Build gb with $GOROOT set to a clone of this repo, afterwards you can build with `gb build -gcflags='-nonfatalwarnings=1'`.

<hr/>

<br/>

**TODO**:
  - Extending the list of all irritating errors that can be turned into warnings (currently only unused variables/packages) (if there are any)


<br/>
<hr/>
(original readme)


# The Go Programming Language

Go is an open source programming language that makes it easy to build simple,
reliable, and efficient software.

![Gopher image](doc/gopher/fiveyears.jpg)

For documentation about how to install and use Go,
visit https://golang.org/ or load doc/install-source.html
in your web browser.

Our canonical Git repository is located at https://go.googlesource.com/go.
There is a mirror of the repository at https://github.com/golang/go.

Please report issues here: https://golang.org/issue/new

Go is the work of hundreds of contributors. We appreciate your help!

To contribute, please read the contribution guidelines:
	https://golang.org/doc/contribute.html

##### Please note that we do not use pull requests.

Unless otherwise noted, the Go source files are distributed
under the BSD-style license found in the LICENSE file.

--

## Binary Distribution Notes

If you have just untarred a binary Go distribution, you need to set
the environment variable $GOROOT to the full path of the go
directory (the one containing this file).  You can omit the
variable if you unpack it into /usr/local/go, or if you rebuild
from sources by running all.bash (see doc/install-source.html).
You should also add the Go binary directory $GOROOT/bin
to your shell's path.

For example, if you extracted the tar file into $HOME/go, you might
put the following in your .profile:

	export GOROOT=$HOME/go
	export PATH=$PATH:$GOROOT/bin

See https://golang.org/doc/install or doc/install.html for more details.
