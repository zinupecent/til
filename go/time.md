# Go：time 包基础

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	now := time.Now()
	fmt.Println(now.Format("2006-01-02 15:04:05"))

	t := time.Date(2026, 11, 15, 10, 0, 0, 0, time.Local)
	fmt.Println(t.Weekday())  // Sunday
}
```

- Go 的时间格式是"参考时间" `2006-01-02 15:04:05`，照着这个样子写。
- `time.Now()` 拿当前时间，`time.Date` 拼指定时间。
- 算时间差用 `t2.Sub(t1)`，得到 `Duration`，能直接和 `time.Second` 比大小。
