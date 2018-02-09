# sorting

数组排序的方法:
 1 传统方法:两两比较,经过一轮之后,最大的放到最后. 比较ary.length-1 次就可以完成

   //另一种思想:两两比较换位置,一轮比较完成之后,最大的就在最后
  let ary=[3,4,1]
   function shorting(ary){
    for(var i=0;i<ary.length-1;i++){
     for(var j=0;j<ary.length-1;j++){
         let current=ary[j];
         let next=ary[j+1];
         let temp=next;
         if(next<current){
            ary[j]=current;
            ary[j+1]=temp;
         }
     }
   }

   }
   console.log(shorting(ary))
方法二:巧用apply 进行数组排序

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



