# Spring Native Error

## Errors

When run `./mvnw clean spring-boot:build-image`, Spring Native will throw an exception:
```
[INFO]     [creator]     Fatal error:java.lang.TypeNotPresentException: Type javax.servlet.Filter not present
[INFO]     [creator]            at java.base/sun.reflect.generics.factory.CoreReflectionFactory.makeNamedType(CoreReflectionFactory.java:117)
[INFO]     [creator]            at java.base/sun.reflect.generics.visitor.Reifier.visitClassTypeSignature(Reifier.java:125)
[INFO]     [creator]            at java.base/sun.reflect.generics.tree.ClassTypeSignature.accept(ClassTypeSignature.java:49)
[INFO]     [creator]            at java.base/sun.reflect.generics.visitor.Reifier.reifyTypeArguments(Reifier.java:68)
[INFO]     [creator]            at java.base/sun.reflect.generics.visitor.Reifier.visitClassTypeSignature(Reifier.java:138)
[INFO]     [creator]            at java.base/sun.reflect.generics.tree.ClassTypeSignature.accept(ClassTypeSignature.java:49)
[INFO]     [creator]            at java.base/sun.reflect.generics.visitor.Reifier.reifyTypeArguments(Reifier.java:68)
[INFO]     [creator]            at java.base/sun.reflect.generics.visitor.Reifier.visitClassTypeSignature(Reifier.java:138)
[INFO]     [creator]            at java.base/sun.reflect.generics.tree.ClassTypeSignature.accept(ClassTypeSignature.java:49)
[INFO]     [creator]            at java.base/sun.reflect.generics.repository.MethodRepository.computeReturnType(MethodRepository.java:75)
[INFO]     [creator]            at java.base/sun.reflect.generics.repository.MethodRepository.getReturnType(MethodRepository.java:66)
[INFO]     [creator]            at java.base/java.lang.reflect.Method.getGenericReturnType(Method.java:292)
[INFO]     [creator]            at com.oracle.svm.reflect.hosted.ReflectionMetadataFeature.replacer(ReflectionMetadataFeature.java:65)
[INFO]     [creator]            at com.oracle.graal.pointsto.meta.AnalysisUniverse.replaceObject(AnalysisUniverse.java:565)
[INFO]     [creator]            at com.oracle.graal.pointsto.ObjectScanner.scanArray(ObjectScanner.java:236)
[INFO]     [creator]            at com.oracle.graal.pointsto.ObjectScanner.doScan(ObjectScanner.java:351)
[INFO]     [creator]            at com.oracle.graal.pointsto.ObjectScanner.access$400(ObjectScanner.java:60)
[INFO]     [creator]            at com.oracle.graal.pointsto.ObjectScanner$2$1.run(ObjectScanner.java:388)
[INFO]     [creator]            at com.oracle.graal.pointsto.util.CompletionExecutor.lambda$execute$0(CompletionExecutor.java:173)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinTask$RunnableExecuteAction.exec(ForkJoinTask.java:1426)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinTask.doExec(ForkJoinTask.java:290)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinPool$WorkQueue.topLevelExec(ForkJoinPool.java:1020)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinPool.scan(ForkJoinPool.java:1656)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinPool.runWorker(ForkJoinPool.java:1594)
[INFO]     [creator]            at java.base/java.util.concurrent.ForkJoinWorkerThread.run(ForkJoinWorkerThread.java:183)
[INFO]     [creator]     Caused by: java.lang.ClassNotFoundException: javax.servlet.Filter
[INFO]     [creator]            at java.base/java.net.URLClassLoader.findClass(URLClassLoader.java:471)
[INFO]     [creator]            at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:589)
[INFO]     [creator]            at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:522)
[INFO]     [creator]            at java.base/java.lang.Class.forName0(Native Method)
[INFO]     [creator]            at java.base/java.lang.Class.forName(Class.java:398)
[INFO]     [creator]            at java.base/sun.reflect.generics.factory.CoreReflectionFactory.makeNamedType(CoreReflectionFactory.java:114)
[INFO]     [creator]            ... 24 more
[INFO]     [creator]     Error: Image build request failed with exit status 1
[INFO]     [creator]     unable to invoke layer creator
[INFO]     [creator]     unable to contribute native-image layer
[INFO]     [creator]     error running build
[INFO]     [creator]     exit status 1
[INFO]     [creator]     ERROR: failed to build: exit status 1
```

After removing `spring-boot-starter-security` and `spring-security-test`, everything is going fine.