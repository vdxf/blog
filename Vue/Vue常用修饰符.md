## 修饰符是什么
修饰符是用于限定类型以及类型成员的声明的一种符号
在Vue中，修饰符处理了许多DOM事件的细节，让我们不再需要花大量的时间去处理这些烦恼的事情，而能有更多的精力专注于程序的逻辑处理。

## vue修饰符分为以下几种
1. 表单修饰符
2. 事件修饰符
3. 鼠标事件修饰符
4. 键盘修饰符
5. v-bind修饰符

## 表单修饰符
1. lazy
默认情况下，v-model 会在每次 input 事件后更新数据。你可以添加 lazy 修饰符来改为在每次 change 事件后更新数据
  <input type="text" v-model.lazy="value">
  <p>{{value}}</p>

2. trim
自动去除用户输入内容中两端的空格
  <input type="text" v-model.trim="value">

3. number
让用户输入自动转换为数字
  <input v-model.number="age" type="number">

## 事件修饰符
1. stop
阻止了事件冒泡，相当于调用了event.stopPropagation方法，单击事件将停止传递
  <div @click="shout(2)">
    <button @click.stop="shout(1)">ok</button> 
  </div> 
  //只输出1

2. prevent
阻止了事件的默认行为，相当于调用了event.preventDefault方法，提交事件将不再重新加载页面
  <form @submit.prevent="onSubmit"></form>

3. self
仅当 event.target 是元素本身时才会触发事件处理器
  <div @click.self="doThat"></div>

4. once
绑定了事件以后只能触发一次，第二次就不会触发
  <button @click.once="shout(1)">ok</button>

5. capture
采用事件捕获
  <div @click.capture="shout(1)"> // 1
    obj1
    <div @click.capture="shout(2)"> // 1 2
      obj2
      <div @click="shout(3)"> // 1 2 3
        obj3
        <div @click="shout(4)"> // 1 2 4 3
          obj4
        </div>
      </div>
    </div>
  </div>
 
6. passive
告诉浏览器你不想阻止事件的默认行为

7. native
可以帮助操作组件上的原生事件
  <templace>
    <button> 按钮 </button>
  </templace>

  <Button @click="add()"/> // 这个点击事件会没有效果，因为他触发的是封装button这个组件里面的button，而不是这个封装的组件。

  <Button @click.native="add()"/>

## 鼠标按钮修饰符
left 左键点击
right 右键点击
middle 中键点击

## 键盘修饰符
<input type="text" @keyup.keyCode="shout()">

## v-bind修饰符
1. .sync
能对props进行一个双向绑定
  //父组件
  <comp :myMessage.sync="bar"></comp> 
  //子组件
  this.$emit('update:myMessage',params);