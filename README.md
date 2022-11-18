# Protobuf Prefab
[![](https://img.shields.io/badge/Minimum%20Sdk-24-2196F3)](https://github.com/RohitVerma882/libcxx-prefab)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)
[![Maven Central](https://img.shields.io/maven-central/v/io.github.rohitverma882/protobuf-prefab.svg?label=Maven%20Central)](https://search.maven.org/artifact/io.github.rohitverma882/protobuf-prefab)

Prefab package for (https://android.googlesource.com/platform/external/protobuf)

## Integration

This is a [Prefab](https://google.github.io/prefab/) library, so you will need to enable it in your project (requires Android Gradle Plugin 4.1+):

```gradle
android {
    ...
    buildFeatures {
        ...
        prefab true
    }
}
```

Add dependency:

```gradle
repositories {
    mavenCentral()
}

dependencies {
    implementation 'io.github.rohitverma882:protobuf-prefab:<letest-version>'
}
```

## Usage

### ndk-build

```makefile
LOCAL_STATIC_LIBRARIES := protobuf

# You can remove this block if you are using NDK r21+.
ifneq ($(call ndk-major-at-least,21),true)
    $(call import-add-path,$(NDK_GRADLE_INJECTED_IMPORT_PATH))
endif

$(call import-module,prefab/protobuf)
```

### CMake

```cmake
find_package(protobuf REQUIRED CONFIG)
target_link_libraries(<your lib> protobuf::libprotobuf)
```
