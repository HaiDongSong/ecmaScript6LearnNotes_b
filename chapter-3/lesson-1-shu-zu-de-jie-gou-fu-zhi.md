![](/assets/import9.png)

数组解构

```js
<script type="text/traceur">
    let [foo, [[bar], base]] = [1, [[2], 3]];
    console.log(foo);    //1
    console.log(bar);    //2
    console.log(base);    //3

    let [, , third] = ["first", "second", "third"];
    console.log(third);    //third

    let [one, , three] = ["One", "Two", "Three"];
    console.log(one);    //One
    console.log(three);    //Three

    let [head, ...tail] = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    console.log(head);    //0
    console.log(tail);    //[1, 2, 3, 4, 5, 6, 7, 8, 9]

</script>
```

---

不完全解构

```js
<script type="text/traceur">
    let [x, y] = [1, 2, 3];
    console.log(x);    //1
    console.log(y);    //2

    let [a, [b], c] = [1, [2, 3], 4];
    console.log(a);    //1
    console.log(b);    //2
    console.log(c);    //4
</script>
```

---

解构不成功

```js
<script type = "module">
var [temp] = [];
console.log(temp); //undefined
var [first, second] = [100];
console.log(first); //100
console.log(second);//undefined
</script>
```

--------



