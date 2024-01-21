<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>User Name Input</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 20px;
      background-image: url('https://img.freepik.com/free-vector/little-red-heart-background_53876-98914.jpg');
      background-repeat: no-repeat;
      background-size: cover;
    }

    .button1 {
      display: inline-block;
      border-radius: 4px;
      background-color: #f4511e;
      border: none;
      color: #FFFFFF;
      text-align: center;
      font-size: 20px;
      padding: 20px;
      width: 150px;
      transition: all 0.5s;
      cursor: pointer;
      margin: 5px;
    }

    .button1 span {
      cursor: pointer;
      display: inline-block;
      position: relative;
      transition: 0.5s;
    }

    .button1 span:after {
      content: '\00bb';
      position: absolute;
      opacity: 0;
      top: 0;
      right: -20px;
      transition: 0.5s;
    }

    .button1:hover span {
      padding-right: 20px;
    }

    .button1:hover span:after {
      opacity: 1;
      right: 0;
    }

    #getToKnowBtn {
      border-radius: 4px;
      background-color: #f4511e;
      border: none;
      color: #FFFFFF;
      text-align: center;
      font-size: 20px;
      padding: 20px;
      transition: all 0.5s;
      cursor: pointer;
      margin: 5px;
    }

    #getToKnowBtn span {
      cursor: pointer;
      position: relative;
      transition: 0.5s;
    }

    #getToKnowBtn span:after {
      content: '\00bb';
      position: absolute;
      opacity: 0;
      top: 0;
      right: -20px;
      transition: 0.5s;
    }

    #getToKnowBtn:hover span {
      padding-right: 25px;
    }

    #getToKnowBtn:hover span:after {
      opacity: 1;
      right: 0;
    }

    input {
      padding: 10px;
      margin: 10px;
    }

    #getToKnowBtn {
      display: none;
    }

    @keyframes heartbeat {
      0% { transform: scale(1); }
      25% { transform: scale(1.1); }
      50% { transform: scale(1); }
      75% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }

    #heartbeat {
      animation: heartbeat 2s infinite;
      display: inline-block;
      color: red;
      font-size: 15em;
    }

    #outputDiv {
      font-size: 20px;
      padding: 20px;
    }
  </style>
</head>
<body>
<center>
  <h1 id="nameHeading">Enter Your Name</h1>
  <form id="nameForm" onsubmit="return storeUserName()">
    <input type="text" id="userNameInput" placeholder="Your Name" required>
    <button class="button1" style="vertical-align:middle" type="submit"><span>Submit</span></button>
  </form>

  <div id="outputDiv"></div>
  <div id="heart"></div>

  <button id="getToKnowBtn" onclick="getToKnow()"><span>Get to Know</span></button>
</center>
  <script>
    function storeUserName() {
      var userName = document.getElementById("userNameInput").value;

      if (userName.trim() === "") {
        alert("Please enter your name.");
        return false;
      }

      document.getElementById("outputDiv").innerHTML = "Hello, " + userName + " Do you want to know who is my most special person?";
      document.getElementById("nameHeading").style.display = "none";
      document.getElementById("userNameInput").style.display = "none";
      document.querySelector('.button1').style.display = 'none';
      document.getElementById("getToKnowBtn").style.display = "block";

      return false;
    }

    function getToKnow() {
      var userName = document.getElementById("userNameInput").value;
      var specialPerson = "My most special person is someone you " + userName;
      var heartbeating = "<span id='heartbeat'>&#10084;</span>";
      document.getElementById("outputDiv").innerHTML = specialPerson;
      document.getElementById("heart").innerHTML = heartbeating;
      document.getElementById("getToKnowBtn").style.display = "none";
      return false;
    }
  </script>
</body>
</html>
