forEach()方法会对数组的每个元素执行一次回调函数，没有返回值，仅仅是遍历数组。
arr = [1, 2, 3, 4]
arr.forEach((num) => {
console.log(num * 2) // 2 4 6 8
}) 

map()方法会对数组的每个元素执行一次回调函数，并将回调函数的返回值组成一个新的数组返回，不会修改原数组。
arr = [1, 2, 3, 4]
const newArr = arr.map((num) => {
return num * 2
})
console.log(newArr) // [2, 4, 6, 8]