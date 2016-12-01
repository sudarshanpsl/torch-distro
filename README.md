Self-contained Torch installation for PPC64  
============

#### Please refer to the [Torch installation guide](http://torch.ch/docs/getting-started.html#_) for details on how to make a fresh install of Torch.


## Repo content
#### Dependencies
Globally installed dependencies can be installed via:
```bash
bash install-deps
```

#### Lua and Torch
The self-contained Lua and Torch installations are performed via:
```bash
./install.sh
```

By default Torch will install LuaJIT 2.1. If you want other options, you can use the command:
```bash
# If a different version was installed, used ./clean.sh to clean it
TORCH_LUA_VERSION=LUA51 ./install.sh
TORCH_LUA_VERSION=LUA52 ./install.sh
```

## Update
To update your already installed distro to the latest `master` branch of `torch/distro` simply run:
```bash
./update.sh
```

## Cleaning
To remove all the temporary compilation files you can run:
```bash
./clean.sh
```

To remove the installation run:
```bash
# Warning: this will remove your current installation
rm -rf ./install
```
You may also want to remove the `torch-activate` entry from your shell start-up script (`~/.bashrc` or `~/.profile`).

## Test
You can test that all libraries are installed properly by running:
```bash
./test.sh
```

Tested on Ubuntu 16.04

**NOTE**: If you intend on downloading release directly from GitHub interface, note that it doesn't include submodules.

Please proceed as following to get all the file appropriately:

```
git clone https://github.com/PPC64/torch-distro.git --recursive
cd torch-distro
git checkout <RELEASE_NAME>
```

Otherwise `./install.sh` will not work
