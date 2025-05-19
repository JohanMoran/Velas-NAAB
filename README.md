<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Costos de Velas</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .container { max-width: 600px; margin: auto; padding: 20px; border: 1px solid #ddd; border-radius: 10px; }
        h1 { text-align: center; color: #ff6b6b; }
        .input-group { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; }
        input { width: 100%; padding: 8px; box-sizing: border-box; }
        button { background: #4CAF50; color: white; border: none; padding: 10px 15px; cursor: pointer; width: 100%; }
        button:hover { background: #45a049; }
        #resultado { margin-top: 20px; padding: 15px; background: #f9f9f9; border-radius: 5px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Calculadora de Costos de Velas</h1>
        <div class="input-group">
            <label for="cera">Costo de cera (por gramo, $):</label>
            <input type="number" id="cera" step="0.01" placeholder="Ej: 0.05">
        </div>
        <div class="input-group">
            <label for="fragancia">Costo de fragancia (por ml, $):</label>
            <input type="number" id="fragancia" step="0.01" placeholder="Ej: 0.20">
        </div>
        <div class="input-group">
            <label for="pabilo">Costo de pabilo (por unidad, $):</label>
            <input type="number" id="pabilo" step="0.01" placeholder="Ej: 0.30">
        </div>
        <div class="input-group">
            <label for="color">Costo de colorante (por gota, $):</label>
            <input type="number" id="color" step="0.01" placeholder="Ej: 0.02">
        </div>
        <div class="input-group">
            <label for="otros">Otros costos ($):</label>
            <input type="number" id="otros" step="0.01" placeholder="Ej: 1.50">
        </div>
        <div class="input-group">
            <label for="ganancia">% de Ganancia deseado:</label>
            <input type="number" id="ganancia" placeholder="Ej: 30">
        </div>
        <div class="input-group">
            <label for="cantidad">Cantidad de velas (opcional):</label>
            <input type="number" id="cantidad" placeholder="Ej: 1" value="1">
        </div>
        <button onclick="calcular()">Calcular Precio</button>
        <div id="resultado"></div>
    </div>

    <script>
        function calcular() {
            const cera = parseFloat(document.getElementById('cera').value) || 0;
            const fragancia = parseFloat(document.getElementById('fragancia').value) || 0;
            const pabilo = parseFloat(document.getElementById('pabilo').value) || 0;
            const color = parseFloat(document.getElementById('color').value) || 0;
            const otros = parseFloat(document.getElementById('otros').value) || 0;
            const ganancia = parseFloat(document.getElementById('ganancia').value) || 0;
            const cantidad = parseInt(document.getElementById('cantidad').value) || 1;

            const costoPorVela = cera + fragancia + pabilo + color + otros;
            const costoTotal = costoPorVela * cantidad;
            const precioVenta = costoPorVela * (1 + ganancia / 100);
            const precioTotal = precioVenta * cantidad;

            document.getElementById('resultado').innerHTML = `
                <h3>Resultados</h3>
                <p><strong>Costo por vela:</strong> $${costoPorVela.toFixed(2)}</p>
                <p><strong>Costo total (${cantidad} velas):</strong> $${costoTotal.toFixed(2)}</p>
                <p><strong>Precio de venta por vela (con ${ganancia}% de ganancia):</strong> $${precioVenta.toFixed(2)}</p>
                <p><strong>Precio total (${cantidad} velas):</strong> $${precioTotal.toFixed(2)}</p>
            `;
        }
    </script>
</body>
</html>
