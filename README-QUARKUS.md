# playing-quarkus

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## upgrade to the newer Quarkus-Version

### from version 1.4.2.Final to 1.11.0.Final

1. edit the cradle.properties and replace:

   ```
   quarkusPluginVersion=1.4.2.Final
   quarkusPlatformVersion=1.4.2.Final
   ```

2. Install corresponding GraalVM `20.3.0` in the Community-Version. I tried `20.3.1` ... https://github.com/graalvm/graalvm-ce-builds/releases ... please update the Environment variable to the new version `export GRAALVM_HOME=/Users/wagnerol/bin/SDKs/graalVM/current/Contents/Home` - for example at `.bashrc`.

Thats all. Now you can use the commands to build the Quarkus-Server.

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```
./gradlew quarkusDev
```

## Packaging and running the application

The application can be packaged using `./gradlew quarkusBuild`.
It produces the `quarkus01hello-0.0.1-SNAPSHOT-runner.jar` file in the `build` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `build/lib` directory.

The application is now runnable using `java -jar build/quarkus01hello-0.0.1-SNAPSHOT-runner.jar`.

If you want to build an _über-jar_, just add the `--uber-jar` option to the command line:
```
./gradlew quarkusBuild --uber-jar
```

## Creating a native executable

After extracting the tar.gz - After doing this you have to export the variable `export GRAALVM_HOME=/Users/wagnerol/bin/SDKs/graalVM/current/Contents/Home` (for example at .zshrc). Now go to `${GRAALVM_HOME}/Contents/Home/bin` and execute `./gu install native-image` (install the GraalVM with Native-Image support). 

You can create a native executable using: `./gradlew quarkusBuild -Dquarkus.package.type=native`.

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: `./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true`.

You can then execute your native executable with: `./build/quarkus01hello-0.0.1-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/gradle-tooling#building-a-native-executable.