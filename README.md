<!DOCTYPE html>
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
      font-size: 0,5px;
      margin-top: 5px;
    }
  </style>
</head>
<body>
  <input type="number" id="zahlInput" oninput="pruefeZahl()">
  <button id="backButton" onclick="zurueck()">Zurück</button>
  <div id="schuhschrankText">Siehe Schuhschrank</div>

  <script>
    function pruefeZahl() {
      var zahlInput = document.getElementById("zahlInput");
      var backButton = document.getElementById("backButton");
      var schuhschrankText = document.getElementById("schuhschrankText");

      if (zahlInput.value == 21) {
        zahlInput.style.display = "none";
        backButton.style.display = "block";
        schuhschrankText.style.display = "block";
      } else {
        zahlInput.style.display = "block";
        zahlInput.style.backgroundColor = "red";
        backButton.style.display = "none";
        schuhschrankText.style.display = "none";
      }
    }

    function zurueck() {
      var zahlInput = document.getElementById("zahlInput");
      var backButton = document.getElementById("backButton");
      var schuhschrankText = document.getElementById("schuhschrankText");

      zahlInput.value = "";
      zahlInput.style.display = "block";
      backButton.style.display = "none";
      schuhschrankText.style.display = "none";
    }
  </script>
</body>
</html>
