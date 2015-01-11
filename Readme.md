# SCIndent

![image](image.png)

## 概要
- Schemeのプログラムのインデント変換を行うHTMLです。

- Schemeのプログラムを作成する場合、  
  テキストエディタにインデント(字下げ)を支援する機能がなければ、  
  ユーザが自分で空白を入力する必要があります。  
  本アプリは、この空白の入力を支援するための簡易ツールです。

- 実行例は、以下のページにあります。  
  https://hamayapp.appspot.com/static/scindent.html


## 使い方
- scindent.html を ブラウザで開くと起動します。

- srcのテキストボックスにSchemeのプログラムを貼り付けて、  
  convertボタンをクリックすると、インデント変換を実行します。  
  結果は、outのテキストボックスに表示されます。  
  また、その下には括弧ごとに色分けした結果も表示されます。

- initial indentのテキストボックスに数値を入力すると、  
  変換時の初期インデント量を設定できます。  
  プログラムの途中の部分のみを変換する場合等に利用ください。

- また、colorのチェックボックスのチェックを外すと、  
  色を付けなくなります。

- また、paren noのチェックボックスにチェックを入れると、  
  括弧のとなりに番号を表示します。  
  開き括弧と閉じ括弧の対応を確認したい場合等に利用ください。

- clearボタンをクリックすると、入出力をすべてクリアします。


## 注意事項
1. インデントの単位は、半角スペース2個に固定です。

2. 入力にタブ文字があった場合は、半角スペース4個として計算します。  
   (出力は半角スペースのみになります(リテラル内を除く))

3. 未対応の構文キーワードが存在すると思われます。  
   現在の設定はHTML内の keyword_table に記述されています。

4. 複数行コメント(#|～|#)は、インデントを変更しません。

5. S式コメント(#;)は未対応です。コメント扱いになりません。

6. 以下のリテラルに対応しています。
   ```
     シンボル                     |～|
     文字                         #\a
     文字列                       "～"
     ベクタ                       #(～)
     文字集合(*)                  #[～]
     正規表現(*)                  #/～/ および #/～/i
     ユニフォームベクタ(*)        #u8(～) #s8(～) #f64(～) 等
     デバッグマクロ(*)            #?=
     不完全文字列(*)              #*"～"
     補間文字列(*)                #"～"
     旧補間文字列(*)              #`"～"
     アンインターンドシンボル(*)  #:foo
     (*)はGauche専用(ただし#u8(～)はR7RSに存在)
   ```


## 環境等
- 以下の環境で動作を確認しました。
  - OS
    - Windows 8 (64bit)
  - ブラウザ
    - Chrome v39

## 履歴
- 2015-1-6  v1.00 (初版)
- 2015-1-7  v1.01 一部処理見直し
- 2015-1-7  v1.02 空文字列等の解析ミス修正
- 2015-1-8  v1.03 一部処理見直し
- 2015-1-8  v1.04 一部処理見直し
- 2015-1-8  v1.05 一部処理見直し
- 2015-1-8  v1.06 インデント計算ミス修正(括弧のネストでずれる)
- 2015-1-8  v1.07 一部処理見直し
- 2015-1-9  v1.08 キーワードと色テーブル見直し
- 2015-1-9  v1.09 コメント修正のみ
- 2015-1-9  v1.10 インデント計算ミス修正(開き括弧直後の複数改行でずれる)(クォートでずれる)
- 2015-1-10 v1.11 一部処理見直し
- 2015-1-10 v1.12 インデント計算ミス修正(文字リテラルの記号対応)(#false対応)
- 2015-1-10 v1.13 文字リテラルの記号見直し。デリミタ見直し。波括弧対応
- 2015-1-10 v1.14 クォートリストの角括弧、波括弧対応抜け修正
- 2015-1-10 v1.15 アンインターンドシンボル対応
- 2015-1-11 v1.16 特別扱いのキーワード処理を追加


(2015-1-11)
