# Code-Share

Pembuatan konten media sosial yang menampilkan potongan kode (HTML, CSS, JavaScript, dll.) beserta tampilannya, ditujukan untuk berbagi pengetahuan dasar pemrograman dan inspirasi sederhana yang mudah dipraktikkan.

## CodeShare #1 - Pixel Loading

**Source Code:** <a href="https://github.com/hmpstrplpolmed/code-share/blob/main/pixel-loading.html" target="_blank">https://github.com/hmpstrplpolmed/code-share/blob/main/pixel-loading.html</a>  
**Demo:** <a href="https://hmpstrplpolmed.github.io/code-share/pixel-loading" target="_blank">https://hmpstrplpolmed.github.io/code-share/pixel-loading</a>

### HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>
  <body>
    <div class="wrapper">
      <div class="box box-1"></div>
      <div class="box box-2 fill" data-order="1"></div>
      <div class="box box-3 fill" data-order="2"></div>
      <div class="box box-4"></div>
      <div class="box box-5 fill" data-order="8"></div>
      <div class="box box-6"></div>
      <div class="box box-7"></div>
      <div class="box box-8 fill" data-order="3"></div>
      <div class="box box-9 fill" data-order="7"></div>
      <div class="box box-10"></div>
      <div class="box box-11"></div>
      <div class="box box-12 fill" data-order="4"></div>
      <div class="box box-13"></div>
      <div class="box box-14 fill" data-order="6"></div>
      <div class="box box-15 fill" data-order="5"></div>
      <div class="box box-16"></div>
    </div>
  </body>
</html>
```

### CSS

```css
* {
  margin: 0;
  padding: 0;
}
.wrapper {
  display: grid;
  grid-template-columns: repeat(4, 2rem);
  grid-template-rows: repeat(4, 2rem);
  padding: 0.125rem;
  width: fit-content;
  margin: 2rem auto;
}
.box {
  background-color: #fff;
}
.fill {
  transition: background-color 0.5s ease;
}
.fill.black {
  background-color: #000;
}
```

### JavaScript

```javascript
const fills = []
for (let num = 1; num <= 8; num++) {
  const element = document.querySelector(`[data-order="${num}"]`)
  if (element) {
    fills.push(element)
  }
}
const delayBetweenElements = 200
const activeDuration = 400
const intervalDuration = 1600
fills.forEach((el, i) => {
  setTimeout(() => {
    el.classList.add('black')
    setTimeout(() => {
      el.classList.remove('black')
    }, activeDuration)
  }, delayBetweenElements * i)
})
setInterval(() => {
  fills.forEach((el, i) => {
    setTimeout(() => {
      el.classList.add('black')
      setTimeout(() => {
        el.classList.remove('black')
      }, activeDuration)
    }, delayBetweenElements * i)
  })
}, intervalDuration)
```
