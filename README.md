Npackd Devbox Package Repository
================================

Packages in this repository are public tools, well known to everybody.
We are using these packages for internal purposes in FirstBeatMedia
Devbox development environment.

After researching other package managers like Chocolatey, CoApp or
0install, we decided to use [Npackd][1] as an application manager for
Windows.

[1]: https://code.google.com/p/windows-package-manager/

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

### Installing packages: Cpuio




