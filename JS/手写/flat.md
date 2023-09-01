Array.prototype.myflat = function (n) {
  let res = []
  for (let i = 0; i < this.length; i++) {
    if (Array.isArray(this[i]) && n > 0) {
      res = res.concat(this[i].myflat(n - 1))
    } else {
      res.push(this[i])
    }
  }
  return res
}
let arr = [1, 2, [3, 4, [5, [6]]]]
console.log(arr.myflat(1)) // [1, 2, 3, 4, [5, [6]]]