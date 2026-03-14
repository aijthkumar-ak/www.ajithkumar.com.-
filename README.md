<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Love Family Birthday Animation</title>
<style>
  body {
    margin: 0;
    padding: 0;
    overflow: hidden;
    font-family: Arial, sans-serif;
    position: relative;
    height: 100vh;
    background: #ffe6f0; /* Light pink background */
  }

  /* Love emojis animation container */
  .emoji-container {
    position: absolute;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  /* Individual emoji styles */
  .emoji {
    position: absolute;
    font-size: 24px;
    animation: floatUp 20s linear forwards;
  }

  @keyframes floatUp {
    0% {
      transform: translateY(100vh) translateX(0);
      opacity: 1;
    }
    100% {
      transform: translateY(-10vh) translateX(20px);
      opacity: 0;
    }
  }

  /* Top birthday wish box */
  .top-box {
    position: fixed;
    top: 20px;
    width: 90%;
    max-width: 600px;
    margin: 0 auto;
    padding: 15px;
    background-color:#ffe6f0;
    border-radius: 10px;
    text-align: center;
    font-size: 1.5em;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
  }

  /* Bottom name box */
  .bottom-box {
    position: fixed;
    bottom: 20px;
    width: 90%;
    max-width: 600px;
    margin: 0 auto;
    padding: 15px;
    background-color:#ffe6f0;
    border-radius: 10px;
    text-align: center;
    font-size: 1.5em;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
  }
</style>
</head>
<body>

<!-- Love Emoji Moving Animation -->
<div class="emoji-container" id="emojiContainer"></div>

<!-- Top Birthday Wishes -->
<div class="top-box">
  ✨Happy Birthday to You paa🌹!
</div>

<!-- Bottom Name Box -->
<div class="bottom-box">
  💃Sowmiii👀❤️
</div>

<script>
  const emojiContainer = document.getElementById('emojiContainer');

  // Function to generate random emojis and animate them
  function createEmoji() {
    const emoji = document.createElement('div');
    emoji.className = 'emoji';
    emoji.innerHTML = '❤️'; // Love emoji, you can add more emojis if desired

    // Random horizontal start position
    const startX = Math.random() * 100;
    emoji.style.left = startX + 'vw';

    // Random size
    const size = Math.random() * 10 + 20; // 20px to 30px
    emoji.style.fontSize = size + 'px';

    // Random delay
    const delay = Math.random() * 10; // 0 to 10 seconds
    emoji.style.animationDelay = delay + 's';

    // Append and remove after animation
    emojiContainer.appendChild(emoji);

    // Remove emoji after animation duration
    setTimeout(() => {
      emoji.remove();
    }, (20 + delay) * 1000); // 20s animation + delay
  }

  // Generate emojis periodically
  setInterval(createEmoji, 300); // Every 300ms create a new emoji

  // Optional: create some at start
  for(let i=0; i<20; i++) {
    createEmoji();
  }
</script>

</body>
</html>
