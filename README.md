
<!DOCTYPE html>
<html lang="si">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Unchanging Love</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Sinhala:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  background: linear-gradient(135deg, #21102e, #68416f, #d49bb3);
  color: white;
  font-family: 'Noto Sans Sinhala', sans-serif;
  text-align: center;
  overflow-x: hidden;
}

.container {
  padding: 35px 15px;
}

h1 {
  font-size: clamp(25px, 6vw, 42px);
  color: #ffe6f2;
  text-shadow: 0 0 18px #ffb4db;
}

.subtitle {
  color: #f8d8e8;
  margin-bottom: 55px;
}

/* 3D BOOK */

.scene {
  perspective: 1200px;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 420px;
  margin: 20px auto;
}

.book {
  position: relative;
  width: min(65vw, 280px);
  aspect-ratio: 2 / 3;
  transform-style: preserve-3d;
  transform: rotateY(-22deg) rotateX(3deg);
  transition: transform 0.5s ease;
  filter: drop-shadow(20px 25px 18px #160b2080);
}

.book:hover {
  transform: rotateY(-8deg) rotateX(2deg) scale(1.05);
}

.book::before {
  content: "";
  position: absolute;
  top: 0;
  left: -20px;
  width: 20px;
  height: 100%;
  background: linear-gradient(
    to right,
    #2b142b,
    #e9c5d9,
    #603b57
  );
  transform-origin: right;
  transform: rotateY(-90deg);
  border-radius: 3px 0 0 3px;
}

.book::after {
  content: "";
  position: absolute;
  top: 0;
  right: -12px;
  width: 12px;
  height: 100%;
  background: linear-gradient(
    to right,
    #f5e6ed,
    #c5a0b5,
    #74506a
  );
  transform: translateZ(-2px);
}

.cover {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 3px 8px 8px 3px;
  box-shadow:
    inset -8px 0 15px #0005,
    5px 5px 15px #0005;
  transform: translateZ(12px);
  backface-visibility: hidden;
}

.message {
  max-width: 550px;
  margin: 35px auto;
  line-height: 2;
  color: #fff0f7;
}

.butterfly {
  position: fixed;
  font-size: 25px;
  pointer-events: none;
  animation: fly 9s linear infinite;
  opacity: 0.8;
}

@keyframes fly {
  0% {
    transform: translate(0, 100vh) rotate(0deg);
  }
  100% {
    transform: translate(80px, -15vh) rotate(360deg);
  }
}

footer {
  padding: 25px;
  color: #f5d6e8;
  font-size: 13px;
}

@media (max-width: 480px) {
  .scene {
    min-height: 350px;
  }

  .book {
    width: 220px;
  }
}
</style>
</head>

<body>

<div class="butterfly" style="left:10%; animation-delay:0s;">🦋</div>
<div class="butterfly" style="left:80%; animation-delay:3s;">🦋</div>
<div class="butterfly" style="left:45%; animation-delay:5s;">🦋</div>

<div class="container">

<h1>Unchanging Love</h1>
<p class="subtitle">Some feelings never fade...</p>

<div class="scene">

  <div class="book" id="book">
    <img
      src="cover.jpg"
      alt="Unchanging Love Book Cover"
      class="cover">
  </div>

</div>

<div class="message">
  <p>
    සමහර ආදර කතා කාලයත් සමඟ මැකී යන්නේ නැහැ.
    ඒවා හදවතේ සදාකාලිකවම ජීවත් වෙනවා.
  </p>

  <p>Unchanging Love ❤️</p>
</div>

</div>

<footer>
W.A.D Nirmal Dhananjana
</footer>

<script>
const book = document.getElementById("book");

document.addEventListener("pointermove", (e) => {
  if (e.pointerType === "touch") return;

  const x = (e.clientX / window.innerWidth - 0.5) * 25;
  const y = (e.clientY / window.innerHeight - 0.5) * -15;

  book.style.transform =
    `rotateY(${-22 + x}deg) rotateX(${3 + y}deg)`;
});

document.addEventListener("pointerleave", () => {
  book.style.transform = "rotateY(-22deg) rotateX(3deg)";
});
</script>

</body>
</html>
# wenas-nowana-adarayaks
