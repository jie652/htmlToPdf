# htmlToPdf

#### 介绍
前端将html导出pdf，通过遍历dom，解决html被分页节段问题
基于jspdf html2canvas两个库封装的

* 这是借鉴了[qq_251025116](https://blog.csdn.net/qq_24882601?type=blog)大佬的解决方案并优化升级完成的，[原文链接](https://blog.csdn.net/qq_24882601/article/details/123863353?ops_request_misc=&request_id=&biz_id=102&utm_term=html%E8%BD%ACpdf%E5%88%86%E9%A1%B5%E9%97%AE%E9%A2%98%E7%BB%88%E6%9E%81%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88%20k-htmlpdf&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-123863353.nonecase&spm=1018.2226.3001.4187)

# 1.安装依赖
```js
    npm install jspdf html2canvas
```
# 2.使用方法
```js
    import htmlToPdffrom './index.js'
    const suc = () => {
	  message.success('success');
	};
    //记得在需要打印的div上面添加 id
  let dom = document.querySelector('#testPdf');
  let pdf = new htmlToPdf(dom, '测试', 'splitPages', ',', suc, 2);
  pdf.outPutPdfFn('测试');
```
# 3.使用说明
```js
 //splitPages 是需要添加的类名，需要再那个地方分页就在那个地方添加类名 splitPages
    
 //如：
         <SpeciesIdentification class="splitPages" :baseData="baseData" />

        <SpeciesIdentificationSecond class="splitPages" :baseData="baseData" />

        <RepetPic class="splitPages" :baseData="baseData" />

        <RepetTable class="splitPages" :baseData="baseData" />

        <GeneralAnnotation class="splitPages" :baseData="baseData" />
```
# 导出效果对比：
## 分页被截断
![alt text](2.png)
## 分页不被截断
![alt text](1.png)

