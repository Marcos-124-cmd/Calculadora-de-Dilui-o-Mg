

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Diluição - MG Auto Shop</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            color: #333;
            text-align: center;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            max-width: 400px;
            margin: 50px auto;
        }
        h1 {
            color: #007BFF; /* Azul */
        }
        label {
            display: block;
            margin: 10px 0 5px;
        }
        input {
            width: calc(100% - 20px);
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            background-color: #007BFF; /* Azul */
            color: white;
            border: none;
            padding: 10px;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
        }
        button:hover {
            background-color: #0056b3; /* Azul mais escuro */
        }
        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Calculadora de Diluição</h1>
        <label for="volume">Volume Total Desejado (ml):</label>
        <input type="number" id="volume" name="volume" required>
        
        <label for="dilution">Diluição (ex: 10 para 1:10):</label>
        <input type="number" id="dilution" name="dilution" required>
        
        <button type="button" onclick="calculateDilution()">Calcular</button>
        
        <div id="result"></div>
    </div>
    
    <script>
        function calculateDilution() {
            var volume = document.getElementById('volume').value;
            var dilution = document.getElementById('dilution').value;
            
            var concentrated = volume / (dilution + 1);
            var solvent = volume - concentrated;
            
            document.getElementById('result').innerHTML = `Você precisa de aproximadamente ${concentrated.toFixed(2)} ml do produto concentrado e ${solvent.toFixed(2)} ml de diluente.`;
        }
    </script>
</body>
</html>


