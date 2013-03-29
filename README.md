Npackd Devbox Package Repository
================================

Packages in this repository are public tools, well known to everybody.
We are using these packages for internal purposes in FirstBeatMedia
Devbox development environment.

After researching other package managers like [Chocolatey][choco], CoApp or
0install, we decided to use [Npackd][npackd] as an application manager for
Windows.

## Install Npackd package manager

Install command line package manager by typing: 

<!-- msiexec.exe /qb- /norestart /i http://bit.ly/npackdcl-1_16_4 APPDIR=C:\NpackdCL && SET PATH=C:\NpackdCL;%PATH% -->

    msiexec.exe /qb- /i http://bit.ly/npackdcl-1_16_4

If you are so desperate for GUI version, you can install it also. But
for now, we will skip it. More information can be found on [Npackd wiki page][1].

We must __add our repository__ that contains description of our specific
packages:

    npackdcl add-repo --url=https://raw.github.com/michfield/devbox-npackd/master/devbox64.xml

[1]: https://code.google.com/p/windows-package-manager/wiki/CommandLineInstallation

## Basic package manipulation

I will write an examples for package __CpuIO__ whose full name is
`net.sourceforge.gnuwin32.Cpuid` and short-name is `Cpuid`.

### Installing packages

    npackdcl add --package=Cpuid

### Search for package, installed or not

    npackdcl search --query=cpuid

### Check if a package is installed

    npackdcl search --status=installed --query=net.sourceforge.gnuwin32.Cpuid

Well, this one didn't show the results I expected. With this query, it
didn't find any package?

### Uninstall a package

    npackdcl remove --package=net.sourceforge.gnuwin32.Cpuid --version=3.3.1

This one also didn't remove a packege. So I tried with different
approaches.

I couldn't remove package, and I'm not sure why. Found a package by
typing:

    npackdcl search --status=installed | grep -i cpuid

But I can't remove it! And this leads me to conclusion.

## Conclusion

For now, forget about Npackd. I just had too much problems for such a
short time. I liked it more than [Chocolatey][choco], but it simply does
not work - for now.

[choco]: http://chocolatey.org/
[npackd]: https://code.google.com/p/windows-package-manager/

## A word of warning!

One very annoying thing action has been done.

Npackd created a subdirectory named `.Npackd` in each one folder of
installed programs on my computer. That means hundreds of directories
named `.Npackd` in my `Program Files`. Big fail.

I'm not sure when this happened. Maybe command `detect` or similar.
Anyway, I really don't like it.

