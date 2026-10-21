<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Probabilidade</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #101827;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .calculadora {
            background: #1e293b;
            padding: 25px;
            border-radius: 16px;
            width: 300px;
            text-align: center;
        }

        h1 {
            font-size: 23px;
            color: #38bdf8;
        }

        input {
            box-sizing: border-box;
            width: 100%;
            padding: 12px;
            margin: 8px 0;
            border-radius: 8px;
            border: none;
            font-size: 16px;
        }

        button {
            width: 100%;
            padding: 12px;
            margin-top: 10px;
            background: #0284c7;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background: #0369a1;
        }

        #resultado {
            margin-top: 20px;
            font-size: 18px;
            overflow-wrap: anywhere;
        }
    </style>
</head>

<body>
    <div class="calculadora">
        <h1>Calculadora de Probabilidade</h1>

        <p>Casos favoráveis:</p>
        <input type="number" id="favoraveis"
               min="0" placeholder="Ex.: 5">

        <p>Casos possíveis:</p>
        <input type="number" id="possiveis"
               min="1" placeholder="Ex.: 20">

        <button onclick="calcular()">
            Calcular probabilidade
        </button>

        <div id="resultado"></div>
    </div>

    <script>
        function calcular() {
            const favoraveis =
                Number(document.getElementById("favoraveis").value);

            const possiveis =
                Number(document.getElementById("possiveis").value);

            const resultado =
                document.getElementById("resultado");

            if (
                document.getElementById("favoraveis").value === "" ||
                document.getElementById("possiveis").value === "" ||
                favoraveis < 0 ||
                possiveis <= 0 ||
                favoraveis > possiveis
            ) {
                resultado.textContent =
                    "Digite valores válidos!";
                return;
            }

            const probabilidade = favoraveis / possiveis;
            const porcentagem = probabilidade * 100;

            resultado.innerHTML =
                "Probabilidade: " +
                probabilidade.toFixed(4) +
                "<br><br>" +
                "Porcentagem: " +
                porcentagem.toLocaleString("pt-BR",
                    { maximumFractionDigits: 2 }) +
                "%";
        }
    </script>
</body>
</html>
