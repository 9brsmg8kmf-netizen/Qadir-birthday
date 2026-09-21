<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Qadir's 2nd Birthday Invitation!</title>
  <style>
    body {
      margin: 0;
      padding: 20px;
      background: #f0f8ff;
      font-family: 'Comic Sans MS', 'Chalkboard SE', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* Envelope Styles */
    .envelope-container {
      width: 320px;
      height: 220px;
      background: #d2b48c;
      border-radius: 8px;
      position: relative;
      cursor: pointer;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
      display: flex;
      justify-content: center;
      align-items: center;
      transition: transform 0.3s;
    }
    .envelope-container:hover {
      transform: scale(1.03);
    }
    .envelope-btn {
      background: #ff4500;
      color: white;
      padding: 12px 24px;
      font-size: 1.2rem;
      font-weight: bold;
      border-radius: 20px;
      border: none;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    /* Card Container */
    .card {
      display: none;
      width: 100%;
      max-width: 400px;
      background: #fff;
      border: 8px solid #ffd700;
      border-radius: 24px;
      padding: 20px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.15);
      position: relative;
      animation: popUp 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
    }

    @keyframes popUp {
      0% { opacity: 0; transform: scale(0.5) translateY(100px); }
      100% { opacity: 1; transform: scale(1) translateY(0); }
    }

    /* Floating Interactive Title */
    .title-letter {
      display: inline-block;
      font-size: 2.2rem;
      font-weight: bold;
      cursor: pointer;
      transition: transform 0.2s;
      user-select: none;
    }
    .title-letter:hover {
      animation: bounce 0.4s ease infinite alternate;
    }

    @keyframes bounce {
      0% { transform: translateY(0); }
      100% { transform: translateY(-10px); }
    }

    /* Event Details Box */
    .details-box {
      background: #f9f9f9;
      border-radius: 12px;
      padding: 15px;
      margin: 15px 0;
      text-align: left;
      font-size: 0.95rem;
      line-height: 1.6;
    }

    /* Interactive Balloons */
    .balloon-zone {
      display: flex;
      justify-content: space-around;
      margin-top: 15px;
    }
    .balloon {
      width: 50px;
      height: 65px;
      border-radius: 50% 50% 50% 50% / 40% 40% 60% 60%;
      cursor: pointer;
      position: relative;
      animation: float 2s ease-in-out infinite alternate;
      transition: transform 0.1s;
    }
    .balloon::after {
      content: "";
      position: absolute;
      bottom: -12px;
      left: 24px;
      width: 2px;
      height: 15px;
      background: #aaa;
    }

    @keyframes float {
      0% { transform: translateY(0); }
      100% { transform: translateY(-8px); }
    }

    .red { background: #ff4d4d; }
    .blue { background: #1e90ff; }
    .yellow { background: #ffd700; }
    .green { background: #3cb371; }

    .popped {
      visibility: hidden;
      pointer-events: none;
    }
  </style>
</head>
<body>

  <!-- TAP-TO-OPEN ENVELOPE -->
  <div class="envelope-container" id="envelope" onclick="openEnvelope()">
    <button class="envelope-btn">✉️ Tap to Open!</button>
  </div>

  <!-- INTERACTIVE CARD -->
  <div class="card" id="inviteCard">
    <h2 style="color: #e63946; margin-bottom: 5px;">Sesame Street Party!</h2>
    <p style="color: #457b9d; margin: 0 0 10px 0;">Can you tell me how excited we are?</p>

    <!-- FLOATING LETTERS -->
    <div>
      <span class="title-letter" style="color:#1e90ff" onclick="bounceLetter(this)">Q</span>
      <span class="title-letter" style="color:#ff4d4d" onclick="bounceLetter(this)">a</span>
      <span class="title-letter" style="color:#ffd700" onclick="bounceLetter(this)">d</span>
      <span class="title-letter" style="color:#3cb371" onclick="bounceLetter(this)">i</span>
      <span class="title-letter" style="color:#ff69b4" onclick="bounceLetter(this)">r</span>
      <span class="title-letter" style="color:#1e90ff" onclick="bounceLetter(this)">'</span>
      <span class="title-letter" style="color:#ff4d4d" onclick="bounceLetter(this)">s</span>
      <br />
      <span class="title-letter" style="color:#1e90ff; font-size: 2.8rem;" onclick="bounceLetter(this)">2nd Birthday!</span>
    </div>

    <!-- DETAILS -->
    <div class="details-box">
      📅 <strong>Date:</strong> Saturday, 30th January 2027<br />
      ⏰ <strong>Time:</strong> 3:00 PM<br />
      📍 <strong>Location:</strong> Lot 2 Delph Street, Campbellville[span_1](start_span)[span_1](end_span)
    </div>

    <p style="font-size: 0.85rem; color: #666;">Tap the balloons to pop them!</p>

    <!-- TAP TO POP BALLOONS -->
    <div class="balloon-zone">
      <div class="balloon red" onclick="popBalloon(this)"></div>
      <div class="balloon blue" onclick="popBalloon(this)"></div>
      <div class="balloon yellow" onclick="popBalloon(this)"></div>
      <div class="balloon green" onclick="popBalloon(this)"></div>
    </div>
  </div>

  <script>
    function openEnvelope() {
      document.getElementById('envelope').style.display = 'none';
      document.getElementById('inviteCard').style.display = 'block';
    }

    function bounceLetter(element) {
      element.style.transform = 'scale(1.4) rotate(10deg)';
      setTimeout(() => {
        element.style.transform = 'scale(1) rotate(0deg)';
      }, 200);
    }

    function popBalloon(element) {
      element.classList.add('popped');
    }
  </script>
</body>
</html>
