# crate-based&unikernel 方式构造定制操作系统内核

## 联系人 

- 微信id：chyyuu  ，limingth
- email：yuchen AT tsinghua.edu.cn ，limingth AT gmail.com

欢迎感兴趣做下面题目的朋友，联系我们，我们会定期组织自学习和讨论组件化内核设计与实现。

## 模块（已有&需要改进以便于OS组合）

### 文件系统
- easyfs
- fatfs

### netstack
- lose-net-stack 已经实现了 `udp`等
- smoltcp

### 基础图形库
- embedded-graphics (2D graphics library)

### 存储设备驱动
- virtio-blk
- nvme

### 网络设备驱动
- virtio-net
- e1000

### 人机交互设备驱动
- virtio-input（键盘/鼠标）
- virtio-gpu（图形显示）

### 硬件平台设备驱动
- pci

## OS或Hypervisor（已有&需要改进以便于OS组合）
- rcore-tutorial-v3
- rcore-tutorial-in-single-workspace
- aceros
- Rust-for-Linux
- RVM


## 可选择的题目

### 改进组合已有crates

- （入门）改进virtio-drivers crates，支持virtio协议的各种虚拟外设/功能模块
- （入门）把新的crates组合入rcore-tutorial-v3 或 rcore-tutorial-in-single-workspace
- （中级）把已有crate组合入新的OS中，如aceros 
- （高级）把已有crate组合入新的OS中，如Rust-for-Linux

### 文件系统类题目

- （中级）log xv6fs文件系统
- （高级）ext2文件系统


### 网络类题目

- lose-net-stack 已经实现了 `udp`等，可以对 `lose-net-stack` 进行扩展

- （中级）添加 `lose-net-stack` `tcp` 支持
- （高级）添加 `lose-net-stack` `ipv6` 支持
- （中级）添加 `lose-net-stack` `icmp` 支持

或者基于 `lose-net-stack` 编写相关的用例.（也可以使用 `smoltcp`）

- （中级）基于 `lose-net-stack` 的 `dns` `client`(`udp` 协议)
- （中级）基于 `lose-net-stack` 的 `ntp` `client`(`udp` 协议 网络时间协议，可以通过网络同步操作系统时间，可以补全很多个人编写的 `os` 时间不准或者不支持的问题。)

### UI类题目 

基于 `virtio-gpu` 在rcore-tutorial等

- （中级）利用字库显示文字(unicode)
    - `bmp` 文件的解析和显示
    - `ico` 文件的解析和显示
    - `jpg` 文件的解析和显示
    - `png` 文件的解析和显示

- （高级）在有对图片的和字库的支持下，可以再结合 `virtio-input` 实现鼠标的移动和键盘输入的显示。


### 设备驱动类题目
- （初级）支持virtio协议的各种虚拟外设/功能模块
- （中级）各种Qemu中模拟设备的驱动程序crate

### 操作系统类题目
- （初级）扩展/改进rcore-tutorial-v3，支持各种内核crates
- （初级）扩展/改进rcore-tutorial-in-single-workspace，支持各种内核crates
- （中级）扩展arceos等，形成unikernel形态，支持Linux系统调用和Linux应用程序。
- （高级）设计实现TPU/GPU/APU driver crate on rcore-tutorial..Rust for Linux,可运行在RISC-V or ARM开发板上
- （高级）扩展 Rust for Linux，更好地支持跨OS的内核相关crates
- （高级）扩展 Rust for Linux on RISC-V 32/64
- （高级）扩展RVM，支持可调度/多核支持的Hypervisor，可运行在ARM上
- （高级）移植各种OS/Hypervisor在x86-64\RISC-V64/AARCH64\LoongArch上