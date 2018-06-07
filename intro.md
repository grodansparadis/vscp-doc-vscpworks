# A short introduction

VSCP Works is a toolbox for VSCP developers and advanced users that is available for Linux and Windows. It can be used to update code in in-house nodes and nodes that sit at a location on the other side of the earth. It can be used to view events sent by a node, to configure a node using a high end interface and to simulate a node. New functionality will be added to VSCP Works as needs arise.

There is a three video walkthroughs on Youtube that look at some of the essential parts of VSCP Works

- [Part 1](http://www.youtube.com/watch?v=uIMSG8ewvIw)
- [Part 2](http://www.youtube.com/watch?v=XenCTnhWJKM)
- [Part 3](http://www.youtube.com/watch?v=fd6cNc7iIzE)

## Terms used in this documentation

* **Remote node** is often used in this document. A remote node is a node that is connected over tcp/ip and which exports the [VSCP tcp/ip link protocol](https://grodansparadis.gitbooks.io/the-vscp-specification/vscp_over_tcp_ip.html). The most cmmon remote node is the [VSCP Daemon](https://grodansparadis.gitbooks.io/the-vscp-daemon) but it can be any node exporting the interface.
* **Drivers** VSCP Works can use Level I (CANAL) drivers. This type of driver exports the [CANAL interface](https://grodansparadis.gitbooks.io/the-vscp-daemon/canal_interface_specification.html)
 which is a minimum common interface solution in VSCP that also work for very resource limited devices. A Level I (CANAL) driver usually interface hardware directly but can also implement virtual functionality or connect to remote functionality.

{% include "./bottom_copyright.md" %}