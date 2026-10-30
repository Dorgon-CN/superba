# dist 分支：Ubuntu 20.04 自编译二进制

本分支存放 Superba v0.1.1-alpha.12 在 **Ubuntu 20.04.6 (x86_64, glibc 2.31)** 上
从源码编译的发布包，供其他 Ubuntu 20.04+ 机器直接使用。
源码与官方 [krill-lab/superba](https://github.com/krill-lab/superba) v0.1.1-alpha.12
完全一致（同一提交），按 Apache-2.0 / MIT 双许可证分发。

## 在新机器上安装

```bash
wget https://github.com/Dorgon-CN/superba/raw/dist/superba-0.1.1-alpha.12-ubuntu20.04-x86_64.tar.gz
tar xzf superba-0.1.1-alpha.12-ubuntu20.04-x86_64.tar.gz
cd superba-0.1.1-alpha.12-ubuntu20.04-x86_64
./install.sh
```

安装内容：`superba`（GUI）、`spb`（CLI）、`superba-router` → `~/.local/bin/`，
含应用菜单图标。

## 源码编译方法（20.04）

见官方 README，或：

```bash
sudo apt install -y build-essential pkg-config git libxkbcommon-dev \
  libwayland-dev libxcb-render0-dev libxcb-shape0-dev libxcb-xfixes0-dev libgl1-mesa-dev
rustup default stable   # 需 ≥ 1.98
cargo build --release -p superba-gui -p superba-cli -p superba-router
```
