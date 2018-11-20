## vue格式與輸出

#### 1.輸出格式:
- 步驟:
    - 1.首先先創建js 的vue物件
    - 2.欲使用id與vue進行綁定
    - 3.必須先宣告變數(something)
    - 4.在HTML文本進行輸出
```javascript
var app = new Vue({
    el: '#app',
    data:{
        something:'這裡是一段話'
    }
})
```
- 創建vue空間
```html
<div id="app">
  {{something}}
</div>
```
- 輸出類型說明
    - 1.text(三種)
        - {{something}}
        - ```<input type="text" v-model="something">```
        - ```<div v-text="something"></div>```
    - 2.html
        - ```<div v-html="something"></div>```




