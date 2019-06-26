# sailgun :sailboat:

Sailgun is a [Nailgun](https://github.com/facebook/nailgun) client written in Scala.

The goal of sailgun is to be a flexible, cross-platform, zero-dependency
Nailgun client that can be used both as a *binary* and as a *library
dependency*.

## Motivation :ocean:

Nailgun is a useful protocol to communicate lightweight, short-lived clients
with long-running servers.

Developers have traditionally used Nailgun to communicate native-like clients
with services running on the JVM. However, there are many use cases that
require JVM clients connect to Nailgun servers and those are currently unsupported.

Sailgun is an alternative implementation to the [default Python and C
clients](https://github.com/facebook/nailgun/tree/master/nailgun-client) of
the Nailgun protocol that intends to be extensible, fast and support
**both** JVM and Native clients.

* It provides a simple API that for any JVM-based programming language.
* It can be compiled to a Native binary that is 10x faster than the default Python nailgun client through [GraalVM's Native Image](https://www.graalvm.org/docs/reference-manual/aot-compilation/).

Sailgun's major use cases are:

1. You need a client that talks the Nailgun protocol but you need to customize it.
1. You need to communicate with a Nailgun server implemented in another language.
1. You need to communicate a JVM client with a Nailgun server on the JVM. For
   example, if the server cannot be compiled to native or synchronizes
   concurrent clients.