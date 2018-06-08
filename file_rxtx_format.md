# VSCP Works receive/transmission data file format

Format for data files saved from the session receive window.

```xml
<?xml version = "1.0" encoding = "UTF-8" ?>
 
<!-- Version 0.0.1	2007-11-28 -->
 
<vscprxdata>
    <event>
        <dir>rx|tx</dir>
        <time>(real)-time when event was received</time>
        <head>priority etc</head>
        <class>class code</class>
        <type>type code</type>
        <guid>XX:YY:ZZ.....</guid>
        <data>Comma separated list with data values</data>
        <timestamp>Relative timestamp for event</timestamp>
        <note>User note about line</note>
    </event>
</vscprxdata>
```


{% include "./bottom_copyright.md" %}