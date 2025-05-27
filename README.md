<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Selamat Ulang Tahun!</title>

<!-- Mengimpor font dari Google -->
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Montserrat:wght@400;700&display=swap" rel="stylesheet">

<style>
  /* Reset */
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    height: 100vh;
    background: radial-gradient(circle at center, #fceabb, #f8b500);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    font-family: 'Montserrat', sans-serif;
    color: #4a2c0d;
    user-select: none;
  }

  .container {
    text-align: center;
    max-width: 650px;
    padding: 20px;
    background: rgba(255, 255, 255, 0.85);
    border-radius: 25px;
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.15);
    backdrop-filter: blur(12px);
    position: relative;
  }

  h1 {
    font-family: 'Great Vibes', cursive;
    font-size: 5rem;
    letter-spacing: 0.1em;
    margin-bottom: 0.2em;
    color: #f05e23;
    text-shadow:
      1px 1px 1px #ffa676,
      2px 2px 3px #cc4e07;
    animation: pop 1.5s ease forwards;
  }

  @keyframes pop {
    0% {
      transform: scale(0.7);
      opacity: 0;
    }
    80% {
      transform: scale(1.1);
      opacity: 1;
    }
    100% {
      transform: scale(1);
    }
  }

  p {
    font-size: 1.5rem;
    color: #7c3c00cc;
    margin-bottom: 1.5em;
    font-weight: 600;
    letter-spacing: 0.05em;
  }

  /* Style untuk link yang mirip tombol */
  a.wish-link {
    display: inline-block;
    background: #f05e23;
    color: white;
    text-decoration: none;
    padding: 1em 2em;
    border-radius: 30px;
    font-weight: 700;
    letter-spacing: 0.1em;
    box-shadow: 0 4px 15px rgba(240, 94, 35, 0.5);
    cursor: pointer;
    transition: background 0.3s ease;
    user-select: none;
  }
  a.wish-link:hover,
  a.wish-link:focus {
    background: #d14a0d;
  }
  a.wish-link:disabled,
  a.wish-link.disabled {
    background: #b65713;
    cursor: default;
    pointer-events: none;
  }

  /* Gaya balon */
  .balloon {
    position: absolute;
    bottom: -150px;
    width: 60px;
    height: 80px;
    background: linear-gradient(135deg, #ff5964, #ff9a95);
    border-radius: 50% 50% 45% 45% / 60% 60% 40% 40%;
    box-shadow: inset -10px -15px 15px #cc464a;
    animation: floatUp linear infinite;
    filter: drop-shadow(0 7px 3px #c8474aaa);
  }

  .balloon::after {
    content: '';
    position: absolute;
    bottom: -15px;
    left: 50%;
    width: 2px;
    height: 25px;
    background: #5e292d;
    transform: translateX(-50%);
    border-radius: 1px;
  }

  /* Warna balon yang berbeda */
  .balloon:nth-child(1) {
    left: 25%;
    background: linear-gradient(135deg, #ff6f91, #ffc3a0);
    animation-duration: 7s;
    animation-delay: 0s;
  }
  .balloon:nth-child(2) {
    left: 55%;
    width: 50px;
    height: 70px;
    background: linear-gradient(135deg, #6a0572, #a2018b);
    animation-duration: 9s;
    animation-delay: 2s;
  }
  .balloon:nth-child(3) {
    left: 80%;
    width: 70px;
    height: 95px;
    background: linear-gradient(135deg, #ef476f, #ff9a95);
    animation-duration: 8s;
    animation-delay: 4s;
  }
  .balloon:nth-child(4) {
    left: 40%;
    width: 55px;
    height: 75px;
    background: linear-gradient(135deg, #ffd166, #f9f871);
    animation-duration: 6.5s;
    animation-delay: 1.5s;
  }
  .balloon:nth-child(5) {
    left: 70%;
    width: 50px;
    height: 70px;
    background: linear-gradient(135deg, #06d6a0, #1ec3a6);
    animation-duration: 7.5s;
    animation-delay: 3.5s;
  }

  @keyframes floatUp {
    0% {
      transform: translateY(0) translateX(0) rotate(0deg);
      opacity: 1;
    }
    50% {
      transform: translateY(-250px) translateX(15px) rotate(15deg);
      opacity: 0.9;
    }
    100% {
      transform: translateY(-500px) translateX(0) rotate(-10deg);
      opacity: 0;
    }
  }

  /* Kontainer confetti */
  .confetti-wrapper {
    position: fixed;
    top: 0; left: 0;
    width: 100vw; height: 100vh;
    pointer-events: none;
    overflow: visible;
    z-index: 10;
  }

  .confetti {
    position: absolute;
    width: 8px;
    height: 8px;
    background-color: #ff595e;
    opacity: 0.78;
    border-radius: 2px;
    animation: confetti-fall linear forwards;
  }

  @keyframes confetti-fall {
    0% {
      transform: translateY(-20px) rotate(0deg);
      opacity: 1;
    }
    100% {
      transform: translateY(100vh) rotate(360deg);
      opacity: 0;
    }
  }

</style>
</head>
<body>
  <div class="confetti-wrapper" aria-hidden="true"></div>

  <div class="container" role="main" aria-label="Ucapan Selamat Ulang Tahun">
    <h1>Selamat Ulang Tahun!</h1>
    <p>Semoga harimu dipenuhi dengan cinta, tawa, dan kebahagiaan.</p>
    <a href="#" id="wishLink" class="wish-link" role="button" aria-pressed="false">Kirim Ucapan</a>

    <div class="balloon" aria-hidden="true"></div>
    <div class="balloon" aria-hidden="true"></div>
    <div class="balloon" aria-hidden="true"></div>
    <div class="balloon" aria-hidden="true"></div>
    <div class="balloon" aria-hidden="true"></div>
  </div>

<script>
  const confettiWrapper = document.querySelector('.confetti-wrapper');
  const wishLink = document.getElementById('wishLink');

  function randomRange(min, max) {
    return Math.random() * (max - min) + min;
  }

  function createConfettiPiece() {
    const confetti = document.createElement('div');
    confetti.classList.add('confetti');
    confetti.style.left = randomRange(0, window.innerWidth) + 'px';
    confetti.style.animationDuration = randomRange(3, 6) + 's';
    confetti.style.backgroundColor = `hsl(${randomRange(0, 360)}, 80%, 60%)`;
    return confetti;
  }

  function launchConfetti() {
    for (let i = 0; i < 70; i++) {
      const confetti = createConfettiPiece();
      confettiWrapper.appendChild(confetti);
      setTimeout(() => {
        confetti.remove();
      }, 6000);
    }
  }

  wishLink.addEventListener('click', (event) => {
    event.preventDefault();
    launchConfetti();
    wishLink.textContent = "Ucapan Terkirim!";
    wishLink.classList.add('disabled');
    wishLink.setAttribute('aria-pressed', 'true');
    wishLink.style.pointerEvents = 'none';

    setTimeout(() => {
      wishLink.textContent = "Kirim Ucapan";
      wishLink.classList.remove('disabled');
      wishLink.setAttribute('aria-pressed', 'false');
      wishLink.style.pointerEvents = 'auto';
    }, 4000);
  });
</script>
</body>
</html>

