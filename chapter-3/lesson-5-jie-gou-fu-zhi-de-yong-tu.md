![](/assets/import13.png)

交换变量的值

```js
<script type="text/traceur">
    //ES5
    console.log("ES5:");
    var a = 100;
    var b = 200;
    console.log("交换前：");
    console.log("a = " + a);    //a = 100
    console.log("b = " + b);    //b = 200
    var temp;
    temp = a;
    a = b;
    b = temp;
    console.log("交换后：");
    console.log("a = " + a);    //a = 200
    console.log("b = " + b);    //b = 100

    //ES6
    console.log("ES6:");
    var x = 100;
    var y = 200;
    console.log("交换前：");
    console.log("x = " + x);    //x = 100
    console.log("y = " + y);    //y = 200
    [x, y] = [y, x];
    console.log("交换后：");
    console.log("x = " + x);    //x = 200
    console.log("y = " + y);    //y = 100
</script>
```

相比ES5好处：

* 代码量变少
* 占用内存少
* 容易理解

---

从函数返回多个值，可以使一个数组也可以是一个对象

```js
<script type="text/traceur">
	function fun () {
		return [1, 2, 3];
	};

	var [x, y, z] = fun();
	console.log(x);	//1
	console.log(y);	//2
	console.log(z);	//3
</script>
```

```js
<script type="text/traceur">
	function fun () {
		return {
			id  : "007",
			name: "Conan",
			age : 28
		};
	};

	var { id, name, age } = fun();
	console.log(id);	//007
	console.log(name);	//Conan
	console.log(age);	//28

	var { id: person_id, name: person_name, age: person_age } = fun();
	console.log(person_id);		//007
	console.log(person_name);	//Conan
	console.log(person_age);	//28
</script>
```



