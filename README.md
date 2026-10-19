# Custom Java-Tron Build

- **Custom Patch**: Bypassed strict JDK version check to allow running and building on newer or custom JDK environments.

---

### 📝 Modified Files & Code

#### 1. Arch.java
- **Path**: `/platform/src/main/java/common/org/tron/common/arch/Arch.java`
- **Description**: Bypassed architecture-specific runtime version enforcement.

```java
public static void throwIfUnsupportedJavaVersion() {
    //if ((isX86() && !isJava8()) || (isArm64() && !isJava17())) {
    //      logger.info(withAll());
    //      throw new UnsupportedOperationException(String.format(
    //          "Java %s is required for %s architecture. Detected version %s", isX86() ? "1.8" : "17",
    //          getOsArch(), javaSpecificationVersion()));
    //}
}
```

#### 2. Arch.java
- **Path**: `/framework/src/main/java/org/tron/program/FullNode.java`
- **Description**: Disabled startup JDK validation routine.

```java
private static void checkJdkVersion() {
}
```

#### 2. build.gradle
- **Path**: `/build.gradle`
- **Description**: Disabled compile-time Gradle version check.

```java
//if (!archInfo.java.is(archInfo.requires.JavaVersion)) {
//    throw new GradleException("Java ${archInfo.requires.JavaVersion} is required for${archInfo.name}. Detected version ${archInfo.java}")
//}
```

