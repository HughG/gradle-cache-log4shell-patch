# gradle-cache-log4shell-patch

Gradle init script to automatically patch any vulnerable versions of log4j-core JAR
in your cache whenever they are used.

Note that this will **NOT** patch any running or already built project outputs.
It also may require a clean build to take effect.

Place this file in an `init.d` sub-folder of your Gradle user home directory in order to
automatically delete vulnerable files from any version of log4j-core whenever any
Gradle project uses it.  This may be preferable or necessary when building older
versions of existing projects, e.g., to use debuggers or add logging to diagnose
user issues.  You should re-test your project after it is built with a modified
log4j-core JAR, as removing the vulnerable classes may change behaviour.

You may need to create the `init.d` folder if it does not already exist.
Your Gradle user home directory defaults to the `.gradle` directory under
your home directory, or may be overridden by the `GRADLE_USER_HOME` environment
variable.

See <https://docs.gradle.org/current/userguide/init_scripts.html#init_scripts>
for more details of how init scripts are used.  You or your organisation may
wish to automatically push this file or similar into that directory on all
developer and build machines.
