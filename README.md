<!-- index.php -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Beautiful Surprise Puzzle ❤️</title>

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family:'Poppins',sans-serif;
    }

    body{
      overflow:hidden;
      background:linear-gradient(135deg,#ffb6d9,#ffd6ec,#ffc2e2);
      height:100vh;
    }

    .floating-hearts span{
      position:absolute;
      bottom:-100px;
      color:#fff;
      font-size:20px;
      animation:float 10s linear infinite;
      opacity:0.7;
    }

    @keyframes float{
      0%{
        transform:translateY(0) rotate(0deg);
        opacity:0;
      }
      30%{
        opacity:1;
      }
      100%{
        transform:translateY(-120vh) rotate(360deg);
        opacity:0;
      }
    }

    .container{
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      height:100vh;
      position:relative;
      z-index:2;
      text-align:center;
      padding:20px;
    }

    h1{
      color:white;
      font-size:3rem;
      text-shadow:0 0 20px #ff4fa3;
      margin-bottom:20px;
      animation:glow 2s infinite alternate;
    }

    @keyframes glow{
      from{
        text-shadow:0 0 10px #ff5ca8;
      }
      to{
        text-shadow:0 0 25px #ff007f;
      }
    }

    .puzzle-box{
      width:320px;
      height:320px;
      background:white;
      border-radius:30px;
      padding:10px;
      box-shadow:0 0 30px rgba(255,255,255,0.7);
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:4px;
      margin-top:20px;
      overflow:hidden;
      animation:floatBox 3s ease-in-out infinite;
    }

    @keyframes floatBox{
      0%,100%{
        transform:translateY(0px);
      }
      50%{
        transform:translateY(-10px);
      }
    }

    .piece{
      background-image:url('https://images.unsplash.com/photo-1517841905240-472988babdf9?q=80&w=800&auto=format&fit=crop');
      background-size:300px 300px;
      border-radius:10px;
      transition:0.4s;
      cursor:pointer;
    }

    .piece:hover{
      transform:scale(1.05);
      box-shadow:0 0 15px hotpink;
    }

    .piece:nth-child(1){background-position:0 0;}
    .piece:nth-child(2){background-position:-100px 0;}
    .piece:nth-child(3){background-position:-200px 0;}
    .piece:nth-child(4){background-position:0 -100px;}
    .piece:nth-child(5){background-position:-100px -100px;}
    .piece:nth-child(6){background-position:-200px -100px;}
    .piece:nth-child(7){background-position:0 -200px;}
    .piece:nth-child(8){background-position:-100px -200px;}
    .piece:nth-child(9){background-position:-200px -200px;}

    .btn{
      margin-top:30px;
      padding:15px 40px;
      border:none;
      border-radius:50px;
      background:linear-gradient(45deg,#ff4fa3,#ff8ad4);
      color:white;
      font-size:1.2rem;
      cursor:pointer;
      transition:0.4s;
      box-shadow:0 0 20px rgba(255,0,128,0.4);
    }

    .btn:hover{
      transform:scale(1.1);
      box-shadow:0 0 30px hotpink;
    }

    .note{
      position:absolute;
      width:100%;
      height:100vh;
      background:linear-gradient(135deg,#ffb6d9,#ffe1f2);
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      top:100%;
      left:0;
      transition:1s;
      z-index:10;
      overflow:hidden;
    }

    .note.active{
      top:0;
    }

    .message-box{
      background:rgba(255,255,255,0.3);
      backdrop-filter:blur(15px);
      padding:40px;
      border-radius:30px;
      width:80%;
      max-width:700px;
      box-shadow:0 0 30px rgba(255,255,255,0.5);
      animation:popup 1s ease;
    }

    @keyframes popup{
      from{
        transform:scale(0.5);
        opacity:0;
      }
      to{
        transform:scale(1);
        opacity:1;
      }
    }

    .message-box h2{
      color:#ff007f;
      font-size:3rem;
      margin-bottom:20px;
    }

    .message-box p{
      color:#7a0045;
      font-size:1.3rem;
      line-height:2;
    }

    .sparkle{
      position:absolute;
      width:10px;
      height:10px;
      background:white;
      border-radius:50%;
      animation:spark 4s linear infinite;
      opacity:0.8;
    }

    @keyframes spark{
      0%{
        transform:translateY(0) scale(0);
        opacity:0;
      }
      50%{
        opacity:1;
      }
      100%{
        transform:translateY(-800px) scale(1.5);
        opacity:0;
      }
    }

    .love-text{
      margin-top:25px;
      font-size:1.4rem;
      color:#ff0080;
      animation:pulse 2s infinite;
    }

    @keyframes pulse{
      0%,100%{
        transform:scale(1);
      }
      50%{
        transform:scale(1.08);
      }
    }

  </style>
</head>
<body>

<div class="floating-hearts"></div>

<div class="container">
  <h1>✨ Solve The Heart Puzzle ✨</h1>

  <div class="puzzle-box">
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
    <div class="piece"></div>
  </div>

  <button class="btn" onclick="showNote()">
    Open Surprise ❤️
  </button>
</div>

<div class="note" id="notePage">

  <div class="message-box">
    <h2>💖 Surprise Note 💖</h2>

    <p>
      You are the most beautiful part of every moment... ✨<br><br>

      Your smile feels like magic 🌸<br>
      Your eyes shine brighter than stars 🌙<br>
      Every conversation with you feels special 💕<br><br>

      If happiness had a face, it would probably look like you ❤️
    </p>

    <div class="love-text">
      Forever a beautiful vibe ✨💗
    </div>
  </div>

</div>

<script>

  const heartsContainer = document.querySelector('.floating-hearts');

  for(let i=0;i<40;i++){
    let heart = document.createElement('span');
    heart.innerHTML='💖';

    heart.style.left=Math.random()*100+'vw';
    heart.style.animationDuration=(Math.random()*5+5)+'s';
    heart.style.fontSize=(Math.random()*20+15)+'px';

    heartsContainer.appendChild(heart);
  }

  function showNote(){
    document.getElementById('notePage').classList.add('active');
    createSparkles();
  }

  function createSparkles(){

    for(let i=0;i<80;i++){

      let sparkle=document.createElement('div');
      sparkle.classList.add('sparkle');

      sparkle.style.left=Math.random()*100+'vw';
      sparkle.style.top=Math.random()*100+'vh';
      sparkle.style.animationDuration=(Math.random()*3+2)+'s';

      document.body.appendChild(sparkle);

      setTimeout(()=>{
        sparkle.remove();
      },5000);
    }
  }

</script>

</body>
</html>
