# ideaJVMPerfomance
latest dump for JVM opts for best Intellij

## Mac Mojave + Idea VM settings..


```
# custom IntelliJ IDEA VM options
-server
-Xss16m
-Xms24G
-Xmx24G
-XX:ReservedCodeCacheSize=240m
-XX:+AlwaysPreTouch
-XX:+TieredCompilation
-XX:+UseCompressedOops
-XX:+UseCompressedStrings
-XX:+UseCompressedClassesPointers
-XX:SoftRefLRUPolicyMSPerMB=50
-XX:+OptimizeStringConcat
-Dsun.io.useCanonCaches=false
-Djava.net.preferIPv4Stack=true
-ea

# GC tuning
-XX:NewRatio=1
-XX:+UseConcMarkSweepGC
-XX:+CMSParallelRemarkEnabled
-XX:+UseParNewGC
# ParallelGCThreads + 1
-XX:ConcGCThreads=21
-XX:+ScavengeBeforeFullGC
-XX:+CMSScavengeBeforeRemark
-XX:+ParallelRefProcEnabled
-XX:+ExplicitGCInvokesConcurrent
-XX:+CMSClassUnloadingEnabled
-XX:+CMSParallelRemarkEnabled
-XX:ParallelGCThreads=20
# Percentage of the (entire) heap occupancy to start a concurrent GC cycle.
# GCs that trigger a concurrent GC cycle based on the occupancy of the entire heap
# and not just one of the generations, including G1, use this option.
# A value of 0 denotes 'do constant GC cycles'. The default value is 45.
-XX:InitiatingHeapOccupancyPercent=70

# Metaspace caps
-XX:CompressedClassSpaceSize=300m
-XX:MaxMetaspaceFreeRatio=30
-XX:MetaspaceSize=300m
-XX:MinMetaspaceFreeRatio=10


# GC output
-Xloggc:/tmp/intellij-gc-%t.log
-XX:+PrintGCDetails
-XX:+PrintGCDateStamps
-XX:+PrintGCCause
-XX:+PrintTenuringDistribution
-XX:+PrintReferenceGC -XX:+PrintAdaptiveSizePolicy
-XX:+PrintGCTimeStamps
-Dide.no.platform.update=true

```
