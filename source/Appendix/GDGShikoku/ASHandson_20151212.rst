Android Studio開発講座
======================

実施日
------

2015/12/12 13:00 - 17:30

お題目
------

Android Studioの便利なところを学ぶ

本日の資料
----------

https://goo.gl/T7awKh


* エラー訂正(Jump to Next Error)

  * ``[F2]`` を押す
  * ``Alt + Enter`` で修正候補をリストアップしてくれる
  * ``Alt + Enter`` は、リテラルで書いている部分を ``string.xml`` に追い出したり

* コード生成(Code generation)

  * ``Alt + Insert``
  * Getter/Setterを一括生成できる
  * インスタンスフィールドの先頭に「m」を付加していると、生成されたGetter/Setterにも「m」が付加された状態で生成されてしまう
  * 防ぎたければ、IDEの設定を「コードスタイルでプレフィックスを除去する」よう変更するか、個別に ``Alt + Enter`` で追加する

* リファクタリング

  * インラインの記述をローカル変数に移動

    * ``Ctrl + Alt + V``
    * 逆に、ローカル変数をメンバー変数にしたい場合は ``Ctrl + Alt + F``

  * 処理をメソッドに切り出す

    * ``Ctrl + Alt + M``

  * 名前を変更

    * ``Shift + F6``
    * Javaソース上のものだけでなく、XMLリソースに設定されているView IdやAndroidManifest.xmlの更新もやってくれる

* ユニットテスト(JUnit 4)

  * テストは、将来の自分のために積み立てておこう
  * junit4以外にも、Support Annotationsとtest Runnerライブラリが必要
  * ``build.gradle`` に ``testInstrumentationRunner`` の設定を入れないと、ライブラリを依存に追加していてもテストが実行されないので注意
  * ユニットテストのソースコードは、すでにプロジェクト生成時に置き場所が掘られている（ ``src/AndroidTest/java`` ）ので、そこにパッケージを一致させて配置すればよい
  * テストの実行は、Gradleの ``connectedAndroidTest`` タスクを実行する　
  * テストは「接続された機器」で実行されるが、1.5からはAndroidに依存しないテストは ``src/test/java`` 以下に配置することができるようになった
  