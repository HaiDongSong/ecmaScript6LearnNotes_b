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

	fun();	//undefined
</script>
```



