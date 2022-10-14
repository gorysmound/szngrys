<html>
<head>
   <title>duar mamak</title>
   <style>* {
   margin: 0;
   padding: 0;
   }
   
   body {
   background-color: black;
   }
   
   h1 {
   margin-top: 5%;
   font-family: 'Segoe UI';
   font-size: 60px;
   text-align: center;
   color: white;
   }
   </style>
</head>
<body>
	<h1>HAPPY BIRTHDAY SYARIFA ZAFIRA NAJWA</h2>
      <h1>#16 NOVEMBER 2022</h1>
   <script>var rnd = Math.random, flr = Math.floor;
   let canvas = document.createElement('canvas');
   
   document.getElementsByTagName('body')[0].appendChild(canvas);
   canvas.style.position = 'absolute';
   canvas.style.width = '100%';
   canvas.style.height = '100%';
   
   canvas.width = canvas.clientWidth;
   canvas.height = canvas.clientHeight;
   
   let ctx = canvas.getContext('2d');
   
   function rndNum(num) {
   return rnd() * num + 1;
   }
   
   function vector(x, y) {
   this.x = x;
   this.y = y;
   
   this.add = function(vec2) {
   this.x = this.x + vec2.x;
   this.y = this.y + vec2.y;
   }
   }
   
   function particle(pos, vel) {
   this.pos = new vector(pos.x, pos.y);
   this.vel = vel;
   this.finish = false;
   this.start = 0;
   
   this.update = function(time) {
   let timeSpan = time - this.start;
   
   if (timeSpan > 500) {
   this.finish = true;
   }
   
   if (!this.finish) {
   this.pos.add(this.vel);
   this.vel.y = this.vel.y + gravity;
   }
   };
   
   this.draw = function() {
   if (!this.finish) {
   drawDot(this.pos.x, this.pos.y, 1);
   }
   }
   
   }
   
   function firework(x, y) {
   this.pos = new vector(x, y);
   this.vel = new vector(0, -rndNum(10) - 3);
   this.color = 'hsl(' + rndNum(360) + ', 100%, 50%)'
   this.size = 4;
   this.finish = false;
   this.start = 0;
   let exParticles = [], exPLen = 100;
   
   let rootShow = true;
   
   this.update = function(time) {
   if (this.finish) {
   return;
   }
   
   rootShow = this.vel.y < 0;
   
   if (rootShow) {
   this.pos.add(this.vel);
   this.vel.y = this.vel.y + gravity;
   } else {
   if (exParticles.length === 0) {
   flash = true;
   for (let i = 0; i < exPLen; i++) {
   exParticles.push(new particle(this.pos, new vector(-rndNum(10) + 5, -rndNum(10) + 5)));
   exParticles[exParticles.length - 1].start = time;
   }
   }
   let countFinish = 0;
   for (let i = 0; i < exPLen; i++) {
   let p = exParticles[i];
   p.update(time);
   if (p.finish) {
   countFinish++;
   }
   }
   
   if (countFinish === exPLen) {
   this.finish = true;
   }
   
   }
   }
   
   this.draw = function() {
   if (this.finish) {
   return;
   }
   
   ctx.fillStyle = this.color;
   if (rootShow) {
   drawDot(this.pos.x, this.pos.y, this.size);
   } else {
   for (let i = 0; i < exPLen; i++) {
   let p = exParticles[i];
   p.draw();
   }
   }
   }
   
   }
   
   function drawDot(x, y, size) {
   ctx.beginPath();
   
   ctx.arc(x, y, size, 0, Math.PI * 2);
   ctx.fill();
   
   ctx.closePath();
   }
   
   var fireworks = [],
   gravity = 0.2,
   snapTime = 0,
   flash = false;
   
   function init() {
   let numOfFireworks = 20;
   for (let i = 0; i < numOfFireworks; i++) {
   fireworks.push(new firework(rndNum(canvas.width), canvas.height));
   }
   }
   
   function update(time) {
   for (let i = 0, len = fireworks.length; i < len; i++) {
   let p = fireworks[i];
   p.update(time);
   }
   }
   
   function draw(time) {
   update(time);
   
   ctx.fillStyle = 'rgba(0,0,0,0.3)';
   if (flash) {
   flash = false;
   }
   ctx.fillRect(0, 0, canvas.width, canvas.height);
   
   ctx.fillStyle = 'white';
   ctx.font = "30px Segoe UI";
   let newTime = time - snapTime;
   snapTime = time;
   
   ctx.fillStyle = 'blue';
   for (let i = 0, len = fireworks.length; i < len; i++) {
   let p = fireworks[i];
   if (p.finish) {
   fireworks[i] = new firework(rndNum(canvas.width), canvas.height);
   p = fireworks[i];
   p.start = time;
   }
   p.draw();
   }
   
   window.requestAnimationFrame(draw);
   }
   
   window.addEventListener('resize', function() {
   canvas.width = canvas.clientWidth;
   canvas.height = canvas.clientHeight;
   });
   
   init();
   draw();
   </script>
</body>
</html>

<html>
	<head>
		<body>
			<body bgcolor="black"><center><br>
			<font face="Abel" size="6px" color="grey"><b></b>
			<br><font size="3px">
			<font color="white">[ </font><marquee scrollamount="5" width="630" height="20" behavior="alternate">Happy Birthday Buat Kamu :) Semoga Yang kamu cita - citakan Terwujud. Semoga kamu bahagia selalu :) </marquee><font color="white"> ]</font>
			<br><br><font size="3px" face="Ubuntu Condensed">
		</body>
	</font>
