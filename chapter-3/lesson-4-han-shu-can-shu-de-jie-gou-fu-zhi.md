![](/assets/import12.png)函数参数的解构赋值

```js
<script type="text/traceur">
    function sum([x, y]) {
        return x + y;
    };

    console.log(sum([1, 2]));    //3
</script>
```

函数参数解构赋值的默认值

```js
<script type="text/traceur">
    function fun ({x = 0, y = 0} = {}) {
        return [x, y];
    };

    console.log(fun({x: 100, y: 200}));    //[100, 200]
    console.log(fun({x: 100}));            //[100, 0]
    console.log(fun({}));                //[0, 0]
    console.log(fun());                    //[0, 0]
</script>
```

函数参数解构赋值的默认值undefined

```js
<script type="text/traceur">
	function fun ({x, y} = { x: 0, y: 0 }) {
		return [x, y];
	};

	console.log(fun({x: 100, y: 200}));	//[100, 200]
	console.log(fun({x: 100}));			//[100, undefined]
	console.log(fun({}));				//[undefined, undefined]
	console.log(fun());					//[0, 0]
</script>
```



