## v-class 知識

#### 應用
- 使用 :class="{'rotate':isTransform}" 進行改變
    - 格式: v-bind:class="{'類別名':布林變數}" (v-bind可簡化成:(冒號)) 
    - 若為true則啟用,false為失效

```html
<div id="app">
  <div class="box" :class="{'rotate':isTransform}"></div>
  <hr>
  <button class="btn btn-outline-primary" @click="isTransform = !isTransform">選轉物件</button>
</div>

<script>
var app = new Vue({
  el: '#app',
  data: {
    isTransform: false
  },
});
</script>

<style>
.box {
  transition: transform .5s;
}
.box.rotate {
  transform: rotate(45deg)
}
</style>
```
