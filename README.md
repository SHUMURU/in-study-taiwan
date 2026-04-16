
# in-study-taiwan<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Story</title>

  <link rel="stylesheet" href="style.css">
</head>
<body>

<nav>
  <a href="index.html">Home</a>
  <a href="about.html">Story</a>
  <a href="product.html">Product</a>
  <a href="contact.html">Contact</a>
</nav>

<section class="fade-in">
  <h1>Our Story</h1>
  <p>
    厳選された素材と伝統技術。  
    時間をかけて生まれる一杯。
  </p>
</section>

<script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Contact</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<nav>
  <a href="index.html">Home</a>
  <a href="about.html">Story</a>
  <a href="product.html">Product</a>
  <a href="contact.html">Contact</a>
</nav>

<section class="fade-in">
  <h1>Contact</h1>
  <p>Email: example@email.com</p>
</section>

<script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>YEBISU Premium</title>
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <section class="hero fade-in">
    <h1>YEBISU Premium</h1>
    <p class="subtitle">本物のビールには、理由がある。</p>

    <img class="zoom" src="https://images.unsplash.com/photo-1608270586620-248524c67de9" alt="beer">

    <p class="tagline">弟兄の味</p>

    <button onclick="buyNow()">今すぐ味わう</button>
  </section>

  <section class="content fade-in">
    <h2>Crafted for Perfection</h2>
    <p>
      厳選された素材と伝統の技術。<br>
      一杯に込められた、本物の価値。
    </p>
  </section>

  <script src="script.js"></script>
</body>
</html><h1></h1>
<p class="subtitle"></p>
<p class="tagline"></p>
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Product</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<nav>
  <a href="index.html">Home</a>
  <a href="about.html">Story</a>
  <a href="product.html">Product</a>
  <a href="contact.html">Contact</a>
</nav>

<section class="fade-in">
  <h1>Product</h1>
  <img src="https://images.unsplash.com/photo-1608270586620-248524c67de9">
  <p>香り、コク、余韻。</p>
</section>

<script src="script.js"></script>
</body>
</html>
function buyNow() {
  alert("購入ページへようこそ 🍺");
}

// 滚动动画（重点）
const faders = document.querySelectorAll('.fade-in');

const appearOptions = {
  threshold: 0.2
};

const appearOnScroll = new IntersectionObserver(function(
  entries,
  observer
) {
  entries.forEach(entry => {
    if (!entry.isIntersecting) {
      return;
    } else {
      entry.target.classList.add('show');
      observer.unobserve(entry.target);
    }
  });
}, appearOptions);

faders.forEach(fader => {
  appearOnScroll.observe(fader);
});const faders = document.querySelectorAll('.fade-in');

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('show');
    }
  });
});

faders.forEach(el => observer.observe(el));
const url = "你的Supabase URL";
const key = "你的API KEY";

fetch(`${url}/rest/v1/content`, {
  headers: {
    "apikey": key,
    "Authorization": `Bearer ${key}`
  }
})
.then(res => res.json())
.then(data => {
  const content = data[0];

  document.querySelector("h1").innerText = content.title;
  document.querySelector(".subtitle").innerText = content.subtitle;
  document.querySelector(".tagline").innerText = content.description;
});
body {
  margin: 0;
  font-family: serif;
  background: linear-gradient(180deg, #0B0B0B, #1a1a1a);
  color: white;
  text-align: center;
}

/* Hero */
.hero {
  padding: 100px 20px;
}

h1 {
  font-size: 60px;
  color: #D4AF37;
}

.subtitle {
  font-size: 20px;
  margin-top: 10px;
  color: #ccc;
}

/* 图片动画 */
.zoom {
  width: 300px;
  margin: 40px 0;
  border-radius: 10px;
  transition: transform 1.5s ease;
}

.zoom:hover {
  transform: scale(1.1);
}

/* 文案 */
.tagline {
  font-size: 24px;
  margin-top: 10px;
}

/* 按钮动画 */
button {
  margin-top: 30px;
  padding: 12px 30px;
  border: none;
  background: #D4AF37;
  color: black;
  font-weight: bold;
  border-radius: 30px;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover {
  transform: translateY(-3px);
  background: #f0c94b;
}

/* 内容区 */
.content {
  padding: 80px 20px;
}

/* 滚动渐显（核心） */
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: all 1s ease;
}

.fade-in.show {
  opacity: 1;
  transform: translateY(0);
}body {
  margin: 0;
  font-family: serif;
  background: #0B0B0B;
  color: white;
  text-align: center;
}

nav {
  background: black;
  padding: 20px;
}

nav a {
  color: #D4AF37;
  margin: 0 15px;
  text-decoration: none;
}

section {
  padding: 100px 20px;
}

h1 {
  font-size: 50px;
  color: #D4AF37;
}

img {
  width: 300px;
  margin-top: 20px;
}

/* 动画 */
.fade-in {
  opacity: 0;
  transform: translateY(40px);
  transition: 1s;
}

.fade-in.show {
  opacity: 1;
  transform: translateY(0);
}
