## TodoList 練習

#### 實現基本結構
- 建立 資料陣列(todos) 與 暫時資料變數(newtodo)
- 在 input 使用 v-model 得到使用者輸入字串 
- 在列表使用 v-for 處理列表資料
- 在 li標籤 建立 v-for循環結構

#### 實現增加資料   
- 增加 methods addTodo 用來增加資料
- 將 addTodo 放入 button(@click="addTodo") 與 input( @keyup.enter) 方便加入列表資料
- 將 {{item.title}} 放入label標籤內顯示資料名稱
- 將 :for="item.id" 與 :id="item.id" 放入label 與 input 方便辨識各個資料
  
#### 實現刪除資料
- 建立 removeTodo 方法 來刪除列表資料
- 在 v-for 裡面增加 key => v-for="(item,key) in todos"
- 在下面 button 加入 removeTodo 方法並傳入 key 指定刪除此資料
  
#### 實現刪除線
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
  
#### 實現過濾資料
- 增加預設全部顯示 : 在 data 內新增 visibility='all'
- 於 全部.進行中.已完成 連結增加 :class="{'active': visibility =='對應的參數'}" @click="visibility='對應的參數'"
- 增加 computed 計算函數 : filteredTodos來回傳顯示的陣列資料

```javascript
computed:{
	filteredTodos(){
		let newTodos = [];
		if(this.visibility == 'all'){
			return this.todos;
		}else if(this.visibility == 'active'){
			//對todos每一項資料進行循環檢測
			this.todos.forEach(function(item){
				if(!item.completed){
					//將未完成資料放入新的陣列
					newTodos.push(item);
				}
			})
			return newTodos;
		}else if(this.visibility == 'completed'){
			//對todos每一項資料進行循環檢測
			this.todos.forEach(function(item){
				if(item.completed){
					//將未完成資料放入新的陣列
					newTodos.push(item);
				}
			})
			return newTodos;
		}
	}
}
```
- 將 v-for 的 todos 改成 filteredTodos 來顯示過濾後資料 即可進行過濾

#### 實現雙擊修改標題功能
- 新增預設變數 cacheTodo,cacheTile 存取更改資料
- 新增修改函數 editTodo 存取使用者欲更改資料 
- 新增雙擊事件 @dblclick="editTodo(item)
- 新增 input輸入框 與 列表資料互相切換顯示 : v-if="item.id !== cacheTodo.id" 與 v-if="item.id === cacheTodo.id"
- 在 input 內增加 esc離開編輯,enter完成編輯 事件
```html

```
