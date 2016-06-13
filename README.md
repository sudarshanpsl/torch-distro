Self-contained Torch installation for PPC64
============

Install dependencies. Uses `apt-get` on Ubuntu, which might require `sudo`.
```sh
curl -s https://raw.githubusercontent.com/PPC64/torch-distro/ppc64/install-deps | bash
```

Install this repo, which installs the torch distribution, with a lot of nice goodies.
```sh
git clone https://github.com/PPC64/torch-distro.git ~/torch --recursive
cd ~/torch; ./install.sh
```

By default Torch will install LuaJIT 2.1. If you want other options, you can use the command:
```sh
TORCH_LUA_VERSION=LUA51 ./install.sh
TORCH_LUA_VERSION=LUA52 ./install.sh
```

Now, everything should be installed. Either open a new shell, or source your profile via
```sh
. ~/.bashrc  # or: . ~/.zshrc
th -e "print 'I just installed Torch! Yesss.'"
```

Note: If you use a non-standard shell, you'll want to run this command
```sh
./install/bin/torch-activate
```

Tested on Ubuntu 14.04

**NOTE**: If you indend on downloading release directly from GitHub interface, note that it doesn't include submodules.

Please proceed as following to get all the file appropriately:

```
git clone https://github.com/PPC64/torch-distro.git --recursive
cd torch-distro
git checkout <RELEASE_NAME>
```

Or else `./install.sh` will not work
