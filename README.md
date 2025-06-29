<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Apagador de Escalera - CONALEP</title>
  <style>
    body {
      background: #f0f4f8;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 50px;
    }

    .logo {
      width: 150px;
      margin-bottom: 20px;
    }

    h2 {
      color: #333;
      margin-bottom: 30px;
      text-align: center;
    }

    .card {
      background: white;
      border-radius: 16px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
      padding: 30px;
      text-align: center;
      width: 320px;
    }

    .switches {
      margin-bottom: 20px;
    }

    label {
      display: block;
      margin-bottom: 10px;
      font-weight: 600;
      color: #444;
    }

    select {
      padding: 8px 12px;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 16px;
      width: 100%;
      margin-top: 5px;
      margin-bottom: 15px;
    }

    .light-bulb {
      font-size: 80px;
      margin-top: 20px;
      transition: all 0.3s ease;
    }

    .estado {
      font-size: 18px;
      font-weight: bold;
      color: #555;
      margin-top: 10px;
    }

    .encendida {
      color: orange;
      text-shadow: 0 0 10px orange;
    }

    .apagada {
      color: gray;
    }

    .footer {
      margin-top: 40px;
      font-size: 14px;
      color: #888;
      text-align: center;
    }
  </style>
</head>
<body>

  <!-- Logo de CONALEP (desde URL) -->
  <img src="https://th.bing.com/th/id/R.6cfd926bdd3976d484d841dd8167a04a?rik=cptvJUphIF2SKA&pid=ImgRaw&r=0&sres=1&sresct=1" class="logo">

  <h2>🔌 Simulador de Apagador de Escalera</h2>

  <div class="card">
    <div class="switches">
      <label for="switchA">Interruptor A:</label>
      <select id="switchA" onchange="calcularLuz()">
        <option value="0">0 (Abajo)</option>
        <option value="1">1 (Arriba)</option>
      </select>

      <label for="switchB">Interruptor B:</label>
      <select id="switchB" onchange="calcularLuz()">
        <option value="0">0 (Abajo)</option>
        <option value="1">1 (Arriba)</option>
      </select>
    </div>

    <div id="bombilla" class="light-bulb apagada">💡</div>
    <div id="estadoLuz" class="estado apagada">Luz apagada</div>
  </div>

  <div class="footer">
    Hecho con ❤️ en CONALEP<br>
    Para la materia de Temas Selectos de Matematicas I
  </div>

  <script>
    function calcularLuz() {
      const A = parseInt(document.getElementById("switchA").value);
      const B = parseInt(document.getElementById("switchB").value);

      const luz = (A && !B) || (!A && B);

      const bombilla = document.getElementById("bombilla");
      const estado = document.getElementById("estadoLuz");

      if (luz) {
        bombilla.textContent = "🔆";
        bombilla.className = "light-bulb encendida";
        estado.textContent = "Luz encendida";
        estado.className = "estado encendida";
      } else {
        bombilla.textContent = "💡";
        bombilla.className = "light-bulb apagada";
        estado.textContent = "Luz apagada";
        estado.className = "estado apagada";
      }
    }

    calcularLuz(); // Ejecutar al inicio
  </script>

</body>
</html>
