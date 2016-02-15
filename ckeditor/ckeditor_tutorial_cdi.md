---
layout: layout
title: CKEditorの使い方 (CDNを使う場合)
---

# CKEditorの使い方 (CDNを使う場合)

## CDNにあるckeditor.jsを参照

CKEditorを使いたいHTMLで、以下の行を追加する
```
<script src="//cdn.ckeditor.com/4.5.7/standard/ckeditor.js"></script>
```

## CKEditorの初期化

- エディタを表示したい位置に、textareaタグをおく
- CKEditor.replace()で初期化する (引数にはtextareaのnameを指定する)

## サンプル

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>CKEditor</title>
        <script src="http://cdn.ckeditor.com/4.5.7/standard/ckeditor.js"></script>
    </head>
    <body>
        <form action="javascript:submit_func();">
          <textarea name="editor1" id="e1"></textarea>
          <input type="submit" value="submit" />
          (Submitボタンで、下のtextareaに編集結果のHTMLを表示します)
        </form>

        <textarea name="editor2" id="e2" cols="100" rows="10"></textarea>

        <script>
            function submit_func() {
              var e1 = document.getElementById('e1');
              e2.value = e1.value;
            }

            CKEDITOR.replace( 'editor1' );
        </script>
    </body>
</html>
```

## サンプルを試してみる

[ckeditor_sample1.html](ckeditor_sample1.html)

## メモ

このサンプルでは、Submitを押したときにjavascriptで処理しているが、
実際にはactionにCGIプログラムなどを指定し、method="POST"でサーバに送信すれば、通常のWEBアプリケーションと同じようにデータを取得できる。
このとき、編集結果はHTMLとして取得できる。
