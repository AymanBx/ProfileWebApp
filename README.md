<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXD7ZKYWV3"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-VHG41VV9P7');
    </script>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Profile WebAPP</title>
    <style>
        body {text-align: center; background-color: lightseagreen; color: black;}
        #user1 {float: left; width: 50%; background-color: blue; color: burlywood;}
        #user2 {float: left; width: 50%; background-color: rgb(178, 32, 178); color: rgb(0, 0, 0);}
    </style>
    <img id="bannerImage" src="Aymangram.png" width="device-width" height="400">
</head>


<body>

    <div id="user1">
        <h2>User 1</h2><br>
        <!-- <button id="pullUser1DataButton">Pull Data</button><br><br> -->
        <h3 id="user1ID" type="text"></h3><br>
        <h3 id="user1Name" type="text"></h3><br>
        <img id="user1Image" src="" width="" height=""></img><br>
        <h3 id="user1Email" type="text"></h3><br>
        <h3 id="user1SignUpDate" type="text"></h3><br>
        <br><br><br><br>
    </div>

    <div id="user2">
        <h2>User 2</h2><br>
        <!-- <button id="pullUser2DataButton">Pull Data</button><br><br> -->
        <h3 id="user2ID" type="text"></h3><br>
        <h3 id="user2Name" type="text"></h3><br>
        <img id="user2Image" src="" width="" height=""></img><br>
        <h3 id="user2Email" type="text"></h3><br>
        <h3 id="user2SignUpDate" type="text"></h3><br>
        <br><br><br><br>
    </div>

    <div id="webApp">
        <h1>Profile App</h1>
        <iframe src="https://thunkable.site/w/4XAhUWFvzhoZXUIKdm1EF" width="600" height="800"></iframe>

    </div>


    <script type="module">
            // For java script??
            // Import the functions you need from the SDKs you need
            import { initializeApp } from "https://www.gstatic.com/firebasejs/10.4.0/firebase-app.js";
            // import { 
            //     getAuth, //To enable us to get started
            //     createUserWithEmailAndPassword,
            //     signInWithEmailAndPassword,
            //     onAuthStateChanged, // To know whether user is signed in or not
            //     signOut
            //  } from "https://www.gstatic.com/firebasejs/10.4.0/firebase-auth.js";
            import {getDatabase, get, ref, child} from "https://www.gstatic.com/firebasejs/10.4.0/firebase-database.js";
          
            // Your web app's Firebase configuration
            // For Firebase JS SDK v7.20.0 and later, measurementId is optional
            const firebaseConfig = {
              apiKey: "AIzaSyD-aD13kTxDROr9V5jK3TdtCFJYNOPmbHc",
              authDomain: "profileapp-11111.firebaseapp.com",
              databaseURL: "https://profileapp-11111-default-rtdb.firebaseio.com",
              projectId: "profileapp-11111",
              storageBucket: "profileapp-11111.appspot.com",
              messagingSenderId: "934068354226",
              appId: "1:934068354226:web:3ee956c88e4fab5be31dab",
              measurementId: "G-KPT5159EES"
            };
            
            // Initialize Firebase assign it to a variable "app"
            const app = initializeApp(firebaseConfig);
            // Pull the database
            const db = getDatabase()
            // Setup authentication with our firebase app, assign it to "auth"
            // const auth = getAuth(app);

            
            
            // Declare variables linked to html componenets 
            
            const user1 = "KPHDv9QMGvSXJNXFpDfGOdYD17N2";
            const user2 = "vHcpPlQtgkYHrWUeN9eyTcSmOm82";
            var pull1Btn = document.querySelector("#pullUser1DataButton");
            var pull2Btn = document.querySelector("#pullUser2DataButton");
            var user1ID = document.querySelector("#user1ID");
            var user1Email = document.querySelector("#user1Email");
            var user1Image = document.querySelector("#user1Image");
            var user1Name = document.querySelector("#user1Name");
            var user1SignUpDate = document.querySelector("#user1SignUpDate");
            var user2ID = document.querySelector("#user2ID");
            var user2Email = document.querySelector("#user2Email");
            var user2Image = document.querySelector("#user2Image");
            var user2Name = document.querySelector("#user2Name");
            var user2SignUpDate = document.querySelector("#user2SignUpDate");

            
            function PullUser1() {
                get(child(dbref, user1))
                .then((snapshot)=>{
                    user1ID.innerHTML = "ID: " + snapshot.val().ID;
                    user1Email.innerHTML = "Email: " + snapshot.val().Email;
                    user1Name.innerHTML = "Namr: " + snapshot.val().Name;
                    user1SignUpDate.innerHTML = "Sign Up Date: " + snapshot.val().Sign_Up_Date;
                    user1Image.width = "500";
                    user1Image.height = "400";
                    user1Image.src = snapshot.val().Image;
                    
                })
                .catch((error)=>{
                    alert(error)
                });
                
            }
            
            function PullUser2() {
                get(child(dbref, user2))
                .then((snapshot)=>{
                    user2ID.innerHTML = "ID: " + snapshot.val().ID;
                    user2Email.innerHTML = "Email: " + snapshot.val().Email;
                    user2Name.innerHTML = "Name: " + snapshot.val().Name;
                    user2SignUpDate.innerHTML = "Sign Up Date: " + snapshot.val().Sign_Up_Date;
                    user2Image.width = "500";
                    user2Image.height = "400";
                    user2Image.src = snapshot.val().Image;
                })
                .catch((error)=>{
                    alert(error)
                })
            }   
            
            // Do stuff.....
            // pull1Btn.addEventListener('click', PullUser1);
            // pull2Btn.addEventListener('click', PullUser2);
            const dbref = ref(db);
            PullUser1();
            PullUser2();
            





        </script>
    </body>
</html>
