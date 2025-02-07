<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Función</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f9;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        input[type="number"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px;
        }
        button:hover {
            background-color: #0056b3;
        }
        .result {
            margin-top: 20px;
            font-size: 1.2em;
        }
        .precision-control {
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Calculadora de Función</h1>
        <p>Ingrese los valores de \( x \) y \( n \) para calcular \( f(x) = \left( \frac{2}{3 + x} \right)^n \):</p>
        <input type="number" id="x" placeholder="Ingrese el valor de x">
        <input type="number" id="n" placeholder="Ingrese el valor de n">
        <div class="precision-control">
            <label for="precision">Precisión (cifras significativas):</label>
            <input type="number" id="precision" value="3" min="1" max="10">
            <button onclick="calcular()">Calcular</button>
        </div>
        <div class="result" id="resultado"></div>
    </div>

    <script>
        function calcular() {
            const x = parseFloat(document.getElementById('x').value);
            const n = parseFloat(document.getElementById('n').value);
            const precision = parseInt(document.getElementById('precision').value);

            if (isNaN(x) || isNaN(n) || isNaN(precision)) {
                document.getElementById('resultado').innerText = "Por favor, ingrese valores válidos para x, n y precisión.";
                return;
            }

            const resultado = Math.pow(2 / (3 + x), n);
            document.getElementById('resultado').innerText = `El resultado es: ${resultado.toPrecision(precision)}`;
        }
    </script>
</body>
</html>
