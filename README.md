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
const fills = [];
for (let num = 1; num <= 8; num++) {
  const element = document.querySelector(`[data-order="${num}"]`);
  if (element) {
    fills.push(element);
  }
}
const delayBetweenElements = 200;
const activeDuration = 400;
const intervalDuration = 1600;
fills.forEach((el, i) => {
  setTimeout(() => {
    el.classList.add("black");
    setTimeout(() => {
      el.classList.remove("black");
    }, activeDuration);
  }, delayBetweenElements * i);
});
setInterval(() => {
  fills.forEach((el, i) => {
    setTimeout(() => {
      el.classList.add("black");
      setTimeout(() => {
        el.classList.remove("black");
      }, activeDuration);
    }, delayBetweenElements * i);
  });
}, intervalDuration);
```

## CodeShare #2 - Profile Hover

**Source Code:** <a href="https://github.com/hmpstrplpolmed/code-share/blob/main/profile-hover.html" target="_blank">https://github.com/hmpstrplpolmed/code-share/blob/main/profile-hover.html</a>  
**Demo:** <a href="https://hmpstrplpolmed.github.io/code-share/profile-hover" target="_blank">https://hmpstrplpolmed.github.io/code-share/profile-hover</a>

### HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,200..900;1,200..900&display=swap"
      rel="stylesheet"
    />
    <title>Profile Hover Challange Farid</title>
  </head>
  <body>
    <div class="wrapper">
      <div class="outside">
        <img
          src="./logo-codify-dark.png"
          alt="Profile"
          class="profile profile-outside"
        />
        <div class="triangle"></div>
      </div>
      <div class="card">
        <div class="header">
          <a
            href="https://www.instagram.com/codifyacademy.id"
            target="_blank"
            rel="noopener noreferrer"
            class="user"
          >
            <img
              src="./logo-codify-dark.png"
              alt="Profile"
              class="profile profile-inside"
            />
            <div class="name">
              <span class="nickname">Codify Academy</span>
              <span class="username">@codifyacademy.id</span>
            </div>
          </a>
          <button>Follow</button>
        </div>
        <div class="main-text">
          Part of
          <a href="https://www.instagram.com/hmpstrpl.polmed" target="_blank"
            >@hmpstrpl.polmed</a
          ><br />
          Science and Technology Division of HMPS TRPL<br />
          🌐
          <a href="https://hmpstrplpolmed.com" target="_blank" class="website"
            >hmpstrplpolmed.com</a
          >
        </div>
        <div class="follow">
          <div>
            <span class="text">Followers</span>
            <span class="number">198,549</span>
          </div>
          <div>
            <span class="text">Following</span>
            <span class="number">4,513</span>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

### CSS

```css
*::before,
*::after {
  box-sizing: border-box;
}
* {
  padding: 0;
  margin: 0;
}

/* General Style */
body,
button {
  font-family: "Source Sans 3", sans-serif;
  background-color: #6c49f6;
}
body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Main Style */
.wrapper {
  position: relative;
}
.profile {
  border-radius: 50%;
  aspect-ratio: 1;
}
.outside {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: fit-content;
  gap: 15.97px;
  position: absolute;
  top: -59px;
  left: 12px;
}
.profile-outside {
  width: 40px;
  height: 40px;
  /* border: 1px solid #fff; */
  box-sizing: border-box;
}
.triangle {
  width: 12px;
  height: 12px;
  background-color: rgba(255, 255, 255, 0.9);
  transform: rotate(45deg);
}
.profile-inside {
  width: 50px;
  height: 50px;
}
.card {
  background-color: #fff;
  padding: 25px;
  border-radius: 6px;
  width: 400px;
  box-shadow: 0 1rem 2rem #4517c8;
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.header {
  display: flex;
  justify-content: space-between;
}
.user {
  display: flex;
  gap: 15px;
  text-decoration: none;
  color: inherit;
}
.name {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.nickname {
  font-weight: 600;
}
.username {
  font-size: 14px;
  color: rgba(0, 0, 0, 0.6);
}
.header button {
  padding-block: 7px;
  padding-inline: 18px;
  border: none;
  border-radius: 3px;
  color: #fff;
  height: fit-content;
  font-weight: 16px;
  font-weight: 500;
  box-shadow: 0 0.25rem 2rem rgba(108, 73, 246, 0.75);
}
.main-text {
  line-height: 26px;
}
.main-text a {
  color: inherit;
  text-decoration: none;
  font-weight: 600;
}
.main-text .website {
  color: #6c49f6;
}
.follow {
  display: flex;
  gap: 30px;
}
.follow div {
  display: flex;
  flex-direction: column;
}
.follow div .text {
  color: rgba(0, 0, 0, 0.6);
}
.follow div .number {
  font-weight: 600;
  font-size: 22px;
}
```
