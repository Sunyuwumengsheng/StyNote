- 什么是切片
	- 引用集合中部分连续元素，而不是引用整个集合
	  background-color:: yellow
	  ```rust
	  let s =String::from("hello world")
	  let hello = &s[0..5]; //左闭右开区间  0～4
	  let world = &s[6..11];
	  ```
	  对于 let world 来说 world 是一个切片对应的指针指向的是第 7 个索引也就是 6（因为索引是从 0 开始的）指针指向的图是这样
	  ![](https://pic1.zhimg.com/80/v2-69da917741b2c610732d8526a9cc86f5_1440w.jpg)
	- 注意点对字符串使用切片时要考虑边界值如 UTF8下的中文字符 
	  ```rust
	  let s = "中国人"
	  let a = &s[0..2];
	  //该代码会保存一个中文占三个字节 两个长度取不完整导致崩溃
	  //let a = &s[0..3]; 改为该代码就能编译		
	  ```
		- 对于 UTF8 的字符操作可以看参见[这里](https://course.rs/basic/compound-type/string-slice.html#%E6%93%8D%E4%BD%9C-utf-8-%E5%AD%97%E7%AC%A6%E4%B8%B2)
		-
-