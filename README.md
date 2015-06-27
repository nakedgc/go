# Naked Go Compiler

This is a complete fork of the [go repo](https://go.googlesource.com/go/), but it only changes *gc*, the Go Compiler. This version of gc is friendlier than the default version, as you can tell it to shut up about certain errors (like unused variables).

This project aims to provide a drop-in replacement for the standard 'go' executable.

	[23:01] <johto> there are several ways of enforcing that people don't go out naked
	in public. Go's way is makign sure everyone showers clothed. I prefer the world
	where I can choose to shower naked, so long as I put something on before I leave 
	my front door

We currently turn errors about unused variables and unused packages into warnings when the flag `-Wno-error` is passed.

Example:

	go build -Wno-error hello.go

**TODO**:
  - Documentation in `go --help`
  - Complete list of all irritating errors that can be turned into warnings (currently only unused variables)
  - Repo with some code that should compile with ngc

<br/>
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
