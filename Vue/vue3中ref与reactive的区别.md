## ref
ref是一个函数，它可以将一个普通数据类型（如数字、字符串等）转换为一个响应式对象，从而让这个数据在Vue的响应式系统中被追踪。ref返回一个对象，这个对象有一个.value属性，用来获取和设置这个响应式对象的值

import { ref } from 'vue';
​
const count = ref(0);
console.log(count.value); // 0
​
count.value = 1;
console.log(count.value); // 1

## reactive
reactive是一个函数，它可以将一个普通的Javascript对象转换为一个响应式对象。它会递归地将这个对象的所有属性都转换为响应式对象，从而让整个对象在Vue的响应式系统中被追踪。reactive返回一个Proxy对象，用来代理原始对象的访问和修改

import { reactive } from 'vue';
​
const state = reactive({
  count: 0,
  message: 'hello'
});
​
console.log(state.count); // 0
console.log(state.message); // 'hello'
​
state.count = 1;
state.message = 'world';
​
console.log(state.count); // 1
console.log(state.message); // 'world'

## 区别：
主要区别在于用途和用法。
ref主要用于创建一个单一的响应式数据，而reactive则适用于创建一个复杂的、包含多个属性的响应式数据对象
ref 通常用于包装基本数据类型或非响应式对象，而 reactive 用于创建包含多个属性的响应式对象。
对于 ref，你需要使用 .value 来访问和修改值，而 reactive 直接访问属性。