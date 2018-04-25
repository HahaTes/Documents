Python
=====
****

## 目录

- [流输出](#流输出)


 流输出
------
```Python
import time
import sys

# 类似进度条的输出，只有一行，信息会更新
for i in range(15):
    time.sleep(0.3)
    sys.stdout.write('\r>>%02d/%02d' %(i+1,15))
```
