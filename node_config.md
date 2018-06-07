# The Node Configuration Window

The node configuration window can be used to set parameters for a device.

On Ubuntu Linux this window looks like this

In the above screenshot I have highlighted the registry entry that set the interval for temperature reports on the Kelvin module. To change it just click on the value and update. The operations are the same if the module is locally connected or located on the other side of the earth.

And on Windows FIXME

Before this windows a session must be selected just as for the communication settings window. It is possible to connect through a local CANAL driver or a remote TCP/IP server. The only difference is that you need to enter a valid nickname id for a CANAL session before clicking update and that this id must be a full interface id with the least significant byte set to the nickname id of the device on that interface.

The update loads all registers from the device, both custom and standard. A clear text field is available at the bottom of the screen where data is presented in a more human suitable form. For instance the MDF URL is in clear text etc.

After updating the registers they can be edited and have threre register content changed and after that another click on the update button will write the content back.

The undo button can be used to reset all register to the content they had when the register session was opened.

In the clear register mode VSCP Work only recognize standard registers. It is therefore impossible for it to differentiate between read only and read/write registers in the custom register space. The MDF button address this.

After an update a click on the MDF button will automatically donwload the MDF file belonging to the device. It will then parse it and use the correct descriptions also for the custom registers. Further more now the abstractions can be used and entering register values can be done in a more human friendly way,

The nodeid field looks different when connected to a remote server as above or to a local CANAL driver. For a remote server the interface GUID is part of the id for the node and it tells which interface to talk to on the server. The least significant byte is the node id for the device connected to that interface. For a session connected directly to a CANAL device just the node-id is entered here.

To the right of the node-id field is a search button. It can be used to check that a node with the entered node-id really is present.

The connected/disconnected button tell if the connection to the server is active or not.

{% include "./bottom_copyright.md" %}