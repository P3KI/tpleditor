# tpleditor
Proof of Concept for a 2D TPL editor for TreeDNS Languages

# UI latency (graph updates)
Updating the graph is delayed, as for every change we do a call to an external program `./tpl/bin/tpl`. 
Using `./tpl/bin/tpl` as a library (jar) would make updating the UI in realtime possible but
we didn't have it as a library and it was not in the requirements file.

# How to build & execute

extract libcallwrapper in a way that `./tpl/bin/tpl` exists and is executable.

    $ ls -lathr tpls/bin
    -rwxr-xr-x 1 joachim users 5,4K 23. Apr 17:02 tpl
    ...

We use the `fatJar` target and not the normal build target:

    gradle clean
    gradle fatJar

Note: do not use `gradle build` as this won't find the required libraries (use `fatJar` instead).

Afterwards execute the `tpleditor_gradle-all-1.0.jar`

    java -jar build/libs/tpleditor_gradle-all-1.0.jar

Warning: Make sure you execute `build/libs/tpleditor_gradle-all-1.0.jar`
from the build root directory (which must contain `./tpl/bin/tpl`) as
illustrated above. If not you will see this errors:

    java.io.IOException: Cannot run program "./tpl/bin/tpl": error=2, No such file or directory

# Author

Paul Seitz <paul.m.setiz@gmail.com>
