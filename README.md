# rust-playground

Rustの自己学習するぞ

## インストール

参考リンク https://www.rust-lang.org/ja/learn/get-started

rustupでRustインストール（cargoも一緒にインストールされる）
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```



バージョン確認

```
$ rustc --version
rustc 1.61.0 (fe5b13d68 2022-05-18)

$ cargo --version
cargo 1.61.0 (a028ae42f 2022-04-29)
```

## IDE
IntelliJで開発するならRust Pluginがある
https://plugins.jetbrains.com/plugin/8182-rust

## 入門参考リンク

The Rust Programming Language 日本語版  
https://doc.rust-jp.rs/book-ja/

## 用語集

- Cargo（カーゴ）
  - ビルドツール 兼 依存関係管理ツール
- Rustfmt
  - コーディングスタイル

## Rustの基本

### ファイル名はスネークケース

`hello_world.rs`

`main`関数は特別で、常にすべてのRustプログラムで走るさいshのコードになる。


### コンパイラ
Rustプログラムを実行するには、Rustコンパイラを使用する。

```
$ rustc main.rs
```

### ビルド

```
cargo build
```

`target/debug/`にプロジェクト名と同名のバイナリファイルが出力される

実行ファイルを実行してみる

```
$ ./target/debug/rust-playground
```

`cargo build`を初めて実行すると、Cargoは最上位に Cargo.lock というファイルを作成する。
このファイルにはプロジェクト内の依存関係の正確なバージョンを記録していく。

### ビルド + 実行

`cargo run`を使うと、コードのコンパイル、できた実行ファイルの実行までを一つのコマンドで行える。

ファイルが変更されていなければ、単にバイナリを実行するだけ、となる。  
もしソースコードを変更していたら、Cargoは実行前にプロジェクトを再ビルドして、バイナリを実行する。

`cargo check`でコンパイルチェックも行える（実行ファイルは生成しない）

リリースビルドの生成

```
$ cargo build --release
```