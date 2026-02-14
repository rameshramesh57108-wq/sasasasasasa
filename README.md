<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Mihira ❤️</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins', sans-serif;
}

body{
  height:100vh;
  overflow:hidden;
  background: linear-gradient(135deg, #ffd6e8, #ffeaf4, #ffc2dd);
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
  position:relative;
}

.container{
  width:90%;
  max-width:600px;
  padding:30px;
  background:rgba(255,255,255,0.85);
  border-radius:20px;
  box-shadow:0 10px 30px rgba(0,0,0,0.1);
  position:relative;
  transition:opacity 0.5s ease, transform 0.5s ease;
}

.hidden{
  display:none;
}

h1{
  font-size:1.8rem;
  margin-bottom:20px;
  color:#d63384;
}

p{
  font-size:1rem;
  margin-bottom:20px;
  color:#444;
  line-height:1.6;
}

button{
  padding:10px 20px;
  border:none;
  border-radius:25px;
  margin:10px;
  cursor:pointer;
  font-size:1rem;
  transition:0.3s;
}

.yes-btn{
  background:#ff4d88;
  color:white;
}

button:hover{
  transform:scale(1.1);
}

/* Rose petals */
.petal{
  position:fixed;
  top:-20px;
  width:12px;
  height:18px;
  background:#ff4d6d;
  border-radius:50% 50% 50% 0;
  transform:rotate(45deg);
  opacity:0.8;
  animation:fall linear forwards;
}
@keyframes fall{
  to{transform:translateY(110vh) rotate(360deg);}
}

/* Final text and cat emoji */
#finalPopup{
  display:none;
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%, -50%);
  text-align:center;
  z-index:100;
}

#finalPopup h1{
  font-size:2.5rem;
  color:#d63384;
  margin-bottom:15px;
  animation:popText 1.5s ease forwards;
}

#finalPopup p{
  font-size:1.2rem;
  margin-bottom:15px;
  animation:fadeInText 2s ease forwards;
}

#finalCat{
  font-size:5rem;
  display:block;
  margin:0 auto 20px auto;
  transform:scale(0);
  animation:catPop 1s ease forwards;
}

@keyframes popText{
  0%{transform:scale(0); opacity:0;}
  60%{transform:scale(1.2);}
  100%{transform:scale(1); opacity:1;}
}

@keyframes fadeInText{
  from{opacity:0; transform:translateY(20px);}
  to{opacity:1; transform:translateY(0);}
}

@keyframes catPop{
  0%{transform:scale(0);}
  60%{transform:scale(1.3);}
  100%{transform:scale(1);}
}

</style>
</head>
<body>

<!-- Page 1 -->
<div class="container" id="page1">
  <h1>Hello Mihira ❤️</h1>
  <p>Your so-called boyfriend has something to tell you this Valentine’s Day… Would you like to proceed? 🥺</p>
  <button class="yes-btn" onclick="nextPage(2)">Yes</button>
</div>

<!-- Page 2 -->
<div class="container hidden" id="page2">
  <h1>Before I Ask You Something… 💌</h1>
  <p>
    These last few months have been a little crazy.  
    But out of everything, <b>you</b> are the best thing that has happened to me.  
    I know I’m not perfect, but I’m trying every day to be better.  
    I’ve never been more sure about anything than I am about this.  
  </p>
  <button class="yes-btn" onclick="nextPage(3)">Continue 💖</button>
</div>

<!-- Page 3 -->
<div class="container hidden" id="page3">
  <h1>Will You Be My Valentine? 💍💖</h1>
  <button class="yes-btn" onclick="showFinalPopup()">Yes</button>
  <button class="yes-btn" onclick="showFinalPopup()">Aama</button>
  <button class="yes-btn" onclick="showFinalPopup()">Avunu</button>
</div>

<!-- Final Popup -->
<div id="finalPopup">
  <div id="finalCat">😽</div>
  <h1>I Love U Mihi ❤️</h1>
  <p>And trust me… choosing me will be the best decision you ever made.</p>
</div>

<script>
function nextPage(page){
  document.getElementById("page1").classList.add("hidden");
  document.getElementById("page2").classList.add("hidden");
  document.getElementById("page3").classList.add("hidden");
  document.getElementById("page"+page).classList.remove("hidden");
}

/* Show final popup with rose petals */
function showFinalPopup(){
  for(let i=0;i<30;i++){
    createPetal(i*100);
  }
  setTimeout(()=>{
    document.getElementById("finalPopup").style.display="block";
  },300);
}

/* Rose petals */
function createPetal(delay){
  setTimeout(()=>{
    const petal=document.createElement("div");
    petal.classList.add("petal");
    petal.style.left=Math.random()*100+"vw";
    petal.style.animationDuration=(Math.random()*4+4)+"s";
    document.body.appendChild(petal);
    setTimeout(()=>petal.remove(),8000);
  },delay);
}
</script>

</body>
</html>
