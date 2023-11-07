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

## 繰り返し生成される仮想DOMについて

* ある親要素の子要素同士で，Keyが一意になるようにする。
* 配列のINDEXはKeyに指定しない方がいい。表示の際に，保持する値が紐付いてしまうので..

## createPortalって？

* 子要素（A）の子要素を、親要素のDOMに子要素（B）として生成できる関数。
* createPortal（ 生成したコンポーネント, 生成する箇所のDOM )

オレオレスニペット

```js
import createPortal from "react-dom";

// ..省略..

const [TF, setTF] = useState(false);

<button onClick={()=>setTF(true)} disable={TF}></button>

{TF && (createPortal(
  <Modal></Modal>,
  document.querySelector(".container")
))}

```

これで親でも子でも孫でもどこでも，classNameが存在する場所にコンポーネントを生成できる！

## forwardRefとは？

forwardRefとは，コンポーネントをラップ化し，引数に指定した子コンポーネントが，親からrefを受け取れるようになる関数。
親のアクションによって影響を受けるアクションを記述できる。
ただ、子コンポーネントで値（今回の場合はDOM要素）を格納できてしまう。ので，
親子の依存関係が強くなり、データの流れが子→親への流れを作ってしまうのであまり良くはない。


## useImperativeHandleでは

親側で自由に操作できすぎてしまうのでハンドルできるように、Refを置き換えて使用用途を子要素側で絞ることができる。

## 関数型プログラミングについて

Reactでは基本的に関数型プログラミング使っていこう。

* 用意されている関数を屈指して、行数の少ないコードを目指そう！ってことやねん。
* 定義する関数は純粋関数で定義すること。（極力ね!）
* 絶対やってはあかんのは、グローバルな偏差を多用すること。それがミュータブル（変更できる）であればあるほど。

関数の中ではイミュータビリティーを保持して実装すること。

関数内でもルールは3つ（+1）準(？)純粋関数を目指そう！

* 関数外で定義した変数を使用しない。
* 関数外に影響を及ぼさない。
* 引数で渡された値を変更しない。
（ * 決まった値→決まった値を返すこと。厳密には親コンポーネントでは実現できないのでアレ。）

## 重要なReactの関数

* react
useState, useReducer
useRef, forwardRef, useImperativeHandle

* react-dom
createPortal

## useReducerって何？

useStateの上位互換。

### useReducer

* 第一引数:reducer関数
* 第二引数:stateの初期値

### reducer関数

* 第一引数:state（前の）
* 第二引数:dispatchから受け取った引数

## useContextってなんなん？

親から子へ，子から孫へというデータ（プロップス）を渡す際に，処理を簡略化できる。

createContext

## useEffectって美味しいの？


## useMemo

Reactにおけるパフォーマンス改善に用いる


## useCallback

Reactにおけるパフォーマンス改善に用いる

## Custom Hooksって自分で関数作れる感じか

(システムによって独自関数はでてきそうだね．)


## Reduxをざっくり

vueにもおなじような機能あってけど，ざっくりフロントエンドのDB？マスタ？的なイメージ．

## パフォーマンス最適化

→実務に活かせるものがあるかもね．

## Rest APIもみたい

## Next.jsでアプリ作ろう！


