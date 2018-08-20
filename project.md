# 開発テーマ

- Ruby開発支援ツール（デバッガ、プロファイラ、静的コード解析ツール等）

# プロジェクト名

- gobject-introspection gemのLLVM対応

# プロジェクトの詳細

GObject IntrospectionのRubyバインディングであるgobject-introspection gemの機能拡充を行います。
GObject IntrospectionはCで実装されたライブラリーの言語バインディングを簡単に実装できるようにするライブラリーです。
このライブラリーを使うことで実行時にバインディングを自動生成できます。

### 現在の課題

GObject Introspectionを使ったバインディング開発には以下の課題があります。

- 手書きより遅い
- オーバーヘッドがある
  - 動的な引数の変換
  - libffiを使った関数呼び出し

### 改善案

- RubyのGObject Introspectionのレイヤーで、LLVMのAPIを使う
- GObject IntrospectionのFFIの機能を使わずに直接バインド対象の関数を呼び出す

この機能拡充により手書きと同じくらいの高速な実装になることを目指します。

# プロジェクトの成果物

- 手書きと同じ速さで自動生成のバインディングを実装できるようにする
- 手書きとGObject Introspectionのパフォーマンスを比較した計測結果を用意する
