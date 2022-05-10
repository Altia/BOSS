# Binary Open Source Software Packages

Welcome! This repository contains pre-built libraries and include files for popular open source packages that are (sometimes) difficult to build and/or too time consuming to build frequently in an automated build environment.  Feel free to use this (AS-IS, at your own risk, etc., etc.), however do be aware of some caveats:

## V8
V8 has been precompiled in such a way to be compatible with other build configurations, configuration that may not be compatible with your environment.  In particular:

* Compiled as a monolithic static library with in Visual Studio 2019 (16.11)
* Compiled with the /MD[d] flag for projects that use dynamic linking
* Built with the following project arguments (args.gn):

````
is_clang = false
use_lld = false
v8_enable_system_instrumentation = false
is_component_build = false
is_debug = [true|false]
enable_iterator_debugging = [true|false]
v8_static_library = true
v8_monolithic = true
v8_enable_test_features = false
v8_use_external_startup_data = false
v8_enable_webassembly = false
v8_enable_i18n_support = false
use_custom_libcxx = false
target_cpu = "x64"
use_goma = false
dcheck_always_on = false
treat_warnings_as_errors = false
symbol_level = [1|0]
````