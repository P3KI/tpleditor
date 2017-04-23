# tpleditor
Proof of Concept for a 2D TPL editor for TreeDNS Languages

# How to build & execute

extract libcallwrapper in a way that `./tpl/bin/tpl` exists.

We use the `fatJar` target and not the normal build target:

    gradle fatJar

Afterwards execute the `tpleditor_gradle-all-1.0.jar`

    java -jar build/libs/tpleditor_gradle-all-1.0.jar

Warning: Make sure you execute `build/libs/tpleditor_gradle-all-1.0.jar`
from the build root directory (which must contain `./tpl/bin/tpl`) as
illustrated above.

# Author

Paul Seitz <paul.m.setiz@gmail.com>
