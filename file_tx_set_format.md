# VSCP Works Transmission set file format

Format for saved transmission sets from the session window.

```xml
<?xml version = "1.0" encoding = "UTF-8" ?>
 
<!-- Version 0.0.1	2007-11-27 -->
 
<vscptxset>
    <set>
        <active>true|false</active>
        <name>Descriptive name for transmission line</name>
        <class>class code</class>
        <type>type code</type>
        <priority>priority 0-7</priority>
        <guid default="yes|no">xx.yy.xx.....</guid>
        <data>Comma separated list with data values</data>
        <count>Count value</count>
        <period>Period value</period>
        <trigger>Code for trigger</trigger>
    </set>
</vscptxset>
```

{% include "./bottom_copyright.md" %}