<style>
  .graduation-container {
    text-align: center;
    padding: 60px 20px;
    min-height: 80vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
  }

  .graduation-title {
    font-size: 4rem;
    font-weight: bold;
    margin: 30px 0;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadeInUp 1s ease-out;
  }

  /* Graduation Cap */
  .graduation-cap {
    width: 200px;
    height: 200px;
    position: relative;
    margin: 40px auto;
    animation: float 3s ease-in-out infinite;
  }

  .cap-top {
    width: 200px;
    height: 10px;
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
    position: absolute;
    top: 50px;
    border-radius: 2px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
  }

  .cap-top:before {
    content: '';
    width: 180px;
    height: 180px;
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
    position: absolute;
    top: -90px;
    left: 10px;
    border-radius: 50% 50% 0 0;
    box-shadow: 0 -5px 20px rgba(0,0,0,0.2);
  }

  .cap-button {
    width: 20px;
    height: 20px;
    background: #ffd700;
    border-radius: 50%;
    position: absolute;
    top: -10px;
    left: 90px;
    box-shadow: 0 5px 15px rgba(255,215,0,0.5);
  }

  .tassel {
    width: 3px;
    height: 60px;
    background: linear-gradient(180deg, #ffd700 0%, #ffed4e 100%);
    position: absolute;
    top: 10px;
    left: 98px;
    transform-origin: top;
    animation: swing 2s ease-in-out infinite;
  }

  .tassel:after {
    content: '';
    width: 15px;
    height: 15px;
    background: #ffd700;
    position: absolute;
    bottom: -7px;
    left: -6px;
    border-radius: 50%;
  }

  /* Balloons */
  .balloon {
    width: 80px;
    height: 95px;
    border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
    position: absolute;
    animation: float-balloon 4s ease-in-out infinite;
    bottom: -100px;
  }

  .balloon:before {
    content: '';
    width: 2px;
    height: 80px;
    background: rgba(0,0,0,0.2);
    position: absolute;
    bottom: -80px;
    left: 39px;
  }

  .balloon:after {
    content: '▼';
    position: absolute;
    bottom: -5px;
    left: 32px;
    font-size: 10px;
    color: inherit;
  }

  .balloon-1 {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    left: 10%;
    animation-delay: 0s;
    animation-duration: 6s;
  }

  .balloon-2 {
    background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
    left: 25%;
    animation-delay: 1s;
    animation-duration: 5s;
  }

  .balloon-3 {
    background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
    left: 40%;
    animation-delay: 2s;
    animation-duration: 7s;
  }

  .balloon-4 {
    background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);
    right: 35%;
    animation-delay: 0.5s;
    animation-duration: 6.5s;
  }

  .balloon-5 {
    background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);
    right: 20%;
    animation-delay: 1.5s;
    animation-duration: 5.5s;
  }

  .balloon-6 {
    background: linear-gradient(135deg, #30cfd0 0%, #330867 100%);
    right: 5%;
    animation-delay: 2.5s;
    animation-duration: 6s;
  }

  /* Confetti */
  .confetti {
    width: 10px;
    height: 10px;
    background: #ffd700;
    position: absolute;
    animation: confetti-fall 3s linear infinite;
  }

  .confetti:nth-child(1) { left: 10%; animation-delay: 0s; background: #667eea; }
  .confetti:nth-child(2) { left: 20%; animation-delay: 0.5s; background: #f5576c; }
  .confetti:nth-child(3) { left: 30%; animation-delay: 1s; background: #00f2fe; }
  .confetti:nth-child(4) { left: 40%; animation-delay: 1.5s; background: #38f9d7; }
  .confetti:nth-child(5) { left: 50%; animation-delay: 2s; background: #fee140; }
  .confetti:nth-child(6) { left: 60%; animation-delay: 0.7s; background: #764ba2; }
  .confetti:nth-child(7) { left: 70%; animation-delay: 1.2s; background: #f093fb; }
  .confetti:nth-child(8) { left: 80%; animation-delay: 1.8s; background: #4facfe; }
  .confetti:nth-child(9) { left: 90%; animation-delay: 2.3s; background: #43e97b; }

  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
  }

  @keyframes swing {
    0%, 100% { transform: rotate(-5deg); }
    50% { transform: rotate(5deg); }
  }

  @keyframes float-balloon {
    0% { 
      transform: translateY(0) translateX(0);
      bottom: -100px;
    }
    100% { 
      transform: translateY(-20px) translateX(20px);
      bottom: 100vh;
    }
  }

  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes confetti-fall {
    0% {
      transform: translateY(0) rotate(0deg);
      opacity: 1;
      top: 0;
    }
    100% {
      transform: translateY(100vh) rotate(360deg);
      opacity: 0;
      top: 100vh;
    }
  }

  @media (max-width: 768px) {
    .graduation-title {
      font-size: 2.5rem;
    }
    .graduation-cap {
      width: 150px;
      height: 150px;
    }
    .cap-top {
      width: 150px;
    }
  }
</style>

<div class="graduation-container">
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>
  <div class="confetti"></div>

  <div class="graduation-cap">
    <div class="cap-top">
      <div class="cap-button"></div>
    </div>
    <div class="tassel"></div>
  </div>

  <h1 class="graduation-title">🎓 Projeto Alvaro Diplomado 🎓</h1>

  <div class="balloon balloon-1"></div>
  <div class="balloon balloon-2"></div>
  <div class="balloon balloon-3"></div>
  <div class="balloon balloon-4"></div>
  <div class="balloon balloon-5"></div>
  <div class="balloon balloon-6"></div>
</div>
