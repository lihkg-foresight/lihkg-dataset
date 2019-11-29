### blank-vote-posts.csv

由 2019-11-16 至 2019-11-24 所有包含「白票」的留言

### random-sample-400.csv

來自 `blank-vote-posts.csv`，以 `Math.random()` 隨機抽取數據

### random-sample-500-seed.csv

來自 `blank-vote-posts.csv`，以下列方式隨機抽取數據

```js
function getRandomArray(inArray, n) {
    var arr = [];
    var output = [];

    var seed = 1;
    function random() {
        var x = Math.sin(seed++);
        return x - Math.floor(x);
    }

    while (arr.length < n) {
        var r = Math.floor(random() * (inArray.length - 1));
        if (arr.indexOf(r) === -1) {
            output.push(inArray[r])
            arr.push(r);
        }
    }
    return output;
}
```

### opinion

| opinion | description                                 |
|---------|---------------------------------------------|
| 0       | 相關討論，未有未有明確表示認同/不認同投白票 |
| 1       | 「認同/不反對/鼓勵/將會」投白票             |
| 2       | 「不認同/反對/指責」投白票                  |