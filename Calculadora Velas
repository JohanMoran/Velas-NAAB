<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora de Costos de Velas</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fff5f8;
      color: #333;
      padding: 20px;
      max-width: 800px;
      margin: auto;
    }
    h2 {
      color: #d97a9b;
    }
    label {
      font-weight: bold;
      display: block;
      margin-top: 10px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-top: 4px;
      margin-bottom: 12px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .section {
      background-color: #ffeaf0;
      padding: 20px;
      border-radius: 12px;
      margin-bottom: 20px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.05);
    }
    button {
      background-color: #e38da8;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      border-radius: 6px;
      cursor: pointer;
    }
    button:hover {
      background-color: #d5779a;
    }
    #resultado {
      margin-top: 20px;
      font-size: 18px;
      background-color: #fbe5eb;
      padding: 15px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <h1>Calculadora de Costos de Velas Artesanales</h1>

  <div class="section">
    <h2>Cera</h2>
    <label>Costo de 1kg de cera: ($)</label>
    <input type="number" id="costoCera">
    <label>Cera por vela (gramos):</label>
    <input type="number" id="gramosCera">
  </div>

  <div class="section">
    <h2>Fragancia</h2>
    <label>Costo del bote de fragancia: ($)</label>
    <input type="number" id="costoFragancia">
    <label>Tamaño del bote de fragancia (gramos):</label>
    <input type="number" id="tamanoFragancia">
    <label>Porcentaje de fragancia usado en la vela (%):</label>
    <input type="number" id="porcentajeFragancia">
  </div>

  <div class="section">
    <h2>Colorante</h2>
    <label>Costo del colorante por frasco: ($)</label>
    <input type="number" id="costoColorante">
    <label>Uso por vela (gramos):</label>
    <input type="number" id="usoColorante">
    <label>Cantidad del frasco (gramos):</label>
    <input type="number" id="cantidadColorante">
  </div>

  <div class="section">
    <h2>Otros Costos</h2>
    <label>Costo de la mecha/pabilo (por vela): ($)</label>
    <input type="number" id="costoMecha">
    <label>Costo del frasco/contenedor (por vela): ($)</label>
    <input type="number" id="costoFrasco">
    <label>Costo de la etiqueta (por vela): ($)</label>
    <input type="number" id="costoEtiqueta">
    <label>Costos indirectos (por vela): ($)</label>
    <input type="number" id="costoIndirecto" value="0">
  </div>

  <div class="section">
    <h2>Margen de Beneficio</h2>
    <label>Margen de beneficio deseado (%):</label>
    <input type="number" id="margen" value="35">
  </div>

  <button onclick="calcularCosto()">Calcular</button>

  <div id="resultado"></div>

  <script>
    function calcularCosto() {
      const costoCera = parseFloat(document.getElementById('costoCera').value);
      const gramosCera = parseFloat(document.getElementById('gramosCera').value);
      const costoFragancia = parseFloat(document.getElementById('costoFragancia').value);
      const tamanoFragancia = parseFloat(document.getElementById('tamanoFragancia').value);
      const porcentajeFragancia = parseFloat(document.getElementById('porcentajeFragancia').value);

      const costoColorante = parseFloat(document.getElementById('costoColorante').value);
      const usoColorante = parseFloat(document.getElementById('usoColorante').value);
      const cantidadColorante = parseFloat(document.getElementById('cantidadColorante').value);

      const costoMecha = parseFloat(document.getElementById('costoMecha').value);
      const costoFrasco = parseFloat(document.getElementById('costoFrasco').value);
      const costoEtiqueta = parseFloat(document.getElementById('costoEtiqueta').value);
      const costoIndirecto = parseFloat(document.getElementById('costoIndirecto').value);
      const margen = parseFloat(document.getElementById('margen').value);

      const costoPorGramoCera = costoCera / 1000;
      const costoCeraPorVela = costoPorGramoCera * gramosCera;

      const gramosFragancia = gramosCera * (porcentajeFragancia / 100);
      const costoPorGramoFragancia = costoFragancia / tamanoFragancia;
      const costoFraganciaPorVela = gramosFragancia * costoPorGramoFragancia;

      const costoColorantePorGramo = costoColorante / cantidadColorante;
      const costoColorantePorVela = usoColorante * costoColorantePorGramo;

      const costoTotal = costoCeraPorVela + costoFraganciaPorVela + costoColorantePorVela + costoMecha + costoFrasco + costoEtiqueta + costoIndirecto;
      const precioVenta = costoTotal * (1 + margen / 100);

      document.getElementById('resultado').innerHTML =
        `<strong>Costo total por vela:</strong> $${costoTotal.toFixed(2)}<br>` +
        `<strong>Precio sugerido de venta (con ${margen}% de margen):</strong> $${precioVenta.toFixed(2)}`;
    }
  </script>
</body>
</html>
