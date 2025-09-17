# test-capture-html

网页截图的三种方式对比
- html2canvas
- snapdom
- html-to-image

同样的方式导出结果：
```
长图：
html2canvas 生成图片耗时：377ms
snapdom 生成图片耗时：1771ms
html2img 生成图片耗时：297ms

小图：
html2canvas 生成图片耗时：273ms
snapdom 生成图片耗时：547ms
html2img 生成图片耗时：60ms
```
