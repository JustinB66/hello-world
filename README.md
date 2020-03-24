<!DOCTYPE html>
<html>
<head>
	<title>To-Do List App</title>
	<style>
		.header {
			background-color: Lime;
			width: 100%;
			height: 50px
			text-align: center;
			}
		.title {
			font-size: 16pt;
			text-align: center;
			color: MidnightBlue;
		}
		.p {
			text-align: left;
			font-size: 16pt;
		}
		.padding {
			padding: 25px;
		}
	</style>
	<script>
		function addItem() {
			var newItem = document.createElement("div");
			newItem.innerHTML = document.getElementById("box").value;
			newItem.onclick = removeItem;
			document.getElementById("list").appendChild(newItem);
			saveList();
		}
		function removeItem() {
			document.getElementById("list").removeChild(this);
			saveList();
		}
		function saveList() {
			localStorage.storedList = document.getElementById("list").innerHTML;
		}
		function loadList() {
			document.getElementById("list").innerHTML = localStorage.storedList;
			for(var i = 0; i < list.children.length; i++) {
				list.children[i].onClick = removeItem;
			}
		}
	</script>
</head>
<body>
<div class= header>Special Exhibition To-Do List</div>
	<br/>
	<p>Add and Remove Items to your To-Do List!</p> 
	<br/>
	<input type= "text" id= "box" value= "Type HERE to add task"/>
	<br/>
	<input type= "button" value= "Add Item" onclick= "addItem()"/>
	<br/>
	<div id= "list"></div>
	<script>
		if(localStorage.storedList) {
			loadList();
		}
	</script>
</body>
</html>
