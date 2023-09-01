## Array.prototype.sort()
const arr = [5, 12, 3, 18, -6, -1, 0]
arr.sort() // [-1, -6, 0, 12, 18, 3, 5]

//升序
arr.sort((a, b) => a - b) // [-6, -1, 0, 3, 5, 12, 18]
//降序
arr.sort((a, b) => b - a) // [18, 12, 5, 3, 0, -1, -6]

## Array.prototype.reverse()
反转数组中的元素

const arr = [1, 2, 3]
arr.reverse() // [3, 2, 1]
console.log(arr) // [3, 2, 1]

## 简单选择排序
平均时间复杂度 O(n²) 最好情况 O(n²) 最坏情况 O(n²) 空间复杂度 O(1) 不稳定排序

let arr = [1, 7, 9, 8, 3, 2, 6, 0, 5, 4];
let n = arr.length;
for(let i = 0; i < n; i++){
    let minIndex = i;
    for(let k = i + 1; k < n; k++){
        if(arr[k] < arr[minIndex]) minIndex = k;
    }
    [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
}
console.log(arr) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

## 冒泡排序 
平均时间复杂度 O(n²) 最好情况 O(n) 最坏情况 O(n²) 空间复杂度 O(1) 稳定排序

const arr = [1, 7, 9, 8, 3, 2, 6, 0, 5, 4];
const n = arr.length;
for ( let i = 0; i < n; i++ ) {
  for (let j = 0; j < n - i - 1; j++ ) {
    if (arr[j] > arr[j + 1]) {
      [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]
    }
  }
}
console.log(arr); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

## 快速排序
平均时间复杂度 O(nlogn) 最好情况 O(nlogn) 最坏情况 O(n²) 空间复杂度 O(logn) 不稳定排序

let arr = [5, 12, 45, 3, -9, 43, 11, 0, -22];
var sortArray = function (arr) {
    shuffle(arr)
    return QuickSort(arr, 0, arr.length - 1)
}
var QuickSort = (arr, p, q) => {
    if (p >= q) return arr
    let m = partition(arr, p, q)
    QuickSort(arr, p, m - 1)
    QuickSort(arr, m + 1, q)
    return arr
}
var partition = (arr, p, q) => {
    let x = arr[p]
    let i = p + 1
    let j = q
    while (i < j) {
        while (i < j && arr[i] <= x) i++
        while (i < j && arr[j] >= x) j--
        swap(arr, i, j)
    }
    if (arr[j] >= x) j--
    swap(arr, p, j)
    return j
}
var swap = (arr, i, j) => {
    let temp = arr[i]
    arr[i] = arr[j]
    arr[j] = temp
}
var randOne = (n, m, shuffledArr) => {
    let num = n + Math.floor(Math.random() * (m - n + 1));
    if (shuffledArr[num] === undefined) { 
        shuffledArr[num] = true;
        return num;
    } else { 
        while (shuffledArr[num] !== undefined) {
            num++;
            if (num > m) num = n;
        }
        shuffledArr[num] = true;
        return num;
    }
}
var shuffle = (arr) => {
    let n = arr.length;
    let nn = [];
    let shuffledArr = {};
    for (let i = 0; i < n; i++) {
        let randIndex = randOne(0, n - 1, shuffledArr);
        nn.push(arr[randIndex]);
    }
    return nn;
}
console.log(sortArray(arr)); // [-22, -9, 0, 3, 5, 11, 12, 43, 45]

## 归并排序
平均时间复杂度 O(nlogn) 最好情况 O(nlogn) 最坏情况 O(nlogn) 空间复杂度 O(n) 稳定排序

function merger(arr, start, mid, end, auxArr){
    var startStroage = start;
    var midRight = mid + 1;
    var count = 0;
    while(start <= mid && midRight <= end){
        if(arr[start] <= arr[midRight]) auxArr[count++] = arr[start++];
        else auxArr[count++] = arr[midRight++];
    }
    while(start<=mid) auxArr[count++] = arr[start++];
    while(midRight<=end) auxArr[count++] = arr[midRight++];
    for(let i=0; i<count; ++i) arr[i+startStroage] = auxArr[i];
    return arr;
}

function mergeSort(arr, start, end, auxArr) {
  if(start<end) {
    var mid = Math.floor((start+end)/2);
    var left = mergeSort(arr, start, mid, auxArr); 
    var right = mergeSort(arr, mid+1, end, auxArr); 
    arr = merger(arr, start, mid, end, auxArr);  
  }
  return arr;
}

var arr = [1, 7, 9, 8, 3, 2, 6, 0, 5, 4];
arr = mergeSort(arr, 0, arr.length-1, []);
console.log(arr); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
