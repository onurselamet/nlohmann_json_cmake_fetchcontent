# Release-tracking repository for nlohmann/json

This repository is based on: [astoeckel/json](https://github.com/astoeckel/json)
The goal is to provide a lightweight repository tracking every releases of
[nlohmann/json](https://github.com/nlohmann/json).
This repository is compatible with cmake [FetchContent](https://cmake.org/cmake/help/v3.11/module/FetchContent.html).

You can depends on nlohmann/json using:

**Example**:
~~~cmake
include(FetchContent)

FetchContent_Declare(json
  GIT_REPOSITORY https://github.com/ArthurSonzogni/nlohman_json
  GIT_TAG v2.0.9)

FetchContent_GetProperties(json)
if(NOT json_POPULATED)
  FetchContent_Populate(json)
  add_subdirectory(${json_SOURCE_DIR} ${json_BINARY_DIR} EXCLUDE_FROM_ALL)
endif()

target_link_libraries(foo PRIVATE nlohmann_json::nlohmann_json)
~~~

You can replace always replace the URL by the official repository:
https://github.com/nlohmann/json
The only difference is the download size. It will several orders of magnitude
larger.

This repository is fully autonomous. It updates itself every week using github
actions.

See:
- [#2073](https://github.com/nlohmann/json/issues/2073),
- [#732](https://github.com/nlohmann/json/issues/732),
- [#620](https://github.com/nlohmann/json/issues/620),
- [#556](https://github.com/nlohmann/json/issues/556),
- [#482](https://github.com/nlohmann/json/issues/482),
- [#96](https://github.com/nlohmann/json/issues/96)
