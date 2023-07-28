# How to reproduce the error

```
~/guava_capability_error $ ./gradlew -p one-library-with-libraries-bom build
> Task :compileJava FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileJava'.
> Could not resolve all files for configuration ':compileClasspath'.
   > Could not resolve com.google.guava:guava:32.1.1-jre.
     Required by:
         project : > com.google.cloud:libraries-bom:26.19.0
         project : > com.google.cloud:google-cloud-storage:2.22.6
      > Module 'com.google.guava:guava' has been rejected:
           Cannot select module with conflict on capability 'com.google.guava:listenablefuture:1.0' also provided by [com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava(compile)]
   > Could not resolve com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava.
     Required by:
         project : > com.google.cloud:google-cloud-storage:2.22.6
      > Module 'com.google.guava:listenablefuture' has been rejected:
           Cannot select module with conflict on capability 'com.google.guava:listenablefuture:9999.0-empty-to-avoid-conflict-with-guava' also provided by [com.google.guava:guava:32.1.1-jre(jreApiElements)]
```