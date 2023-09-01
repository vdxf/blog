Array.prototype.myFind = function ( fn ) {
  for (let i = 0; i < this.length; i++) {
    let isFlag = fn ( this[i], i, this )
    if (isFlag) return this[i]
  }
}
const findResult = arr.myFind( function (item, index, array) {
  return item % 2 === 0
} )
console.log(findResult)