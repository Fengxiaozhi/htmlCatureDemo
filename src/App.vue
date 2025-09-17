<script setup>
import * as htmlToImage from 'html-to-image';
import { snapdom } from '@zumer/snapdom';
import html2canvas from 'html2canvas';
import htmlTpl from './htmlTpl.vue'
import smallHtmlTpl from './smallHtmlTpl.vue'
const captureForHtml2canvas = async () => {
  let time1 = Date.now()
  const el = document.getElementById('captureBody');
  // 把 DOM 节点转成 canvas
  const canvas = await html2canvas(el, {
    backgroundColor: null, // 保持透明背景（可选）
    useCORS: true,         // 允许跨域图片（如果有）
    foreignObjectRendering: true, // 使用foreignObject方式
  });

  let time2 = Date.now()
  // console.log(`html2canvas 生成图片耗时：${time2 - time1}ms`)
  console.log(`html2canvas （foreignObject方式）生成图片耗时：${time2 - time1}ms`)
  // 转成 base64 PNG
  const dataUrl = canvas.toDataURL("image/png");

  // 生成下载链接并触发
  const link = document.createElement("a");
  link.href = dataUrl;
  link.download = "captureForHtml2canvas.png";
  link.click();
}
const captureForSnapdom = async () => {
  let time1 = Date.now()
  const el = document.getElementById('captureBody');
  // 方式1
  // const result = await snapdom(el);
  // await result.download({
  //   format: "png", 
  //   filename: "captureForSnapdom.png",
  // })
  // let time2 = Date.now()
  // console.log(`snapdom 生成图片耗时：${time2 - time1}ms`)

  // 方式2
  const canvas = await snapdom.toCanvas(el)
  // 转成 base64 PNG
  let time2 = Date.now()
  console.log(`snapdom 生成图片-canvas耗时：${time2 - time1}ms`)
  const dataUrl = canvas.toDataURL("image/png");
  var link = document.createElement('a');
  link.download = 'captureForSnapdom.png';
  link.href = dataUrl;
  link.click();
}
const captureForHtml2img = () => {
  let time1 = Date.now()
  htmlToImage
  .toCanvas(document.getElementById('captureBody'))
  .then((canvas) => {
    let time2 = Date.now()
    console.log(`html2img 生成图片耗时：${time2 - time1}ms`)
    const dataUrl = canvas.toDataURL("image/png");
    var link = document.createElement('a');
    link.download = 'captureForHtml2img.png';
    link.href = dataUrl;
    link.click();
  });
}

</script>

<template>
  <div class="captureBody">
    <div class="body">
      <!-- <smallHtmlTpl /> -->
      <htmlTpl />
    </div>
    <div class="btns">
      <button @click="captureForHtml2canvas">html2canvas</button>
      <button @click="captureForSnapdom">snapdom</button>
      <button @click="captureForHtml2img">html2img</button>
    </div>
  </div>
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
#app {
  position: relative;
  width: 100%;
  height: 100%;
}
.captureBody {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.body {
  width: 100%;
  height: 70%;
  flex: 1 1 auto;
  overflow-y: auto;
}
.btns {
  height: 100px;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
