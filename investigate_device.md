# Investigate a new device

![](./images/vscp_device_on_bench.jpg)

You get that device on your desk. You hook it up. An then? Usually you need to dig up info in manuals trying to understand how to work with the device. Every device is different. Even hooking it up can be a big deal. There is many ways to do so. If it needs power you must at least know what voltage is needed and where to connect it.

VSCP relax much of this. Lets have a look at a piece of hardware. In this case it is a [CAN4VSCP device](https://grodansparadis.gitbooks.io/the-vscp-specification/vscp_over_can_can4vscp.html) but it could be a wireless device, an Ethernet connected device or a Bluetooth mesh. 

## The interface abstraction
VSCP abstracts the physical connection to a device with one of two interfaces called Level I and Leve II. Both telling how higher level software systems talk to a low end device. What the device is and how it works is important here. It does not even have too be a physical "thing". The interface abstraction layer only specify that on the other side of this interface is a device of some sort. We can talk to this device as it was a VSCP device. But it can just act as one, it does not have to be one. All devices can be hooked up in this way. **ALL!**

## Discovery
You buy a device, you hook it up, VSCP will discovery it through it's heartbeats. This heartbeat looks different on different transport mediums. It can be a beacon signal on a Bluetooth device, a multicast datagram on wifi and Ethernet, etc. For CAN4VSCP it is a just a heartbeat message. **"Messages"** however is called **"events"** in VSCP. 

If you are intrested the standard VSCP heartbeat is [CLASS1.INFORMATION, Type=9, Node Heartbeat](https://grodansparadis.gitbooks.io/the-vscp-specification/class1.information.html#type--9-0x09-node-heartbeat)

The VSCP session window open up a communication channel through a Level I or Level II interface. This can be a connection to a single device or to a bus with many devices. It can also be a connection to the [VSCP Daemon](https://grodansparadis.gitbooks.io/the-vscp-daemon) which is an edge IoT server.

We will only look at how this works for CANBUS as a transport. The functionality is the same for raw Ethernet, TCP/IP, Bluetooth, WIFI etc 

### CAN4VSCP discovery

For a CAN4VSCP node we can use any CANBUS adapter to connect a bus with such devices to a computer. On Linux we can use [SocketCAN](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwjWnoLb5MvbAhVoyKYKHVcGBzcQFggoMAA&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FSocketCAN&usg=AOvVaw1wC_MpUCU_F_3fvkDWpN4A) which have drivers for most physical CANBUS interfaces already in the Kernel.

On Windows you directly use the VSCP driver available for the adapter. There is a driver available for most common CANBUS interfaces.

We add the [Level I socketCAN driver](https://grodansparadis.gitbooks.io/the-vscp-daemon/level1_driver_socketcan.html) to VSCP Works.

![](./images/vscpwors_canal_session_socketcan.png)

It is basically a name, the path to the driver and which SocketCAN interface to use (*can0*).

If we now open a VSCP Works session window and let it stay open for a while we see

![](./images/socketcan_heartbeat.png)

In the right window we see that we get a heartbeat from a device that have a nickname set to 1. Nickname id's are short id's used as device identifiers instead of GUID's when the transport mechanism is unable to handle the full GUID. So now we know there is a device. 

Instead of waiting for heartbeats from a node one can actively search for it

![](./images/scan_for_device.png)

Here we again see one device with nickname equal to 1 after a scan. If we right click om the discovered node we get two choices

![](/images/scan_menu.jpg)

* Update node info from MDF.
* Open configuration window...

selecting the first entry fill in some info

![](/images/scan_info2.png)

we get plenty of information about the device here. We see that this is an A/D conversion module. We also get the URL to the module. We can open it and get all information about the module.

[https://www.grodansparadis.com/vilnius/vilnius.html](https://www.grodansparadis.com/vilnius/vilnius.html)

This information is for a human user. 

More interesting is another item, the path to the MDF (Module Description File). The MDF is an XML file that describe any VSCP piece of hardware (or simulated hardware) and which is readable for a machine. The node just holds the URL to the MDF, in this case

[http://www.grodansparadis.com/vilnius/vilnius.html](http://www.grodansparadis.com/vilnius/vilnius.html)

If we open this file in a browser we get plenty of information about the hardware device

![](/images/vilnius_mdf1.png)

If we scroll down we see

![](/images/vilnius_mdf2.png)

Here we can get a picture of the hardware (even severall).

[https://www.grodansparadis.com/accra/images/accra14.png](http://www.grodansparadis.com/accra/images/accra14.png)

![](./images/accra14.png)

We can get the **path to the latest firmware**. Perfect for some software that can update it, you can get the path to the manual for the device. And a lot more things.

After the general info, register definitions, abstractions, boot loader info, wizards and a lot of strange things appear in the file. Nothing of this is for humans. In fact all of the MDF is for computers to read,

### Simpler way

There is a simpler way to look at the MDF content and investigate a device. We can let VSCP Works scan it for us by going to the configuration window, that is the second alternative from above.

This is how the Vilnius A/D converter device look in the configuration window

![](./images/vilnius_config_window.png)

This window let us view and change configuration information and real time information such as measurements from the node. The default view is to look at the registers. 

### Register Abstraction

All configuration and other information on a VSCP node is presented to the world as information in 8-bit registers. This means that to get data from a VSCP node or write data to a VSCP node only two ow level operations are needed.

* Read a register.
* Write a register.

Easy to implement in most systems. Not always so convenient for humans.

### Abstractions

![](./images/vilnius_abstractions.png)

Abstractions are put above registers and is a presenting register content of a node if a more higher level way using strings, floating point values etc whcih we are used to handle.

### Decision Matrix

![](./images/vilnius_decision_matrix.png)

Next is the decision matrix. Not all devices have one but when it is there is a standard way to configure dynamic behaviour of a hardware device.

### Wizards

![](./images/vilnius_wizards.png)

Vilnius has no wizards defined so this item is empty here. But wizards is predefined configuration steps that can lead a user step by step in the configuration of a specific functionality. The MDF file can hold many, many such sep by step instruction sequence's. 

From the defined wizard sequence abstractions and registers of the remote node is set.

{% include "./bottom_copyright.md" %}