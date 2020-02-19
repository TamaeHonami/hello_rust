# Installing rust

## Summary

下記のバージョンをインストールする.  
Install version: `1.40.0`  

## Text

### Install command

下記のコマンドでインストールできる.  

```
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

インストール途中に下記の選択肢が出てくる.  
番号で指定するので、対象の番号を指定してEnterでOK.  

- デフォルトでインストール: 基本これでOK
- カスタムでインストール: インストール先とか変えたい時にこれを選択(設定パス変わるので注意)
- インストールの中止: Rustのインストールをやめる

### Path setting

**下記の`export`設定が入ってなければ追記すること(多分大丈夫)**  
**bash以外は自分で設定が必要っぽい???**  

```
$ vim ~/.bash_profile

export PATH="$HOME/.cargo/bin:$PATH"
```

### Install check

下記でインストールのチェックをする.  

```
$ rustc --version
rustc 1.40.0 (73528e339 2019-12-16)
$ rustup --version
rustup 1.21.1 (7832b2ebe 2019-12-20)
$ cargo --version
cargo 1.40.0 (bc8e4c8be 2019-11-22)
```

バージョンが表示されていれば問題なし.  
**表示されない場合は端末を開き直すか`source`コマンドで設定再読み込みを試す**  

### Extra

`Hello World!!`を表示させる. 
ソース格納用のディレクトリを作成&移動.  

```
$ mkdir /path/to/rust/src
$ cd /path/to/rust/src
```

実行するソースは下記の通り.  

```
$ vim hello.rs

fn main() {
    println!("Hello World!!");
}
```

ソースコードのコンパイル&実行.  

```
$ rustc hello.rs
$ ls
hello		hello.rs
$ ./hello 
Hello World!!
```

下記のようなエラーが出た場合の対処について(**Mac限定**)  

```
error: linking with `cc` failed: exit code: 69

[中略]

          Agreeing to the Xcode/iOS license requires admin privileges, please run “sudo xcodebuild -license” and then retry this command.
          
          
          

error: aborting due to previous error
```

XCodeのライセンス承認が終わってないので、エラー文言にある通りXCodeのライセンス承認を実行する.  

```
$ sudo xcodebuild -license
```

## Reference material
- 公式サイト: https://www.rust-lang.org/tools/install

test
