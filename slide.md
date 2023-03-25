---
transition: "slide"
title: "検証ツールを使ってコードに触れてみよう"
---

検証ツールを使ってコードに触れてみよう

<div style="display:flex;justify-content:space-evenly;align-items:center;background:lightgray;">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Google_Chrome_icon_%28February_2022%29.svg/2048px-Google_Chrome_icon_%28February_2022%29.svg.png" alt="" style="height:100px;">
<img src="https://kanda-it-school-kensyu.com/wp-content/uploads/html5.png" alt="" style="height:100px;">
<img src="https://kanda-it-school-kensyu.com/wp-content/uploads/javascript.png" alt="" style="height:100px;">
</div>

---

## 自己紹介

--

```json
{
  "name": "大杉太郎",
  "nickname": ["たろさん", "たろ先生"],
  "birth": 1987,
  "place": ["茨城県", "北海道", "東京都", "福岡県"],
  "work": ["講師", "エンジニア（Laravel メイン）"],
  "skills": [
    "JavaScript",
    "TypeScript",
    "React",
    "PHP",
    "Laravel",
    "Deno",
    "Fresh"
  ],
  "like": ["📚", "✈️ 🚃 🚌", "🚮", "🥃🍺🍷", "Rust"],
  "twitter": "@taro_osg"
}
```

--

```txt
                  ＿人人人人人人人人人人人人人人人＿
                  ＞　開発はたのしい！！　＜
                  ￣Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y^Y￣
```

---

## もくじ

--

- 本講座の狙い
- Web アプリケーションとは
- Web アプリケーションの動く仕組み
- 検証ツールとその使い方
- Web サイトをハック！1（HTML）
- Web サイトをハック！2（JS）
- まとめ

---

## 本講座の狙い

--

- Web アプリの開発に興味を持つ．

- 検証ツールで HTML と JavaScript を体験する．

- あらゆる機能を実現できることを知る．

---

## Web アプリケーションとは

--

- Web アプリケーションはインターネットを通じて動作するプログラム．

- 「サーバ」と「クライアント」で構成される．

--

サーバ

- インターネット上の大きなコンピュータ
- データやプログラムを保管
- クライアントからのリクエストに応じて情報を提供

--

クライアント

- ユーザが使うコンピュータやスマートフォン
- サーバにアクセスし情報をリクエスト
- サーバから受け取った情報をもとに Web アプリケーションの画面を表示・操作

---

## Web アプリケーションの仕組み

--

1. ブラウザに URL を入力する．
2. サーバは Web サイトの HTML，CSS，JavaScript のコードをブラウザに送信する．
3. ブラウザは受け取ったコードを読み，画面に情報を表示する．

--

```txt
      クライアント               サーバ
          |                      |
          |-----1.リクエスト------>|
          |                      |
          |<---2.データ/プログラム--|
          |                      |
          |------3.表示/操作-------|
          |                      |
```

--

---

## 検証ツールとその使い方

--

- 検証ツールは，ブラウザに組み込まれている開発者向けのツールである．

- HTML，CSS，JavaScript をリアルタイムで編集・デバッグできる．

- 画面上で右クリックして「検証」！

--

早速触ってみましょう！

---

## Web サイトをハック！1（HTML）

--

1. 検証ツールを開く
2. 「Elements」タブを選択
3. HTML を書き換えてみよう！

---

## Web サイトをハック！2（JS）

--

1. 検証ツールを開く
2. 「Console」タブを選択
3. コードを貼り付けて実行してみよう！

--

処理を書いたコード

```js
function randomColor() {
  return "#" + Math.floor(Math.random() * 16777215).toString(16);
}

function randomFontSize() {
  return Math.floor(Math.random() * (56 - 10 + 1)) + 10 + "px";
}

function changeTextProperties(className, index = 0) {
  const elements = document.getElementsByClassName(className);
  if (elements.length > 0) {
    if (index < elements.length) {
      const element = elements[index];
      element.style.setProperty("color", randomColor(), "important");
      element.style.setProperty("font-size", randomFontSize(), "important");
      changeTextProperties(className, index + 1);
    } else {
      setTimeout(() => changeTextProperties(className), 200);
    }
  } else {
    console.log("No elements with the specified class found");
  }
}
```

--

実行するコード

```js
changeTextProperties("top-catch-01");
changeTextProperties("top-catch-02");
changeTextProperties("top-catch-03");
changeTextProperties("top-catch-04");
```

---

## まとめ

--

- Web アプリケーションはいいぞ

- 検証ツール使ってみよう

- どんなことができるかイメージしてみよう
