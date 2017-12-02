const 不能重复定义

```js
<script type="module">    
    var pi = 0;  //Error...
    const pi = 3.141592653;
    //pi = 3;
    console.log(pi);    

</script>
```

```js
<script type="text/traceur">
    const person = {};
    person.name  = "Zhangsan";
    person.age   = 30;

    console.log(person.name);    //Zhangsan
    console.log(person.age);    //30
    console.log(person);        //Object {name: "Zhangsan", age: 30}
</script>
```

```js
<script type="text/traceur">
    const person = {};
    person.name  = "Zhangsan";
    person.age   = 30;

    console.log(person.name);
    console.log(person.age);
    console.log(person);

    person = {};    //person is read-only
</script>
```

```js
<script type="text/traceur">
    const arr = [];
    console.log(arr);
    console.log(arr.length);
    console.log("------");
    arr.push("Hello world!");
    console.log(arr);
    console.log(arr.length);
    console.log("------");
    arr.length = 0;
    console.log(arr);
    console.log(arr.length);
    console.log("------");

    // 错误用法
    arr = ["Hello Everyone!"];
</script>
```

```js
//彻底冻结对象的函数
var constantize = (obj) => {
	Object.freeze(obj);
	Object.keys(obj).forEach( (key, value) => {
		if ( typeof obj[key] === 'object' ) {
			constantize( obj[key] );
		};
	});
};
```



