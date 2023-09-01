## new 运算符的工作流程
1. 创建一个空对象 {}
2. 将创建对象的 __proto__ 指向构造函数的 prototype
3. 改变 this 的指向，将新创建的对象作为 this 的上下文，执行构造函数
4. 返回新对象。如果该函数没有返回对象，则返回 this

function Person1 (name) {
  // 让this指向新对象
  this.name = name
}

// 修改新对象原型链
Person1.prototype.say = function () {
  console.log(`my name is ${this.name}`)
}

// 创建一个新的空对象
const b = new Person1('abc')
b.say() // my name is abc

// 模拟new函数
function myNew (fn, ...args) {
  // 创建一个空对象
  const obj = {}
  // 将该对象的 __proto__ 属性链接到构造函数原型对象
  obj.__proto__ = fn.prototype
  // 将该对象作为 this 上下文调用构造函数并接收返回值
  const res = fn.apply(obj, args)
  // 如果返回值存在并且是引用数据类型，返回构造函数返回值，否则返回创建的对象
  return typeof res === 'object' ? res : obj 
}
const c = myNew(Person1, '123')
c.say() // my name is 123