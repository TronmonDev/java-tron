# Custom Java-Tron Build

- **Custom Patch**: Bypassed strict JDK version check (`throwIfUnsupportedJavaVersion`) to allow running and building on newer or custom JDK environments.

- /platform/src/main/java/common/org/tron/common/arch/Arch.java
public static void throwIfUnsupportedJavaVersion() {
//if ((isX86() && !isJava8()) || (isArm64() && !isJava17())) {
//      logger.info(withAll());
//      throw new UnsupportedOperationException(String.format(
//          "Java %s is required for %s architecture. Detected version %s", isX86() ? "1.8" : "17",
//          getOsArch(), javaSpecificationVersion()));
//    }
  }

./framework/src/main/java/org/tron/program/FullNode.java
private static void checkJdkVersion() {
  }

  
./build.gradle 
//if (!archInfo.java.is(archInfo.requires.JavaVersion)) {
//    throw new GradleException("Java ${archInfo.requires.JavaVersion} is required for ${archInfo.name}. Detected version ${archInfo.java}")
//}
