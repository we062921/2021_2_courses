# 開發系統建置 windows

- [下載安裝檔](https://rustup.rs/)
- 安裝
```
elcome to Rust!

This will download and install the official compiler for the Rust
programming language, and its package manager, Cargo.

Rustup metadata and toolchains will be installed into the Rustup
home directory, located at:

  C:\Users\KSU\.rustup

This can be modified with the RUSTUP_HOME environment variable.

The Cargo home directory located at:

  C:\Users\KSU\.cargo

This can be modified with the CARGO_HOME environment variable.

The cargo, rustc, rustup and other commands will be added to
Cargo's bin directory, located at:

  C:\Users\KSU\.cargo\bin

This path will then be added to your PATH environment variable by
modifying the HKEY_CURRENT_USER/Environment/PATH registry key.

You can uninstall at any time with rustup self uninstall and
these changes will be reverted.

Current installation options:


   default host triple: x86_64-pc-windows-msvc
     default toolchain: stable (default)
               profile: default
  modify PATH variable: yes

1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
```
- 驗證安裝是否成功
  - rustc --version

## 第一支程式
- 建立專案 ==>cargo new hello-world [creates a new Rust project in a hello-world folder]
- cd hello-world
- 撰寫 src/main.rs程式
- 回到根目錄 ==> 看看 Cargo.toml
- 在根目錄執行 cargo run

## 開發工具 
- [visual studio code](https://code.visualstudio.com/)
