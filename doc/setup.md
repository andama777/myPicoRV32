# picoRV32を動かしてみる

## RV ツールチェーンのセットアップ
公式のすすめる方法はこちら
https://risc-v-getting-started-guide.readthedocs.io/en/latest/linux-qemu.html#

```
git clone https://github.com/riscv-collab/riscv-gnu-toolchain.git -b 2022.05.15
cd riscv-gnu-toolchain
mkdir build
./configure --prefix=${RISCV}
sudo make linux -j$(nproc)
make install

```
sudo apt-get install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev -y

git clone --recursive https://github.com/riscv/riscv-gnu-toolchain
cd riscv-gnu-toolchain

./configure --prefix=/opt/riscv32 --with-arch=rv32ima --with-abi=ilp32d
sudo make -j 4 linux
export PATH=/opt/riscv32/bin:$PATH
source ~/.bashrc
```


## コンパイル
