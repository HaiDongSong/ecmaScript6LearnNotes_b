const 不能重复定义

\`\`\`

		&lt;script type="module"&gt;	

			var pi = 0;  //Error...

			const pi = 3.141592653;

			//pi = 3;

			console.log\(pi\);			

		&lt;/script&gt;

\`\`\`

```js
        <script type="module">            
            const pi = 3.141592653;

            //pi = 3;
            console.log(pi);


        </script>
```



