# Arduino IDE によるコーディング
## 関数を様々な引数に対応させる
### 方法1 関数のオーバーロード
```cpp
void loop () {
  int a = sumFunc(10, 20); // a == 30
  int b = sumFunc(10, 20, 30); // b == 60
}

int sumFunc (int x, int y) {
  return x + y;
}

int sumFunc (int x, int y, int z) {
  return x + y + z;
}
```
