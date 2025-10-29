<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Impresión Kaskis3D — Calculadora de costes</title>
  <meta name="description" content="Impresión Kaskis3D: calculadora de costes de impresión 3D, recursos, ofertas y contacto." />
  <style>
    /* ====== Reset y base ====== */
    :root{
      --bg:#0b0b0b;
      --card:#0f1113;
      --muted:#bfc7d1;
      --neon-blue:#4dd2ff;
      --neon-green:#35ff8a;
      --neon-red:#ff4d6d;
      --glass: rgba(255,255,255,0.03);
      --accent-glow: 0 6px 24px rgba(77,210,255,0.06);
      --radius:14px;
      --maxw:1100px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:Inter,ui-sans-serif,system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;
      background: linear-gradient(180deg, #050506 0%, var(--bg) 100%);
      color:var(--muted);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.4;
    }
    a{color:inherit;text-decoration:none}
    .container{
      max-width:var(--maxw);
      margin:36px auto;
      padding:28px;
    }

    /* ====== Header ====== */
    header{display:flex;align-items:center;justify-content:space-between;gap:20px;margin-bottom:24px}
    .brand{
      display:flex;align-items:center;gap:14px;
    }
    .logo{
      width:56px;height:56px;border-radius:12px;background:linear-gradient(135deg,var(--neon-blue),var(--neon-green));
      display:flex;align-items:center;justify-content:center;color:#060708;font-weight:700;font-size:20px;box-shadow:var(--accent-glow);
    }
    .title{
      font-size:20px;color:var(--neon-blue);font-weight:700;
    }
    nav{display:flex;gap:12px;align-items:center}
    .nav-link{
      padding:8px 12px;border-radius:10px;color:var(--muted);font-weight:600;font-size:14px;
    }
    .nav-link:hover{background:rgba(255,255,255,0.02);color:var(--neon-green)}

    /* ====== Main layout ====== */
    .hero{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
      border-radius:var(--radius);
      padding:28px;
      box-shadow: 0 8px 40px rgba(0,0,0,0.6);
      display:flex;gap:26px;align-items:center;
    }
    .hero-left{flex:1}
    .hero-right{width:360px;min-width:260px}

    h1{margin:0;font-size:28px;color:var(--neon-green)}
    p.lead{margin-top:8px;color:#cfeee0}

    /* ====== Card styles ====== */
    .card{
      background:var(--card);
      border-radius:12px;
      padding:18px;
      box-shadow: 0 6px 30px rgba(0,0,0,0.6);
      border: 1px solid rgba(255,255,255,0.02);
    }

    /* ====== Calculator layout ====== */
    .calc-grid{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:12px;
      margin-top:16px;
    }
    @media (max-width:900px){
      .hero{flex-direction:column}
      .hero-right{width:100%}
      .calc-grid{grid-template-columns:repeat(2,1fr)}
    }
    @media (max-width:560px){
      .calc-grid{grid-template-columns:1fr}
    }
    label{display:block;font-size:13px;color:#9fb8b0;margin-bottom:6px}
    input[type="number"], input[type="text"], select{
      width:100%;
      padding:10px 12px;border-radius:10px;border:1px solid rgba(255,255,255,0.04);
      background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));
      color:var(--muted);font-weight:600;
    }
    .small{font-size:12px;color:#8ea7a0}
    .muted-note{font-size:13px;color:#97a8a0;margin-top:8px}

    /* ====== Results ====== */
    .results{
      margin-top:16px;padding:16px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);
      display:flex;flex-direction:column;gap:10px;
    }
    .result-row{display:flex;justify-content:space-between;align-items:center}
    .result-title{color:#b8e9d1;font-weight:700}
    .result-value{font-weight:800;font-size:18px}
    .total {
      font-size:22px;color:var(--neon-blue);font-weight:900;text-shadow:0 6px 30px rgba(77,210,255,0.06);
    }

    /* ====== Buttons ====== */
    .btn{
      display:inline-block;padding:10px 14px;border-radius:10px;font-weight:800;
      cursor:pointer;border:0;background:var(--neon-blue);color:#021;box-shadow:var(--accent-glow);
    }
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.04);color:var(--neon-green)}

    /* ====== Sections below ====== */
    .grid-2{display:grid;grid-template-columns:2fr 1fr;gap:16px;margin-top:20px}
    @media (max-width:900px){ .grid-2{grid-template-columns:1fr} }

    .offer-list{display:flex;flex-direction:column;gap:12px}
    .offer{
      padding:12px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), transparent);border:1px solid rgba(255,255,255,0.02);
    }

    /* ====== Footer ====== */
    footer{margin-top:28px;padding:20px;border-radius:12px;background:var(--glass);display:flex;justify-content:space-between;align-items:center;gap:12px}
    .tag{
      padding:8px 12px;border-radius:10px;background:rgba(255,255,255,0.02);font-weight:700;color:var(--neon-red)
    }

    /* highlight placeholders */
    .placeholder-highlight{color:var(--neon-red);font-weight:900;background:rgba(255,77,109,0.04);padding:2px 8px;border-radius:8px}
    .uppercase{font-weight:900;letter-spacing:0.6px;text-transform:uppercase}
    .accent-link{color:var(--neon-blue);font-weight:800}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">K3D</div>
        <div>
          <div class="title">Impresión Kaskis3D</div>
          <div style="font-size:12px;color:#9fb8b0;margin-top:2px">Costes · Ofertas · Sorteos · Cursos</div>
        </div>
      </div>

      <nav>
        <a class="nav-link" href="#inicio">Inicio</a>
        <a class="nav-link" href="#calculadora">Calculadora</a>
        <a class="nav-link" href="#ofertas">Ofertas</a>
        <a class="nav-link" href="#links">TUS ENLACES</a>
        <a class="nav-link" href="#redes">TUS REDES</a>
      </nav>
    </header>

    <!-- HERO -->
    <section id="inicio" class="hero card">
      <div class="hero-left">
        <h1>Impresión Kaskis3D</h1>
        <p class="lead">Calcula el coste real de tus impresiones 3D al instante. Material + energía + margen de error + margen de ganancia. Comparte ofertas, sorteos y cursos.</p>

        <div style="margin-top:14px;display:flex;gap:10px;flex-wrap:wrap">
          <button class="btn" onclick="document.getElementById('calculadora').scrollIntoView({behavior:'smooth'})">Abrir calculadora</button>
          <a class="btn-ghost" href="#ofertas">Ver ofertas</a>
        </div>

        <p class="muted-note">Consejo: usa los multiplicadores recomendados para ventas por mayor o llaveros — están en la calculadora.</p>
      </div>

      <div class="hero-right card">
        <div style="display:flex;flex-direction:column;gap:10px">
          <div style="font-size:13px;color:#9fb8b0">Vídeo destacado</div>
          <!-- VIDEO PLACEHOLDER: cambia el src por tu video de YouTube si quieres -->
          <div style="aspect-ratio:16/9;border-radius:10px;overflow:hidden;background:#000">
            <iframe width="100%" height="100%" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Vídeo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div>
          <div style="font-size:13px;color:#9fb8b0">Publica aquí tus sorteos, cursos o promociones.</div>
        </div>
      </div>
    </section>

    <!-- CALCULADORA -->
    <section id="calculadora" style="margin-top:18px;">
      <div class="card">
        <div style="display:flex;justify-content:space-between;align-items:center">
          <div>
            <h2 style="margin:0;color:var(--neon-blue)">Calculadora de costes</h2>
            <div style="font-size:13px;color:#9fb8b0">Material + electricidad + margen de error + ganancia</div>
          </div>
          <div style="text-align:right">
            <div style="font-size:12px;color:#97a8a0">Resultado actualizado en tiempo real</div>
          </div>
        </div>

        <!-- Grid de inputs: 3 columnas -->
        <div class="calc-grid">
          <!-- Col 1 -->
          <div>
            <label>Precio por KG (€/kg)</label>
            <input id="priceKg" type="number" min="0" step="0.01" value="20.00" />
            <div class="small">Ej: 20.00 €</div>
          </div>

          <div>
            <label>Gramos de filamento (g)</label>
            <input id="grams" type="number" min="0" step="1" value="50" />
            <div class="small">Peso real de la pieza</div>
          </div>

          <div>
            <label>Margen de error / desperdicio (%)</label>
            <input id="wastePct" type="number" min="0" step="0.1" value="5.0" />
            <div class="small">Porcentaje aplicado al material (ej: 5%)</div>
          </div>

          <!-- Col 2 -->
          <div>
            <label>Consumo impresora (W)</label>
            <input id="printerW" type="number" min="0" step="1" value="120" />
            <div class="small">Ej: 120 W</div>
          </div>

          <div>
            <label>Tiempo de impresión — HORAS</label>
            <input id="timeH" type="number" min="0" step="1" value="2" />
            <div class="small">Horas</div>
          </div>

          <div>
            <label>Tiempo de impresión — MINUTOS</label>
            <input id="timeM" type="number" min="0" max="59" step="1" value="30" />
            <div class="small">Minutos</div>
          </div>

          <!-- Col 3 -->
          <div>
            <label>Precio energía (€/kWh)</label>
            <input id="priceKwh" type="number" min="0" step="0.001" value="0.25" />
            <div class="small">Precio por kWh</div>
          </div>

          <div>
            <label>Margen de ganancia (multiplicador)</label>
            <select id="multiplier" onchange="multiplierChanged()">
              <option value="1.5">Recomendado: Mayorista / ministiets — x1.5</option>
              <option value="2.5">Llaveros / pequeños objetos — x2.5</option>
              <option value="3.5">Retail / precio final — x3.5</option>
              <option value="custom">PERSONALIZADO</option>
            </select>
            <input id="customMultiplier" type="number" min="0" step="0.1" value="1.5" style="margin-top:8px;display:none" />
            <div class="small">Elige un multiplicador o usa uno propio</div>
          </div>

          <div>
            <label>Mostrar margen de seguridad (%) — (opcional)</label>
            <input id="safetyPct" type="number" min="0" step="0.1" value="0" />
            <div class="small">Añade % extra al precio final si quieres</div>
          </div>
        </div>

        <!-- botones -->
        <div style="display:flex;gap:10px;margin-top:14px;align-items:center">
          <button class="btn" onclick="calculate()">Calcular</button>
          <button class="btn-ghost" onclick="resetForm()">Reset</button>
          <div style="margin-left:auto;font-size:13px;color:#9fb8b0">Exportar: <button class="btn-ghost" onclick="copyResults()">Copiar resultados</button></div>
        </div>

        <!-- RESULTADOS -->
        <div id="resultsBox" class="results">
          <div class="result-row"><div class="result-title">Material (filamento)</div><div id="resMaterial" class="result-value">--</div></div>
          <div class="result-row"><div class="result-title">Electricidad</div><div id="resElectric" class="result-value">--</div></div>
          <div class="result-row"><div class="result-title">Subtotal (material + energía)</div><div id="resSubtotal" class="result-value">--</div></div>
          <div class="result-row"><div class="result-title">Precio con margen de ganancia</div><div id="resWithMargin" class="result-value total">--</div></div>
          <div class="result-row"><div class="result-title">Precio con margen de seguridad</div><div id="resFinal" class="result-value total">--</div></div>
          <div style="font-size:13px;color:#9fb8b0;margin-top:6px">Desglose: puedes ajustar <strong>Precio por kg</strong>, <strong>Precio kWh</strong>, <strong>Consumo</strong> y <strong>margen de error</strong> para afinar resultados.</div>
        </div>
      </div>
    </section>

    <!-- CONTENIDO: ofertas / sorteos / cursos -->
    <section id="ofertas" class="grid-2">
      <div>
        <div class="card">
          <h3 style="color:var(--neon-green);margin-top:0">Publicaciones — Sorteos / Ofertas / Cursos</h3>
          <p class="muted-note">Aquí puedes publicar sorteos, enlaces de afiliado, o incrustar vídeos y cursos.</p>

          <div class="offer-list">
            <!-- Ejemplo de oferta: copia y edita -->
            <div class="offer">
              <div style="display:flex;justify-content:space-between;align-items:center">
                <div>
                  <div style="font-weight:800;color:var(--neon-blue)">Sorteo: Pack de filamento</div>
                  <div style="font-size:13px;color:#9fb8b0">Bases: sigue las redes y comparte. Enlace en la descripción.</div>
                </div>
                <div><a class="accent-link" href="#" onclick="alert('Sustituye este enlace por tu URL de sorteo')">Enlace</a></div>
              </div>
            </div>

            <div class="offer">
              <div style="display:flex;justify-content:space-between;align-items:center">
                <div>
                  <div style="font-weight:800;color:var(--neon-green)">Curso rápido: Inicio en impresión 3D</div>
                  <div style="font-size:13px;color:#9fb8b0">Vídeo / PDF / Recursos</div>
                </div>
                <div><a class="accent-link" href="#">Acceder</a></div>
              </div>
            </div>
          </div>

          <p style="margin-top:12px;font-size:13px;color:#9fb8b0">Puedes añadir aquí tantos items como quieras. Cada card admite enlace de afiliado.</p>
        </div>

        <!-- Video o recurso subida -->
        <div class="card" style="margin-top:12px">
          <h3 style="margin:0;color:var(--neon-red)">Tutorial destacado</h3>
          <p class="small">Incrusta aquí tus vídeos si los subes a YouTube o enlaza al recurso.</p>
          <div style="aspect-ratio:16/9;border-radius:10px;overflow:hidden;background:#000;margin-top:10px">
            <!-- Cambia este iframe por tu vídeo -->
            <iframe width="100%" height="100%" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="Tutorial" frameborder="0" allowfullscreen></iframe>
          </div>
        </div>
      </div>

      <!-- Sidebar: enlaces y redes -->
      <aside>
        <div class="card">
          <h4 style="margin:0;color:var(--neon-blue)">TUS ENLACES</h4>
          <p class="small">Reemplaza estos items con tus páginas recomendadas (Thingiverse, MyMiniFactory, etc.)</p>
          <ul style="padding-left:14px;margin-top:10px">
            <li><a class="accent-link" href="#" onclick="alert('Sustituye por tu enlace 1')">ENLACE 1 — Nombre del sitio</a></li>
            <li><a class="accent-link" href="#" onclick="alert('Sustituye por tu enlace 2')">ENLACE 2 — Modelos 3D</a></li>
            <li><a class="accent-link" href="#" onclick="alert('Sustituye por tu enlace 3')">ENLACE 3 — Repuestos</a></li>
          </ul>

          <div style="margin-top:12px">
            <h4 style="margin:0;color:var(--neon-green)" id="redesTitle">TUS REDES</h4>
            <p class="small">Sustituye por tus enlaces de redes sociales.</p>
            <div style="display:flex;flex-direction:column;gap:8px;margin-top:8px">
              <a class="nav-link" href="#" style="display:inline-block">Instagram — @TU_USUARIO</a>
              <a class="nav-link" href="#" style="display:inline-block">YouTube — Canal</a>
              <a class="nav-link" href="#" style="display:inline-block">Twitter / X</a>
            </div>
          </div>

          <div style="margin-top:12px">
            <h4 style="margin:0;color:var(--neon-red)">Contacto</h4>
            <p class="small">Correo o WhatsApp para consultas</p>
            <div style="display:flex;gap:8px;margin-top:8px">
              <!-- Cambia el mailto y el link de WhatsApp con tus datos -->
              <a class="btn-ghost" href="mailto:tuemail@dominio.com">Correo</a>
              <a class="btn" href="https://wa.me/34600000000" target="_blank" rel="noopener">WhatsApp</a>
            </div>
          </div>
        </div>

        <!-- Widget rápido de recomendaciones -->
        <div class="card" style="margin-top:12px">
          <h4 style="margin:0;color:var(--neon-blue)">Recomendados (multiplicadores)</h4>
          <ul style="margin-top:8px">
            <li><strong>Mayorista / ministiets:</strong> x1.5 (recomendado)</li>
            <li><strong>Llaveros / pequeños:</strong> x2.5</li>
            <li><strong>Retail (final):</strong> x3.5</li>
          </ul>
        </div>
      </aside>
    </section>

    <footer>
      <div>
        <div style="font-weight:800;color:var(--neon-green)">Impresión Kaskis3D</div>
        <div style="font-size:13px;color:#9fb8b0">© <span id="copyYear"></span> — Todos los derechos</div>
      </div>

      <div style="display:flex;gap:10px;align-items:center">
        <div class="placeholder-highlight uppercase">TUS ENLACES</div>
        <div class="placeholder-highlight uppercase">TUS REDES</div>
      </div>
    </footer>
  </div>

  <script>
    // ====== Helpers y comportamiento del multiplicador ======
    function multiplierChanged(){
      const sel = document.getElementById('multiplier');
      const custom = document.getElementById('customMultiplier');
      if(sel.value === 'custom'){ custom.style.display = 'block'; }
      else { custom.style.display = 'none'; custom.value = sel.value; }
      calculate();
    }

    function parseNum(id){ const el=document.getElementById(id); return Number(el.value)||0 }

    // cálculo principal
    function calculate(){
      // inputs
      const priceKg = parseNum('priceKg');         // €/kg
      const grams = parseNum('grams');             // g
      const wastePct = parseNum('wastePct');       // %
      const printerW = parseNum('printerW');       // W
      const timeH = parseNum('timeH');             // horas
      const timeM = parseNum('timeM');             // minutos
      const priceKwh = parseNum('priceKwh');       // €/kWh
      let multiplier = parseNum('customMultiplier');
      const sel = document.getElementById('multiplier');
      if(sel.value !== 'custom') multiplier = parseFloat(sel.value) || 1.0;
      const safetyPct = parseNum('safetyPct');

      // normalizar tiempo a horas
      const totalHours = timeH + (timeM/60);

      // añadir margen de error al material
      const effectiveGrams = grams * (1 + wastePct/100);

      // material cost
      const materialKg = effectiveGrams / 1000.0; // kg
      const materialCost = materialKg * priceKg;

      // electricity cost: (W -> kW) * hours * price
      const kW = printerW / 1000.0;
      const energyCost = kW * totalHours * priceKwh;

      // subtotal
      const subtotal = materialCost + energyCost;

      // price with multiplier
      const priceWithMargin = subtotal * multiplier;

      // apply safety percentage
      const finalPrice = priceWithMargin * (1 + safetyPct/100);

      // rounding
      function fmt(x){ return '€ ' + x.toFixed(2) }
      function fmtSmall(x){ return x.toFixed(3) }

      // fill results
      document.getElementById('resMaterial').textContent = fmt(materialCost) + ` (${fmtSmall(materialKg)} kg)`;
      document.getElementById('resElectric').textContent = fmt(energyCost) + ` (${totalHours.toFixed(2)} h · ${printerW} W)`;
      document.getElementById('resSubtotal').textContent = fmt(subtotal);
      document.getElementById('resWithMargin').textContent = fmt(priceWithMargin) + ` · x${multiplier}`;
      document.getElementById('resFinal').textContent = fmt(finalPrice);

      // store last calculation in dataset for copy/export
      const box = document.getElementById('resultsBox');
      box.dataset.last = JSON.stringify({
        priceKg, grams, wastePct, printerW, timeH, timeM, priceKwh, multiplier, safetyPct,
        materialCost, energyCost, subtotal, priceWithMargin, finalPrice
      });
    }

    function resetForm(){
      document.getElementById('priceKg').value = '20.00';
      document.getElementById('grams').value = '50';
      document.getElementById('wastePct').value = '5.0';
      document.getElementById('printerW').value = '120';
      document.getElementById('timeH').value = '2';
      document.getElementById('timeM').value = '30';
      document.getElementById('priceKwh').value = '0.25';
      document.getElementById('multiplier').value = '1.5';
      document.getElementById('customMultiplier').value = '1.5';
      document.getElementById('customMultiplier').style.display = 'none';
      document.getElementById('safetyPct').value = '0';
      calculate();
    }

    function copyResults(){
      const box = document.getElementById('resultsBox');
      if(!box.dataset.last){ alert('Primero pulsa Calcular para generar resultados.'); return; }
      const d = JSON.parse(box.dataset.last);
      const txt = [
        '=== CÁLCULO IMPRESIÓN 3D — Impresión Kaskis3D ===',
        `Material: € ${d.materialCost.toFixed(2)} (${(d.grams*(1+d.wastePct/100)/1000).toFixed(3)} kg)`,
        `Electricidad: € ${d.energyCost.toFixed(2)} (${(d.timeH + d.timeM/60).toFixed(2)} h · ${d.printerW} W)`,
        `Subtotal: € ${d.subtotal.toFixed(2)}`,
        `Precio con margen (x${d.multiplier}): € ${d.priceWithMargin.toFixed(2)}`,
        `Precio final (con seguridad ${d.safetyPct}%): € ${d.finalPrice.toFixed(2)}`,
        '-----------------------------------------------'
      ].join('\n');
      navigator.clipboard?.writeText(txt).then(()=>{ alert('Resultados copiados al portapapeles.'); }, ()=>{ alert('No se pudo copiar: copia manualmente.'); });
    }

    // init
    document.getElementById('copyYear').textContent = new Date().getFullYear();
    multiplierChanged();
    calculate();
  </script>
</body>
</html>
