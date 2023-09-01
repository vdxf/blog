Array.prototype.mySort = function (fn) {
  if (!fn) return 
  for ( let i = 0; i < this.length; i++ ) {
    for (let j = 0; j < this.length - i - 1; j++ ) {
      if (fn(this[j], this[j + 1]) > 0) {
          [this[j], arr1[j + 1]] = [this[j + 1], this[j]]
      }
    }
  }
}
const arr1 = [2, 5, 1, 12, 23, 54]
arr1.mySort(function (a, b) {
  return a - b
})
console.log(arr1)