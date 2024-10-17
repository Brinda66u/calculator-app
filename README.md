<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Calculator App</title>
	<link rel="stylesheet" type="text/css" href="style.css">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
	<div class="coantainer">
		<div class="title">
			<div class="toggle">
				<h3>Calc</h3>
				
			</div>
		</div>
		<div class="screen">
			<form name="calc">
				<input type="text" name="text" readonly id="screen">
			</form>
		</div>
		<div class="cal-body">
			<div class="btn">
				<button class="num" onclick="document.calc.text.value+='7'">7</button>
				<button class="num" onclick="document.calc.text.value+='8'">8</button>
				<button class="num" onclick="document.calc.text.value+='9'">9</button>
				<button class="del" onclick="del()">DEL</button>
				<button class="num" onclick="document.calc.text.value+='4'">4</button>
				<button class="num" onclick="document.calc.text.value+='5'">5</button>
				<button class="num" onclick="document.calc.text.value+='6'">6</button>
				<button onclick="document.calc.text.value+='+'">+</button>
				<button class="num" onclick="document.calc.text.value+='1'">1</button>
				<button class="num" onclick="document.calc.text.value+='2'">2</button>
				<button class="num" onclick="document.calc.text.value+='3'">3</button>
				<button onclick="document.calc.text.value+='-'">-</button>
				<button onclick="document.calc.text.value+='.'">.</button>
				<button class="num" onclick="document.calc.text.value+='0'">0</button>
				<button onclick="document.calc.text.value+='/'">/</button>
				<button onclick="document.calc.text.value+='*'">X</button>
				<button class="reset" onclick="document.calc.text.value=''">RESET</button>
				<button class="equal" onclick="document.calc.text.value= eval(calc.text.value)">=</button>
			</div>
		</div>
	</div>
	<script src="calculator.js"></script>
</body>
</html>

@import url('https://fonts.googleapis.com/css2?family=Spartan:wght@700&display=swap');
*{
	padding: 0;
	margin: 0;
	box-sizing: border-box;
	font-family: 'Spartan', sans-serif;
	color: hsl(221, 14%, 31%);
	font-weight: 700;
}

