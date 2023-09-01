## ref
作用：用于创建一个响应式引用，通常用于包装基本数据类型或非响应式对象，使其成为响应式。
用法：用于声明一个引用，通过 .value 访问引用的值，如果该值发生变化，Vue会自动追踪和更新相关的界面。

<template>
  <div>{{ count }}</div>
  <button @click="increment">增加</button>
</template>

import { ref } from 'vue'

const count = ref(0)
// 在方法中修改 count
const increment = () => {
  count.value++
}

## reactive
作用：用于创建一个包含响应式数据的对象，可以将多个属性包装成一个响应式对象。
用法：用于声明一个响应式对象，Vue会自动追踪对象属性的变化，并在界面中更新。

<template>
  <div>{{ user.name }} - {{ user.age }} 岁</div>
</template>

import { reactive } from 'vue'

const user = reactive({
  name: 'John',
  age: 30
})
// 在方法中修改 user
const changeUser = () => {
  user.name = 'Alice'
  user.age = 25
}

## 区别：
主要区别在于用途和用法。
ref 通常用于包装基本数据类型或非响应式对象，而 reactive 用于创建包含多个属性的响应式对象。
对于 ref，你需要使用 .value 来访问和修改值，而 reactive 直接访问属性。
ref 通常用于包装单一的变量，而 reactive 用于创建复杂的响应式数据结构。
在选择使用 ref 还是 reactive 时，取决于需求和数据结构的复杂性。如果只需要包装一个单一的变量，使用 ref 即可。如果需要处理一个包含多个属性的对象或数据结构，可以使用 reactive。
