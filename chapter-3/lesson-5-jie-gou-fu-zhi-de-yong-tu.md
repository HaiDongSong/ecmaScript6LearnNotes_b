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
    console.log(x);    //1
    console.log(y);    //2
    console.log(z);    //3
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
    console.log(id);    //007
    console.log(name);    //Conan
    console.log(age);    //28

    var { id: person_id, name: person_name, age: person_age } = fun();
    console.log(person_id);        //007
    console.log(person_name);    //Conan
    console.log(person_age);    //28
</script>
```

---

函数参数的定义

```js
<script type="text/traceur">
    // 参数是一组有次序的值
    function fun ([x, y, z]) {
        //x = 100;
        //y = 200;
        //z = 300;
    };
    fun([100, 200, 300]);

    // 参数是一组无次序的值
    function fun ({id, name, age}) {
        //id   = "007";
        //name = "Conan";
        //age  = 28;
    };
    fun({id: "007", name: "Conan", age: 28});
</script>
```

让代码看起来更清晰

---

提取json数据

```js
<script type="text/traceur">
    var jsonData = {
        id: "007",
        name: "Conan",
        age: 28,
        score: {
            Chinese: 98,
            Math: 148,
            English: 107
        }
    };
    console.log(jsonData);

    console.log("ES5:");
    console.log("Person's Number is:" + jsonData.id);
    console.log("Person's Name is:" + jsonData.name);
    console.log("Person's age is:" + jsonData.age);
    console.log("Person's Chinese score is:" + jsonData.score.Chinese);
    console.log("Person's Math score is:" + jsonData.score.Math);
    console.log("Person's English score is:" + jsonData.score.English);

    console.log("ES6:");
    let { id: number, name, age, score: score } = jsonData;
    console.log("Person's Number is:" + number);
    console.log("Person's Name is:" + name);
    console.log("Person's age is:" + age);
    console.log("Person's Chinese score is:" + score.Chinese);
    console.log("Person's Math score is:" + score.Math);
    console.log("Person's English score is:" + score.English);
</script>
```

---

函数参数的默认值

```js
<script type="text/traceur">
    jQuery.ajax({
      url: '/path/to/file',
      type: 'POST',
      dataType: 'xml/html/script/json/jsonp',
      data: {param1: 'value1'},
      complete: function(xhr, textStatus) {
        //called when complete
      },
      success: function(data, textStatus, xhr) {
        //called when successful
      },
      error: function(xhr, textStatus, errorThrown) {
        //called when there is an error
      }
    });

    jQuery.ajax = function (url, {
        async = true,
        beforeSend = function() {},
        cache = true,
        complete = function() {},
        crossDomain = false,
        global = true,
        // ...more config
    }) {
        // ... do stuff
    };
    //    避免了在函数体内部再写 var foo = config.foo || 'default foo'; 这样的语句
</script>
```

---

遍历Map结构

```js
<script type="text/traceur">
	var map = new Map();
	map.set("id", "007");
	map.set("name", "Conan");

	console.log(map);
	console.log(typeof(map));

	//	获取键名和键值
	for (let [key, value] of map) {
		console.log(key + " is " + value);
	};
	// id is 007
	// name is Conan
	
	//	获取键名
	for (let [key] of map) {
		console.log(key);
	};
	// id
	// name
	
	for (let [, value] of map) {
		console.log(value);
	};
	// 007
	// Conan
</script>
```

输入模块的制定方法

```js
<script type="text/traceur">
	const { SourceMapConsumer, SourceNode } = require("source-map");
</script>
```



