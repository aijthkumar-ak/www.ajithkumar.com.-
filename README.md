
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Birthday Love Animation</title>

<style>

body{
  margin:0;
  background:linear-gradient(white);
  overflow:hidden;
  height:100vh;
  position:relative;
  font-family:Arial, sans-serif;
}

/* Top Happy Birthday text */
.top-text{
  position:absolute;
  top:40px;
  width:100%;
  text-align:center;
  font-size:40px;
  color:#000080;
  font-weight:bold;
}

/* Bottom Name text moving up & down */
.bottom-name{
  position:absolute;
  bottom:40px;
  width:100%;
  text-align:center;
  font-size:90px;
  color:#00FF00;
  font-weight:bold;
  animation:moveName 0.8s infinite alternate;
}

/* Speed up-down animation */
@keyframes moveName{
  from{ transform:translateY(0); }
  to{ transform:translateY(-25px); }
}

/* Heart style */
.heart{
  position:absolute;
  width:30px;
  height:30px;
  background:red;
  clip-path: polygon(
    50% 0%, 61% 35%, 98% 35%, 68% 57%,
    79% 91%, 50% 70%, 21% 91%, 32% 57%,
    2% 35%, 39% 35%
  );
  opacity:0.8;
  animation:floatUp 8s linear forwards;
}

/* Heart floating animation */
@keyframes floatUp{
  0%{
    transform:translateY(100vh) scale(0.5);
    opacity:0;
  }
  10%{opacity:1;}
  100%{
    transform:translateY(-200px) scale(1);
    opacity:0;
  }
}

</style>
</head>

<body>

<div class="top-text">🎉 Happy Birthday 🎉</div>

<div class="bottom-name">Sowmiii💖</div>

<script>

const totalHearts=30;

for(let i=0;i<totalHearts;i++){
  const heart=document.createElement('div');
  heart.className='heart';

  heart.style.left=Math.random()*100+'vw';

  const delay=Math.random()*5;
  heart.style.animationDelay=delay+'s';

  const size=20+Math.random()*20;
  heart.style.width=size+'px';
  heart.style.height=size+'px';

  document.body.appendChild(heart);
}

</script>

</body>
</html>
