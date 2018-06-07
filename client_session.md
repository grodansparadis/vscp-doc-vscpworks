# The Client session window

## The VSCP Client session Window

With the client window of VSCP works it is possible to open communication sessions that either connect

* Directly to a Level I (CANAL) hardware driver. Depending on the driver, one or more sessions can be opened to the driver. The normal is however one.
* Open a session to a local or remote VSCP node or daemon which in turn have drivers connected to it. The node should export the [VSCP tcp/ip link protocol](https://grodansparadis.gitbooks.io/the-vscp-specification/vscp_over_tcp_ip.html).

To open a new session windoow use the File/New VSCP Client window. You can now select a predefined interface to connect to or create a new.

Below is a picture of how this window looks on Ubuntu Linux

![](./images/vscpworks_new_session.jpg)


Remote item interfaces have **“TCP/IP:”** in front of them and local interface items or direct connection items to Level I (CANAL) drivers have **“CANAL:”** in front of them. 

The first type always listed is the **“Unconnected Mode”** wich opens the window without a connection either to a remote server or a Level I (CANAL) driver. This is useful when one wants to investigate saved session data.

* With the **Add** button a new TCP/IP or Level I (CANAL) interface can be added. 
* With the **Edit** button an already available interface setting can be edited/changed.
* With the **Remove** button an already available interface can be removed.


The image below shows how the Level I (CANAL) session edit window looks like on Ubunto Linux

![](./images/vscpwors_canal_session.jpg)

Standard Level I (CANAL) interface settings is available here.

* **Description** - Set a descriptive name here for use in listboxes etc.
* **Path to Driver** - The box to the right allows location to be found on the system.
* **Device configuration string** - The string used to configure the driver.
* **Flags** - The numerical flag value used to configure the driver.

A Level I (CANAL) driver can have an internal XML file stored that describes the configuration string. If the driver has such information the button to the right of the configuration string can be used to run a wizard that helps in setting up both the flags field and the configuration field in an easy way without needing to find the drivers full documentation.

The image below shows how the remote TCP/IP server edit window looks like on Ubuntu Linux

![](./images/vscpworks_remote_server.jpg)

The remote TCP/IP interface needs the following parameters to be defined and set

* **Description** - Set a descriptive name here for use in listboxes etc.
* **Server URL** - The hostname for the remote VSCP tcp/ip node.
* **Server port** - The port that the remote VSCP tcp/ip node is listening on. Normaly 9598.
* **Username** - Username used to login to the remote node.
* **Password** - Password used to login to the remote node. Leave blank to force VSCP Works to ask before connecting.
* **GUID** - This is the globally unique id (GUID) for the rmote interface and it should normally be set to all zero for a standard remote connection. In this case a sent event from our client will be sent on all aailable interfaces on the remote node. If a valid interface GUID is entered here (a GUID for the remote nodes interface) all sent events will only go to devices on the selected interface. As a help to set the correct interface the **Get Interface** button is available which will fetch all available interfaces from the remote node and allow you to slect one of them.

Use the **Set Filter** button to set an incoming filter fpr this session. Only events that satisfy the filter/mask combination will be received from the remote node.

Use the **Test Connection** button to test the connection to the remote node.

----

Selecting one of the interfaces and pressing OK (or double clicking the line) opens the session window

Ubuntu Linux session window

![](./images/vscpworks_session.jpg)

The session window is divided into three main areas. The upper left area is the **receive list**, the upper right area (when a row is selected in the receive list) is the **information area** and the lower area is the **transmission list**. 

### Receive List
Events that are received from a remote node is listed in the receive list (Marked with **RX**) but also transmitted events are showed here (marked with **TX*). 

Currently a chronological view is available (message log). Other views may follow in the future.

By right clicking on the receive list some functionality will be available

* **Clear all receive events** which lets you removve all events in the receive session window. The command is alos available under the **Edit** menu.
* **Load VSCP events from file** which lets you load saved events from disk to the receive session window. You will get a question asking if you want to remove all events currently in the receive session window brefore the new events is loaded from disk. The command is also available under the **File** menu.
* **Save VSCP events to file** which lets you save (selected or all) VSCP events to a file on disk. The command is also available under the **File** menu. On Linux systems you may need to select the pen icon in the upper left top of the save file window to write a filename (see below).

![](./images/session_rcv_save.png)

In the menus you can 

* Edit the selected row.
* Add a note for the selected row.
* Copy/Cut/paste rows.
* Transmit one or many selected rows.
* Edit and transmit one or many selected rows.
* Save selected row(s) as transmission objects.
* Load VSCP events from file.
* Save VSCP events from file.

### Transmission area

In the transmission area list rows are available that can be transmitted to the connected remote node or driver. It is possible to load and save transmission row sets which can be handy in many situations. It is possible to creat rows that is automatically transmitted with a selected period expressed in milliseconds and which continue to do so as long as they are active. It is also possible to create transmission row objects that automatically send out one or more event when another event is received.

On the right of the Transmission object list is a set of buttons

and on windows

FIXME

that control rows in the list.

The first button add a new transmission object. The second button edit a selected row and the third button delete a row.

The forth button load a transmission ro set from a file and the fifth button save the current rows.

On the right isa single button

and on windows

FIXME

This button is used to send the selected row(s). A single row can also be sent by double clicking on it but by selection several rows and clicking on this button the rows will be sent in sequence.

Some additional functionality is available by right clicking on the transmission object list.

    Transmit selected row(s).
    Add/edit/Delete rows.
    Clone row.
    Enable/disable periodic transmission.

The transmission row edit window looks like this on Ubuntu Linux

and like this on Windows

FIXME

Standard settings for events are available here. To use the GUID assigned by the daemon as the originator for the event set GUID to all zeros.

Data for the event is just a comma separated (mixed if needed) list of hexadecimal or decimal values.

Count is the number of sends of the transmission row.

Period is the time in milliseconds between automatically transmitted rows.

Trigger is a selected trigger among the available triggers.

### Informatin area

Information about a selected event in the receive list is shown in the information area.