## 関数コンポーネント

JSXを関数内で定義する。命名の先頭文字を大文字にする必要がある。
※小文字だと動作をしない。

```.js
function Example() {
  return <h1>こんにちは</h1>
}
```

```
root.render(<Example/>);
```


## コンポーネント

export defaultではインポートするときに，任意の名前をつけて良い。
名前付きエクスポートは，{ Name }で名前つけする必要がある。

## JSX

HTML形式のJSXをBABELでJavascript化する。Javascript（関数）によって、オブジェクト（仮想ROM）に変換され描画する。

## コンポーネントの親子接続

親コンポーネントの変数に`children`を定義してあげる！
↓
タグと閉じタグで囲んで子コンポーネントを挟んで表示することが可能。

## Props

POINT propsの流れは一方通行
POINT propsは読み取り専用

↓
じゃあ，子コンポーネントで保存した値を親コンポーネントで表示したいときはどうしたらいい？どうしてます？
↓
Tobe continue..!

## Reactの色々のはイベントハンドラー

onClick={fn}
→当該要素をクリックした際にfn（関数）で実行する

onChange(onInput)
→Inputから入力した文字をリアルタイムで表示する

onBlur
→Input入力から外れた時に発火

onFocus
→Inputに入力が開始された時に発火

onMouseEnter
→マウスがホバーした時に発火

onMouseLeave
→マウスホバーが外れた時に発火
