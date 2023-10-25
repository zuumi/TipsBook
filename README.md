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
