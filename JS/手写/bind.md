Function.prototype.mybind = function(thisArg, ...arg) {
	const MYBIND = Symbol('mybind')
	thisArg.__proto__[MYBIND] = this
	return (...arg2)=>{
		thisArg[MYBIND](...arg, ...arg2)
		delete thisArg.__proto__[MYBIND]
	}
}

function test(name, age, food, drink) {
	console.log(this)
	console.log(`my name is ${name}, and I ${age} years old`)
	console.log(`FavoriteFood：${food}, favoriteDrink：${drink}`)
}

const obj = {
	name: '张三',
	age: 18 
}

test.mybind(obj, obj.name, obj.age)(['a', 'b'], 'c')
test.bind(obj, obj.name, obj.age)(['d', 'e'], 'f')