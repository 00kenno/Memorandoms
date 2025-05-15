# 情報処理関連

## 鳥科電装開発
### Arduino IDE でのコーディング
- [関数を様々な引数に対応させる](torica/function_parameter.md)
### RP2040
- [rp2040の発振器について](rp2040/oscillator.md)
- 内臓リングオシレーターはシリアル通信など正確な周波数を必要とする動作をするには精度が足りない．
- よって，外部水晶発振器は必須．

## Javascriptに関するメモ
- オブジェクトを返す関数の利用
```javascript
getObject();

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