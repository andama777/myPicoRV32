# picoRV32を動かしてみる

## RV ツールチェーンのセットアップ
InterFace 2019 12月号 4章を参照

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
