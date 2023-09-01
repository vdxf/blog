Array.prototype.myForEach = function (fn) {
    for (let i = 0; i < this.length; i++) {
        fn (this[i], i, this)
    }
}
const arr = [2, 5, 1, 12, 23, 54]
arr.myForEach(function (item, index, array) {
    if ( item % 2 === 0 ) {
        console.log(item)
    }
})