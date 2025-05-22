<!DOCTYPE html>
<html lang="az">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Romantik H?diyy?</title>
<style>
  body {
    background: linear-gradient(to bottom, #fff1e6, #fbc1b8);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    font-family: Arial, sans-serif;
    color: #4a2c25;
    text-align: center;
    user-select: none;
  }

  /* H?diyy? qutusu */
  .gift-box {
    position: relative;
    width: 160px;
    height: 160px;
    background: linear-gradient(145deg, #ff9ab3, #ff6680);
    border-radius: 35px;
    box-shadow:
      0 8px 15px rgba(255, 101, 132, 0.7),
      inset 0 3px 8px rgba(255, 255, 255, 0.3);
    cursor: pointer;
    margin: 0 auto 40px;
    transition: transform 0.2s ease, box-shadow 0.3s ease;
  }
  .gift-box:hover {
    transform: scale(1.1);
    box-shadow:
      0 12px 25px rgba(255, 101, 132, 0.9),
      inset 0 5px 12px rgba(255, 255, 255, 0.5);
  }

  /* Ortadaki + isar?si kald?r?ld? */

  /* Uz?rind?ki yaz? */
  .gift-text {
    position: absolute;
    width: 100%;
    bottom: 15px;
    left: 50%;
    transform: translateX(-50%);
    color: #fff0f5;
    font-weight: 700;
    font-size: 1.1rem;
    user-select: none;
    text-shadow: 0 0 8px rgba(255, 182, 193, 0.9);
  }

  /* M?ktub stili */
  .letter {
    max-width: 320px;
    background: #fff;
    border-radius: 16px;
    padding: 20px 25px;
    box-shadow: 0 8px 24px rgba(255, 101, 132, 0.3);
    color: #4a2c25;
    font-size: 1.1rem;
    line-height: 1.5;
    user-select: text;
  }

  .letter h2 {
    margin-top: 0;
    font-weight: 700;
    color: #ff6584;
  }

  .letter p {
    margin: 10px 0;
  }

  .letter .touch-hint {
    margin-top: 20px;
    font-weight: 600;
    color: #c1275b;
    cursor: pointer;
  }

  /* Cic?k konteyner */
  .flower-container {
    position: relative;
    width: 220px;
    height: 220px;
    margin: 30px auto 0;
    display: none;
  }

  .flower-container.active {
    display: block;
  }

  /* Cic?k */
  .flower {
    position: relative;
    width: 220px;
    height: 220px;
    margin: 0 auto;
  }

  .petal {
    position: absolute;
    width: 90px;
    height: 130px;
    background: radial-gradient(circle at 40% 40%, #ff6584, #c1275b);
    border-radius: 50% 50% 50% 50% / 70% 70% 40% 40%;
    box-shadow: 0 4px 8px rgba(193, 39, 75, 0.5);
    top: 45px;
    left: 65px;
    transform-origin: bottom center;
    animation: sway 4s ease-in-out infinite;
    --angle: 0deg;
  }

  .petal:nth-child(1) { transform: rotate(0deg); animation-delay: 0s; --angle: 0deg;}
  .petal:nth-child(2) { transform: rotate(45deg); animation-delay: 0.5s; --angle: 45deg;}
  .petal:nth-child(3) { transform: rotate(90deg); animation-delay: 1s; --angle: 90deg;}
  .petal:nth-child(4) { transform: rotate(135deg); animation-delay: 1.5s; --angle: 135deg;}
  .petal:nth-child(5) { transform: rotate(180deg); animation-delay: 2s; --angle: 180deg;}
  .petal:nth-child(6) { transform: rotate(225deg); animation-delay: 2.5s; --angle: 225deg;}
  .petal:nth-child(7) { transform: rotate(270deg); animation-delay: 3s; --angle: 270deg;}
  .petal:nth-child(8) { transform: rotate(315deg); animation-delay: 3.5s; --angle: 315deg;}

  @keyframes sway {
    0%, 100% {
      transform: rotate(var(--angle)) translateY(0);
      filter: drop-shadow(0 2px 2px rgba(193,39,75,0.3));
    }
    50% {
      transform: rotate(calc(var(--angle) + 6deg)) translateY(-8px);
      filter: drop-shadow(0 5px 7px rgba(193,39,75,0.5));
    }
  }

  .center {
    position: absolute;
    top: 65%;
    left: 50%;
    width: 60px;
    height: 60px;
    background: radial-gradient(circle at center, #fff59d, #f9a825);
    border-radius: 50%;
    box-shadow:
      0 0 8px 3px #fff176,
      inset 0 0 12px 4px #fbc02d;
    animation: pulse 3s ease-in-out infinite;
    transform: translate(-50%, -30%);
  }

  @keyframes pulse {
    0%, 100% {
      box-shadow:
        0 0 8px 3px #fff176,
        inset 0 0 12px 4px #fbc02d;
      transform: translate(-50%, -30%) scale(1);
    }
    50% {
      box-shadow:
        0 0 15px 6px #fff176,
        inset 0 0 18px 6px #fbc02d;
      transform: translate(-50%, -30%) scale(1.1);
    }
  }

  /* Gul alt?ndak? yaz? */
  .flower-text {
    margin-top: -50px;
    font-weight: 600;
    font-size: 1.2rem;
    color: #c1275b;
    text-shadow: 0 0 4px #ffadc3;
  }
</style>
</head>
<body>

<!-- H?diyy? qutusu -->
<div class="gift-box" id="giftBox">
  <div class="gift-text">Ays?n Gulum<br>Buraya toxun</div>
</div>

<!-- M?ktub -->
<div class="letter" id="letter" style="display:none;">
  <h2>Bal?m,</h2>
  <p>Fikirl?sirdim s?n? nec? bir surpriz ed? bil?r?m dey?...</p>
  <p><strong>Bu m?ktubun icind?ki — s?nin ucundur.</strong></p>
  <p class="touch-hint" id="letterTouch">Buraya toxun</p>
</div>

<!-- Cic?k -->
<div class="flower-container" id="flowerContainer">
  <div class="flower">
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="petal"></div>
    <div class="center"></div>
  </div>
  <div class="flower-text">S?n gulun ozund?n d? daha goz?ls?n.</div>
</div>

<script>
  const giftBox = document.getElementById('giftBox');
  const letter = document.getElementById('letter');
  const flowerContainer = document.getElementById('flowerContainer');
  const letterTouch = document.getElementById('letterTouch');

  giftBox.addEventListener('click', () => {
    giftBox.style.display = 'none';
    letter.style.display = 'block';
  });

  letterTouch.addEventListener('click', () => {
    letter.style.display = 'none';
    flowerContainer.classList.add('active');
  });
</script>

</body>
</html>
