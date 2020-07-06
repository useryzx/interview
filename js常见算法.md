###### 冒泡排序

```javascript
let arr=[3,2,5,1,2,9,7]
//bubbling  冒泡
function bubbling(arr){
    //第一轮结束后最火一个为最大的
	for(let i=0;i<arr.length-1;i++){
        //i没增加一次，内层循环的次数就减少一次，因为每进行一次大循环，最后的数都是最大的
        for(let j=0;j<arr.length-1-i;j++){
            if(arr[j]>arr[j+1]){
                let mid=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=mid
            }
        }
    }
    console.log(arr)
	
}
bubbling(arr)
```

###### 快速排序

```javascript
var arr = [11, 44, 8118, 8900, 9000, 22, 33, 9900];
// var times=0;
var quickSort=function(arr){ 
	//如果数组长度小于等于1无需判断直接返回即可
	if(arr.length<=1){
		return arr;
	}
	var midIndex=Math.floor(arr.length/2);//取基准点
	var midIndexVal=arr.splice(midIndex,1);//取基准点的值,splice(index,1)函数可以返回数组中被删除的那个数arr[index+1]
    // console.log('中间值'+midIndexVal);
    
	var left=[];//存放比基准点小的数组
	var right=[];//存放比基准点大的数组
	//遍历数组，进行判断分配
	for(var i=0;i<arr.length;i++){
		if(arr[i]<midIndexVal){
			left.push(arr[i]);//比基准点小的放在左边数组
		}
		else{
			right.push(arr[i]);//比基准点大的放在右边数组
		}
		// console.log("第"+(++times)+"次排序后："+arr);
	}
	//递归执行以上操作,对左右两个数组进行操作，直到数组长度为<=1；
	return quickSort(left).concat(midIndexVal,quickSort(right));
};
console.log(quickSort(arr));
```





###### 去重

```javascript
let arr=[3,2,5,1,2,9,7];
function remove(arr){
    let newArr=[];
    for(let i=0;i<arr.length;i++){
        let a=arr.slice(i+1)
        if (a.indexOf(arr[i])==-1) {
           newArr.push(arr[i])
       }
    }
    console.log(newArr)
    
}
remove(arr)
```

###### 重载方法

```javascript
//js中没有重载的方法，用arguments实现
//重载就是同名函数不同方法
function loadMore(){
    if(arguments.length==1){
        alert(arguments[0])
    }
    if(arguments.length==2){
        alert(arguments[0]+arguments[1])
    }
}
loadMore(12);
//输出为12
loadMore(12,3)
//输出为15
```

###### 水仙花数

```javascript
//是一个三位数，每一位的3次幂之和等于它本身
function number() {
        for (var i = 100; i < 1000; i++) {
            // 1.把一个三位数拆分  153
            var g = i % 10; //个位
            var s = (i % 100 - g) / 10; //十位
            var b = (i - i % 100) / 100 //十位
            if (g ** 3 + s ** 3 + b ** 3 == i) {
                console.log(i);

        }
    }
}
number()
```

###### 打点计时器

```javascript
//要求如下:
//1、从 start 到 end（包含 start 和 end），每隔 100 毫秒 console.log 一个数字，每次数字增幅为 1
//2、返回的对象中需要包含一个 cancel 方法，用于停止定时操作

//3、第一个数需要立即输出
function count(start, end) {
        console.log(start)
        var timer = setInterval(() => {
            if (start < end) console.log(start += 1)
        }, 100)
        
        return {
            cancel: () => { clearInterval(timer) }
        }
 }
count(2, 12)
```

###### 二分法

```javascript
//二分法查找的数组必须是有序的    
var arr = [11, 22, 33, 44, 8118, 8900, 9000, 9900];
    function twoFind(arr, wantVal, leftIndex, rightIndex) {
        if (leftIndex > rightIndex) {
            console.log('数组不存在： ' + wantVal + ' ！');
            return;
        }
        var minIndex = Math.floor((leftIndex + rightIndex) / 2);
        if (arr[minIndex] > wantVal) {
            twoFind(arr, wantVal, leftIndex, minIndex - 1);
        } else if (arr[minIndex] < wantVal) {
            twoFind(arr, wantVal, minIndex + 1, rightIndex);
        } else {
           console.log('找到了 ' + wantVal + ' ,索引为' + minIndex);
        }
    }


    twoFind(arr, 33, 0, arr.length - 1);
```

###### 统计字符串中出现最多的字母

```javascript
  var str = 'aaaaaafccccccbad';
    function maxStr(str) {
        let obj = {};
        let letter;
        for (var i = 0; i < str.length; i++) {
            letter = str[i];
            if (!obj[letter]) {   // 第一次放进去
                obj[letter] = 1;
            } else {
                obj[letter]++;
            }
        }
        let max_key, max_num = 0;
        for (key in obj) {
            if (max_num < obj[key]) {
                max_num = obj[key];
                max_key = key;
            }
        }
        console.log('字母：' + max_key + '　次数：' + max_num);
    }
    maxStr(str)
```

###### 斐波那契数列

```javascript

    function fbi(n) {
        let arr = [];
        for (let i = 0; i < n; i++) {
                if(i<=1){
                    arr.push(i)
                }
                else{
                    arr.push(arr[i-1]+arr[i-2])
                }

        }
        console.log(arr);
        
    }
    fbi(13)
```

