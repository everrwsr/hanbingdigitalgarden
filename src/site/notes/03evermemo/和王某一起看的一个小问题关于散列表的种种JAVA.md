---
{"dg-publish":true,"title":"和王某一起看的一个小问题关于散列表的种种JAVA","permalink":"/03evermemo/java/","dgPassFrontmatter":true}
---

>[!问题起因]

![83e9eb90855895753c0aa79a0458817.png](https://raw.githubusercontent.com/everrwsr/blogimage/main/83e9eb90855895753c0aa79a0458817.png)

![image.png](https://raw.githubusercontent.com/everrwsr/blogimage/main/20230213134349.png)


>[!结论]
>x.key就是hash(key),
>函数目的是判断key是否一样，先遍历哈希表对应key位置的链表，若x.key和key不一样新建节点，进行头插，一样才会直接更新值。
>1 和17 不一样


## 代码
```
/**  
 * description : * * @author: everr * @date: 2023/02/13 12:20 **///基于拉链法实现的哈希表  
//键值对存储的都是整型  
public class HashMapByLink {  
  
    private class Node {  
        int key;  
        int val;  
        Node next;  
  
        //构造方法  
        public Node(int key, int val, Node next) {  
            this.key = key;  
            this.val = val;  
            this.next = next;  
        }  
    }  
    //实际存储的元素个数  
    private int size;  
    //取模数，默认使用数组的长度  
    private int M;  
    //默认哈希表的长度  
    private static final int DEFAULT_CAPACITY=16;  
    //默认的负载因子  
    private static final double LOAD_FACTORY=0.75;  
    //实际存储Node结点的数组，存储的是Node的元素  
    private Node[] table;//冲突是链表，不冲突是数组  
  
    public HashMapByLink() {  
        this(DEFAULT_CAPACITY);  
    }  
  
    //默认的初始化容量  
    public HashMapByLink(int initcap){  
        this.table=new Node[initcap];  
        this.M=initcap;  
    }  
  
    //若无重复元素，返回value；若key存在，更新Value,返回之前的value  
    public int put(int key,int value){  
        //key是确定需要存储的位置  
        //先求key的hash值  
        int index=hash(key);  
        System.out.println(index);  
  
        //判断当前链表是否已近存在了这个key值，若存在，则更新为value，否则返回旧的value  
        //table[index]为链表的头结点  
        for (Node x=table[index];x!=null;x=x.next) {  
            System.out.println("进入循环前"+x.key+"---"+key);  
            if(x.key==key) {  
                System.out.println("进入循环后"+x.key+"---"+key);  
                int oldValue = x.val;  
                x.val = value;  
                return oldValue;  
            }  
        }  
        //若key不存在，新建一个结点头插相应的链表中  
        Node newNode=new Node(key,value,table[index]);  
        //更新原先头结点指向当前结点  
        table[index]=newNode;  
        size++;  
        return value;  
    }  
    //最简单的key值取模  
    private int hash(int key){  
        return (key & 0x7fffffff)%this.M;  
    }  
  
  
  
}
```
> 散列表



### 测试方法
```
/**  
 * description : * * @author: everr * @date: 2023/02/13 12:21 **/  
public class Test {  
    //默认16  
    public static void main(String[] args) {  
        HashMapByLink hashMapByLink=new HashMapByLink();  
        hashMapByLink.put(1,10);  
        hashMapByLink.put(2,20);  
        hashMapByLink.put(2,16);  
        hashMapByLink.put(17,30);  
        hashMapByLink.put(18,20);  
    }  
  
}

```

## 运行截图

![image.png](https://raw.githubusercontent.com/everrwsr/blogimage/main/20230213135606.png)
![image.png](https://raw.githubusercontent.com/everrwsr/blogimage/main/20230213135640.png)



## 结语

很久没看代码
散列表和哈希表不一样啊
谢谢王某教我
并且欸
我把她思路差点拐到沟里
她也没有很气，哈哈哈。

还有断点调试我会·了·，在idea中

[IDEA中的debug断点调试技巧，学会真的香！ - 腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/1887019)

