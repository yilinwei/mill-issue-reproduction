# Mill problem

 - Mill version: `0.6.1`
 - OS: Arch Linux

## Steps

```sh
  cd src/mill
  mill app.compile
  cd ../..
  mill app.compile
```

## Stacktrace

```
app.sources java.nio.file.FileSystemException: /home/yilin/scala/mill-reproduction/app/src/out/mill-worker-fSigIuC6ILA7VOscy+wh28PLoCA=-1/io: No such device or address
    java.base/sun.nio.fs.UnixException.translateToIOException(UnixException.java:100)
    java.base/sun.nio.fs.UnixException.rethrowAsIOException(UnixException.java:111)
    java.base/sun.nio.fs.UnixException.rethrowAsIOException(UnixException.java:116)
    java.base/sun.nio.fs.UnixFileSystemProvider.newByteChannel(UnixFileSystemProvider.java:219)
    java.base/java.nio.file.Files.newByteChannel(Files.java:374)
    java.base/java.nio.file.Files.newByteChannel(Files.java:425)
    java.base/java.nio.file.spi.FileSystemProvider.newInputStream(FileSystemProvider.java:420)
    java.base/java.nio.file.Files.newInputStream(Files.java:159)
    os.Path.getInputStream(Path.scala:474)
    os.read$inputStream$.apply(ReadWriteOps.scala:231)
    mill.api.PathRef$.$anonfun$apply$2(PathRef.scala:40)
    mill.api.PathRef$.$anonfun$apply$2$adapted(PathRef.scala:30)
    scala.collection.TraversableLike$WithFilter.$anonfun$foreach$1(TraversableLike.scala:792)
    scala.collection.IndexedSeqOptimized.foreach(IndexedSeqOptimized.scala:36)
    scala.collection.IndexedSeqOptimized.foreach$(IndexedSeqOptimized.scala:33)
    scala.collection.mutable.WrappedArray.foreach(WrappedArray.scala:39)
    scala.collection.TraversableLike$WithFilter.foreach(TraversableLike.scala:791)
    mill.api.PathRef$.apply(PathRef.scala:30)
    mill.scalalib.JavaModule.$anonfun$sources$4(JavaModule.scala:168)
    mill.api.Result$Success.map(Result.scala:24)
    mill.api.Result$Success.map(Result.scala:23)
    mill.scalalib.JavaModule.$anonfun$sources$2(JavaModule.scala:168)
    mill.define.Applicative$Applyer.$anonfun$zipMap$1(Applicative.scala:35)
    mill.define.Task$MappedDest.evaluate(Task.scala:379)
```
