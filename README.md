<!Ajithkumar>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Birthday Wishes on Photo</title>
<style>
  body {
    margin: 0;
    font-family: 'Arial', sans-serif;
  }

  /* Container with background image (your photo) */
  .container {
    position: relative;
    width: 100%;
    height: 100vh; /* Full viewport height */
    background-image: url('your-photo.jpg'); /* Replace with your photo URL or path */
    background-size: cover;
    background-position: center;
  }

  /* Overlay for message and button */
  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;
    background: rgba(0, 0, 0, 0.3); /* Optional: dark overlay for better text visibility */
  }

  /* Top message styling */
  .top {
    text-align: center;
    color: white;
    margin-top: 40px;
  }

  .top h1 {
    font-size: 2em;
    margin-bottom: 20px;
  }

  /* Bottom button container */
  .bottom {
    width: 100%;
    position: relative;
    height: 100px;
  }

  /* Thanks button styles */
  #thanksBtn {
    position: absolute;
    padding: 12px 24px;
    font-size: 1.2em;
    background-color: #ff7043;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    top: 50%;
    transform: translateY(-50%);
  }
</style>
</head>
<body>

<div class="container">
  <div class="overlay">
    <!-- Top message -->
    <div class="top" id="birthdayMessage">
      <!-- Dynamic message will be inserted here -->
    </div>
    <!-- Bottom moving button -->
    <div class="bottom">
      <button id="thanksBtn">Thanks</button>
    </div>
  </div>
</div>

<script>
  // Set user's name
  const userName = "Sowmiiii"; // Change as needed
  const messageDiv = document.getElementById('birthdayMessage');
  messageDiv.innerHTML = `<h1>Happy Birthday, ${userName}! 🎉🎂🎈</h1>
                          <p>Wishing you a fantastic year ahead filled with adventure and joy!</p>`;

  const btn = document.getElementById('thanksBtn');

  // Function to automatically move the button left and right
  let direction = 1; // 1 for right, -1 for left
  function moveButton() {
    const parentWidth = document.querySelector('.bottom').clientWidth;
    const btnWidth = btn.offsetWidth;
    let currentX = btn.offsetLeft;

    if (currentX + btnWidth >= parentWidth) {
      direction = -1;
    } else if (currentX <= 0) {
      direction = 1;
    }

    btn.style.left = (currentX + direction * 5) + 'px';

    requestAnimationFrame(moveButton);
  }

  // Start the movement
  moveButton();

  // Center the button on click
  btn.addEventListener('click', () => {
    const parentWidth = document.querySelector('.bottom').clientWidth;
    const btnWidth = btn.offsetWidth;
    btn.style.left = (parentWidth / 2 - btnWidth / 2) + 'px';
  });
</script>

</body>
</html>
