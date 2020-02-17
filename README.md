<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Primer Ejemplo Firebase</title>
	<!-- The core Firebase JS SDK is always required and must be listed first -->
	<script src="https://www.gstatic.com/firebasejs/7.2.1/firebase-app.js"></script>
	<script src="https://www.gstatic.com/firebasejs/6.2.0/firebase-database.js"></script>
	<!-- TODO: Add SDKs for Firebase products that you want to use
		 https://firebase.google.com/docs/web/setup#available-libraries -->
	<script src="https://www.gstatic.com/firebasejs/7.2.1/firebase-analytics.js"></script>
	 <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
	<script>
	  // Your web app's Firebase configuration
	  var firebaseConfig = {
		apiKey: "AIzaSyA2I0KDq0E7gYTuQD2Kw4is8y6niZnsvag",
		authDomain: "elegant-door-151717.firebaseapp.com",
		databaseURL: "https://elegant-door-151717.firebaseio.com",
		projectId: "elegant-door-151717",
		storageBucket: "elegant-door-151717.appspot.com",
		messagingSenderId: "129226723688",
		appId: "1:129226723688:web:412214b6a86ed83777c6dd",
		measurementId: "G-VY7NRKQE39"
	  };
	  // Initialize Firebase
	  firebase.initializeApp(firebaseConfig);
	  firebase.analytics();
	var database = firebase.database();
	var starCountRef = firebase.database().ref('placas');
	starCountRef.on('value', function(snapshot) {
	  //valor_uno = snapshot.val();
	  console.log(snapshot.val());
	   snapshot.forEach(function(childSnapshot) {
		// key will be "ada" the first time and "alan" the second time
		var key = childSnapshot.key;
		// childData will be the actual contents of the child
		var childData = childSnapshot.val();
		 console.log(childData['valor']);
		$("#lista_placas").append(childData['valor'] +  " ->" + childData['time']+  " ->"  );
	$("#lista_placas").append("<br>");
			$("#lista_placas1").append(childData['Propietario']+  " ->" + childData['cargo']+  " ->"  );
	$("#lista_placas1").append("<br>");
				$("#lista_placas2").append(childData['robado'] );
	$("#lista_placas2").append("<br>");
	  });
	  
	});
	</script>
<style>
aside, article, section, nav, header, footer {
  display:block;
  margin: 0;
  padding; 0;
}

html, body{
	margin:0;
	padding:0;
}
html{
	background:#FFF;
}
body{
	background:#ff6;
}
p, h1 ,h2, h3{
	margin:0;
	padding:0;
}

body{
	width:1200px;
	margin:0 auto;
	font-family: Verdana, Geneva, sans-serif;
}
header{
	height:100px;
	background:#E5CBA2;
}
#col1{

	background:#AB8A6c;
	width:400px;
	float:left;
	
}
#col2{

	background:#CCB18E;
	width:400px;
	float:left;
}
#col3{

	background:#AB8A6c;
	width:400px;
	float:left;
}

h1{
	color:#8B0000;
	font-size:2.2em;
	text-align:center;
}
h2{
	color:#593939;
	font-size:1.8em;
	text-align:center;
}
h3{
	color:#8B0000;
	font-size:.8em;
	text-align:center;
}
p{
	padding-left:1em;
	padding-right:1em;
	padding-top:1em;
	line-height:1.4em;
}


</style>
</head>
<body>
<header>
<h1>PAGINA WEB - SISTEMA DE SEGURIDAD</h1>
<h2>TESIS 2</h2>
<h3>CHIPANA VILA</h3>
</header>
<section>
	<aside id="col1" >
		<CENTER>
		<font size=3>
		<STRONG>
		Placa
		<p id="lista_placas" > 
		</p>
		</STRONG>	
		</font>
		</CENTER>
	</aside>
	
	<article id="col2">
		<CENTER>
		<font size=3>
		<STRONG>
		Propietario
		<p id="lista_placas1"> 
		</p>
		</STRONG>	
		</font>
		</CENTER>
	</article>
	
	<aside id="col3">
		
		<CENTER>
		<font size=3>
		<STRONG>
		
		Acceso
		<p id="lista_placas2"> 
		</p>
		</STRONG>	
		</font>
		</CENTER>
	</aside>

</section>
<footer></footer>
</body>
 </html>
 
