telehash secure mesh protocol
==================================

![logo](logo/mesh-logo-128.png)

> see the [v3 release specification](v3/spec/v3.0.0-stable.pdf)

An interoperable private mesh networking standard, see the [introduction](intro.md) for more background.

> the primary discussion area is currently via Slack, anyone can join by getting an [automated invite](http://6.telehash.org:3000).

The full protocol suite is a composite of multiple individual specifications:

* [hashname](hashname.md) - endpoint address format (public key fingerprint)
* [packets](lob.md) - length-object-binary formatted packets, json+binary serialization
* [E3X](e3x/) - end-to-end encrypted exchange (wire encoding, crypto libraries)
* [link](link.md) - establishing and maintaining connections between two endpoints
* [mesh](mesh.md) - higher level tools to manage multiple links and do local discovery
* [routing](routing.md) - when one endpoint assists two others to establish/maintain a link
* [uri](uri.md) - how to encode/decode endpoint info via URIs for out-of-band bootstrapping
* [transports](transports/) - details (encoding, timeouts, discovery, etc) for mapping/supporting different network transports
* [logo](logo/) - for use to represent telehash support in apps 


<a name="implementations" />
### Implementations

Each implementation provides a library API adapted to its platform or language but they all strive to offer similar functionality including handling hashnames, URIs, and packets (lob), higher level interfaces to create a mesh and links within it, and lower level tools for E3X, transports/pipes, managing keys, etc.  Refer to the [implementers guide](guides/implementers.md) for an overview of the typical methods and patterns.

Experimental implementations are being actively developed at:

* [telehash-js](https://github.com/telehash/telehash-js)
* [telehash-c](https://github.com/telehash/telehash-c)
* [gogotelehash](https://github.com/telehash/gogotelehash)
* [python](https://github.com/telehash/e3x-python)
* [c#](https://github.com/telehash/telehash.net)
* [others in progress](https://github.com/telehash)


|              | hashname | link | uri | routing | streams | sockets | udp | tcp | http | tls | webrtc | bluetooth |
|:------------:|:--------:|:----:|:---:|:-------:|:-------:|:-------:|:---:|:---:|:----:|:---:|:------:|:---------:|
|    node.js   |     ✓    |   ✓  |  ✍ |    ✓    |    ✓    |    ✓    |  ✓  |  ✓  |   ✓  |  ✍ |   ✍   |           |
|  browser js  |     ✓    |  ✍  |     |         |         |         |     |     |  ✍  |     |   ✍   |           |
|   c - unix   |     ✓    |   ✓  |  ✍ |    ✍   |    ✍   |    ✍   |  ✓  |  ✓  |      |     |        |           |
| c - embedded |     ✓    |   ✓  |  ✍ |         |    ✍   |    ✍   |  ✍ |  ✍ |      |     |        |           |
|      go      |     ✓    |   ✓  |     |         |         |         |  ✓  |     |      |     |        |           |
|    python    |     ✓    |   ✍  |    |         |        |        |  ✍ |    |      |     |        |           |
