Function.prototype.mycall = function(thisArg, ...arg) {
	const MYCALL = Symbol('mysymbol')
	thisArg.__proto__[MYCALL] = this
	thisArg[MYCALL](...arg)
	delete this.__proto__[MYCALL]
}

function test(name, age) {
	console.log(this)
	console.log(`my name is ${name}, and I ${age} years old`)
}

const obj = {
	name: '张三',
	age: 18 
}

test.mycall(obj, obj.name, obj.age)
test.call(obj, obj.name, obj.age)