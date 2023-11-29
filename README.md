<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Meine Website</title>

  <style>
    body {
      background-color: black;
      color: white;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    input {
      padding: 10px;
      font-size: 16px;
      margin-bottom: 10px;
      background-color: white; 
    }
    #backButton {
      display: none;
      background-color: white;
      color: black;
      padding: 20px;
      font-size: 24px;
      border: none;
      cursor: pointer;
    }
    #schuhschrankText {
      display: none;
      font-size: 1.5px;
      margin-top: 2px;
    }
  </style>
</head>
<body>
  <input type="text" id="zahlInput" onkeydown="pruefeEnterTaste(event)">
  <button id="backButton" onclick="zurueck()">Zurück</button>
  <div id="schuhschrankText">Siehe Schuhschrank</div>
<script>
  function pruefeEnterTaste(event) {
    var zahlInput = document.getElementById("zahlInput");
    var backButton = document.getElementById("backButton");
    var schuhschrankText = document.getElementById("schuhschrankText");
    if (event.keyCode !== 13) {
    if (zahlInput.value === "") {
        zahlInput.style.backgroundColor = "white";
        backButton.style.display = "none";
        schuhschrankText.style.display = "none";
      }
      return;
    }
    var enteredValue = parseFloat(zahlInput.value);
    if (isNaN(enteredValue) || enteredValue !== Math.floor(enteredValue)) {
      // Wenn die Eingabe keine ganze Zahl ist
      zahlInput.style.backgroundColor = "red";
      backButton.style.display = "none";
      schuhschrankText.style.display = "none";
    } else {
      if (enteredValue === 21) {
        zahlInput.style.backgroundColor = "white";
        zahlInput.style.display = "none";
        backButton.style.display = "block";
        schuhschrankText.style.display = "block";
      } else {
        zahlInput.style.backgroundColor = "red";
        backButton.style.display = "none";
        schuhschrankText.style.display = "none";
      }
    }
  }
function zurueck() {
    var zahlInput = document.getElementById("zahlInput");
    var backButton = document.getElementById("backButton");
    var schuhschrankText = document.getElementById("schuhschrankText");
    zahlInput.value = "";
    zahlInput.style.backgroundColor = "white";
    zahlInput.style.display = "block";
    backButton.style.display = "none";
    schuhschrankText.style.display = "none";
  }
</script>
</body>
</html>
