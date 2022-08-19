# package

## パッケージとクレート

- クレート(crate)は木箱の意味
- クレートはバイナリかライブラリのどちらかです
- クレートルート(crate root) とは、Rust コンパイラの開始点となり、クレートのルートモジュールを作るソースファイルのことです
- パッケージはある機能群を提供する１つ以上のクレートです
- パッケージは Cargo.toml という、それらのクレートをどのようにビルドするかを説明するファイルを持っている
- パッケージが何を持ってよいかはいくつかのルールで決まっています
  - パッケージは 0 個か 1 個のライブラリクレートを持ってないといけません
  - バイナリクレートはいくらでも持ってよい
  - 少なくとも（ライブラリでもバイナリでもよいが）一つのクレートを持ってないといけない
- cargo new で作成される src/main.rs がパッケージと同じ名前を持つバイナリクレートのクレートルート
- src/lib.rs が含まれていたら、パッケージにはパッケージと同じ名前の名前のライブラリクレートが含まれており、src/lib.rs がそのクレートルートなのだと判断する
- cargo はクレートルートファイルを rustc に私、ライブラリやバイナリをビルドする
- src/bin/... を作ると、それぞれのファイルが別々のバイナリクレートになります