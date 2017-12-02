![](/assets/import11.png)字符串的属性解构

```js
<script type="text/traceur">
	const { length: len } = "Hello";
	console.log(len);	//5

	const { length } = "Hello World!";
	console.log(length);//12
</script>
```



