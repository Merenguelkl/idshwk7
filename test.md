# 入侵检测与数字取证hwk7
---
### 完成人：57117137刘康亮
### 使用工具：Steghide（已上传至github仓库）
### 测试环境：Window10
---
#### 原始图片：test.jpg
#### 隐藏文件：watermark.txt
#### 隐藏内容：
>57117137刘康亮
#### 经过提取的隐藏内容：res.txt
---
#### 隐藏步骤：
1. 将test.jpg和watermark.txt放入/steghide文件夹中
2. 在PowerShell中执行.\steghide.exe embed -cf test.jpg -ef watermark.txt -p 123456
#### 解出隐藏文件步骤：
1. 在PowerShell中执行.\steghide.exe extract -sf test.jpg -xf res.txt -p 123456
2. 结果即为res.txt
#### 该工具优点：
隐写工具会把你的隐藏文件先加密，然后再进行隐写；提取的时候，需要用同一款隐写工具进行提取，并输入同样的密码，才能提取出来。
假如图片文件落入攻击者手中，他必须同时知道2个信息（你用哪款隐写工具，你隐写时设置的密码），才有可能破解出隐含的信息。因此，安全性较高。