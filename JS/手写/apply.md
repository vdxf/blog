Function.prototype.myapply= function(thisArg, arg) {
	const MYAPPLY= Symbol('myapply')
	thisArg.__proto__[MYAPPLY] = this
	thisArg[MYAPPLY](...arg)
	delete this.__proto__[MYAPPLY]
}

function test(name, age) {
	console.log(this)
	console.log(`my name is ${name}, and I ${age} years old`)
}

const obj = {
	name: '张三',
	age: 18 
}

test.myapply(obj, [obj.name, obj.age])
test.myapply(obj, [obj.name, obj.age])
