# C/C++

## 関数を様々な引数に対応させる

### 方法1 デフォルト引数の設定
```cpp
int sumFunc (int x, int y, int z = 0)

void loop () {
  int a = sumFunc(10, 20, 30); // a == 60
  int b = sumFunc(10, 20); // b == 30
}

int sumFunc (int x, int y, int z) {
  return x + y + z;
}
```

### 方法2 関数のオーバーロード
```cpp
void loop () {
  int a = sumFunc(10, 20, 30); // a == 60
  int b = sumFunc(10, 20); // b == 30
}

int sumFunc (int x, int y, int z) {
  return x + y + z;
}

int sumFunc (int x, int y) {
  return x + y;
}
```
