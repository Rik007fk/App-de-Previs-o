<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Previsão do Tempo Simulada</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        form {
            margin-bottom: 20px;
        }
        input[type="text"] {
            padding: 10px;
            font-size: 16px;
        }
        button {
            padding: 10px 15px;
            font-size: 16px;
            cursor: pointer;
        }
        h2 {
            font-size: 24px;
        }
        p {
            font-size: 18px;
        }
    </style>
</head>
<body>
    <h1>Previsão do Tempo Simulada</h1>
    <form id="weatherForm">
        <input type="text" id="city" placeholder="Digite o nome da cidade" required>
        <button type="submit">Buscar</button>
    </form>

    <div id="result"></div>

    <script>
        document.getElementById("weatherForm").addEventListener("submit", function(event) {
            event.preventDefault();
            
            // Pega o nome da cidade
            const city = document.getElementById("city").value;

            // Gera dados de clima aleatórios
            const temperature = (Math.random() * 20 + 15).toFixed(1); // entre 15 e 35 graus
            const descriptions = ["Ensolarado", "Nublado", "Chuvoso", "Tempestuoso", "Nevoeiro"];
            const description = descriptions[Math.floor(Math.random() * descriptions.length)];

            // Exibe os dados simulados
            document.getElementById("result").innerHTML = `
                <h2>${city}</h2>
                <p>Temperatura: ${temperature} °C</p>
                <p>Descrição: ${description}</p>
            `;
        });
    </script>
</body>
</html>
