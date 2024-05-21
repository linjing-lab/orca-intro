# orca-intro

only introduce how to download ORCA and compute with molecule from molecules.txt which I derived with molecular formula and molecular plane structure from Gaussian View.

## download

### openmpi

click [open-mpi/v4.1/openmpi-4.1.1.tar.bz2](https://download.open-mpi.org/release/open-mpi/v4.1/openmpi-4.1.1.tar.bz2) to download file, use the following command to decompression
```text
tar -xjf openmpi-4.1.1.tar.bz2
```
enter the decompressed folder
```text
cd openmpi-4.1.1
```
enter the command to compile
```text
./configure --prefix=/home/orca/openmpi411 --disable-builtin-atomics
```
> replace `orca` with username in Linux system 

enter the command to install
```text
make all install
```
enter the command to enter the current user's bashrc file and enable vi for editing
```text
vi ~/.bashrc
```
press `i` to enter editing mode, and add commands
```text
export PATH=$PATH:/home/orca/openmpi411/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/orca/openmpi411/lib
```
press `Esc` to exit editing then enter `:wq` to save editing, use the command to make the path effective
```text
source ~/.bashrc
```
view current openmpi
```text
mpiexec -V
```
### orca_shared
enter the command to decompress
```text
tar -xJf orca_5_0_4_linux_x86-64_shared_openmpi411.tar.xz
```
> change folder name to orca504

then vi `~/.bashrc` and enter the commands then source
```text
export PATH=$PATH:/home/orca/orca504
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/orca/orca504
alias orca='/home/orca/orca504/orca'
```
> change `orca` to username in Linux system

run ORCA
```text
orca GLEEVEC.inp > GLEEVEC.out
```

## tips
pal8, use 8 processors in computation

opt, enable geometry optimization

functional: B3LYP, wB97X-D3

basis: 6-31g**, cc-pVTZ, def2-TZVPP

miniprint, selects the minimal output

nopop, turns off all populaton analysis

xyz charge(The charge and polarity of molecule) multi(Spin multiplicity)