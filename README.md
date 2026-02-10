<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Valentine 💕</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: #ffd6e8;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: Arial, sans-serif;
    }

    .page {
      text-align: center;
      display: none;
    }

    .active {
      display: block;
    }

    h1 {
      color: #ff4d88;
      margin-bottom: 30px;
    }

    .buttons {
      width: 100%;
      display: flex;
      justify-content: space-between;
      padding: 0 40px;
    }

    button {
      background: #ff80aa;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 18px;
      border-radius: 20px;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      transition: transform 0.2s;
    }

    button:active {
      transform: scale(0.9);
    }

    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      padding: 20px 30px;
      border-radius: 15px;
      color: #ff4d88;
      font-size: 20px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.25);
      display: none;
    }
  </style>
</head>
<body>

  <!-- Bubble sound -->
  <audio id="bubble">
    <source src="https://www.myinstants.com/media/sounds/bubble-pop.mp3" type="audio/mpeg">
  </audio>

  <!-- Page 1 -->
  <div class="page active" id="page1">
    <h1>will u be my valentine? 💕</h1>
    <div class="buttons">
      <button onclick="yesClick()">YES</button>
      <button onclick="noClick()">NO</button>
    </div>
  </div>

  <!-- Page 2 -->
  <div class="page" id="page2">
    <h1>wow, u saved ur fingers 😌💗</h1>
    <button onclick="nextPage()">next</button>
  </div>

  <!-- Page 3 -->
  <div class="page" id="page3">
    <h1>what's the plan? 😒💕</h1>
  </div>

  <!-- Popup -->
  <div class="popup" id="popup"></div>

  <script>
    const bubble = document.getElementById("bubble");
    const popup = document.getElementById("popup");

    function playSound() {
      bubble.currentTime = 0;
      bubble.play();
    }

    function showPopup(text) {
      popup.textContent = text;
      popup.style.display = "block";
      setTimeout(() => {
        popup.style.display = "none";
      }, 1500);
    }

    function noClick() {
      playSound();
      showPopup("r u sure?");
    }

    function yesClick() {
      playSound();
      document.getElementById("page1").classList.remove("active");
      document.getElementById("page2").classList.add("active");
    }

    function nextPage() {
      playSound();
      document.getElementById("page2").classList.remove("active");
      document.getElementById("page3").classList.add("active");
    }
  </script>

</body>
</html>
