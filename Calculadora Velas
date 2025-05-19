<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculadora de Costos de Velas</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      padding: 20px;
    }
    h2 {
      border-bottom: 2px solid #ccc;
      padding-bottom: 5px;
    }
    .section {
      background: white;
      border-radius: 8px;
      padding: 15px;
      margin-bottom: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.05);
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-bottom: 10px;
    }
    button {
      background: #007bff;
      color: white;
      border: none;
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }
    .resultado {
      margin-top: 20px;
      background: #e8f5e9;
      padding: 15px;
      border-left: 5px solid #4caf50;
    }
  </style>
</head>
<body>
  <h1>Calculadora de Costos por Vela</h1>

  <div class="section">
    <h2>Cera</h2>
    <label>Costo de 1kg de cera ($):</label>
    <input type="number" id="costoCera">

    <label>Cera por vela (g):</label>
    <input type="number" id="gramosCera">
  </div>

  <div class="section">
    <h2>Fragancia</h2>
    <label>Costo del bote ($):</label>
    <input type="number" id="costoFragancia">

    <label>Tamaño del bote (g):</label>
    <input type="number" id="tamanoFragancia">

    <label>Porcentaje usado en la vela (%):</label>
    <input type="number" id="porcentajeFragancia">
  </div>

  <div class="section">
    <h2>Colorante</h2>
    <label>Costo del frasco de colorante ($):</label>
    <input type="number" id="costoColorante">

    <label>Contenido del frasco (g):</label>
    <input type="number" id="contenidoColorante">

    <label>Gramos usados por vela:</label>
    <input type="number" id="usoColorante">
  </div>

  <div class="section">
    <h2>Otros Costos</h2>
    <label>Costo de la mecha/pabilo por vela ($):</label>
    <input type="number" id="costoMecha">

    <label>Costo del frasco por vela ($):</label>
    <input type="number" id="costoFrasco">

    <label>Costo de etiquetas por vela ($):</label>
    <input type="number" id="costoEtiquetas">

    <label>Costos indirectos por vela ($):</label>
    <input type="number" id="costoIndirecto" value="0">
  </div>

  <div class="section">
    <h2>Margen de Beneficio</h2>
    <label>Margen de beneficio deseado (%):</label>
    <input type="number" id="margen" value="35">
  </div>

  <button onclick="calcularCosto()">Calcular</button>

  <div id="resultado" class="resultado" style="display:none;"></div>

  <script>
    function calcularCosto() {
      const costoCera = parseFloat(document.getElementById('costoCera').value);
      const gramosCera = parseFloat(document.getElementById('gramosCera').value);
      const costoFragancia = parseFloat(document.getElementById('costoFragancia').value);
      const tamanoFragancia = parseFloat(document.getElementById('tamanoFragancia').value);
      const porcentajeFragancia = parseFloat(document.getElementById('porcentajeFragancia').value);
      const costoColorante = parseFloat(document.getElementById('costoColorante').value);
      const contenidoColorante = parseFloat(document.getElementById('contenidoColorante').value);
      const usoColorante = parseFloat(document.getElementById('usoColorante').value);
      const costoMecha = parseFloat(document.getElementById('costoMecha').value);
      const costoFrasco = parseFloat(document.getElementById('costoFrasco').value);
      const costoEtiquetas = parseFloat(document.getElementById('costoEtiquetas').value);
      const costoIndirecto = parseFloat(document.getElementById('costoIndirecto').value);
      const margen = parseFloat(document.getElementById('margen').value);

      const costoCeraVela = (costoCera / 1000) * gramosCera;
      const gramosFragancia = (gramosCera * porcentajeFragancia) / 100;
      const costoFraganciaVela = (costoFragancia / tamanoFragancia) * gramosFragancia;
      const costoColoranteVela = (costoColorante / contenidoColorante) * usoColorante;

      const costoTotal = costoCeraVela + costoFraganciaVela + costoColoranteVela + costoMecha + costoFrasco + costoEtiquetas + costoIndirecto;
      const precioVenta = costoTotal * (1 + margen / 100);

      document.getElementById('resultado').style.display = 'block';
      document.getElementById('resultado').innerHTML = `
        <strong>Costo total por vela:</strong> $${costoTotal.toFixed(2)}<br>
        <strong>Precio sugerido de venta (con ${margen}% de ganancia):</strong> $${precioVenta.toFixed(2)}
      `;
    }
  </script>
</body>
</html>
