## TodoList 練習

#### 實現基本結構
  - 建立 資料陣列(todos) 與 暫時資料變數(newtodo)
  - 在 input 使用 v-model 得到使用者輸入字串 
  - 在列表使用 v-for 處理列表資料
  - 在 li標籤 建立 v-for循環結構
- 實現增加資料   
  - 增加 methods addTodo 用來增加資料
  - 將 addTodo 放入 button(@click="addTodo") 與 input( @keyup.enter) 方便加入列表資料
  - 將 {{item.title}} 放入label標籤內顯示資料名稱
  - 將 :for="item.id" 與 :id="item.id" 放入label 與 input 方便辨識各個資料
- 實現刪除資料
  - 建立 removeTodo 方法 來刪除列表資料
  - 在 v-for 裡面增加 key => v-for="(item,key) in todos"
  - 在下面 button 加入 removeTodo 方法並傳入 key 指定刪除此資料
- 實現刪除線
  - 增加 css
  
    ```css
	<style>
	.completed {
		text-decoration: line-through;
	}
	</style>
    ```
  - 於input checkbox內增加 v-model="item.completed"(當按下時變為true)
  - 於label 增加 :class="{'completed':item.completed}" 來進行切換
```html

```
