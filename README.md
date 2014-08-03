Test Kitchen - UTF-8 Drivers Fork
=================================

This is a fork of v1.2.1 of the test-kitchen gem that includes a trivial patch to address https://github.com/test-kitchen/test-kitchen/issues/485

It's particularly useful if you're using the [kitchen-vagrant](https://github.com/test-kitchen/kitchen-vagrant) driver, with Vagrant's [vagrant-lxc](https://github.com/fgrehm/vagrant-lxc) provider, and Vagrant baseboxes from [vagrant-lxc-base-boxes](https://github.com/fgrehm/vagrant-lxc-base-boxes) (which have unicode characters in the baseboxes metadata.json), but it might help in any circumstance where kitchen is calling a driver via `Kitchen::Driver::Base#run_command` and causing character encoding problems by forcing the locale of the driver to be 'C', and by implication causing `Encoding.default_external` and the character set of `File.read()` to be US-ASCII instead of UTF-8.

For documentation about test-kitchen, visit https://github.com/test-kitchen/test-kitchen/
