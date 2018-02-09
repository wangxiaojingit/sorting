# sorting
巧用apply 进行数组排序

感觉数组排序两两比较挺麻烦的,于是就自己就开始想最简单的逻辑,就是每次找出数组中的从小项,拿出来,就这么easy,是不是不用想那么多.
在这里我巧用了Math.min( ) 和apply. 上代码


let ary=[3,4,1,2,6,5]
 function shorting(ary){
    let ary1=[];
    let ary2=ary.slice(0);
    for(var i=0;i<ary2.length;i++){
    let a= Math.min.apply(null,ary2);
    ary1.push(a)
    let index=ary2.findIndex(function(item){
        return a==item
    })
    ary2.splice(index,1)
    i--
    }
    return ary1
 } 
 
console.log(shorting(ary))


