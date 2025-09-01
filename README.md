tizen-buildroot
===============

#### Scripts preparing buildroot directory from scratch, used for Tizen system

## Prerequisites

Before running the build scripts, ensure you have all required host tools installed.

## Setup Instructions

1. Create "user_path_config.sh" and edit paths there (see "user_path_config.example").

## Build Process

2. To create rootfs and build packages for required architecture:

```bash
./build_pkgs.sh mipsel    
sudo ./prepare_rootfs.sh mipsel    
sudo ./build_rpms.sh mipsel
```
  
You can specify which rpms need to build:
```bash
sudo ./build_rpms.sh mipsel "argp-standalone acl"
```

## Required Host Tools

	help2man, flex, flex-devel, ncurses-devel, texinfo, texinfo-tex, gettext-devel, rcs, transfig, libtool, autoconf, automake, bison, gperf, libgpg-error-devel, libxml2-devel

## Environment Variables

By default temporary build directory will be deleted. To preserve it, set:     
```bash
export DONT_CLEAN=1
```

## Important Notes
  
*You should update macros.tizen-platform for new snapshot of Tizen (copy it from libtzplatform-config-devel-1.0-0.mipsel.rpm).*
              
**Important:** The bash package v.4.3.30 works incorrectly in chroot, so currently using v.4.2.  
