![](/assets/import10.png)

变量名与属性名不一样

```js
<script type="text/traceur">
    // var { person_name, person_age, person_id } = { id: "007", name: "Conan", age: 28 };
    // console.log(person_name);    //undefined
    // console.log(person_age);    //undefined
    // console.log(person_id);        //undefined

    var { name: person_name, age: person_age, id: person_id } = { id: "007", name: "Conan", age: 28 };
    console.log(person_name);    //Conan
    console.log(person_age);    //28
    console.log(person_id);        //007

    let object = { first: "Hello", last: "World" };
    let { first: firstName, last: lastName} = object;
    console.log(firstName);    //Hello
    console.log(lastName);    //World
</script>
```

---

对象结构默认值

```js
<script type="text/traceur">
    var { x = 3 } = {};
    console.log(x);    //3

    var { x, y = 5 } = { x: 1 };
    console.log(x);    //1
    console.log(y);    //5

    var { message: msg = "You Are A Person!" } = {};
    console.log(msg);    //You Are A Person!
</script>
```

---



