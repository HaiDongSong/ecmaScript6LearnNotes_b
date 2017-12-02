![](/assets/import7.png)

```js
//第一种场景
<script type="text/javascript">
    var time = new Date();

    function fun() {
        console.log(time);
        if (false) {
            var time = "Hello World!";
        };
    };

    fun();    //undefined
</script>
```

```js
<title>第一种场景</title>
<script type="text/javascript">
	var string = "Hello World!";

	for (var i = 0; i < string.length; i++) {
		console.log(string[i]);
	};

	console.log("循环结束");
	console.log(i);	//12
</script>
```

```js
<script type="text/javascript">
	console.log("ES5:");

	function fun() {
		var num = 100;
		if (true) {
			var num = 200;
		};
		console.log(num);
	};

	fun();	//200
</script>
<script type="text/traceur">
	console.log("ES6:");

	function fun() {
		let num = 100;
		if (true) {
			let num = 200;
		};
		console.log(num);
	};

	fun();	//100
</script>
```

```js
<script type="text/javascript">
	console.log("ES5:");
	function fun() {
		console.log("I am outside!");
	};

	(function () {
		if (false) {
			function fun() {
				console.log("I am inside!");
			};
		};

		fun();
	}());
</script>
```



