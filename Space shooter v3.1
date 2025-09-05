<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Star Wars Space Shooter Complet</title>
<style>
  body { margin:0; background:black; display:flex; justify-content:center; align-items:center; height:100vh; overflow:hidden;}
  canvas { border:2px solid white;}
</style>
</head>
<body>
<canvas id="gameCanvas" width="400" height="600"></canvas>
<script>
const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

// Audio
const laserSound = new Audio('laser.mp3');
const explosionSound = new Audio('explosion.mp3');

const ship = { x: 180, y: 550, width: 40, height: 40, speed: 8 };
let bullets = [];
let enemies = [];
let stars = [];
let explosions = [];
let powerUps = [];
let frame = 0;
let score = 0;
let gameOver = false;
let shootSpeed = 10;

// Créer étoiles pour fond spatial
for(let i=0;i<100;i++){
  stars.push({x:Math.random()*canvas.width, y:Math.random()*canvas.height, size:Math.random()*2+1, speed:Math.random()*1+0.5});
}

// Contrôles
let keys = {};
document.addEventListener("keydown", e=>keys[e.key]=true);
document.addEventListener("keyup", e=>keys[e.key]=false);

// Tir
function shoot() {
  bullets.push({ x: ship.x + ship.width/2 - 5, y: ship.y, width: 10, height: 20 });
  laserSound.currentTime = 0;
  laserSound.play();
}

// Créer ennemis avec types différents et difficulté croissante
function createEnemy() {
  const difficultyFactor = 0.01 * score; 
  const type = Math.random() < 0.7 - difficultyFactor ? "tie" : "destroyer";
  const x = Math.random() * (canvas.width - 40);
  if(type==="tie") enemies.push({ x:x, y:-40, width:40, height:40, speed:2 + score/50, hp:1, type:"tie"});
  else enemies.push({ x:x, y:-60, width:60, height:60, speed:1 + score/100, hp:2, type:"destroyer"});
}

// Créer power-up aléatoire
function createPowerUp() {
  const x = Math.random()*(canvas.width-30);
  powerUps.push({x:x, y:-30, width:30, height:30, type:"rapid"});
}

// Collision
function collision(a,b) {
  return a.x < b.x + b.width && a.x + a.width > b.x &&
         a.y < b.y + b.height && a.y + a.height > b.y;
}

// Boucle de jeu
function update() {
  if(gameOver) return;

  ctx.clearRect(0,0,canvas.width,canvas.height);

  // Dessiner étoiles
  ctx.fillStyle="white";
  for(let s of stars){
    ctx.fillRect(s.x,s.y,s.size,s.size);
    s.y += s.speed + score/100;
    if(s.y>canvas.height) s.y=0;
  }

  // Déplacement vaisseau
  if(keys["ArrowLeft"] && ship.x>0) ship.x -= ship.speed;
  if(keys["ArrowRight"] && ship.x+ship.width<canvas.width) ship.x += ship.speed;
  if(keys[" "] && frame%shootSpeed===0) shoot();

  // Dessiner vaisseau
  ctx.font="30px Arial";
  ctx.fillText("🛸", ship.x, ship.y+30);

  // Déplacer et dessiner balles
  for(let i=bullets.length-1;i>=0;i--){
    let b = bullets[i];
    b.y -= 12;
    ctx.fillStyle="lime";
    ctx.fillRect(b.x,b.y,b.width,b.height);
    if(b.y+b.height<0) bullets.splice(i,1);
  }

  // Créer ennemis
  const enemyInterval = Math.max(20, 50 - Math.floor(score/10));
  if(frame % enemyInterval ===0) createEnemy();
  if(frame%800===0) createPowerUp();

  // Déplacer et dessiner ennemis
  ctx.font="30px Arial";
  for(let i=enemies.length-1;i>=0;i--){
    let e = enemies[i];
    e.y += e.speed;
    ctx.fillText(e.type==="tie"?"🔴":"⬛", e.x, e.y+e.height);

    // Collision vaisseau
    if(collision(e,ship)) gameOver=true;

    // Collision balles
    for(let j=bullets.length-1;j>=0;j--){
      if(collision(e,bullets[j])){
        e.hp--;
        bullets.splice(j,1);
        if(e.hp<=0){
          explosions.push({x:e.x, y:e.y, life:20});
          explosionSound.currentTime = 0;
          explosionSound.play();
          enemies.splice(i,1);
          score += e.type==="tie"?1:3;
        }
        break;
      }
    }

    // Ennemi hors écran
    if(e.y>canvas.height) enemies.splice(i,1);
  }

  // Déplacer et dessiner power-ups
  for(let i=powerUps.length-1;i>=0;i--){
    let p = powerUps[i];
    p.y += 2;
    ctx.font="25px Arial";
    ctx.fillText("💚",p.x,p.y+p.height);
    if(collision(p,ship)){
      shootSpeed = 5;
      setTimeout(()=>{shootSpeed=10},5000);
      powerUps.splice(i,1);
    }
    if(p.y>canvas.height) powerUps.splice(i,1);
  }

  // Dessiner explosions
  for(let i=explosions.length-1;i>=0;i--){
    let exp = explosions[i];
    ctx.font="20px Arial";
    ctx.fillText("💥", exp.x, exp.y);
    exp.life--;
    if(exp.life<=0) explosions.splice(i,1);
  }

  // Afficher score
  ctx.fillStyle="white";
  ctx.font="20px Arial";
  ctx.fillText("Score: "+score,10,30);

  frame++;
  requestAnimationFrame(update);
}

update();
</script>
</body>
</html>
