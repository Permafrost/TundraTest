# TundraTest ❄

Unit test services for [Tundra], a package of cool services for
[webMethods Integration Server] 7.1 and higher.

## Installation

This project contains the unit test services for the [Tundra]
package, but is not a [webMethods Integration Server] package
itself. Instead, it is intended to be symlinked directly into an
existing installation of the [Tundra] package.

To install, first make sure that:

* Git is [installed](http://git-scm.com/downloads) on your
  Integration Server.
* Your Integration Server has internet access to https://github.com
  (for cloning the repository).
* The [Tundra] package is installed and enabled on your Integration
  Server.

Choose a new directory in which to store this project within your
Integration Server installation directory other than the packages
directory, since this project is not a package.

Then from your Integration Server installation directory clone this
project into your chosen directory, then symlink the unit test
services into the Tundra package:

### Windows

```sh
$ mkdir .\test\packages\
$ git clone https://github.com/Permafrost/TundraTest.git .\test\packages\TundraTest
$ # symlink the test services into the Tundra package
$ mklink /d .\packages\Tundra\ns\tundra\support\test .\test\packages\TundraTest\ns\tundra\support\test
```
### *nix

```sh
$ mkdir ./test/packages/
$ git clone https://github.com/Permafrost/TundraTest.git ./test/packages/TundraTest
$ ln -s ./test/packages/TundraTest/ns/tundra/support/test  ./packages/Tundra/ns/tundra/support/test
```

Then reload the [Tundra] package in your Integration Server to complete the installation.

## Upgrading

From your Integration Server installation:

```sh
$ cd ./test/packages/TundraTest/
$ git pull
```

Then reload the [Tundra] package in your Integration Server to complete the upgrade.

## Testing

To execute the unit test suite either:

* Run the `Tundra/tundra:test($package = "Tundra")` service directly, or
* Visit the <http://server:port/invoke/tundra/test?$package=Tundra> web page.

## Contributions

1. Check out the latest master to make sure the feature hasn't been
   implemented or the bug hasn't been fixed yet.
2. Check out the issue tracker to make sure someone already hasn't
   requested it and/or contributed it.
3. Fork the project.
4. Start a feature/bugfix branch.
5. Commit and push until you are happy with your contribution.

[Tundra]: <https://github.com/Permafrost/Tundra>
[webMethods Integration Server]: <http://www.softwareag.com/corporate/products/wm/integration/products/ai/overview/default.asp>
