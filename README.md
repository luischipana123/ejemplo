<!DOCTYPE html>
 <html>
  <head>
   <meta charset="UTF-8">
   <title>Primer Ejemplo Firebase</title>
  </head>

	<body>
	<CENTER>
	<Table border=1 width=50% bgcolor="#8B0000">
	<font COLOR="#8B0000" SIZE=9>
	<STRONG>Registro de Placas vehicularesA</STRONG>
	</font>
	</Table>

	 <h1 id ="holaMundo"> </h1>

	<!-- The core Firebase JS SDK is always required and must be listed first -->
	<script src="https://www.gstatic.com/firebasejs/7.2.1/firebase-app.js"></script>


	<script src="https://www.gstatic.com/firebasejs/6.2.0/firebase-database.js"></script>

	<!-- TODO: Add SDKs for Firebase products that you want to use
		 https://firebase.google.com/docs/web/setup#available-libraries -->
	<script src="https://www.gstatic.com/firebasejs/7.2.1/firebase-analytics.js"></script>
	 <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>

	<div id="lista_placas"> 

	</div>
	<Table border=10 width=100% bgcolor="#8B0000">
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

		$("#lista_placas").append(childData['valor'] +  " - " + childData['time'] +  " - " + childData['Propietario'] );
	$("#lista_placas").append("<br>");

	  });

	});


	</script>
	</Table>
	</CENTER>
  </body>

 </html>