:root{
	--mainbgcolor: hsl(222, 26%, 31%);
	--mainbg1color: hsl(0, 0%, 90%);
	--mainbg2color: hsl(268, 75%, 9%);
	--twotkbg: hsl(0, 5%, 81%);
	--tbgkbgsbg: hsl(268, 71%, 12%);
}
body{
	width: 100%;
	max-width: 1440px;
	background-color: var(--mainbgcolor);
	height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;

}
body.active1{
	background-color: var(--mainbg1color);
}
body.active1 .btn{
	background-color: var(--twotkbg);
}
body.active2{
	background-color: var(--mainbg2color);
}
.toggle{
	display: flex;
	justify-content: space-between;
}
.right{
	display: flex;
	justify-content: flex-end;
}
.toggle p{
	margin: 0 5px;
	color: #FFF;
	cursor: pointer;
}
body.active1 .toggle h3{
	color: #111;
}
body.active2 .toggle h3{
	color: hsl(52, 100%, 62%);
}
h3{
	color: #FFF;
}
.control{
	display: flex;
	justify-content: flex-end;
}
.control .box{
	width: 60px;
	height: 15px;
	background-color: hsl(224, 36%, 15%);
	border-radius: 30px;
	margin-left: 4px;
	position: relative;
}
body.active1 .control .box{
	background-color: var(--twotkbg);
}
body.active2 .control #circle{
	background-color: hsl(176, 100%, 44%);
}
.control #circle{
	width: 15px;
	height: 15px;
	background-color: hsl(6, 63%, 50%);
	position: absolute;
	top: 0;
	left: 0;
	z-index: 1;
	border-radius: 30px;
}
body.active1 .control #circle{
	background-color: hsl(25, 98%, 40%);
}
.control p{
	color: #FFF;
	cursor: pointer;
	margin-right: 4px;
}
body.active1 .control p{
	color: #111;
}
body.active1 .right p{
	color: #111;
}
body.active2 .control p{
	color: hsl(52, 100%, 62%);
}
body.active2 .right p{
	color: hsl(52, 100%, 62%);
}
.screen{
	width: 450px;
}
#screen{
	width: 100%;
	height: 100px;
	margin: 10px 0;
	text-align: right;
	font-size: 32px;
	background-color: hsl(224, 36%, 15%);
	color: #FFF;
	border: 0;
	outline: none;
	border-radius: 7px;
}
body.active1 #screen{
	background-color: hsl(0, 0%, 93%);
	color: #111;
}
body.active2 #screen{
	background-color: var(--tbgkbgsbg);
	color: hsl(52, 100%, 62%);
}
button{
	width: 90px;
    padding: 15px;
    outline: none;
    cursor: pointer;
    border: 0;
    border-radius: 5px;
    box-shadow: 0px 3px 0px 0px hsl(28, 16%, 65%);
    margin: 10px 10px;
    font-size: 32px;
    color: ;
}
body.active1 button{
	box-shadow: 0px 3px 0px 0px hsl(35, 11%, 61%);
}
body.active2 button{
	box-shadow: 0px 3px 0px 0px hsl(268, 47%, 21%);
	background-color: hsl(290, 70%, 36%);
	color: hsl(52, 100%, 62%);
}
.btn{
	display: flex;
	width: 450px;
	flex-flow: wrap;
	background-color: hsl(224, 36%, 15%);
	padding: 10px 5px;
	margin: 8px 0;
	border-radius: 7px;
}
body.active2 .btn{
	background-color: var(--tbgkbgsbg);
}
.reset,.del{
	box-shadow: 0px 3px 0px 0px hsl(224, 28%, 35%);
	background-color: hsl(225, 21%, 49%);
	color: #FFF;
	font-size: 16px;
}
body.active1 .reset, body.active1 .del{
	box-shadow: 0px 3px 0px 0px hsl(35, 11%, 61%);
	background-color: hsl(185, 42%, 37%);
}
body.active2 .reset, body.active2 .del{
	box-shadow: 0px 3px 0px 0px hsl(290, 70%, 36%);
	background-color: hsl(268, 47%, 21%);
	color: #fff;
}
.reset,.equal{
	width: 200px;
	color: #FFF;
	font-size: 16px;
}
.equal{
	box-shadow: 0px 3px 0px 0px hsl(6, 70%, 34%);
	background-color: hsl(6, 63%, 50%);
}
body.active1 .equal{
	box-shadow: 0px 3px 0px 0px hsl(25, 99%, 27%);
	background-color: hsl(25, 98%, 40%);
}
body.active2 .equal{
	box-shadow: 0px 3px 0px 0px hsl(177, 92%, 70%);
	background-color: hsl(176, 100%, 44%);
	color: #fff;
}
.num{

}

button:hover {
    background-color: #ddd;
}
background: rgba(255, 255, 255, 1);

button:active {
    background-color: #ccc;
}
function del(){
    var value=document.getElementById('screen').value;
    document.getElementById('screen').value=value.substr(0,value.length-1);
}

var two=document.getElementById('two');
two.addEventListener('click',function(){
    var body=document.querySelector('body');
    var toggle=document.getElementById('circle');
    body.classList.add('active1');
    body.classList.remove('active2');
    toggle.style.left='36%';
})
var one=document.getElementById('one');
one.addEventListener('click',function(){
    var body=document.querySelector('body');
    var toggle=document.getElementById('circle');
    body.classList.remove('active1');
    body.classList.remove('active2');
    toggle.style.left='0';
})
var three=document.getElementById('three');
three.addEventListener('click',function(){
    var body=document.querySelector('body');
    var toggle=document.getElementById('circle');
    body.classList.add('active2');
    body.classList.remove('active1');
    toggle.style.left='65%';
})
