# Javascript

## オブジェクトを返す関数

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
