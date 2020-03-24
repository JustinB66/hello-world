<!DOCTYPE html>
<html>
<head>
	<title>Security Game</title>
	<style>
		#board {
			background: url('GameBackground.jpg');
			background-size: cover;
			border: 1px solid black;
			height: 350px;
			width: 650px;
		}
		.character {
			background: url('Guest.jpg');
			backround-size: cover;
			width: 120px;
			height: 120px;
			padding: 10px;
			margin: 10px;
			float: left;
			display: none;
		}
		.thief {
			background: url('Thief.jpg');
			background-size: cover;
		}
		.hidden {
			display: none;
		}
		.visible {
			display: block;
		}
	</style>
</head>
<body>
	<input type="button" value="Play" onclick="startGame()";/>
	<div id="board">
		<div class="character">1</div>
		<div class="character">2</div>
		<div class="character">3</div>
		<div class="character">4</div>
		<div class="character">5</div>
		<div class="character">6</div>
	</div>
	<script>
		function startGame() {
			gameLoop();
		}
		var loops = 0;
		var peopleVisible = false;
		var gameScore = 0
		function gameLoop() {
			peopleVisible = !peopleVisible;
			createCharacters();
			loops++;
			if(loops < 12) {
				setTimeout(gameLoop, peopleVisible ? 1000 : 3000);
			}
			else {
				alert("You Scored" + gameScore);
			}
		}
		function createCharacters() {
			var board = document.getElementById("board");
			var classToSet = peopleVisible ? "character visible" : "character hidden";
			for(var index = 0; index < 6; index++) {
				board.children[index].className = classToSet;
				board.children[index].innerHTML = "";
				board.children[index].onclick = function() {
					gameScore += -2;
					}
				}
				var randomNumber = Math.floor(Math.random() * 6) + 1;
				board.children[randomNumber-1].innerHTML = "";
				board.children[randomNumber-1].onclick = function() {
					gameScore++;
				}
				board.children[randomNumber-1].className = classToSet + " thief";
			}
	</script>
</body>
</html>
