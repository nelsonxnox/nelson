<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Opiniones Vzla-EEUU (FIX CODIFICACIÓN)</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Segoe UI', sans-serif; background: linear-gradient(135deg, #28a745, #20c997); min-height: 100vh; padding: 20px; }
    .app { max-width: 500px; margin: 40px auto; background: white; border-radius: 20px; overflow: hidden; box-shadow: 0 15px 40px rgba(0,0,0,0.3); }
    .header { background: #28a745; color: white; padding: 30px; text-align: center; }
    .content { padding: 30px; }
    input { width: 100%; padding: 15px; margin: 12px 0; border: 2px solid #ddd; border-radius: 12px; font-size: 16px; }
    input:focus { border-color: #28a745; outline: none; }
    button { width: 100%; background: #007bff; color: white; border: none; padding: 18px; border-radius: 12px; font-size: 20px; font-weight: bold; cursor: pointer; margin: 15px 0; transition: 0.3s; }
    button:hover { background: #0056b3; transform: scale(1.02); }
    button:disabled { background: #ccc; cursor: not-allowed; }
    .opinion { margin-top: 20px; padding: 20px; background: #f8f9fa; border-radius: 12px; border-left: 5px solid #28a745; display: none; line-height: 1.7; font-size: 16px; }
    .opinion strong { color: #28a745; }
    .fecha { font-size: 14px; color: #666; margin-top: 12px; }
    .spinner { text-align: center; padding: 25px; font-size: 18px; color: #28a745; }
    .error { background: #f8d7da; color: #721c24; padding: 15px; border-radius: 12px; margin-top: 10px; display: none; }
    .success { background: #d4edda; color: #155724; padding: 15px; border-radius: 12px; margin-top: 10px; display: none; }
    .info { background: #e9f7ef; padding: 18px; border-radius: 12px; margin-top: 20px; font-size: 15px; }
    .copiar { background: #dc3545; margin-top: 12px; font-size: 16px; padding: 12px; color: white; }
  </style>
</head>
<body>
  <div class="app">
    <div class="header">
      <h2>Opiniones Médicas Vzla-EEUU</h2>
      <p><strong>FIX: Codificación clave xai_</strong></p>
    </div>
    <div class="content">
      <input type="password" id="apiKey" placeholder="Pega tu clave xai_... aquí">
      
      <button onclick="testKey()">PROBAR CLAVE</button>
      <button id="generarBtn" onclick="generarOpinión()" disabled>GENERAR OPINIÓN HOY</button>
      
      <div id="spinner" class="spinner" style="display:none;">Conectando...</div>
      <div id="error" class="error"></div>
      <div id="success" class="success"></div>
      
      <div id="opinion" class="opinion">
        <div id="textoOpinión"></div>
        <div class="fecha" id="fecha"></div>
        <button class="copiar" onclick="copiarOpinión()">Copiar a WhatsApp</button>
      </div>
      
      <div class="info">
        <strong>FIX:</strong> Codificación automática (soporta +, /, =)<br>
        <strong>Modelo:</strong> grok-3-mini (gratis)<br>
        Primero toca <strong>PROBAR CLAVE</strong>
      </div>
    </div>
  </div>

  <script>
    // FUNCIÓN SEGURA PARA CODIFICAR LA CLAVE
    function safeFetch(apiKey, body) {
      const encodedKey = encodeURIComponent(apiKey); // FIX: Codifica + / =
      return fetch('https://api.x.ai/v1/chat/completions', {
        method: 'POST',
        headers: {
          'Authorization': 'Bearer ' + apiKey, // Usa clave original
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(body)
      });
    }

    async function testKey() {
      const apiKey = document.getElementById('apiKey').value.trim();
      if (!apiKey) return mostrarError('Pega tu clave xai_...');

      const spinner = document.getElementById('spinner');
      const success = document.getElementById('success');
      const error = document.getElementById('error');
      const generarBtn = document.getElementById('generarBtn');
      
      spinner.style.display = 'block';
      success.style.display = 'none';
      error.style.display = 'none';

      try {
        const response = await safeFetch(apiKey, {
          model: 'grok-3-mini',
          messages: [{ role: 'user', content: 'Di: "¡Clave OK!"' }],
          max_tokens: 10
        });

        if (!response.ok) throw new Error(`Error ${response.status}`);

        const data = await response.json();
        const msg = data.choices[0].message.content;

        mostrarSuccess('¡CLAVE VÁLIDA! Respuesta: ' + msg);
        generarBtn.disabled = false;
      } catch (err) {
        mostrarError('Error: ' + err.message + '<br><small>Intenta con otra clave o VPN</small>');
        generarBtn.disabled = true;
      } finally {
        spinner.style.display = 'none';
      }
    }

    async function generarOpinión() {
      const apiKey = document.getElementById('apiKey').value.trim();
      const spinner = document.getElementById('spinner');
      const opinion = document.getElementById('opinion');
      const hoy = new Date().toLocaleDateString('es-VE');

      spinner.style.display = 'block';
      opinion.style.display = 'none';

      const especialidades = ['Infectólogo', 'Emergenciólogo', 'Farmacólogo'];
      const nombres = ['Dr. Rafael Acosta', 'Dra. Luisa Herrera', 'Dr. Miguel Torres'];
      const ciudades = ['Caracas', 'Maracaibo', 'Valencia'];
      
      const especialidad = especialidades[Math.floor<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Opiniones Vzla-EEUU (FIX CODIFICACIÓN)</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Segoe UI', sans-serif; background: linear-gradient(135deg, #28a745, #20c997); min-height: 100vh; padding: 20px; }
    .app { max-width: 500px; margin: 40px auto; background: white; border-radius: 20px; overflow: hidden; box-shadow: 0 15px 40px rgba(0,0,0,0.3); }
    .header { background: #28a745; color: white; padding: 30px; text-align: center; }
    .content { padding: 30px; }
    input { width: 100%; padding: 15px; margin: 12px 0; border: 2px solid #ddd; border-radius: 12px; font-size: 16px; }
    input:focus { border-color: #28a745; outline: none; }
    button { width: 100%; background: #007bff; color: white; border: none; padding: 18px; border-radius: 12px; font-size: 20px; font-weight: bold; cursor: pointer; margin: 15px 0; transition: 0.3s; }
    button:hover { background: #0056b3; transform: scale(1.02); }
    button:disabled { background: #ccc; cursor: not-allowed; }
    .opinion { margin-top: 20px; padding: 20px; background: #f8f9fa; border-radius: 12px; border-left: 5px solid #28a745; display: none; line-height: 1.7; font-size: 16px; }
    .opinion strong { color: #28a745; }
    .fecha { font-size: 14px; color: #666; margin-top: 12px; }
    .spinner { text-align: center; padding: 25px; font-size: 18px; color: #28a745; }
    .error { background: #f8d7da; color: #721c24; padding: 15px; border-radius: 12px; margin-top: 10px; display: none; }
    .success { background: #d4edda; color: #155724; padding: 15px; border-radius: 12px; margin-top: 10px; display: none; }
    .info { background: #e9f7ef; padding: 18px; border-radius: 12px; margin-top: 20px; font-size: 15px; }
    .copiar { background: #dc3545; margin-top: 12px; font-size: 16px; padding: 12px; color: white; }
  </style>
</head>
<body>
  <div class="app">
    <div class="header">
      <h2>Opiniones Médicas Vzla-EEUU</h2>
      <p><strong>FIX: Codificación clave xai_</strong></p>
    </div>
    <div class="content">
      <input type="password" id="apiKey" placeholder="Pega tu clave xai_... aquí">
      
      <button onclick="testKey()">PROBAR CLAVE</button>
      <button id="generarBtn" onclick="generarOpinión()" disabled>GENERAR OPINIÓN HOY</button>
      
      <div id="spinner" class="spinner" style="display:none;">Conectando...</div>
      <div id="error" class="error"></div>
      <div id="success" class="success"></div>
      
      <div id="opinion" class="opinion">
        <div id="textoOpinión"></div>
        <div class="fecha" id="fecha"></div>
        <button class="copiar" onclick="copiarOpinión()">Copiar a WhatsApp</button>
      </div>
      
      <div class="info">
        <strong>FIX:</strong> Codificación automática (soporta +, /, =)<br>
        <strong>Modelo:</strong> grok-3-mini (gratis)<br>
        Primero toca <strong>PROBAR CLAVE</strong>
      </div>
    </div>
  </div>

  <script>
    // FUNCIÓN SEGURA PARA CODIFICAR LA CLAVE
    function safeFetch(apiKey, body) {
      const encodedKey = encodeURIComponent(apiKey); // FIX: Codifica + / =
      return fetch('https://api.x.ai/v1/chat/completions', {
        method: 'POST',
        headers: {
          'Authorization': 'Bearer ' + apiKey, // Usa clave original
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(body)
      });
    }

    async function testKey() {
      const apiKey = document.getElementById('apiKey').value.trim();
      if (!apiKey) return mostrarError('Pega tu clave xai_...');

      const spinner = document.getElementById('spinner');
      const success = document.getElementById('success');
      const error = document.getElementById('error');
      const generarBtn = document.getElementById('generarBtn');
      
      spinner.style.display = 'block';
      success.style.display = 'none';
      error.style.display = 'none';

      try {
        const response = await safeFetch(apiKey, {
          model: 'grok-3-mini',
          messages: [{ role: 'user', content: 'Di: "¡Clave OK!"' }],
          max_tokens: 10
        });

        if (!response.ok) throw new Error(`Error ${response.status}`);

        const data = await response.json();
        const msg = data.choices[0].message.content;

        mostrarSuccess('¡CLAVE VÁLIDA! Respuesta: ' + msg);
        generarBtn.disabled = false;
      } catch (err) {
        mostrarError('Error: ' + err.message + '<br><small>Intenta con otra clave o VPN</small>');
        generarBtn.disabled = true;
      } finally {
        spinner.style.display = 'none';
      }
    }

    async function generarOpinión() {
      const apiKey = document.getElementById('apiKey').value.trim();
      const spinner = document.getElementById('spinner');
      const opinion = document.getElementById('opinion');
      const hoy = new Date().toLocaleDateString('es-VE');

      spinner.style.display = 'block';
      opinion.style.display = 'none';

      const especialidades = ['Infectólogo', 'Emergenciólogo', 'Farmacólogo'];
      const nombres = ['Dr. Rafael Acosta', 'Dra. Luisa Herrera', 'Dr. Miguel Torres'];
      const ciudades = ['Caracas', 'Maracaibo', 'Valencia'];
      
      const especialidad = especialidades[Math.floor
