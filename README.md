# 情報処理関連のあらゆるメモ

## 鳥科の電装開発に関するメモ

### rp2040の発振器について
- 内臓リングオシレーターはシリアル通信など正確な周波数を必要とする動作をするには精度が足りない．
- よって，外部水晶発振器は必須．

## Javascriptに関するメモ
- オブジェクトを返す関数
```javascript
function getObject () {
  const object = returnObject();

  console.log(object.val);
  console.log(object.text);
}

function returnObject () {
  return {
    val: 20,
    text: "Hello, world!"
  };
}
```