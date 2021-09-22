# 參考書籍與學習資源
- [官方學習資源](https://www.rust-lang.org/learn)
- [Rust Programming Cookbook(2019)](https://www.packtpub.com/product/rust-programming-cookbook/9781789530667) [[GITHUB]](https://github.com/packtpublishing/rust-programming-cookbook)
  - Ch1.Starting Off with Rust 
- [Rust Standard Library Cookbook(2018)](https://www.packtpub.com/product/rust-standard-library-cookbook/9781788623926) [[GITHUB]](https://github.com/packtpublishing/rust-standard-library-cookbook)
- [Rust Cookbook(2017)](https://www.packtpub.com/product/rust-cookbook/9781785880254)  [[GITHUB]](https://github.com/PacktPublishing/Rust-Cookbook)


# Linux開發系統建置 
- [Rust Cookbook(2017)](https://www.packtpub.com/product/rust-cookbook/9781785880254)  [[GITHUB]](https://github.com/PacktPublishing/Rust-Cookbook)
  - ch1.Let us Make System Programming Great Again

- 安裝
  - curl https://sh.rustup.rs -sSf | sh
  - curl -sf https://static.rust-lang.org/rustup.sh | sudo sh
- 移除 Uninstalling Rust
  - rustup self uninstall
- 驗證安裝是否成功
  - rustc --version

### 第一支程式 linux rust 程式
- mkdir /home/ksu/rust_cookbook
- cd /home/ksu/rust_cookbook
- 撰寫程式 gedit sample.rs
- 編譯程式 rustc ./sample.rs
- 執行程式 ./sample
```
// Task : To explain array in rust
// Author : Vigneshwer
// Version : 1.0
// Date : 3 Dec 2016

fn main() {
	
	// Defining an array 
	let rand_array = [1,2,3];

	println!("random array {:?}",rand_array );
	// indexing starts with 0
	println!("random array 1st element {}",rand_array[0] );
	println!("random array length {}",rand_array.len() );
	// last two elements
	println!("random array {:?}",&rand_array[1..3] );
}
```
# windows開發系統建置 

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
```
info: profile set to 'default'
info: default host triple is x86_64-pc-windows-msvc
info: syncing channel updates for 'stable-x86_64-pc-windows-msvc'
info: latest update on 2021-09-09, rust version 1.55.0 (c8dfcfe04 2021-09-06)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
 17.1 MiB /  17.1 MiB (100 %)   9.7 MiB/s in  1s ETA:  0s
info: downloading component 'rust-std'
 20.1 MiB /  20.1 MiB (100 %)   8.8 MiB/s in  2s ETA:  0s
info: downloading component 'rustc'
 37.4 MiB /  75.4 MiB ( 50 %)   4.1 MiB/s in 21m  3s ETA:  9s
info: retrying download for 'https://static.rust-lang.org/dist/2021-09-09/rustc-1.55.0-x86_64-pc-windows-msvc.tar.xz'
 75.4 MiB /  75.4 MiB (100 %)   9.7 MiB/s in  8s ETA:  0s
info: downloading component 'rustfmt'
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 17.1 MiB /  17.1 MiB (100 %) 978.4 KiB/s in 25s ETA:  0s
info: installing component 'rust-std'
 20.1 MiB /  20.1 MiB (100 %)   1.8 MiB/s in 15s ETA:  0s
info: installing component 'rustc'
 75.4 MiB /  75.4 MiB (100 %)   6.6 MiB/s in 15s ETA:  0s
info: installing component 'rustfmt'
info: default toolchain set to 'stable-x86_64-pc-windows-msvc'

  stable-x86_64-pc-windows-msvc installed - rustc 1.55.0 (c8dfcfe04 2021-09-06)


Rust is installed now. Great!

To get started you may need to restart your current shell.
This would reload its PATH environment variable to include
Cargo's bin directory (%USERPROFILE%\.cargo\bin).

Press the Enter key to continue.
```
- 驗證安裝是否成功
  - rustc --version
```
C:\Users\KSU>rustc --version
rustc 1.55.0 (c8dfcfe04 2021-09-06)
```
## 第一支程式
- 建立專案 ==>cargo new hello-world [creates a new Rust project in a hello-world folder]
- cd hello-world
- 撰寫 src/main.rs程式
- 回到根目錄 ==> 看看 Cargo.toml
- 在根目錄執行 cargo run

## 開發工具 
- [visual studio code](https://code.visualstudio.com/)
