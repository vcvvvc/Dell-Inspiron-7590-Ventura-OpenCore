# Dell-Inspiron-7590-Ventura

- Dell-Inspiron-7590 （4K由于没机器未测试，但理论上没问题）
 
- OC: 0.9.1
 
- macOS Ventura 13.4 (22F66)
 
- 启动第二阶段黑屏已修复
 
- 修复睡眠无法唤醒
  
虽然OC中设置了igfxonln，但是有时还是不能唤醒

```
#https://www.kancloud.cn/q952008898/hei_ping_guo/1117535
查看当前睡眠模式设置，在终端输入以下指令：
pmset -g | grep hibernatemode

你应该在终端中看到类似如下的结果：
$ pmset -g | grep hibernatemodehibernatemode 3

要改变睡眠模式，你又需要使用pmset指令了，还需要加上变量以及相对应的你想要改变的值，所以如果你想要回到老式睡眠模式（从上面可以知道是模式0），输入下列指令：
sudo pmset -a hibernatemode 0
```

- 等待Sonoma 14.5发布

---

## Desktop

![dk](./img/dk.png)

---

## Macos12.5 

https://github.com/6923403/Dell-Inspiron-7590-Monterey
