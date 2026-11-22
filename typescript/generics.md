# TS：泛型，写一次函数、类型跟着参数走

不写泛型，同一个逻辑要给每种类型复制一份；写了 `any`，类型检查就白做了。

## 最小例子

```ts
function first<T>(arr: T[]): T | undefined {
  return arr[0];
}
const n = first([1, 2, 3]);      // T 被推断成 number，n 是 number | undefined
const s = first(["a", "b"]);     // T 是 string
```

## 约束和默认值

```ts
function longest<T extends { length: number }>(a: T, b: T): T {
  return a.length >= b.length ? a : b;
}
longest("hello", "hi");   // 可以，字符串有 length
// longest(1, 2);         // 报错，number 没有 length

type Box<T = string> = { value: T };
const b: Box = { value: "x" };  // 默认 string，不写就是 Box<string>
```

## 什么时候用

- 工具函数（first、map、pipe）：泛型是刚需。
- 业务代码：类型只有一种就别泛型，过度抽象比重复更难读。
