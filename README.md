Splitter is a tool for splitting TEI-Lite XML files into separate layers. By 
default it separates out layers for add, del, sic, corr, abbrev, expan, 
and also (not in TEI-Lite) rdg. For each layer splitter creates a file:

&lt;orig-name&gt;-&lt;layer&gt;&lt;index&gt;.xml

Splitter only recognises parallel segmentation variants, and it will assume that 
all &lt;rdg&gt; elements are alternatives within the enclosing &lt;app&gt; element.

Splitter is a part of the calliope web service. However, it can be used also as a 
standalone tool. For the source code see the calliope project at 
www.github.com/AUSTESE-Infrastructure/calliope/.

To use splitter you must have version 1.6 or better of Java installed. To test if 
it is there open a commandline shell (or DOS shell) and type:

java -version

If it replies with something like:

java version "1.6.0_35"
Java(TM) SE Runtime Environment (build 1.6.0_35-b10-428-11M3811)
Java HotSpot(TM) 64-Bit Server VM (build 20.10-b01-428, mixed mode)

then all is well. If not you can install a new version for your operating system from 
http://www.oracle.com/technetwork/java/javase/downloads/index.html

To run splitter go into the directory where you copied splitter.jar and type:

java -jar splitter.jar test.xml

To specify another XML file swap "test.xml" for your own TEI-XML file.
The split files will appear in the same directory and will be encoded in UTF-8.

The config file allows you to specify different elements to treat than the standard 
TEI ones, also to define different behaviours for variant-elements. However, it is 
presently undocumented. The code is in 
calliope/handler/post/importer/Splitter.java. 
Specifying no config file will use 
the existing one, which is built-into the code. There is no need to specify it on 
the commandline.
