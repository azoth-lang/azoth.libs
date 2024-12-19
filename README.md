# Azoth Standard Library

The Azoth Standard Library provides a common foundation for Azoth programs and libraries. It is
composed of multiple packages. However, most applications should import it all by referencing the
`azoth.standard_library` package. The standard library encompasses most of the `azoth.*` namespaces
with the exception of those defined by the compiler (i.e. `azoth.compiler`).

Packages in the standard library include:

* `azoth.standard_library`: includes the complete standard library including platform dependent
  functionality. Imported by most applications.
* `azoth.core`: the core, platform-independent parts of the standard library. Should be imported by
  most library packages unless they really need something in the standard library.
* `azoth.compilation`: attributes used to direct how the compiler handles code.
* `azoth.compiler.intrinsics`: an empty package used to indicate a dependency on the version of
  intrinsic functions and types offered by the compiler.
* `azoth.collections.raw`: provides the raw collection types.

Packages in this repository not included in the standard library:

* `azoth.text.unicode`: provides advanced Unicode functionality that requires additional lookup
  tables and may need to be updated with the Unicode standard more frequently than the standard
  library.

Packages of note that are not in this repository:

* `azoth.compiler.toolset`: used to force the usage of a particular version of the compiler when
  compiling the source code of a package.
