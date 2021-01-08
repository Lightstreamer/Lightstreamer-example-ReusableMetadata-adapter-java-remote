# Lightstreamer - Reusable Metadata Adapters - Java Remote Adapter

<!-- START DESCRIPTION lightstreamer-example-reusablemetadata-adapter-java-remote -->

<b>WARNING. This project is obsolete, the relevant code has been merged into this project [Lightstreamer Java Remote Adapter SDK](https://github.com/Lightstreamer/Lightstreamer-lib-adapter-java-remote#literalbasedprovider-metadata-adapter); which you need to refer to for an updated version of the LiteralBasedProvider Metadata Adapter.</b>

This project includes a simple full implementation of Remote Metadata Adapter in Java made available as sample for inspiration and/or extension.

## LiteralBasedProvider Metadata Adapter

The LiteralBasedProvider is the Remote equivalent of the *LiteralBasedProvider* Metadata Adapter in [Lightstreamer - Reusable Metadata Adapters - Java Adapters](https://github.com/Lightstreamer/Lightstreamer-example-ReusableMetadata-adapter-java).
It extends the [com.lightstreamer.adapters.remote.MetadataProviderAdapter](https://lightstreamer.com/api/ls-adapter-remote/latest/com/lightstreamer/adapters/remote/MetadataProviderAdapter.html) abstract class (which in turn implements the [com.lightstreamer.adapters.remote.MetadataProvider](https://lightstreamer.com/api/ls-adapter-remote/latest/com/lightstreamer/adapters/remote/MetadataProvider.html) interface).
It is used in Lightstreamer examples and demos based on the Java Remote Adapter SDK, in combination with suitable Data Adapters and Clients.
Its binaries are included in the Java Remote Adapter SDK library.

<!-- END DESCRIPTION lightstreamer-example-reusablemetadata-adapter-java-remote -->
<br>
<br>

## Build

Before you can compile the adapter, some dependencies need to be solved:
* Get the Lightstreamer Java Remote Adapter library `ls-adapter-remote.jar` file from the `DOCS-SDKs/sdk_adapter_java_remote/lib` folder of the [latest Lightstreamer distribution](http://www.lightstreamer.com/download/), and put it in a temporary folder, let's call it `compile_libs`.

Note that `ls-adapter-remote.jar` already includes the class files for com.lightstreamer.adapters.metadata.LiteralBasedProvider; we can ignore that for a moment.
If you are testing your own modified version of the LiteralBasedProvider code, take care of changing the package name, or, at least, the class name.

Now you can generate the jar for the sample Metadata Adapter, let's call it `ls-generic-adapter-remote.jar`, with the following commands:
```sh
 > mkdir tmp_classes
 > javac -source 1.7 -target 1.7 -nowarn -g -classpath compile_libs/ls-adapter-remote.jar -sourcepath src -d tmp_classes src/com/lightstreamer/adapters/remote/metadata/LiteralBasedProvider.java
 > jar cvf ls-generic-adapter-remote.jar -C tmp_classes com/lightstreamer
```

### Deploy

To use the Metadata Adapter just built in some Remote Server, just include the `ls-generic-adapter-remote.jar` library in addition to `ls-adapter-remote.jar`.
As said, the class files for com.lightstreamer.adapters.remote.metadata.LiteralBasedProvider are already included in `ls-adapter-remote.jar`; hence this step is not needed for the LiteralBasedProvider.

The LiteralBasedProvider can be configured through suitable initialization parameters. See the [class documentation](https://lightstreamer.com/api/ls-adapter-remote/latest/com/lightstreamer/adapters/remote/metadata/LiteralBasedProvider.html) for details.

## See Also
* [Adapter Remoting Infrastructure Network Protocol Specification](https://lightstreamer.com/api/ls-generic-adapter/latest/ARI%20Protocol.pdf)

### Related Projects
* [Lightstreamer - Reusable Metadata Adapters - Java Adapter](https://github.com/Lightstreamer/Lightstreamer-example-ReusableMetadata-adapter-java)
* [Lightstreamer - Reusable Metadata Adapters - .NET Adapter](https://github.com/Lightstreamer/Lightstreamer-example-ReusableMetadata-adapter-dotnet)
* [Lightstreamer - Stock-List Demo - Java Remote Adapter](https://github.com/Lightstreamer/Lightstreamer-example-Stocklist-adapter-java-remote)

## Lightstreamer Compatibility Notes

* Compatible with Lightstreamer SDK for Java Remote Adapters since 1.0
