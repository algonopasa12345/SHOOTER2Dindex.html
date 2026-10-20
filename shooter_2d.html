<!doctype html>
<html lang="es">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Neon Assault - Shooter 2D</title>
<style>
  *{box-sizing:border-box} html,body{margin:0;height:100%;overflow:hidden;background:#080b12;color:#fff;font-family:Arial,sans-serif}
  canvas{display:block;width:100vw;height:100vh;cursor:crosshair;background:radial-gradient(circle at center,#151d2c 0,#090d15 65%,#05070b 100%)}
  #ui{position:fixed;inset:0;pointer-events:none}
  .top{display:flex;justify-content:space-between;padding:18px 22px;font-weight:800;text-shadow:0 2px 6px #000}
  .left,.right{display:flex;gap:18px;align-items:center}
  .bar{width:220px;height:18px;border:2px solid #fff5;border-radius:20px;overflow:hidden;background:#0008}
  #hp{height:100%;width:100%;background:linear-gradient(90deg,#ff334f,#ff7a4b)}
  #center{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);text-align:center;background:#080b12dd;border:1px solid #ffffff22;padding:28px 34px;border-radius:18px;pointer-events:auto;min-width:320px;box-shadow:0 20px 70px #000b}
  h1{margin:0 0 10px;font-size:42px;letter-spacing:2px;color:#61eaff;text-shadow:0 0 20px #00d9ff88}
  p{color:#c7d0df;line-height:1.5}
  button{border:0;border-radius:12px;padding:13px 24px;font-size:17px;font-weight:800;background:#61eaff;color:#041017;cursor:pointer;box-shadow:0 0 25px #00d9ff55}
  button:hover{transform:scale(1.04)}
  #waveMsg{position:absolute;top:22%;left:50%;transform:translateX(-50%);font-size:34px;font-weight:900;opacity:0;text-shadow:0 0 20px #61eaff}
  .small{font-size:13px;color:#8f9bad}
</style>
</head>
<body>
<canvas id="game"></canvas>
<div id="ui">
  <div class="top">
    <div class="left"><span>❤️ VIDA</span><div class="bar"><div id="hp"></div></div></div>
    <div class="right"><span>⭐ <b id="score">0</b></span><span>🌊 OLEADA <b id="wave">1</b></span></div>
  </div>
  <div id="waveMsg"></div>
  <div id="center">
    <h1>NEON ASSAULT</h1>
    <p><b>WASD</b> para moverte · <b>Ratón</b> para apuntar<br><b>Clic izquierdo</b> para disparar</p>
    <button id="start">JUGAR</button>
    <p class="small">Sobrevive el mayor número de oleadas posible.</p>
  </div>
</div>
<script>
const c=document.getElementById('game'),x=c.getContext('2d');
const hpEl=document.getElementById('hp'),scoreEl=document.getElementById('score'),waveEl=document.getElementById('wave'),center=document.getElementById('center'),waveMsg=document.getElementById('waveMsg');
let W,H,dpr=Math.min(devicePixelRatio||1,2),running=false,last=0,score=0,wave=1,toSpawn=0,spawnTimer=0,between=false;
const keys={},mouse={x:0,y:0,down:false}; let bullets=[],enemies=[],particles=[];
const player={x:0,y:0,r:18,speed:300,hp:100,maxHp:100,angle:0,fireCd:0,inv:0};
function resize(){W=innerWidth;H=innerHeight;c.width=W*dpr;c.height=H*dpr;c.style.width=W+'px';c.style.height=H+'px';x.setTransform(dpr,0,0,dpr,0,0)} addEventListener('resize',resize);resize();
addEventListener('keydown',e=>keys[e.key.toLowerCase()]=true);addEventListener('keyup',e=>keys[e.key.toLowerCase()]=false);
c.addEventListener('mousemove',e=>{mouse.x=e.clientX;mouse.y=e.clientY});c.addEventListener('mousedown',()=>mouse.down=true);addEventListener('mouseup',()=>mouse.down=false);
function reset(){score=0;wave=1;bullets=[];enemies=[];particles=[];player.x=W/2;player.y=H/2;player.hp=100;player.inv=0;toSpawn=5;spawnTimer=.4;between=false;updateUI()}
document.getElementById('start').onclick=()=>{reset();center.style.display='none';running=true;last=performance.now();requestAnimationFrame(loop)};
function updateUI(){hpEl.style.width=Math.max(0,player.hp)+'%';scoreEl.textContent=score;waveEl.textContent=wave}
function shoot(){const a=Math.atan2(mouse.y-player.y,mouse.x-player.x);bullets.push({x:player.x+Math.cos(a)*26,y:player.y+Math.sin(a)*26,vx:Math.cos(a)*720,vy:Math.sin(a)*720,r:4,life:1.1});player.fireCd=.13;burst(player.x+Math.cos(a)*25,player.y+Math.sin(a)*25,'#61eaff',3)}
function spawnEnemy(){let side=Math.floor(Math.random()*4),ex,ey;if(side===0){ex=Math.random()*W;ey=-30}else if(side===1){ex=W+30;ey=Math.random()*H}else if(side===2){ex=Math.random()*W;ey=H+30}else{ex=-30;ey=Math.random()*H}let tough=Math.random()<Math.min(.12+wave*.025,.4);enemies.push({x:ex,y:ey,r:tough?24:16,hp:tough?3:1,speed:(tough?70:105)+wave*7,tough,hit:0})}
function burst(px,py,color,n=8){for(let i=0;i<n;i++){let a=Math.random()*Math.PI*2,s=Math.random()*150+40;particles.push({x:px,y:py,vx:Math.cos(a)*s,vy:Math.sin(a)*s,life:.35+Math.random()*.35,max:.7,color})}}
function nextWave(){between=true;wave++;updateUI();waveMsg.textContent='OLEADA '+wave;waveMsg.style.opacity=1;setTimeout(()=>waveMsg.style.opacity=0,1200);setTimeout(()=>{toSpawn=4+wave*2;spawnTimer=.2;between=false},1500)}
function gameOver(){running=false;center.style.display='block';center.innerHTML=`<h1>GAME OVER</h1><p>Puntuación: <b>${score}</b><br>Has llegado a la oleada <b>${wave}</b></p><button id="again">VOLVER A JUGAR</button><p class="small">WASD · Ratón · Clic para disparar</p>`;document.getElementById('again').onclick=()=>{reset();center.style.display='none';running=true;last=performance.now();requestAnimationFrame(loop)}}
function update(dt){
 let dx=(keys.d?1:0)-(keys.a?1:0),dy=(keys.s?1:0)-(keys.w?1:0),l=Math.hypot(dx,dy)||1;player.x+=dx/l*player.speed*dt;player.y+=dy/l*player.speed*dt;player.x=Math.max(player.r,Math.min(W-player.r,player.x));player.y=Math.max(player.r,Math.min(H-player.r,player.y));player.angle=Math.atan2(mouse.y-player.y,mouse.x-player.x);player.fireCd-=dt;player.inv-=dt;if(mouse.down&&player.fireCd<=0)shoot();
 if(toSpawn>0){spawnTimer-=dt;if(spawnTimer<=0){spawnEnemy();toSpawn--;spawnTimer=Math.max(.15,.65-wave*.025)}}else if(enemies.length===0&&!between)nextWave();
 bullets.forEach(b=>{b.x+=b.vx*dt;b.y+=b.vy*dt;b.life-=dt});bullets=bullets.filter(b=>b.life>0&&b.x>-20&&b.x<W+20&&b.y>-20&&b.y<H+20);
 for(let e of enemies){let a=Math.atan2(player.y-e.y,player.x-e.x);e.x+=Math.cos(a)*e.speed*dt;e.y+=Math.sin(a)*e.speed*dt;e.hit-=dt;if(Math.hypot(e.x-player.x,e.y-player.y)<e.r+player.r&&player.inv<=0){player.hp-=e.tough?22:14;player.inv=.65;burst(player.x,player.y,'#ff334f',15);updateUI();if(player.hp<=0){gameOver();return}}}
 for(let bi=bullets.length-1;bi>=0;bi--){let b=bullets[bi];for(let ei=enemies.length-1;ei>=0;ei--){let e=enemies[ei];if(Math.hypot(b.x-e.x,b.y-e.y)<b.r+e.r){bullets.splice(bi,1);e.hp--;e.hit=.08;burst(b.x,b.y,'#ffcf5a',5);if(e.hp<=0){score+=e.tough?30:10;burst(e.x,e.y,e.tough?'#ff4d8d':'#9cff57',12);enemies.splice(ei,1);updateUI()}break}}}
 particles.forEach(p=>{p.x+=p.vx*dt;p.y+=p.vy*dt;p.vx*=.96;p.vy*=.96;p.life-=dt});particles=particles.filter(p=>p.life>0)
}
function drawGrid(){x.strokeStyle='#ffffff0a';x.lineWidth=1;let s=50;for(let gx=0;gx<W;gx+=s){x.beginPath();x.moveTo(gx,0);x.lineTo(gx,H);x.stroke()}for(let gy=0;gy<H;gy+=s){x.beginPath();x.moveTo(0,gy);x.lineTo(W,gy);x.stroke()}}
function draw(){x.clearRect(0,0,W,H);drawGrid();
 particles.forEach(p=>{x.globalAlpha=Math.max(0,p.life/p.max);x.fillStyle=p.color;x.beginPath();x.arc(p.x,p.y,3,0,Math.PI*2);x.fill()});x.globalAlpha=1;
 bullets.forEach(b=>{x.shadowBlur=14;x.shadowColor='#61eaff';x.fillStyle='#bff8ff';x.beginPath();x.arc(b.x,b.y,b.r,0,Math.PI*2);x.fill()});x.shadowBlur=0;
 enemies.forEach(e=>{x.save();x.translate(e.x,e.y);x.fillStyle=e.hit>0?'#fff':(e.tough?'#ff4d8d':'#9cff57');x.shadowBlur=18;x.shadowColor=e.tough?'#ff4d8d':'#9cff57';x.beginPath();x.arc(0,0,e.r,0,Math.PI*2);x.fill();x.fillStyle='#08100b';x.beginPath();x.arc(-5,-3,3,0,Math.PI*2);x.arc(5,-3,3,0,Math.PI*2);x.fill();x.restore()});x.shadowBlur=0;
 x.save();x.translate(player.x,player.y);x.rotate(player.angle);x.globalAlpha=player.inv>0&&Math.floor(player.inv*12)%2?0.35:1;x.fillStyle='#61eaff';x.shadowBlur=20;x.shadowColor='#00d9ff';x.beginPath();x.arc(0,0,player.r,0,Math.PI*2);x.fill();x.fillStyle='#dffcff';x.fillRect(8,-5,28,10);x.fillStyle='#071018';x.beginPath();x.arc(4,-5,3,0,Math.PI*2);x.fill();x.restore();x.globalAlpha=1;x.shadowBlur=0;
}
function loop(t){if(!running)return;let dt=Math.min((t-last)/1000,.033);last=t;update(dt);draw();if(running)requestAnimationFrame(loop)}
draw();
</script>
</body>
</html>
