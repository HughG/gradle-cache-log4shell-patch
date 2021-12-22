# gradle-cache-log4shell-patch
Gradle init script to automatically patch any vulnerable versions of log4j-core JAR
in your cache whenever they are used.

Place this file in an `init.d` sub-folder of your Gradle home directory in order to
automatically delete vulnerable files from any version of log4j-core whenever any
Gradle project uses it.  This may be preferable or necessary when building older
versions of existing projects, e.g., to use debuggers or add logging to diagnose
user issues.  You should re-test your project after it is built with a modified
log4j-core JAR, as removing the vulnerable classes may change behaviour.
