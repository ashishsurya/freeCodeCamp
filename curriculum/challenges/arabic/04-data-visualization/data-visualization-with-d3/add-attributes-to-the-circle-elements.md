---
id: 587d7fab367417b2b2512bd8
title: أضف سمات (Attributes) إلى عناصر Circle
challengeType: 6
forumTopicId: 301471
dashedName: add-attributes-to-the-circle-elements
---

# --description--

أنشئت في التحدي السابق عناصر `circle` لكل نقطة في `dataset`، وربطهم بلوحة (canvas) SVG. لكن D3 يحتاج إلى مزيد من المعلومات حول موقع (position) وحجم (size) كل `circle` لعرضها بشكل صحيح.

لدي `circle` في SVG ثلاث سمات (attributes) رئيسية. تكون السمات (attributes) المسمى `cx` و `cy` إحداثيات. ويخبروا D3 أين موقع (position) *مركز (center)* للشكل على لوحة (canvas) SVG. تغير سمة (attribute) نصف قطر (radius) (تكتب مثل: `r`) يأثر على حجم `circle`.

مثل مقياس الإحداثيات `rect` داخل `y`، تقاس `cy` داخل `circle` من الجزء العلوي للوحة (canvas) SVG، ليس من الأسفل.

تستطيع جميع السمات (attributes) الثلاث باستخدام وظيفة لإعادة التفعيل (callback function) لتحديد قيمها بشكل ديناميكي. تذكر أن جميع الطرق (methods) المسلسلة بعد وظيفة `data(dataset)` تفعّل مرة واحدة لكل عنصر في `dataset`. تشير `d` في وظيفة إعادة التفعيل إلى العنصر الحالي في `dataset`، وهو قائمة لكل نقطة. استخدم رمز الأقواس، مثل `d[0]`، للوصول إلى القيم في تلك القائمة.

# --instructions--

أضف السمات `cx` و `cy` و `r` إلى العناصر المسمى `circle`. The `cx` value should be the first number in the array for each item in `dataset`. The `cy` value should be based off the second number in the array, but make sure to show the chart right-side-up and not inverted. The `r` value should be `5` for all circles.

# --hints--

Your code should have 10 `circle` elements.

```js
assert($('circle').length == 10);
```

The first `circle` element should have a `cx` value of `34`, a `cy` value of `422`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(0).attr('cx') == '34' &&
    $('circle').eq(0).attr('cy') == '422' &&
    $('circle').eq(0).attr('r') == '5'
);
```

The second `circle` element should have a `cx` value of `109`, a `cy` value of `220`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(1).attr('cx') == '109' &&
    $('circle').eq(1).attr('cy') == '220' &&
    $('circle').eq(1).attr('r') == '5'
);
```

The third `circle` element should have a `cx` value of `310`, a `cy` value of `380`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(2).attr('cx') == '310' &&
    $('circle').eq(2).attr('cy') == '380' &&
    $('circle').eq(2).attr('r') == '5'
);
```

The fourth `circle` element should have a `cx` value of `79`, a `cy` value of `89`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(3).attr('cx') == '79' &&
    $('circle').eq(3).attr('cy') == '89' &&
    $('circle').eq(3).attr('r') == '5'
);
```

The fifth `circle` element should have a `cx` value of `420`, a `cy` value of `280`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(4).attr('cx') == '420' &&
    $('circle').eq(4).attr('cy') == '280' &&
    $('circle').eq(4).attr('r') == '5'
);
```

The sixth `circle` element should have a `cx` value of `233`, a `cy` value of `355`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(5).attr('cx') == '233' &&
    $('circle').eq(5).attr('cy') == '355' &&
    $('circle').eq(5).attr('r') == '5'
);
```

The seventh `circle` element should have a `cx` value of `333`, a `cy` value of `404`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(6).attr('cx') == '333' &&
    $('circle').eq(6).attr('cy') == '404' &&
    $('circle').eq(6).attr('r') == '5'
);
```

The eighth `circle` element should have a `cx` value of `222`, a `cy` value of `167`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(7).attr('cx') == '222' &&
    $('circle').eq(7).attr('cy') == '167' &&
    $('circle').eq(7).attr('r') == '5'
);
```

The ninth `circle` element should have a `cx` value of `78`, a `cy` value of `180`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(8).attr('cx') == '78' &&
    $('circle').eq(8).attr('cy') == '180' &&
    $('circle').eq(8).attr('r') == '5'
);
```

The tenth `circle` element should have a `cx` value of `21`, a `cy` value of `377`, and an `r` value of `5`.

```js
assert(
  $('circle').eq(9).attr('cx') == '21' &&
    $('circle').eq(9).attr('cy') == '377' &&
    $('circle').eq(9).attr('r') == '5'
);
```

# --seed--

## --seed-contents--

```html
<body>
  <script>
    const dataset = [
                  [ 34,    78 ],
                  [ 109,   280 ],
                  [ 310,   120 ],
                  [ 79,    411 ],
                  [ 420,   220 ],
                  [ 233,   145 ],
                  [ 333,   96 ],
                  [ 222,   333 ],
                  [ 78,    320 ],
                  [ 21,    123 ]
                ];


    const w = 500;
    const h = 500;

    const svg = d3.select("body")
                  .append("svg")
                  .attr("width", w)
                  .attr("height", h);

    svg.selectAll("circle")
       .data(dataset)
       .enter()
       .append("circle")
       // Add your code below this line



       // Add your code above this line

  </script>
</body>
```

# --solutions--

```html
<body>
  <script>
    const dataset = [
                  [ 34,    78 ],
                  [ 109,   280 ],
                  [ 310,   120 ],
                  [ 79,    411 ],
                  [ 420,   220 ],
                  [ 233,   145 ],
                  [ 333,   96 ],
                  [ 222,   333 ],
                  [ 78,    320 ],
                  [ 21,    123 ]
                ];


    const w = 500;
    const h = 500;

    const svg = d3.select("body")
                  .append("svg")
                  .attr("width", w)
                  .attr("height", h);

    svg.selectAll("circle")
       .data(dataset)
       .enter()
       .append("circle")
       .attr("cx", (d) => d[0])
       .attr("cy", (d) => h - d[1])
       .attr("r", 5)

  </script>
</body>
```
