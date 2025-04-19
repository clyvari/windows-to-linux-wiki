# Windows To Linux Wiki
The aim of this repo is to provide a reference list of documents, tools and configurations to help migrate from Windows to Linux.
It will list common issues and how to fix/work around them as I find them.
This will be mostly tailored for my own usage and workflows, but I will make this document public as maybe it will help others.

# Table of content
1. [Current Issues](#current-issues)
1. [Linux Distribution](#linux-distribution)
2. [Install](#install-debian)

# Current Issues
* I'm hoping to find a bitlocker kind of encryption, that would automatically decrypt the `/home/<user>` parition upon login, rather than a fully encrypted LVM that prompts for a specific password at boot. Read: https://wiki.archlinux.org/title/Trusted_Platform_Module

# Linux Distribution
Debian Stable (12 - Bookworm) has been chosen for now.
The obvious "disadvantage" is that most software present in the Debian repositories is often not the most up-to-date version possible (TODO: debian update policy)
However, I've decided that I do not care:
* In my experience, Debian as always been rock solid, even during major version updates
* The package update policy is a + for me, as it makes things predictable and unlikely to change much (outside of performing a major Debian update)
* I might decide to upgrade to Debian Testing (13 - Trixie), as I'm estimating we are at most 1 year away from this verison being the stable one anyway, and it might make more sense to iron out the issues on this next version rather than on the current (somewhat old) stable version. However, I'm not there yet

# Install Debian
Standard install on an empty drive. No dual boot, all necessary Windows-only software wil lhave to run in a VM.
TODO: detail steps
### Parition scheme
Unencrypted LVM in a single parition (+swap partition)
Simple with some flexibility, and quite like Windows anyway.
Unencrypted LVM + seperate /home parition is probably the best, especially if distro hoping or something.
Also: I'm hoping to find a bitlocker kind of encryption, that would automatically decrypt the `/home/<user>` parition upon login, rather than a fully encrypted LVM that prompts for a specific password at boot. Read: https://wiki.archlinux.org/title/Trusted_Platform_Module

Here is a simple footnote[^1]. With some additional text after it.

[^1]: My reference.

See the docs of [testthat][1] on how to write unit tests.

Links
-----

- [RStudio Devtools](http://www.rstudio.com/products/rpackages/devtools/)
- [Testthat](https://github.com/hadley/testthat)
- [Tests][1]

[1]: http://r-pkgs.had.co.nz/tests.html
