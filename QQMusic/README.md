## 前言

这个库是专门用于解密QQ音乐加密音频

这里感谢: [https://github.com/Presburger/qmc-decoder](https://github.com/Presburger/qmc-decoder) 大佬的解密算法，由于python处理的硬伤，处理效率低下，故使用C++封装了个python库供调用以解决该问题

如果对python的实现过程感兴趣可参考: [https://github.com/rizhiyi/QQMusicDecoder/blob/master/src/decoder.py](https://github.com/rizhiyi/QQMusicDecoder/blob/master/src/decoder.py)

## 功能说明

该库定义了一个函数 **decrypt**，用于负责解密文件，且只能对单个文件做解密，因为传参要注意

使用方法

```python
from QQMusicDecrypt import decrypt
MusicFile = "/Users/rizhiyi/github/MusicDecoder/music/张宇-趁早.qmcflac"
CovertTime = decrypt(MusicFile)
# 单位秒
print(CovertTime)
```

## 返回信息

1. 正常返回结果为解密耗时，单位：秒
2. 异常返回为：[-6 : -1]

- -1：failed to read file
- -2：file seek failed
- -3：create buffer error
- -4：file read error
- -5：failed to write file
- -6：write file error

## TODO

- [ ] 支持直接解密指定目录文件

