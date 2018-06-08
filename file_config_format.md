# VSCP Works configuration file format

Format for the VSCP Works configuration file.

```xml
<?xml version = "1.0" encoding = "UTF-8" ?>
 
<!-- Version 0.0.1	2007-10-26 -->
 
<vscpworksconfig>
 
    <general>
        <width>Client window startup width</width>
        <height>Client window startup height</height>
        <xpos>Client window X startup position</xpos>
        <ypos>Client window Y startup position</ypos>
        <path2tempfiles>
        Path to folder holding temporary files
        </path2tempfiles>
        <path2logfile enable="true|false" 
                        level="1">
        Path including filename to log file
        </path2logfile>
    </general>
 
    <vscpclient>
        <VscpRcvFrameRxTextColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpRcvFrameRxTextColour>
        <VscpRcvFrameRxBgColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpRcvFrameRxBgColour>
        <VscpRcvFrameTxTextColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpRcvFrameTxTextColour>
        <VscpRcvFrameTxBgColour r="value" 
                                g="value" 
                                b="value">
        </VscpRcvFrameTxBgColour>
        <VscpRcvFrameLineColour r="value" 
                                g="value" 
                                b="value">
        </VscpRcvFrameLineColour>
        <VscpRcvFrameFont></VscpRcvFrameFont>
        <!-- Enable/Disable grey background on odd rows -->
        <VscpRcvPyjamasStyle>true|false</VscpRcvPyjamasStyle>
        <!-- Enable/Disable autoscroll when filling grid -->
        <Autoscroll>true|false</Autoscroll>
        <VscpRcvShowField0 enable="true|false">
        </VscpRcvShowField0>
        <VscpRcvShowField1 enable="true|false">
        </VscpRcvShowField1>
        <VscpRcvShowField3 enable="true|false">
        </VscpRcvShowField3>
        <VscpRcvShowField4 enable="true|false">
        </VscpRcvShowField4>
        <VscpRcvShowField5 enable="true|false">
        </VscpRcvShowField5>
        <VscpRcvShowField6 enable="true|false">
        </VscpRcvShowField6>
        <VscpRcvShowField7 enable="true|false">
        </VscpRcvShowField7>
        <VscpRcvFieldText0>Dir</VscpRcvFieldText0>
        <VscpRcvFieldText1>Time</VscpRcvFieldText1>
        <VscpRcvFieldText2>GUID</VscpRcvFieldText2>
        <VscpRcvFieldText3>Class</VscpRcvFieldText3>
        <VscpRcvFieldText4>Type</VscpRcvFieldText4>
        <VscpRcvFieldText5>Head</VscpRcvFieldText5>
        <VscpRcvFieldText6>Cnt</VscpRcvFieldText6>
        <VscpRcvFieldText7>Data</VscpRcvFieldText7>
        <VscpRcvFieldText8>Timestamp</VscpRcvFieldText8>
        <VscpRcvFieldText9>Note</VscpRcvFieldText9>
        <VscpRcvFieldOrder0>0</VscpRcvFieldOrder0>
        <VscpRcvFieldOrder1>1</VscpRcvFieldOrder1>
        <VscpRcvFieldOrder2>2</VscpRcvFieldOrder2>
        <VscpRcvFieldOrder3>3</VscpRcvFieldOrder3>
        <VscpRcvFieldOrder4>4</VscpRcvFieldOrder4>
        <VscpRcvFieldOrder5>5</VscpRcvFieldOrder5>
        <VscpRcvFieldOrder6>6</VscpRcvFieldOrder6>
        <VscpRcvFieldOrder7>7</VscpRcvFieldOrder7>
        <VscpRcvFieldOrder8>8</VscpRcvFieldOrder8>
        <VscpRcvFieldOrder9>9</VscpRcvFieldOrder9>
        <VscpRcvFieldWidth0>30</VscpRcvFieldWidth0>
        <VscpRcvFieldWidth1>110</VscpRcvFieldWidth1>
        <VscpRcvFieldWidth2>250</VscpRcvFieldWidth2>
        <VscpRcvFieldWidth3>70</VscpRcvFieldWidth3>
        <VscpRcvFieldWidth4>70</VscpRcvFieldWidth4>
        <VscpRcvFieldWidth5>60</VscpRcvFieldWidth5>
        <VscpRcvFieldWidth6>60</VscpRcvFieldWidth6>
        <VscpRcvFieldWidth7>300</VscpRcvFieldWidth7>
        <VscpRcvFieldWidth8>90</VscpRcvFieldWidth8>
        <VscpRcvFieldWidth9>200</VscpRcvFieldWidth9>
        <VscpTrmitFrameTextColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpTrmitFrameTextColour>
        <VscpTrmitFrameBgColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpTrmitFrameBgColour>
        <VscpTrmitFrameLineColour r="value" 
                                    g="value" 
                                    b="value">
        </VscpTrmitFrameLineColour>
        <VscpTrmitFrameFont></VscpTrmitFrameFont>
        <VscpTrmitShowField0 
            enable="true|false">
        </VscpTrmitShowField0>
        <VscpTrmitShowField1 
            enable="true|false">
        </VscpTrmitShowField1>
        <VscpTrmitShowField2 
            enable="true|false">
        </VscpTrmitShowField2>
        <VscpTrmitShowField3 
            enable="true|false">
        </VscpTrmitShowField3>
        <VscpTrmitFieldText0></VscpTrmitFieldText0>
        <VscpTrmitFieldText0></VscpTrmitFieldText0>
        <VscpTrmitFieldText1></VscpTrmitFieldText1>
        <VscpTrmitFieldText2></VscpTrmitFieldText2>
        <VscpTrmitFieldText3></VscpTrmitFieldText3>
        <VscpTrmitFieldText4></VscpTrmitFieldText4>
        <VscpTrmitFieldOrder0></VscpTrmitFieldOrder0>
        <VscpTrmitFieldOrder1></VscpTrmitFieldOrder1>
        <VscpTrmitFieldOrder2></VscpTrmitFieldOrder2>
        <VscpTrmitFieldOrder3></VscpTrmitFieldOrder3>
        <VscpTrmitFieldOrder4></VscpTrmitFieldOrder4>
        <VscpTrmitFieldWidth0></VscpTrmitFieldWidth0>
        <VscpTrmitFieldWidth1></VscpTrmitFieldWidth1>
        <VscpTrmitFieldWidth2></VscpTrmitFieldWidth2>
        <VscpTrmitFieldWidth3></VscpTrmitFieldWidth3>
        <VscpTrmitFieldWidth4></VscpTrmitFieldWidth4>
        
    </vscpclient>
 
    <vscpinterface>
 
        <canaldriver> <!-- One or many -->
            <description>Interface description for listbox</description>
            <path>oath to driver</path>
            <config>configstring</config>
            <flags>driver flags</flags>
        </canaldriver>
 
        <vscpdaemon> <!-- One or many -->
            <description>Interface description for listbox</description>
            <host></host>
            <port></port>
            <username></username>
            <password></password>
            <filter priority="xxx" 
                    class="xxx" 
                    type="xxx" 
                    GUID="xxx" >
                    This is the row filter
            </filter>
            <mask priority="xxx" 
                    class="xxx" 
                    type="xxx" 
                    GUID="xxx" >
                    This is the row mask
            </mask>
        </vscpdaemon>
 
    </vscpinterface>
 
</vscpworksconfig>
```

{% include "./bottom_copyright.md" %}