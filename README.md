<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CV - Alexis Michael Mamani Colque</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --azul: #2f80ed;
    --azul-oscuro: #1f5fbf;
    --azul-suave: #eaf3ff;
    --azul-borde: #d5e7ff;
    --texto: #1f2a3a;
    --gris: #5b6675;
  }
  body {
    font-family: "Segoe UI", Helvetica, Arial, sans-serif;
    background: linear-gradient(135deg, #f0f7ff 0%, #c9e2ff 100%);
    min-height: 100vh;
    color: var(--texto);
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0 14px 32px;
  }

  /* MENÚ Y SUBMENÚS */
  .menu {
    position: sticky;
    top: 0;
    z-index: 20;
    width: 100%;
    background: rgba(255,255,255,.94);
    backdrop-filter: blur(6px);
    box-shadow: 0 4px 16px rgba(20,80,160,.12);
    margin-bottom: 26px;
  }
  .menu-lista {
    list-style: none;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 4px;
    padding: 6px 10px;
  }
  .menu-lista li { position: relative; }
  .menu-lista > li > a {
    display: block;
    padding: 12px 16px;
    font-size: 13px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: .8px;
    color: #34465e;
    text-decoration: none;
    border-bottom: 3px solid transparent;
    transition: color .2s, border-color .2s;
  }
  .menu-lista > li > a:hover,
  .menu-lista > li:focus-within > a,
  .menu-lista > li:hover > a {
    color: var(--azul-oscuro);
    border-bottom-color: var(--azul);
  }
  .sub {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    min-width: 190px;
    background: #fff;
    border-radius: 12px;
    box-shadow: 0 10px 28px rgba(20,80,160,.18);
    padding: 6px 0;
    overflow: hidden;
  }
  .sub a {
    display: block;
    padding: 10px 18px;
    font-size: 13px;
    color: #34465e;
    text-decoration: none;
    font-weight: 600;
  }
  .sub a:hover { background: var(--azul-suave); color: var(--azul-oscuro); }
  .con-sub:hover .sub,
  .con-sub:focus-within .sub { display: block; }
  h2, aside, header { scroll-margin-top: 90px; }

  /* TARJETA */
  .cv {
    width: 900px;
    max-width: 100%;
    background: #fff;
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 12px 40px rgba(20,80,160,.2);
    display: grid;
    grid-template-columns: 300px 1fr;
    animation: aparecer 1.2s ease both;
  }
  @keyframes aparecer {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* CABECERA */
  .header {
    grid-column: 1 / -1;
    background: linear-gradient(120deg, var(--azul-oscuro), var(--azul) 60%, #56a8ff);
    padding: 40px 40px 34px;
    color: #fff;
    position: relative;
    overflow: hidden;
  }
  .header::after {
    content: "";
    position: absolute;
    right: -60px; top: -60px;
    width: 220px; height: 220px;
    border-radius: 50%;
    background: rgba(255,255,255,.14);
  }
  .header h1 {
    font-size: 34px;
    font-weight: 800;
    letter-spacing: .5px;
    min-height: 42px;
    text-shadow: 0 2px 8px rgba(0,0,0,.15);
  }
  .header .subtitulo {
    font-size: 19px;
    font-weight: 700;
    margin-top: 8px;
    min-height: 26px;
    max-width: none;
    opacity: .95;
  }
  .header .linea {
    height: 3px;
    width: 0;
    background: #fff;
    margin: 14px 0;
    border-radius: 2px;
    transition: width 1.6s ease .6s;
  }
  .listo .header .linea { width: 100%; }
  .header p {
    font-size: 15px;
    line-height: 1.6;
    font-weight: 600;
    max-width: 620px;
    min-height: 52px;
  }

  /* COLUMNAS */
  .left {
    background: var(--azul-suave);
    padding: 30px 26px;
  }
  .right {
    padding: 30px 34px;
  }
  .section { margin-bottom: 30px; }
  .section h2 {
    font-size: 15px;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    padding-bottom: 8px;
    margin-bottom: 16px;
    border-bottom: 2px solid var(--azul);
    display: flex;
    align-items: center;
    gap: 8px;
    min-height: 28px;
    color: var(--azul-oscuro);
  }
  .contact-item {
    font-size: 13.5px;
    line-height: 1.5;
    margin-bottom: 12px;
    padding-left: 2px;
  }
  .contact-item strong {
    display: block;
    font-size: 11px;
    color: var(--azul);
    text-transform: uppercase;
    letter-spacing: .6px;
  }
  .contact-item a {
    color: var(--azul-oscuro);
    font-weight: 600;
    text-decoration: none;
    border-bottom: 1px dashed var(--azul);
    transition: color .2s;
  }
  .contact-item a:hover { color: var(--azul); }
  .btn-contacto {
    display: block;
    text-align: center;
    margin: 10px 0;
    padding: 10px 14px;
    border-radius: 999px;
    background: linear-gradient(120deg, var(--azul-oscuro), var(--azul));
    color: #fff;
    font-size: 13px;
    font-weight: 700;
    text-decoration: none;
    box-shadow: 0 6px 14px rgba(31,95,191,.25);
    transition: transform .2s ease, box-shadow .2s ease;
  }
  .btn-contacto:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(31,95,191,.35);
  }
  .lang { margin-bottom: 16px; font-size: 14px; }
  .lang .nivel { float: right; font-weight: 700; color: var(--azul-oscuro); }
  .bar {
    height: 8px;
    background: #fff;
    border-radius: 6px;
    margin-top: 6px;
    overflow: hidden;
    box-shadow: inset 0 1px 3px rgba(0,0,0,.08);
  }
  .bar span {
    display: block;
    height: 100%;
    width: 0;
    background: linear-gradient(90deg, var(--azul), #56a8ff);
    border-radius: 6px;
    transition: width 1.8s ease;
  }
  .listo .bar span { width: var(--p); }

  /* HABILIDADES */
  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
  }
  .card {
    background: #fff;
    border: 1px solid var(--azul-borde);
    border-left: 4px solid var(--azul);
    border-radius: 12px;
    padding: 14px 16px;
    box-shadow: 0 3px 10px rgba(20,80,160,.06);
    transition: transform .25s ease, box-shadow .25s ease;
  }
  .card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 18px rgba(31,95,191,.22);
  }
  .card .icono { font-size: 22px; margin-bottom: 6px; }
  .card h3 { font-size: 14.5px; margin-bottom: 4px; min-height: 20px; }
  .card p { font-size: 13px; color: var(--gris); line-height: 1.45; min-height: 20px; }

  /* TARJETA ANCHA CON ILUSTRACIÓN */
  .card.ancha {
    grid-column: span 2;
    display: grid;
    grid-template-columns: 1fr 200px;
    gap: 14px;
    align-items: center;
  }
  .card.ancha .ilustracion svg { width: 100%; height: auto; display: block; }
  @media (max-width: 560px) {
    .card.ancha { grid-column: span 1; grid-template-columns: 1fr; }
  }

  /* FORTALEZAS */
  .tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .tag {
    background: var(--azul-suave);
    border: 1px solid var(--azul);
    color: var(--azul-oscuro);
    padding: 6px 14px;
    border-radius: 999px;
    font-size: 13px;
    font-weight: 600;
    opacity: 0;
    transform: scale(.9);
    transition: opacity .5s ease, transform .5s ease;
  }
  .listo .tag { opacity: 1; transform: scale(1); }

  /* ITEMS */
  .item { margin-bottom: 18px; }
  .item-head {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 10px;
    font-size: 15px;
    font-weight: 700;
  }
  .item-head .fecha { font-weight: 500; font-size: 13px; color: var(--gris); white-space: nowrap; }
  .item .lugar { font-size: 13.5px; color: var(--azul-oscuro); font-weight: 600; margin: 4px 0 8px; }
  .item ul { padding-left: 20px; font-size: 13.5px; line-height: 1.7; color: #3a4658; }
  .item p { font-size: 13.5px; line-height: 1.6; color: #3a4658; }

  /* EFECTO DE ESCRITURA */
  .typing::after {
    content: "|";
    color: var(--azul);
    margin-left: 2px;
    animation: parpadeo .8s steps(2, start) infinite;
  }
  @keyframes parpadeo {
    to { visibility: hidden; }
  }

  .sugerencia {
    position: fixed;
    bottom: 14px;
    left: 50%;
    transform: translateX(-50%);
    background: rgba(20,50,100,.85);
    color: #fff;
    font-size: 12px;
    padding: 6px 14px;
    border-radius: 999px;
    opacity: 0;
    transition: opacity .6s ease;
    pointer-events: none;
  }
  .escribiendo .sugerencia { opacity: 1; }

  @media (max-width: 720px) {
    .cv { grid-template-columns: 1fr; }
    .header { padding: 28px 24px; }
    .header h1 { font-size: 26px; }
    .right { padding: 24px 20px; }
  }
  .con-logo { display: flex; align-items: center; gap: 10px; }
  .logo-mini { width: 36px; height: auto; flex-shrink: 0; border-radius: 4px; }
  /* IMPRESIÓN EN BLANCO Y NEGRO */
  @media print {
    @page { margin: 12mm; }
    * {
      -webkit-print-color-adjust: economy;
      print-color-adjust: economy;
      text-shadow: none !important;
      box-shadow: none !important;
    }
    body {
      background: #fff !important;
      color: #000 !important;
      padding: 0;
      display: block;
    }
    .menu, .sugerencia, .btn-contacto { display: none !important; }
    .cv {
      width: 100%;
      border-radius: 0;
      animation: none;
      background: #fff;
    }
    .header {
      background: #fff !important;
      color: #000 !important;
      border-bottom: 2px solid #000;
    }
    .header::after { display: none; }
    .header h1, .header p, .header .subtitulo { color: #000 !important; }
    .header .linea { background: #000 !important; }
    .left { background: #f2f2f2 !important; }
    .section h2, .section h2 {
      color: #000 !important;
      border-bottom: 2px solid #000 !important;
    }
    .contact-item strong,
    .lang .nivel,
    .item .lugar,
    .item-head .fecha { color: #333 !important; }
    .bar { background: #fff; border: 1px solid #777; }
    .bar span { background: #555 !important; }
    .card {
      background: #fff !important;
      border: 1px solid #999 !important;
      border-left: 4px solid #000 !important;
      transform: none !important;
      break-inside: avoid;
    }
    .card p, .item p, .item ul { color: #222 !important; }
    .card h3, .item-head, .item .lugar, .contact-item { color: #000 !important; }
    .tag {
      background: #fff !important;
      border: 1px solid #000 !important;
      color: #000 !important;
      opacity: 1 !important;
      transform: none !important;
    }
    .ilustracion svg { filter: grayscale(100%); }
    .section { break-inside: avoid; }
    .typing::after { display: none; }
  }
</style>
</head>
<body>

<nav class="menu">
  <ul class="menu-lista">
    <li><a href="#inicio">Inicio</a></li>
    <li><a href="#contacto">Contacto</a></li>
    <li class="con-sub">
      <a href="#habilidades">Habilidades ▾</a>
      <div class="sub">
        <a href="#habilidades">Técnicas</a>
        <a href="#fortalezas">Fortalezas</a>
      </div>
    </li>
    <li><a href="#practicas">Prácticas</a></li>
    <li><a href="#experiencia">Experiencia</a></li>
    <li><a href="#formacion">Formación</a></li>
  </ul>
</nav>

<div class="cv" id="cv">

  <header class="header" id="inicio">
    <h1 data-type data-speed="110">Alexis Michael Mamani Colque</h1>
    <p class="subtitulo" data-type data-speed="45">Arreglando computadoras con una sonrisa</p>
    <div class="linea"></div>
    <p data-type data-speed="28">Estudiante de Arquitectura y Plataformas de Servicios TI.</p>
  </header>

  <aside class="left">
    <div class="section">
      <h2 id="contacto">Contacto</h2>
      <div class="contact-item">
        <strong>Dirección</strong>
        Barrio San Martín, Santa Lucía<br>Lampa, Puno, Perú
      </div>
      <div class="contact-item">
        <strong>Teléfono</strong>
        <a href="tel:+51932015690">932 015 690</a><br>
        <a href="https://wa.me/51932015690" target="_blank" rel="noopener">WhatsApp</a> ·
        <a href="sms:+51932015690">Mensaje</a>
      </div>
      <div class="contact-item">
        <strong>Correo</strong>
        <a href="mailto:alexismamanicolque69@gmail.com">alexismamanicolque69@gmail.com</a>
      </div>
      <a class="btn-contacto" href="https://mail.google.com/mail/?view=cm&fs=1&to=alexismamanicolque69@gmail.com&su=Consulta%20desde%20tu%20CV" target="_blank" rel="noopener">✉ Escribir por Gmail</a>
      <a class="btn-contacto" href="https://wa.me/51932015690?text=Hola%20Alexis%2C%20vi%20tu%20CV" target="_blank" rel="noopener">💬 Escribir por WhatsApp</a>
      <div class="contact-item">
        <strong>DNI</strong>
        72851393
      </div>
    </div>

    <div class="section">
      <h2>Idiomas</h2>
      <div class="lang">
        <strong>Español</strong> <span class="nivel">Nativo</span>
        <div class="bar"><span style="--p: 100%"></span></div>
      </div>
      <div class="lang">
        <strong>Inglés</strong> <span class="nivel">Básico</span>
        <div class="bar"><span style="--p: 33%"></span></div>
      </div>
    </div>
  </aside>

  <main class="right">

    <div class="section">
      <h2 id="habilidades">Habilidades</h2>
      <div class="cards">

        <div class="card ancha">
          <div>
            <h3 data-type data-speed="30">Mantenimiento de computadoras</h3>
            <p data-type data-speed="18">Arreglo y mantenimiento de equipos con actitud positiva, paciencia y una gran sonrisa.</p>
          </div>
          <div class="ilustracion">
            <svg viewBox="0 0 260 170" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Técnico sonriente arreglando una computadora">
              <!-- fondo -->
              <rect x="0" y="0" width="260" height="170" rx="14" fill="#eaf3ff"/>
              <circle cx="40" cy="30" r="22" fill="#d5e7ff"/>
              <circle cx="232" cy="130" r="30" fill="#d5e7ff"/>
              <!-- mesa -->
              <rect x="10" y="140" width="240" height="8" rx="4" fill="#1f5fbf"/>
              <!-- computadora -->
              <rect x="30" y="50" width="120" height="82" rx="8" fill="#2f80ed"/>
              <rect x="40" y="60" width="100" height="62" rx="4" fill="#bfe0ff"/>
              <rect x="40" y="60" width="100" height="62" rx="4" fill="none" stroke="#1f5fbf" stroke-width="2"/>
              <!-- contenido de pantalla (barras) -->
              <rect x="50" y="72" width="50" height="5" rx="2" fill="#1f5fbf" opacity=".6"/>
              <rect x="50" y="84" width="72" height="5" rx="2" fill="#1f5fbf" opacity=".4"/>
              <rect x="50" y="96" width="40" height="5" rx="2" fill="#1f5fbf" opacity=".4"/>
              <rect x="40" y="108" width="100" height="4" rx="2" fill="#1f5fbf" opacity=".2"/>
              <!-- base -->
              <rect x="70" y="132" width="20" height="8" fill="#1f5fbf"/>
              <rect x="55" y="138" width="50" height="4" rx="2" fill="#1f5fbf"/>
              <!-- llave inglesa -->
              <g transform="translate(160 96) rotate(-35)">
                <rect x="-4" y="0" width="8" height="40" rx="3" fill="#8fa3b8"/>
                <circle cx="0" cy="-2" r="9" fill="#8fa3b8"/>
                <rect x="-8" y="-12" width="6" height="8" fill="#eaf3ff"/>
              </g>
              <!-- persona -->
              <!-- cuerpo -->
              <path d="M186 140 L186 104 Q186 92 200 92 L212 92 Q226 92 226 104 L226 140 Z" fill="#1f5fbf"/>
              <!-- cuello -->
              <rect x="201" y="82" width="10" height="12" fill="#f1c79b"/>
              <!-- cabeza -->
              <circle cx="206" cy="66" r="20" fill="#f1c79b"/>
              <!-- cabello -->
              <path d="M186 62 Q186 42 206 42 Q226 42 226 62 Q222 52 206 52 Q192 52 186 62 Z" fill="#3a2a1d"/>
              <!-- ojos -->
              <circle cx="199" cy="66" r="2.2" fill="#3a2a1d"/>
              <circle cx="213" cy="66" r="2.2" fill="#3a2a1d"/>
              <!-- sonrisa -->
              <path d="M198 73 Q206 82 214 73" stroke="#7a3e1d" stroke-width="2.2" fill="none" stroke-linecap="round"/>
              <!-- mejillas -->
              <circle cx="195" cy="74" r="3" fill="#f5a3a3" opacity=".6"/>
              <circle cx="217" cy="74" r="3" fill="#f5a3a3" opacity=".6"/>
              <!-- brazo hacia la computadora -->
              <path d="M190 112 Q176 116 166 110" stroke="#f1c79b" stroke-width="8" fill="none" stroke-linecap="round"/>
              <!-- destellos de alegría -->
              <path d="M240 40 L243 46 L249 46 L244 50 L246 56 L240 52 L234 56 L236 50 L231 46 L237 46 Z" fill="#56a8ff"/>
              <circle cx="20" cy="110" r="3" fill="#2f80ed"/>
              <circle cx="150" cy="30" r="2.5" fill="#2f80ed"/>
            </svg>
          </div>
        </div>

        <div class="card"><div class="icono">💻</div><h3 data-type data-speed="30">Ofimática</h3><p data-type data-speed="18">Manejo de programas de oficina para documentos y presentaciones.</p></div>
        <div class="card"><div class="icono">📊</div><h3 data-type data-speed="30">Excel</h3><p data-type data-speed="18">Organización de datos, tablas y cálculos básicos.</p></div>
        <div class="card"><div class="icono">🔌</div><h3 data-type data-speed="30">Fibra óptica</h3><p data-type data-speed="18">Conocimientos básicos de instalación y revisión de conexiones.</p></div>
        <div class="card"><div class="icono">📐</div><h3 data-type data-speed="30">Diseño en AutoCAD</h3><p data-type data-speed="18">Elaboración de planos y dibujos técnicos en 2D.</p></div>
        <div class="card"><div class="icono">🧰</div><h3 data-type data-speed="30">Uso de herramientas</h3><p data-type data-speed="18">Trabajo con guantes y kit de herramientas aplicando seguridad.</p></div>
      </div>
    </div>

    <div class="section">
      <h2 id="fortalezas">Fortalezas personales</h2>
      <div class="tags">
        <span class="tag">Responsabilidad</span>
        <span class="tag">Puntualidad</span>
        <span class="tag">Aprendizaje rápido</span>
        <span class="tag">Trabajo en equipo</span>
        <span class="tag">Organización</span>
        <span class="tag">Adaptabilidad</span>
      </div>
    </div>

    <div class="section">
      <h2 id="practicas">Prácticas preprofesionales</h2>
      <div class="item">
        <div class="item-head"><span data-type data-speed="30">Prácticas técnicas</span><span class="fecha">08/2025</span></div>
        <div class="lugar con-logo"><img class="logo-mini" src="data:image/png;base64,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" alt="Logo IES Santa Lucía"><span>Tecnológico de Santa Lucía – Perú</span></div>
        <ul>
          <li data-type data-speed="18">Ofimática.</li>
          <li data-type data-speed="18">Mantenimiento.</li>
          <li data-type data-speed="18">Fibra óptica.</li>
          <li data-type data-speed="18">Diseño en AutoCAD.</li>
          <li data-type data-speed="18">Excel.</li>
          <li data-type data-speed="18">Uso de guantes y kit de herramientas.</li>
        </ul>
      </div>
    </div>

    <div class="section">
      <h2 id="experiencia">Experiencia laboral</h2>
      <div class="item">
        <div class="item-head"><span data-type data-speed="30">Registro laboral formal</span><span class="fecha">09/2021</span></div>
        <div class="lugar">RUC 20601845408</div>
        <p data-type data-speed="18">Periodo registrado en el Sistema de Planillas Electrónicas, del 01/09/2021 al 25/09/2021.</p>
      </div>
    </div>

    <div class="section">
      <h2 id="formacion">Formación académica</h2>
      <div class="item">
        <div class="item-head"><span data-type data-speed="30">Estudios en curso</span><span class="fecha">2024 – 2026</span></div>
        <div class="lugar con-logo"><img class="logo-mini" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHgAAACgCAYAAADHCaiQAAAKMWlDQ1BJQ0MgUHJvZmlsZQAAeJydlndUU9kWh8+9N71QkhCKlNBraFICSA29SJEuKjEJEErAkAAiNkRUcERRkaYIMijggKNDkbEiioUBUbHrBBlE1HFwFBuWSWStGd+8ee/Nm98f935rn73P3Wfvfda6AJD8gwXCTFgJgAyhWBTh58WIjYtnYAcBDPAAA2wA4HCzs0IW+EYCmQJ82IxsmRP4F726DiD5+yrTP4zBAP+flLlZIjEAUJiM5/L42VwZF8k4PVecJbdPyZi2NE3OMErOIlmCMlaTc/IsW3z2mWUPOfMyhDwZy3PO4mXw5Nwn4405Er6MkWAZF+cI+LkyviZjg3RJhkDGb+SxGXxONgAoktwu5nNTZGwtY5IoMoIt43kA4EjJX/DSL1jMzxPLD8XOzFouEiSniBkmXFOGjZMTi+HPz03ni8XMMA43jSPiMdiZGVkc4XIAZs/8WRR5bRmyIjvYODk4MG0tbb4o1H9d/JuS93aWXoR/7hlEH/jD9ld+mQ0AsKZltdn6h21pFQBd6wFQu/2HzWAvAIqyvnUOfXEeunxeUsTiLGcrq9zcXEsBn2spL+jv+p8Of0NffM9Svt3v5WF485M4knQxQ143bmZ6pkTEyM7icPkM5p+H+B8H/nUeFhH8JL6IL5RFRMumTCBMlrVbyBOIBZlChkD4n5r4D8P+pNm5lona+BHQllgCpSEaQH4eACgqESAJe2Qr0O99C8ZHA/nNi9GZmJ37z4L+fVe4TP7IFiR/jmNHRDK4ElHO7Jr8WgI0IABFQAPqQBvoAxPABLbAEbgAD+ADAkEoiARxYDHgghSQAUQgFxSAtaAYlIKtYCeoBnWgETSDNnAYdIFj4DQ4By6By2AE3AFSMA6egCnwCsxAEISFyBAVUod0IEPIHLKFWJAb5AMFQxFQHJQIJUNCSAIVQOugUqgcqobqoWboW+godBq6AA1Dt6BRaBL6FXoHIzAJpsFasBFsBbNgTzgIjoQXwcnwMjgfLoK3wJVwA3wQ7oRPw5fgEVgKP4GnEYAQETqiizARFsJGQpF4JAkRIauQEqQCaUDakB6kH7mKSJGnyFsUBkVFMVBMlAvKHxWF4qKWoVahNqOqUQdQnag+1FXUKGoK9RFNRmuizdHO6AB0LDoZnYsuRlegm9Ad6LPoEfQ4+hUGg6FjjDGOGH9MHCYVswKzGbMb0445hRnGjGGmsVisOtYc64oNxXKwYmwxtgp7EHsSewU7jn2DI+J0cLY4X1w8TogrxFXgWnAncFdwE7gZvBLeEO+MD8Xz8MvxZfhGfA9+CD+OnyEoE4wJroRIQiphLaGS0EY4S7hLeEEkEvWITsRwooC4hlhJPEQ8TxwlviVRSGYkNimBJCFtIe0nnSLdIr0gk8lGZA9yPFlM3kJuJp8h3ye/UaAqWCoEKPAUVivUKHQqXFF4pohXNFT0VFysmK9YoXhEcUjxqRJeyUiJrcRRWqVUo3RU6YbStDJV2UY5VDlDebNyi/IF5UcULMWI4kPhUYoo+yhnKGNUhKpPZVO51HXURupZ6jgNQzOmBdBSaaW0b2iDtCkVioqdSrRKnkqNynEVKR2hG9ED6On0Mvph+nX6O1UtVU9Vvuom1TbVK6qv1eaoeajx1UrU2tVG1N6pM9R91NPUt6l3qd/TQGmYaYRr5Grs0Tir8XQObY7LHO6ckjmH59zWhDXNNCM0V2ju0xzQnNbS1vLTytKq0jqj9VSbru2hnaq9Q/uE9qQOVcdNR6CzQ+ekzmOGCsOTkc6oZPQxpnQ1df11Jbr1uoO6M3rGelF6hXrtevf0Cfos/ST9Hfq9+lMGOgYhBgUGrQa3DfGGLMMUw12G/YavjYyNYow2GHUZPTJWMw4wzjduNb5rQjZxN1lm0mByzRRjyjJNM91tetkMNrM3SzGrMRsyh80dzAXmu82HLdAWThZCiwaLG0wS05OZw2xljlrSLYMtCy27LJ9ZGVjFW22z6rf6aG1vnW7daH3HhmITaFNo02Pzq62ZLde2xvbaXPJc37mr53bPfW5nbse322N3055qH2K/wb7X/oODo4PIoc1h0tHAMdGx1vEGi8YKY21mnXdCO3k5rXY65vTW2cFZ7HzY+RcXpkuaS4vLo3nG8/jzGueNueq5clzrXaVuDLdEt71uUnddd457g/sDD30PnkeTx4SnqWeq50HPZ17WXiKvDq/XbGf2SvYpb8Tbz7vEe9CH4hPlU+1z31fPN9m31XfKz95vhd8pf7R/kP82/xsBWgHcgOaAqUDHwJWBfUGkoAVB1UEPgs2CRcE9IXBIYMj2kLvzDecL53eFgtCA0O2h98KMw5aFfR+OCQ8Lrwl/GGETURDRv4C6YMmClgWvIr0iyyLvRJlESaJ6oxWjE6Kbo1/HeMeUx0hjrWJXxl6K04gTxHXHY+Oj45vipxf6LNy5cDzBPqE44foi40V5iy4s1licvvj4EsUlnCVHEtGJMYktie85oZwGzvTSgKW1S6e4bO4u7hOeB28Hb5Lvyi/nTyS5JpUnPUp2Td6ePJninlKR8lTAFlQLnqf6p9alvk4LTduf9ik9Jr09A5eRmHFUSBGmCfsytTPzMoezzLOKs6TLnJftXDYlChI1ZUPZi7K7xTTZz9SAxESyXjKa45ZTk/MmNzr3SJ5ynjBvYLnZ8k3LJ/J9879egVrBXdFboFuwtmB0pefK+lXQqqWrelfrry5aPb7Gb82BtYS1aWt/KLQuLC98uS5mXU+RVtGaorH1futbixWKRcU3NrhsqNuI2ijYOLhp7qaqTR9LeCUXS61LK0rfb+ZuvviVzVeVX33akrRlsMyhbM9WzFbh1uvb3LcdKFcuzy8f2x6yvXMHY0fJjpc7l+y8UGFXUbeLsEuyS1oZXNldZVC1tep9dUr1SI1XTXutZu2m2te7ebuv7PHY01anVVda926vYO/Ner/6zgajhop9mH05+x42Rjf2f836urlJo6m06cN+4X7pgYgDfc2Ozc0tmi1lrXCrpHXyYMLBy994f9Pdxmyrb6e3lx4ChySHHn+b+O31w0GHe4+wjrR9Z/hdbQe1o6QT6lzeOdWV0iXtjusePhp4tLfHpafje8vv9x/TPVZzXOV42QnCiaITn07mn5w+lXXq6enk02O9S3rvnIk9c60vvG/wbNDZ8+d8z53p9+w/ed71/LELzheOXmRd7LrkcKlzwH6g4wf7HzoGHQY7hxyHui87Xe4Znjd84or7ldNXva+euxZw7dLI/JHh61HXb95IuCG9ybv56Fb6ree3c27P3FlzF3235J7SvYr7mvcbfjT9sV3qID0+6j068GDBgztj3LEnP2X/9H686CH5YcWEzkTzI9tHxyZ9Jy8/Xvh4/EnWk5mnxT8r/1z7zOTZd794/DIwFTs1/lz0/NOvm1+ov9j/0u5l73TY9P1XGa9mXpe8UX9z4C3rbf+7mHcTM7nvse8rP5h+6PkY9PHup4xPn34D94Tz+6TMXDkAAInISURBVHja3P13mGXZWd+Lf9Zae++TT+XY1TlPT3dPTpoZSUgaiSQBYgSYbGMEXGzs64i5WD9dY2NfjH0Nug8GEwzYBiQhCcnKYTQzkkaTp3tmOqfqrpzr5LP3XmvdP9bap2qEQAGQ/LutZ55WV1fXOWe/a73h+37f7yv4X+DXB3/zg8X3vZwca2p7XzvhzlqS7G8YWWmjrDEKKS1WpMJq27WtzrSy4rlKID8fzdVe+Nznfmb9b/K9Pfzwu8pzVG5pSfnqBHmXLBV222KkbKEAYYhQISiN7KSIbixEN92MO/HFTqPzbJi0n25f2Tg3feofbnyznq34Zr3wI+94R/B/Xdtzd8OG39NR+TdsqPBQnM/l0kKBOBehRYgJBUJZhACExKSGUAuipINsNrWuta+EneQztt5698iHPvf4s/xW8tf1UB747t+9s1kMvy9WuW/VlerBYHgglOU8QS4iiCRCSGQowQiQhkAC2mKtxXQ1tFNMs550a51rcbvznG42PpMsLz9+8SOfvQDv0f+fNfCrv+1d443q4BtbuegnusXCPa1qXxAXCphcAKEllQKLRFqQEhDWv1GBFaAQCAyBAYlCxQY21q3caD0p653f6J59/r3zz76z9fU+jDf+6B+9btXIn2tVSg8xNp4Lq3lUKUCgkAKksBgsCggQaAXSWMLsSVpBGEgEEjBIGWBjQVxv0F1dacZrzefijdaH2surH7rwibef+/+EgR959TuCXxja+UAtV/7BZqX0rd3B/slOX5kklFgl3SWwFozFIpDCvTHp36GwIJAIYXsGD4xEKEAIAilQRkKtjVpff0rMr/6by//j4T/7Wt7jm3/wd25aVoV/2aj0v1VOTQaqvwCBBGEJsAiDMxgghEQIQcDW4ROC3vsWBoR0f0a6gxhIgRQWEkV3o01zaaneWdl8NFlZ/e/12WsfufTUO2v/f2fghx/+zb5rRN/dyFd/otlfvLc9MiyTQg4tJVpZpLFgwYqe3bBCoKRFWgCLEBYpQRiJ8A9U4R6w8B9ACvd3UgkCFGZl3bLc+KPwxvIvnP+zH7j2lULFv7qw/6eWS5V/KXZNjYjBEkEoUcK9KWElEnewpLVYIUBKAoQ7lEKgrPM0UuLet3UHz4UXS4BEIlAChD8ESkhMM6GxsE59fvVcurT8h/XpG3/48jO/eON/eQP/8Hf9+tDZqPrDG6XyT7b6Bo52hgdICgJQ7gHZ7Cm4WyGE8FYGIQUY7R+wuxlKONcnLCjczcjMLdyzREmJtRaLRakAaRRmbvlGMrfyT2781zf/yZd7nz/4k384caUd/qfW8PDDZtc4qhQgsQgLYXb9MO7GYv3tFd67+N8FKIt7N4G7zdsiC8p/BgQE/v0qXF6hcJ/RaEF3aZP1yzeWGgu13zcbq7/57CM/d/l/OQN/13f9+tBSYfBHV8PiT9eGhw50RsokYQASNBallfvk0m7Z159qJfyXvHvz3tf9vXEGxLrbK4Vz58jsNvgf4k0ikf5UKOxKQ9ulhV9NTz/xjulH39nJ3usbf/B3b1sJyr+X7NpzIhgvI5RCYBDSolD+EtqecZV3xUiDsrL3uu4tWoTyrjk7lFjnaXqf0aLk1sEQANaihEUKiZIC01VsLNZYuzKz2F5Y/h3WF3/96Uf/6cI33cA/8/C7yi9FAz+yqMKfqw0PHeqODJPkQwwGtMZFUInFOOOarSAr7Stjq7DONjIzugEhJdKAlNK5bePcIdmNEsK58ezHKIGw1r2iUoh2gr6x9AGuX/vJS+/5O8vf+WN/8IYbsvz78f69E+FQiUCkLisW7vZlrkH6pyP9jVUyCxuCwNnHxd3s4/g/SyFQUoAxIJ2RA+EOrXdU3rjOYwksWOkORChIYkt9ep31izemu8trvzL34md/Z3r69zvfcAM/85u/Gf7zx/q/d0HJf7o5OHRLc2SAOK/807GgvQsSPjnBggErBUo494f1l88nJcL429tzbwKMQEh3k4QwzojZ7RGid7udy3RZrkCiMNjMICYgnl18zJyZ/m/hcOH/Cg7v61f9eaRP4ALjLCAEGOuyYuEPDdYipCQ0/v1I429h9h5crA6kQVrpQ4ghO4VBlnz1nrr7PiVASeEiFsK9nvPrBEKi64bFS7MsX7vxufbKxi+e+vhPf/YbYmAJvPXH3v0t14z8heVy/7dsjveTFiOsVO7KZf5X4OvELIPKYphASuNOuHfF0n9dCRdrpXd10rhAJwwgtTMmsvfzAwHS+vRLeKMagVUWJQwYQYhAKIHQkC6sYCtFor4C0nsW95mML4WMv5ECMP4gagKrvOuVoAxWGHcwfPYfSHdCt7vgIPMA0iK1MxwCJBbpr7ISEptl49I/G1xosEoiU2ivt5l78XJcv770ro2FuX9z7ul/sfo3ZuAf/3sfuOlCs/3zy7L0/bXR8aA9XEBLAalACOvc8F/4Ys7NOWxAg5RIYZDWfzAhsqjl45fxjwsEBqskyvivCIuS7qZmcc7gyi1pLVYqFMI9XCGw1iJtym0TK3R0jjPLfUQydMmTdA8UJMpq0JaiTCjmFLUkwCfUGAE5K7AIrMLFz54L9zfeHROE3PJawoBU9D6bzC6KkBj/GbeMK7ynEq6isJZAKHQq2Li+yvyZi6fWZxf+0fOf+tlPfzX2Ul+tYX/+X797pDT11n9xUQe/MTs6evfG5IiMK3m0MFjrbq6QeuvMCH+Rty4bSrnTKq1zX9K7YSkEatvtVZJeSSSFQgJRaHAXUjqDSPeAsMbFXBeeiaRh90AdrS3aSKSQBFKAlhRlix+85SLDuSYvLo2hRFYCOdceCIk1ENDl3p2L5JVhpVkEpZBS+QtoQWkCq4lc2u+MIt3NC3yoUWQ5gbvdQma31z0N6d23kKLn1VTP5Uv33oT7nNYKghAqQ3n6JsbGpVJvG5z41jCfTD6xtvaU/kre9ivf2p95z92fu2ieODc4/gs39k0NNMb6iUOJthqsQhiXPFmjtrlmXzII2UuarHWnWkrpyh2fqAgUUgqEFUjp/rGQtvdArRBUo4R7p9YYimoY65EtfzMEEmvda4Hk5Pg6r9s1R4BGELjXkDBWqXN8+AYnRmYYCJtof6hCBKEFaTUBKfdM3uCBg7M0TYLFElmLwhBaC9YyVt5kz9AmUqb+82QHRCGs6HkdJQRKqB5oI00GiriSQQrZy/qzz92rlX2OgXXvEWvR1lAcCNh779F8/8TA95u+HfmvJpx+xV/zc2sr8+QGajuGiMs5tBXepQlnXGV82WKz0hapHNIkspgm/AfxHz/AlT4RitAKlPWZcAZceLRIYZEIml3JocEN/sHdlzgxOAu26w4VzpWFGCTavXYS89abpzk2NIe1HRfDheHmkXV2ldfY37fKnspmzxUKLBqBMYaD/XP8wC0XaXc1i80KYSDda1hLSJO7pi7z5qNXqaouhoBACiJhCZG92jbA+vfNNkjO31bps2yRgTWyh34pqRDCuJubZeP+52ZhCqOpLazQ6dT/5ZVn//nmX4uBP/aBt1/ul8lvFDdbHjYUvVrQ1anORfVyK5n5Z4uwpgfjKWGQEu8avVvGPfxeHSuci5K9Ahmk0nR0jkcuV9nTv8ovv+E53nr4HH2qhkkhMO5nKn/oVps5dldX+MHjlxiNWlgdUJFtbp9YpBh1GS7VOTGySMEmgEVLF0vGSxv80G2n2TuwwJn5EbpJySdcKTsKa3zvzS/zt+98kU4r4cpKH4FRKGuwPowoa7Eexwl8Fu+OhzvcrqSTvVpZ+kOgsgoCgSDwyFwGz+JzEYuyIUoHrF2+8dlHfvul9321CfFX9eto0P6t6tLSShB799hDKuhlyFlQd/WiQWH8iTU9oCDwda7wCUQG3ArpjO+811Z2jY/RkbJMNwf5w1M7Gck3+Bf3P88/uucUJ4YWCNIEqyVKOMe/3Cyy0bC8eu8VHjp8GWlajJSaHBldRZASBjFHJlcp5xOsUCgTMKQ2eNuRl7l36irLrTxXVoewNiCyHe4Yv8pP3/V53nb8FMv1HJ+7vI+uqDhIVQJoDKCNILRd+vIdAqW3UhCxLdb6Wrvnhr0xZWZIyVbiiEYI3XP5xUJCe21Gr84s/Vt4Z/rXmmSdfvYDm8dvecuOmszdExfyaGH9yxqyqyyVi3XWmJ4bypKoDCzwfRkHIljhgYCsHNmC96wHCXqNBxEgrGChUaIvbHPPxAzHRhY5NlzDGJir5elq158NVMKdE/PsG5lnvJIyvVxhZ3mdbz14nki0McISBSGnFsZYaQ1SEC3ecuQs3330NHnV4anZ/Tx+dR8jxQbfeeQ8Dx9/lkOj11hrlfnj5+9genMnoXChw1iJsIZc2ObAwCpHRjcIFdTaEbEIkVIQ+JgrkD2ARvqbLIV1fkz45NJkYc2FDyUkWEEUpAyWE66duviZ//kbf/Z/whn71dgt+FpKpMP94W8vryz83WZfoUhOObSoBynZXu3ojCt6sVcYb0ire8iPNQKpXFklfC0opft6NUwY62+w3pRsxCWMDR3GHCg6pswHzh3klsl17hy/xM0jV9lxX41j46t84Ox+zq6N0enkWWtXsDpgX2WBH7nlBZJEUAhjhFUoYxnOr3N0cI2LS+Pcf+ASb7n5JUr5DepxP+cX+rlpeJbvvPkyt45fJQo26eoij145yoXFna4sRKOsZahQ49DIMofH1wiU4MXr48ysV0mICAUo5et/lMPTjXUJlbAO3dMSoSxKBEDaQ8WEEAgbYI0GaRgfSli7MWPnrq7+2tfST1Zfi4Gf/sKfLP/ZR168bY3C0bia91jsVmGvPGQoffssywKzOlcIiXVfdO5UZKWD8EiW8D/HsH+wzkN7V7hpcBVh2nRTSZwohFRstgvEKdw2sUFRNcirNkfHVjkyUkMnlrnNPHsHG5wYn0OaLhPlFpODNaRIevlCEGganQhhNH/r1peZqs4hrGWzncMaeOPRa9w0dg1JA2ECXl46xHtePslGt59K1GZHeYn79l7m24+d5rapRVY3Kjxyfh9XV8dJZeTqb59puCTPIqVyOLqWPqpZh3JJel2zLCuTQoHQCAxDlZixsS7Pfv76M3/2n/74/4BLX7WBv6YbLISwP/VP3vd7i5sb390aqAhTUCite3HS9UzFthTfUo4sU6UO2A7NWNCII7omJNEOOUJJsmMilHNNsVE8OzdAuyt429FrfPexaa6u5vji9XFeXBlirl7lsekdHB9d5vturhGKLug2x0eusPOedY6P7iGJLXEaQtBBqdglcsZ1s6zV2FRwcuw6B4aW2VnehNSSCslAvsurD14jUAkmNSAUS61JPn7uIN1UcfvUeW4fv87RyVmGy23m14f4yEuHeGZ+H3HaRxBkYcVh78YKpBYOIUMjRZd8aMhHCVEg0DZPIw7RBjDbsmgJUkO+kLJ3qsP89DrTFzd+Bz7W/VpsFnytSNZPPLDrM1c+On12sd65qZ0r+I6Oj8fSuWbZwyVBpBZpNYdGWxys1qjmutRjy1KzxPW1HEutiHpcopnmiXVA4kH3VBZ4brnA/Eaetxy5xsPHrvCavTe4Xivy0swYX5wd4Zlrfdw+McxNY/OIVGBSTX9+le++qcFGOyKyXd+rVQgTAqnLGbw3GS63GKKBNcbFUiCQCRiD9V4nJeDKYoWxwiavuesqB0ZnGcw1acclvnBpH49cPsZsfRIjQwIFRgiksQQkhGGbvIophx36y3VGSl0quSYqEDTjEsvNQeY3QoQOXb281WYCNJGCnaNtKqUuj55emLvwQu393xAs+sf+wZ++84u2/1+u7B7BKgc1Zh2jrIuSJQ9Yi7CWnEyYrDQ4PrrK/VMb3DRZoyjqdLVhpVVkdrPI9VqV2VqRlVaZtXaOzSRHs51DCsvJkSX+1i1neGD3LMWgyXpS4PryMIWwxd6hZVeu+GaD9aEBqx34IRTG+m6Ekb59pzFYpFG4TMA6gFQYrLBgJBKDtgG1uEQpZ8gFdbCK6Y1dfOzszTw3s5eOLhHlEipBi2LYpb/YYjDXYKhcY7RSYzDfoJJrI1TAZlzlxsowF5dGWGyM0kiKODpA0MuqpfAXw6SMDTc5sKvFynLM+//g7G998Nf+7tu/VlsFX4+BD+/sf9/F8/V/tt6q5GwlD1gCnyU7QFgijAcRpKtrEwKuNvJcqw3w+HSHnZU17ppc4d6dKxwfW+JVO68jgK7JUesU2OgWWOqWmdkscn05x9J6iU+d20m9o3jjwVkGig0Gds2AzcDtMCu9e2VF7wt4hMykvoZzcbB3uqVwXUzfjFaAI1kJAmsZjNqApqsrnF3YzVPTu2mmZW7fc52BQoORUoPB0ibVQo3+sEEpSlDKkBrFWnOAa2vjXFic4vrqGGvdKpoQRIgUrs8spUSiMdKDR9bSX06YGm8jQ82lq5t65kb9T75h7UL7iA2+530ffOyp0tC96cQgkPpCX7mWm9nqpW7Ve757ZsAiMNoSGE1fvsFNg+vcO7XAycEF0sVzJN2u6/IYxeB4jn2HyhhC6p0ci6uSpStLSFP3trLuxgnBK1gE4IwvtP/y1t9LAUcOlZnY4TyM1b7lJwUIRadjmV/oMDsTMz9XZ3GlTZooOnGe9e4wI2Nljh6QHN4LE2NQKsfO/RuNNSEbzX5urE1yfnWSq+sTLLcG6CQFQLkET2iEo6k4NogIes0UDFRybfbt3KRSbdJJFB993/T53/uVZ29n8Veb35AbLF4r0h//uQ9+eKCd3LsqrMOQrUVJgRa21zkxxviM2sdlbX2P1WJDEDagrqs8sTjA6ZWdDDUusPKB99NdmEGqAB0nPPRt+/k3//ZWqsUG1TzIpuH//LUnOPNSgzCnAL3VcTcZwL3N1tvPspEYNIGy/OK/PM7bvn8fNu46jyNAG8kzz27wP//sMs89t87cfJdOOyVNBNoTx2QoCaWmUFTsmCxy++2DfOdb9nPgyBRz9QEuLExxcXWChfog3aTiGhUiJQpSlxXbLHx4xEpYn4A5TxSphB3jdcrVBgbNyrplbmbjk1+Pcb9uAwOMjeU+Vb22+Y71Zl8oS5EzoDS+IyLQ1qCk3MZhcjCec6HGxULl2JE2MCQyx3pcptmKSNsCIohbglZ7jFp7L1HuGpFKSE2bdsfQaGvyxoH0OhV009j3or8Ep7MZ9UKCBmM1obTEXe0LFZckpjrk/e+Z4df/nxe5eqPTe+DG+oaBFFgMOoU20GoLVleavPBSjU8/sswbH34Th+6+jQ4hE6U6U32bREIiFSQojM5Rj4ssNypstEsY60ohIbTvRQcEtsPYQI3+vgZGpyAVS3M1Opv641+vnb5uA//Ma46ePvUHX7ysuvER+gpgUg+xedaFlEgreuwMl7lahNEE0gIGawwhDtwQwpCTKaHxjXEkaWixqp/n5m6nPlPgnl3zCLuKCgQqlASBQicxI6PD3HbXHRRyBbSxPYjQZNn9tgttDQRByv79AnTq31fEU0+u8Z9+/RTT1xOifITAMjQ0ym2338rOPXvI5/PoJGVjfYPTL77I+ZdfwqRgheTKpTZ/+l8/yS8d0nzb68ZotQLqcZXlRom1RpVma5jVdoFGXKablBFS9frdyp9CIboMVjuMjNQQsovRAmMEiwutpTMvrTzzDTfwrvt2tR/+2fc9UWilR2Lrujo9Co1vHAjhu009SMtRYYZzmsn+FqPlOn1RlyjoUM6lpPOrvDvfYt4Kwh5zUbKzOkzLhoQyJTWO5oMRWGvQxjA1tYuf+7n/ndGRMdJUO7gU3UPMbRaPPZVHyhal4ocwvAzCoo3gs4/OcuNGQj6Xx6QdhkbG+Wf/4ud54IH7iPIFd1SEwKQpMzdu8Jv/+T/zwfd90B3mQLI4v8z7PrxIbfAh1joDbLTL1OM8Oi1gidzhVgZEzjNJYteL9jBlqRAzNLpJmGuTpgIhLXEMjVr80vLT71z8hhsYoKjN53P1xo+negCjtgjrWV/EGdclMJnPFFKTGEW9myNnU8KSodRnGMhbOmGMlbbXAXGUc8tIQTDW30Hl1phruJag1S6WWUAGAVG+QJTPo1LHRbbCuFjvm/KOvefgP220S7mMQaqANFZsrHmCNinW/08Ii7WQ6oQgiEAIclHEoUOH+Fs/9EMkxpC02uRzJVCStP8Qj185hgirSIzjZkmDVA7VUohedy0DEqVVhKrN2PAmpVKLNHXjLwJDoyno1JOnvlxG8Q0x8GBePJNrdtJ6VweqrHpIlgSMNVtEOps19y2GiFpsWO9EXKaEEpqcSCkVEsrrhlqc3/YANMIIdFqlEY9TzZ13WbHAcaxwfOpOt8vi/DxJN0Zr4+kunn4NrglvLUYasAHFUkJhyGXeVmuEjDh8021EpVnibpcwiFhbW+Xf/et/w8mTJzl64hj79h1gdGyckeFhKpUyx44d5Zf+1b/CaIsxFiu6XFqd5fmlGVrdEt24SicN0UJgCbHGEWkRFqFiMM5JS9FlcLBFpdLGmNS/Z/czN2oJq/X02b+Kjf5KBh7N5a7nNrs3wlTvFTb0QMMW7dRagRXaN5wUATGRTKnkYgaKCUOFNmOFGjuqDXaOdGnOLfGrf9pg3kCkrHexFoMijnegdR/StnukcgMEYcD0tWv88i/9EqEKsVJg/c0T24tA65r21gje+r3fwg887LJ/rMGagAdf8waeea7LRz/yYZLEoCQsLczzsbk5PvXJT5ErFRkcGGBkbIzRkREOHTnM4UOH2LN3H2NjE5Rys9xdfZRju9ZodQvUOv3UW/2sdQqst/todKo04gKdpEhCROKTz/5qi5HhDaBLahxb01qLVYLVtUansaYvftMM/M9/+ds3PvJj77mmUvZqtq6qNIZimFASCdVch7Fykx3lNpOlBiOVOpPlJpPlLuVCTD6oURAJMjJctppIxT0+lvGkTGMlSTJMtzuMYdGb3XsFIWg0mzz/7LNYrbFZQ0MZR9vNiM7atddTbbjr7r0IMeXprhDHAUNDk/z9n/sHjI2O8alPfJL5+VkS47JvbTTtRo3ZjQ1uTF/FIvjExz5OoVhgcsdu7rz7Lt761gFuPzFPPmpBcQNYBCvRRhHbHO20QLtdptUusB5XWev00YpLFPo1UnXp6IAuksTIXsOh2eqsz822bnzTDCyEsN/yY398TujktUIUXZwzlqGCZnd/h8l8nfG+Nv35JqWwQzHsEkloJjkurBdg1WIYAQO5AGauNummzyBEw4HtviullEXbMqu1vdQa02iPf1sM1lqiKM/o4JDLqjWOqIUGozydyOUCFklqDNW+CuAaEBqBTnOkRjE1Ncn/9vd+hofe+Aaefe45zpw5w6WLl1lfW6VZ3yTuxqRa96YZmo0GF18+w6UzL/PcMwP82E+9mmO330GK425hLSJQCGLfwncsznyUMBktkyvOo6WgnQY00zx1XaTZjYiNRJgc1oi5mU98sPZNM7ArffV52h2sqHiaJzQSydWNItdNiJg3ZAExEMJn2xltfGsiD6UIVi5TS0JPSvMUXAMYjRGQmCGkqrhYr128T9OEfYd387M/9/cZ6h8gTbbhc9nwUoZD+7g8PNjBmMexxmKFRMky+bCKUopSOc8dd97KsVtuobFZY211leXlJebmFrh27RozczPM3pjh+tVparV1gkCSYnjp9Ab//j+d4w0//l3khw6gsQQqo9W6cs2xWzRCxIyO1hnUGyC6JFZgjKuGEyPQWKyVJIYZeDT9phpYYK4LnaKsRMrUgRxpRF27VptjaihfEjgwXVr/obN+sJQoHaJ0CWFCn5B5xpInHAsMga2SJAOO56z8EbGWSqXA0ZuPMjY8hk60nyDeMm52pLKJmbhz0Z8QR/G5NrPOtctfoKsFrW6NpJ1yzwMPsGvHFKVKgT1794AVpGlKJ+6wsbbJSy++xP/477/LC8+fwsqAICfZnJlGrT7GoaMlrm/00UnKxETuIvhpSomhv1+TK2vaRmEpYo2Lu4nP4A2CNEnodvXSX9U+f2UD55RcDnSirUA5Cp1FSO0nEwLPP/IYorU9Wopj9Xt2lzVIEROoGIT7gEpaP+lnEWisEKQ6T7M9hrZ5hGhghMvUhZXY2BB3E5IkQQnQviO7BXUYDA58SbVzzwKLUjlOnZrh3//ye+h2U2KbknRTfupnf5qffPvbscI4t+z5VPl8xM6dO9izZxcLCzc4depFT7yTiFSj0lmO77zGruGI+doAS7VhNtuDpCgwkkK5yeDQBoHsYhBoqz3YpsnGBoy0dIyh3dHr33QDdxO9YdKkE0KpB/V7iqzwnGFhHSghZUaDlY5vaBICIejPNTg6Vmd0aJr/FrZpWschdjCAi7N4rLjVGSRNiw4X9rNMDviwWO3GD/S2JI0ed8K4n2YBY0iRhBiECDl06A4KxZdZXL5GPp/HWs0H3vd+RkZHef3rXke5XHGOVoIIJGmacvbsGZ78wpPY1OIawRoRVZhL7uFTZ0+QCxKCQIO1roWZ4hidQ5uE+SZau89l/CjtVvXtMuk4FSRG177pBo7rzYao9McCSgg3FqqEc8luGFD0yO7ZbKyREGIZLSTsHFxnz+AGoxXNwmWXCIltLEQrpD8QzqUnSY7UuNagMSCVYvb6dX7j/3kXYa6ANsZ/v/ETjbaHYBk0EtDxJrfcusTDDw8R2oD9B27jLW9t8Nu/9RskSZcoilhcmOfX/uN/5LOfeYTDhw8zMNhPIAVJJ2Fufp5nn3mKy5cuoQKBsZo4TTl44hZGD95DLRnBdLQjw6MwQhCGMQPD65QKNVLteJiWFINyLrrHzQRhNMYIpKLzzTdwy7akUokQEiGziXe7De+3PZqoFAJrHGSYl5pCTtNJ8zx9fZxWkqczF9Fs5RDGYDRoErRxoElGmLdWYQxYk7qRGSlZXFzkT9/zHu/qRK9+znQ9MmzNNYQkSZxQXx/ju948RBhEqKDM2972MO3GJn/6vvdR29xECNhYW+ezj3yazz32KGEQILAYDXHcdUT4METHKVIqTt52O3e9+ftQfSNo7YwbuoFRZJDQV65RKddIZIzRDid3eYZBo7EuEGOs8eMqBoRNv+kGtqKdGoGRPRqt8OC5d8+Gnjt1oiQOaE+BmUYRUSsAOQKlQK6hopAgDBBB6IjxynFxTZZ/C0sQBARh3sGHHoUMhIcarR9J7LUOey2sjKBM0EmJbT+xLVEQJbRWDA738xM//XYO33SUT33sk5w9f5aN9Q26cReTauI4cZCrlagoRxgpSsUSO6d2cuddt/H6N+4lHGrz7OwMS/UJrAqwQiBESim/Sd/AOjZoe+O6t2QRpNZgsqBiQVs3YmuMIRWJ/KYbOAgLNmPrY0Fa7xqFRRrPcRZb87rCumk/hBvACjBoayDV7B2WvPlnfxSVpFghMKlh586dRJEiThJSralUSvydv/O36bSaCKm2Uijh4MieassrmvxbXzNCIrWlnSvw0lKdO3MgVIA2lnK5wnd8x3fwqvvu59q161y/fpWF+QU2GzXiJHbosVQUS2WGBgbZsXMHu3bsodAvGRx4jKHqC4wOXOXZa7dycfUgXV2kkO8wNLBGGMZo7T2PdKiaxmCtcYmVAazGWN/CVBYhRfRNNzDFXIBUMhuRdFODxuG/fvDM1zqOxW+3Ri0tFi0EgWxz69gc33nsMoeGbsKYWzEGAinQBrrdJsYYDJYwKvDggw9SrVbptSVsNgaxreP/F33Ni7U8Ndvh85evUYpiDowWEYDWBiOgb3CAEwNDnLztJEZrEpM695nh2kJgjUVrQacTc2lxg7Ore9g7Jtg5MMO3HH2CqaV5Xpo/hM0FBPk2CSlYiZHCYdfWYIRPtIzFYDA244YZZCAJ87L0TTdwJxZ5pFJKiVdk0K4kcnO30mTgtNka4bBuRnikVOP+Pde4dWqJWkfwvtMdDg3X2N9XoOvLk63s3HmDWq2OUgFCBk4BJfU9ZOvdtPIESrWN3aGAdIuf1e10We/2c2U9x4HhkivF/IB6nCRY4x629MC39im5MSmpdhl7HCes1mOurEespse4tL6X4eI6OwcX2D0wywOHnmUxrnK92Y8mdLN5RoKIsRaMcDHX4TY+oxYWbTVC5skXov5vuoF1XpWDSOSUBGskyvhYGWS6FW7myKBRFue6hUFJy2Rfg1vG1sGEvPeFQ0xvDBLHRZbrXYYORRQDvU0sQPTQoFanS67VIJ8vuzLFAum2zkLqjZpuK5OSbQCXgE7smhmFSIFPdpSypNob0KS9M2JS304GrLYYnZBqSzdOuL4J6zZERCFd28dsfZD5+g6uNcbZN3GVan6THSVYaPbRdPOPYAVaWqw2vkxyHsF1kdxJktKCYuib76JN0C+DKK88oU6KrCQy23Qp/KyvZywqqwmxWBvx/I0RNjs5Yptzc8QKzq0l7F/tcMtwgHCNX7TRSOsubCdNabZaqCBy1FxSrM3GLA0O5sqQKucGrSejY50XaMeujCtFEiES1/f1yVRiLNaPourMLSUObdLWYNOYJLUsNjQL7TxWhj1pJSkhynWhnDLbrrDQKZEXKVpojJ+P1xiMNhhP9dXGtTKtN67FYmyM0fFeeIeEd5pvHtCRipFcvhQ4JqWfFLQumeppbxgnYqKkAxGtAGMj1uqhHzeFAIdVC6CbKp6bjZnKwVDBeDeWoTzuBjabLaKoQBQGrqTANxh67DvTI5Bv3V3tBjGFINWCnAjoz+cQQKpT4jgljjVp5gKyARFpnQ4lwgEUJqXTTpltBrREgBAKpFf/iepUhtbIRQ1SA9oGdExAQowJDEJrUuMHuj1MrtEYa1wGjfWxOcGY9PDkjwU75v4rN755NzgSu1Qh9CWRhyrd+LrTvzAGGagtPSnhrqmwTrtCKAdBOMKFq6MDIZmrpzy/3OW+HRGhTbx5nDuWSNpdQ6vZQpYLvNI3bw+8dhvmLDxLy6CFQhMQBJJ86FR1unFCt5uQmhRjLK+UGvFeRLsJiCQ2LLUE63EOIcKeEh6qS6l/nbC4ibUaiUBjXHfJ/xhjRE+wzRqXSZvMy0iXcGntZCKiUjTQN5S/eY5vooFzpfyRKAi8cJnASnpaExJvQOGI5dmsa2B6ARqZjYl6yYaMnKdVyNmVLlNFy94+gzYaYxTaCC8naGh1WkS5HEp6uSR/c61/tBbV+5qDXLQ/BpbUSAphjpxyDNBunBAnXec2dSY36qk9SIzWruNjEpqdmIVWiQ45P8/rvi9faVAorIPpuATKv2YKIDQ6zVIKi/ZG1j4UOAkM7dy1tVgrKA3mRbEo7wY++k0x8O23/2QoouiOMIqcsIqvgaUfIcWrxAlAWENANhOLhw/xQ9t+2Mp6tMrzqOtJyItrmsGcJS8t6NQNqPmbHHdiOlFMPq/QxGT8d+0/WIpGWuc1tIVACDSQGEe0KygHkLS7Md1um8RoR+GxkhSnyuOiuvuh1qTEqWa9K6nrguv1WgFWEpZqFKtryKDr3K5xGFXq56fTdIus7ZifljQDqgSkvgZ2zkOCcUQAGah7X6nm+Q00sBm784BQ4oSMdE9gExwfGk8/QTgXHHgsWvSM6w6DE/G0vQ6T6xC6ZoQM4EYj4eKG4WhFI12n1JOtFGnapdlqImXBIV1O0gqrnGSI8eIrTnwNR163loSAJNX0lQTSGjrNDt2OwVjtiHo+6TL+zmftPJNqGh3BUlKmoyKEVU5kLWpS7FskCDfYqmRdTHXvw/ZYKLZX82bf5w1vQNutf4e1qMAQRPr4+P3/Znjhcyx/ww08PFp5ba1SLsjA+psa+Pkkl04L32gItj1l4afvhJAEHuwgM25Pu8L9NOXd28WaYDS0DORSjJZgXEvSYmjHDcJUogh8MsRW9rs99+rNqVu6RmKsoBQGxElCq9MlSWK2zKC9hKL7KMY4IyVJykqap2ZKiMCp41nZpVhdIVdoOJdrXEdIu7wMrY1H0QzWSh9xPaghLFq496yt6yg5GNMdgkgYCiU13rc/OrbwOT77DTWwAAqF3ENxpYoSEdjUCYNlqrEZW8OPqgjr+FFuSFxsyWmJTBXAa0kZVwMqq/3fB6zFggt1w3HZJRKpi5GeNpt2YzqtlHzk55CEgtjL0hovBYGE1IByHKzEt+ryoSWN28SdDjpN3dkQFmWtq32V8SWawKaWRgwbpgKy4BoqMiZfXiIsrbn46bqWaED7rNh4IRo3ourKIeNBFGMNxrHnSbEO7PCInbEJSEl5tCDyZfEq+AYb+Lf+yxNj73167h5KFh1skk/LjoaKJlTulhppUb7ZkM3/fLkZMZmNuBh3CNxwg8+4vZufaQaMhDkmoqbr/Xoo1BpBu9nZpjSntxLfP4fKuNfvisTFeZvQabVIum0MhjR1KrXapmAC0BpDgrGKNIYNW6ItSxhhCYUhKK6Rr66B6Lpoa/HNA9OLwUa4mSwALbUzrhRYo0mtx8eznpLxKwEwpDYiMSFhOUEU7f1fVvjmq6FUfb0GvrrYuCcNS2NxbpUz4hPcCF9AyzahFEhjvHIbXoQkIBCCUDj5+0B6zWTre8ZeQkh6FkfgBcqkojdn3DYFrrQiGolC6xhjEv/2NUnSohvHJFqTpl/uv3Tbf5o0FoQSZBrTanXodjVxNyFNY9K4S5qkpGmXNE2JE0sSd2hoRUNUsNIpAomwQVRaRwRtNKm/sdonT3arQ+SgK1cqGRdjrUm9MV1hl1hLaoxvQEjqaYUX6jfxdO0IFENE1L319T/0+6Pf0BvcSHhjWi6jS8vMy1Ms2pdZk9c4ZO9kUI+7qbmMXOc1Hd34rWNdZHrbNsukhXZfl25aRwqvrealaLWyrCVFZtsxu8M2YEjQnumRECdt8iLPXyReocFP+0NsHNacph3acZs0TeHPaWy6mjQxliSOubjcQO3aQSQViC65yiphYdP1co3J0j9S6zpETvta+PfpUy8/Pm1tVllnCVWKMJCIHDPJCC/Wd3O5PUV/WGeieo1wIBqprTRPAp/8htxga22xY8yrTUHSDRtokdKWG1zm8zwp/pTL6jli1fDiX3ZLyDlTspPZNHum2aidDK+Unu0vnBRC9iYlhMqSCsVskmclDYi1RqQGYR201W136SYpWmtS/5/WmsT/rrPbrZ0rVMJgOg3ibotUJ6/4PvefIU006IS5mRluzC4giZAiJV9eIiiuOuNqR7JxLT/f7rOun6vRGJH1e/0N19rV9Bh3002KFrBmBnimfphPrd/Ghc5eYlGkZQqktkxxRElbSB/8ulivX88/+tBHXzq20dGHZFXSEstom3pBFcGavM4LwYd4Wn6EJXUJpEF6JMnFWqcFIKWLodKK3j4Dp5+l3XiHD6oO105900LQFgWWkiKdOMAY7QsZQZJ06Xa6PQPH/vfE/250SmJTjNakQmJMSqfVpJt2egbOvj/WmiSNSUxMp9XhxRdfRqkyhVyEijZRxWWMSNEGnxxp56IxjjznkyqLj7neyK4uFiRWkJoUa2NiEXC5M8Uj67fwROMm1tJhtHAzXLGNaOgC+UpKKuMH3/3wu9U3xEUv1tqvr8soiPoULVZwkUP2lL27os1VnmedGQ7YO9ivjlMRQyjjNqw43pFfYmAtsiehr3siJNJj2aIXzTVKOIRpNamS6ywzWkhREqxNHS8qaaGUkx9M6ZWXvY5wikELsEogU00at0j9JIWVwRbNxzc3rBRcmr7KjYVFbr19ElVoEZTnIGg6aNFKl1xlCZWlx+M0nmliPGqGNe5QCOVxaMlG2s+LzT2cbe9mU/c5BoivjEGibUBd5+nvC0hzzRN/MNDeAVz/G73B1lpx9Xrt9R0ZEhRiWqaWpa8e2HCjI1LABku8ID7JE+n7meUsser2VNkzd5ypqyppt6mveq8uthSUpXIcZoUkFiHXF1ZptlokqZ+BQhDHrp5NkhSTaFKdkqTObcex+1piNMs3rrBw6XniTgOTWnTqOklaa+I0IYk1aWxobtQ49/JpygOj9I/1EZTmINrwXSWHI7tbbHyJ5NxzYg2pv92pu7NYq93UhU1pobjQ3sMn1u/kqcZRNnQ/2fIKKzJY1R8CXcVGIEbp7/and/2N3+Br1zZ2L22mt5HroyuXaNPwvCeJFbqXyjvOskTT5ro9x4ZZYb84wRF5FwNyFJG6uBzIcGsMwZoeg9Kp9biySXgldzf+KQiVoiPztLtNojCH0T7BSQ3tdocwDLdxs6QDEzymLIXi0vNPsr6xzq7Xv45Y5RAihlSipUM3TOJIb1cuXaKx2WDvXScoj3UQuTVS7dApLVyt6ytaV5cL37jH03EyxM+4zBoMC/Ewpxr7ONeeoG6rLsEw1o8vZ7KQsgcW1dISic2TG2mxdmP9tcB7/0Zv8HMvzb6qbsP+4mCRtl0jFS03GG39pD444S+bzdgrCAQ1tcxp/TiPJu/joniWOGgjsHRWZojXbmDjOqE0BEFEEIZIGThJ4h6e7RXRA0moAqSKOPfSWebnprE2dQ1zbeh0u75cSv2tTNFp6uJwmkA3Juk2ETbB6JQ4NaQ6ReuUNNGkSYKxKRubG5x+6RSjE+OM7x8h7KuRmrjn9lN8/Ldeuc6KXpy1QqCUE/TWHgBpmjKnWgf46OptPFc/TEMPOlDIQEml9JOS9dykddAvRhDbAh3yhH2WTsE8+J/+3kdyf6M3eHap/saVrmCwGjKt1jyYaHtu2nX0HQAv9BapEQQ60MybS6wli6yEs+y+0c+1D36QtFVjYGwP/TsP0T+5l8rYFIXKEGG+gAoUVidAgBSKzsYCV04/yuWnP87a9MucOH6Sb/22NxOGEVZAmqTEcezgUW23Vz1eh8VNCwoRkCYaFSSOiNfDMg1WCC5eucCFC+epNWqUj41R1VVUGBBb7ZI7s0UhEn7li0SQdlLa9Ra11WVELk9xYpx508+pzX2c60zQMpFX93Ni/ljNibLmtRMhv3O1y2I3wBK6FocwtG2eminSX7bokj7wvvWZo8ALfyMGtmu27x//5mdepUtFVD6hodexgXA7h6wFrQnWNWKhiS6E2B0VV+6L7bCVpRvUuTL3GVY+fAN5bhmEpnHjLDee+wS54gDRwDCVkV0M7z5C/+RuBsd2ka8MsnjxWV585H0sXXoJkzQAw8tnzrB3335uuumkR5JSRNciguhLcB+HjBmd0G53kGHkeq9pgpaKIBvwR7K5UeP0s8/RajS4fu4iy7+zwKULZ7nj21/D0N4JrDQEWpJqi+52qa/V2JhbZmN+heWrs6xeXaS5vEZ+cpzhH347Z/pvYybpxzrCM0JuTVpgLDsiyZsnIh6d6bLYNFi/YAsBKYpm0k9fDsSgzrfW2g/8jRn4kReu3rLYFXvKo/2kYYuGqSGsIVrtoq41MdfbRAshUaNM9+6Q9o7tuOQWPFlYjVEfn8aeWyeQIcbvX7BWEDfW6NaX2bxxkZnTnyHIlSgPTlLqH2Tj+gVaG0tIpQhkgJKCbrPB0099kbGxCfr6B5ECtI49RUt+6bgrOkkxJqVUqGJI0UYgjadxWYGxKefPv8zcjWsESkIgaKw0eOHPvsD8uWnufevrqU4Oszo7x/L0IuvXl9hcWKe+sEq33XGYtIbAShqrV5h5/6PUv/sBqISuv5x11azEGEvBdrlzKM/hUsA/PlpidLrNR5e6dMgYszlqSZXJUJIf6lK/VnuDhXeJr1LW4Wsy8LlrS2/Y1EpW8pqV2XOYmcvkbiyRW5BE3TGi8Bbyxd1EO4osF5+nI5b8yP8W41EiiK41GZpOMFaQihg/ooaUwqm9WSeTj9XYbo3W7Bq1GyBVjihQfpOa68BEoWJ+dpbTp5/nnnsexFqBNhqsmzh4pYEhTmOECAhlgE5cz9cI1VN6XV9f5cVTp0nThCBw/14GTlJp+ewMn3zXewhKEe2NBmkrwVrTE/Z2zNIQFbj2rdKG9NlHiIaPYl/3o7SjnN/VKLDaMBmm/PT+iB/eU6BfCr5rIsfRqmLtmTaPbrp9jRZLIsp0TIQotYgr9s7v+Ud/MMKv/sjSX6uBrbXqF//jo69bmD6DeekS60s3qIo8k5UHKYzuRfWNoqISUklI6zSikDWbbTmzPfesMaiRfm69fx/yxiaXZq+ytraKjmPCIJtItGQLatySR0WgXrkLT/gRFaSENOXlF06xY2I3k7t2olMwpIThn2+Bae3kkaJciNEJVgU+03VZ8dkzL7OysogK5JYuKLg9TFLRqjcRGw038iqDHjWpN8co3LIQbQxSWqo2Jn/piyzf9a20x3aD1thUU7IdfupAxD8+VCG/jRC6txRw64Dk8fUEIyOklHQp0KZAmFvHVhi/srxyJ/Dhv1YDf/yz1w6eX64dX1m+wI7IcuTet5LrGydXqiJzOULlN3ZKQ625yVInQGgBkR8Az4BYoN4P3V0RD+6+lz1rR7k2fYkrly+yvrxKkiYo5SocrQTKWFctCRzNVHmQWliENFjtBtRqrRYXL19geHQYlHAwo3UszWz+O5tsGRjoo5smruujjY/PkpXVZc5fOIc2CaFQvdc1NlOBsi47lgKTxVLjhumksX6Oyq0PGhgYZMfOKXZM7eLc2EnmiwMOizeakxXND+/O8SO7C68wLj5HHcxZFNq1FhF0bIl2WiIMNMGoorHQesNfu4HPX129v2ai0s7DB7htdID9h+5jrd2lYyxxKLHKMfbjlmGp0aVmGtiALeNuu0VJHqaLDVQYsae8m6HhAfbsPsD8/HWuXr3GysICnXa7p8Ig/SShUCIrbf3XnHGjfI7JHTsZHBym3emQy+dIccBGaFUvicZagiiiUKwSr685V062I8HQ6bTp6+uj2aiRdGLH6PIzVtaAkf71heuSWQNaWEzi1gXly2WGh0eZmtrL1M4JxoZH2VAFPlm9hU6hCjolMJqHpkJ+aE+BAtDRlrwSrzBwf6RQ0pL4rXGpzdPUfZQCi6jGtPPmtQ8//O7oPe95W/zXYmAp4Or85pviXJWx/j3MzV5iPp1mGYEp5jHVAmk+QBIitCQmIRVfYlhHp/CsSriea7FIkzuHpgjrOfK5EgPDVXbu2MONGzM898zTtJobXgV26yHb3o5eVx1HuTz79+1n/9EjTExMUC3302w2SHXseVDC7zMUCKspRyVEWbKxsY6ODSZ0uFE+KjA6OsFNN58gjEKuXb1G2ul46NLla2Lb4bLWvxcRMjDcx/jEODt37WJ0dJRytZ9yqUQuV+S5Zp7FvimvLmDRMuBPr6dcWm+QE4ZXDwf8+N4S0bZ8sKTcbotsHaslIrYDdE2EjJqYfg6/PHntpq8mm/6qDPzSF2eG/o93v3BPYWqUnOhw6sYiijVykxOIkUHEUBVVjYhEiF2YpXbqFElrmsJ4iXZfgJVuu4qbzHBzuhtFwxONG+w044z29VEpFtlo5ykW+mm2W+BRMdsbG/W7HmxGiLVIGTC1ezfHTpxk94H9jE9MMDY0yPL8Ii++/BJpotFWeK0MSWosndjQbHaxVoN2zYFCucK+A/sBS7lSJsrn6HZjrk9PY42jv0q7NctmvQCbThOGR4a48977GB4ZplysUizlKRbL9FXKrGnBBUZoR33uHfsu2eWW5HLTpe5WaH5wj3Vb1PyvPmUJMV7SUWNFQIc+jIkQqo4YNrm1G43X/rUZ+I++cO6uGmrH6ECFQrcNMkXlIKyWYahC33iJATbYOH+KuU99hLWnH6Us2gzGUzT3ltmYUDQHBGk+dJOEWmLyli/YeebWH+EWMcrt5X1MlgbpK1e4eLZLu9FyYzxZjma3QBMtABKG+oY4dvNJjp+8lT37dlHKl6knsKlSkvwAtrUIWpNEfiEGlqY21NptNIZEJwghiAaLDE3101/oo39gkGKxTLvVZm1tjcbmxiuAki38UXjFPU1/n9PPKkcFSsUiJsqxaBSf7xa4WNwBQeBoSX6qwgFC7sNtJgkdYylvc9PjZUV/vsN62yCVxFhIdJmujAiwhH2aVn/ykMX+3+IrsC2/KgNfX26+Xpf6qZQDCHLko8C1w4o5cgVJfvkSq4+/l8UnHkOvrjGRU5RKOxDzmv7FdfpDw3yfpjYaoPdXiEcLGALinOVCVOdyt8bjzRvcrMe4qzRFvb3pFev8rc2SrMxFG4MxMDQ5wfGTJ7jlpmN0jOHMbIeVbh5b3EHfTlirP07SrrutpcaR+XRXE+uOA/PTlLBcJJnKcbp9jbFuHwdG93K8coJYx1y9dJFL6+uuylNuJ0UvREhn5FQnlIsFRgbHqaeaU3GOU90y5xhgvjhGq1Ddmo/yFKMtHw+d1BCbV9roUDHk7qrgaiPFyBBhNdoW6JgyRaERAdBn79z59n89yW8y+1cy8Evvfnf0Lz4vXlfeWyEnoRVFmJJApk2CZo3W5z7H6jMfIb16hkgKCoUC/dUqifbs5FYXvbFGbn0NXdsgfdUu1MPHMIM+5RRgijBfiFmIr/Nce46+9gzI1N10JIFwM0HCr5l1Cnc5bj5+jLtvv4OVVsKZ+Q5xNI7qyyGFIjeSpzExT+vy84huilASIwQmSdBJQqDd+GZhqkowUSCWKZdrS6zOb3L3zuPcefvtnDn9AlfOX8Joj3VLeklWtpnc2oDrJs+ZZoUztsSV/AStUj+pymOzJdEZ8T6janqWixWSVipof8kdHAkFf3d/nvP1Fi80BFaGdEWBti0T4ueYBuVQZ6x9P/AnfyUD/9bLuSPrVhze1e/0qXSg2SyuYy8/Rufa50nmX2Bz7jq5MKA4PEy+WCS2urdwcXxqkpVCnumZG+iJAvLuXehK1BNWyVbjWSQ2B+t5Qzyi6JOQ0y591mora0WC1JJQKE4cu4nLeonfv/Ak+8buZW9YRHg2owojBqdupr04S3d9hlgLkAGImLgbo5SBUo7c7kGMFJAYgmrEepjw5NxpXr37Xk7ecguPfOxTdFpdp9mTZdC48VEhBJtRP/+zfBNrfSdph0WQoZuqMCBs4icXFT1usDC9DaMW2NCK2pcRanjNSJ5fv1Xwh1e7PFeLaQPSVmmmAV2bQF9Amu889Fc28LXV+DXRyES+VMqBlHRkk8ZYg9onH6GybpicGEJUylT6+imVij12pMVy9OhRDh85yOcefRy9dxD53ftIjg/7OCy2OMvgbqyUSBWg+vKQjzBN3Vs5a7MtLn6uNkVzdvo8z4cv8immmWjM86riPdxSuI2qHEBbTVQdZmDXTcxuzIN2uhpB0oHUrX6v7BxEVUK0ztiPhjSf54lWmeUrqwQrqyRxE6ToCQZkCZ+VltRoWhN7aOw4TqdY8Wx7rx1CSp9coyA7LKfDpCLv14trp6IrBUJolhK4tJlwa1n9uTbfq4ZznByIWIwNiRCc2TzCL595ivXuGkKl2CqvOfy3/13l/O/+s/pfZD/1lZr7/+WDZ3+xsHPy0MhAjsBq5rjO5dI5tGmiF9YYkEWmxqbIlcoo5SbXG7VNVhYWKJZKXLl2nUdunKb55l2Ym4Ydq9BP67mBLef6wlSQX9fkzq2TP71CON9Gak+6k6/kYyNcR+j87BWujae0JvNsmhWuti6wmq5SCosMBP0EIiJfqNLeXKS1ueBafYkh6bSpTJYYuG0SURR+2l6ymlb44sY+vtA5wksvnOPy+3+Pdm3NbVr90u0WxmBEgDl6D/rI/aRBCSttb/RNIpkIr3K4+DQFtUlb59HGjZr2+NtYuknKnoLlNWO5L2uMSAoGQ8lwICgElk8tvMxse93NbyGrLTqf6DzyxPTXZeBLmwcm1lXxlyb27S6VI4WVcEG/zLQ6h9lTgYkqSaOLXq0jkgSLZGNtlRvT11laWubM2TOcN0sk33MQfWyIhBhrFUVbZSqcAmmwzRb56w2Kz6yQf2yW/JNL5K63CK3T+cBqtxUluzrSsTyMFcS1DmmtixgrYqoFEmWZTea53LmEpstQ0EdfcYgwKLA+e5W428RKJz42cvtuirv6saR0bYHzrXE+tXGAFxo70deuYj/yuySXThMqN2jjCPxbCV9vyXNzA7EyQ0CKzBewUQXrF2GX1RqTubP0BTNU5AoWQ2zLaBP58RuXmidoXjUSMBb95e15Czy+eIYzjQXXqsxJaRtiPv74Fz/zdRl45OaH3yBGxv721K4Bp2ITpJxPn2WRSxgZUBidZNfB+xiO9rI0PcPs1cssz8/RaLToGo08MEj4gyfpHHVuuU8McFPuBPequznc2MXaCy9iHjlD7gsL5M5sUFiNySdeI0u524D0OJOll2Rp6WeJbUCw1kDONxBBCP0FdEHSpMHlzmUWOgvkghwT1SlE17K6cJ047VDeUWLszl1QzDGfDvK5+gEe29zHcl0RvfgIxQ+9i9LFp4iUQUvpjGuyhSKih2RhJaq5Tjh9Bvnyk6jplwmbq8hciMpVKeTaDEY3ENQIqVGWi+TVBpqQWBexOF3O5balEhruH44I/pI9OKGUPL16hWdqV9HSYoQgbdrocPFb/2D5zKP6azbw2Inv+/sj+3ffOdyfBwQdmpxNn0fbhMPyBHcHr+V43wMc2PsqxvYdJ9GGpYVpWs0m6vAQ4Q8fRx8ZpGQGOBHewauL38aJzn5WPvF5zv3P91N76mXyMy3CliGSbv+vkaK3fgevOJshWdnXXCbtlXqsJVxPkNM11HKbEAmRIs1ZluwSF7tXaIqYycEd6PUVuvU1pu47gNizm5fqEzyytJOzcxJ9/kWKn/p9Cp/9fYoLlwndVnjH7bbZ67upBP9/ncyCTwyCToNgeZrwwjME558lWJqmqFr0ldaQOUuaGiwxkVgkH8wiZAdtymjypFYx0+xyrF9xoKT+EvqN5Gx9nkdXz9G1noudmqGkKN7b/swTy1+TgR++51cLG7sGfnnv4T0jxTBCCk0smqRpzIncvdwS3c0EU+RMHgxUhybZffMd9E2NMRteQ79pF+KmnRxWJ/mWwpu4I7qXcTmJ6HR45sO/z+LF5wkRKOXD0TZSgPXkNWvcrI7drtPhyXie0+L41VKiuoLcQovg4jLBdI3cQkxYS0naDW5sXGWpu0ReQbVUQA7389xlzVNPL7L+hSfIP/oeCl/8Y/KXnyUXt0E5AX7XnBAoKb0andPS2BI+F1sLgnGNCKVjotoywfUXSc8+T/vqdYRSqPEKsXRUH0WDPPPk5SJWWLQtsZbkqXU63DMMA3+uDbb160Z3g4/MvkjTkXURoQxtNz6ffvTZp76mLPriroGbh4aHDlRKyqX7wlIUFU7k76Ykq0gtXCZoBVKmpDYmyhUZuecOirtexVBpkCO5k9wcnqBfDbkjjyUqD7Dv5APUZi+T6AaIyCFCVrihaGtRKkCFilwuon9ggEI+z+zsLK1Wi6C32dRuQZd+uzhWoxoQXWhiLjax+dBtbikIZsOzbKiQqiqjP6qp1y2m06QvbhMYjZEWoTzihAMjMn0RN81psUqSz5dIkoQ07mCMWyMkrXB1NtbvSRKEWOTGCs0X1ykeGSOQE735X3dEuuTkZYbVHJE4RC05yWOrhv9w7jr/+5Hb2Fuc+LJ2mSz1UwlyrCYNR2rMW5KCfRPw61/TDR6964d/ZPLQ/odG+guOjiNdUzxHjtCEWNyyCafDYf3uekFsE6r5Me4pPcBhdZS8yPdgQgmoIEd1sEp3fZb1xQVSIBABUS5Pua/K8OgIO/bs5sCBIxw9djPHT97CwcNHUCqg3Ulod9qYRHug37MlM5F0sbV4WQFhbJGxIWpqwvUUsdqls9agu1kjjJsE2rUmUQIrA6/r7BWepa/TtZsxinIFJnfu5v77X8Pu3fupVKsEudCxQbTF6C0WpbRuk2mkFAN3HKD40DHSgnL6WBi0cIkV1iBsm1DMo9QcVq5xqXGKy7WrVMIqo8V+cuKVJurqlI/PnmI2Xd/qhcYM5E/c99/TR5+uf5U3+B0yXy28fmS0hEJipEEa3PImASg3Oe9OiJ9CQKKNYUAMMxKNIL3UQiYiKqWLl9IaysOTHL379aSNBosrCwwMDdBfKTMwOERftUqx2ke1VKFcLlOulCkWc+RUwODAGJeuXGDm2jSt5oZT3hEKaYyTjrBukt/NPAms023yk4hudFTJgBRHpQ0z+NMPxZlMpc1LmQpjCMKAwZER9uw+wJ49+7jp5uMkaUxt4yCrG2tsrC+xurzK4tIyjdoGjXqdbjdGWcHU4T2IB49QG4qcQ5WG1GoHV+Jez/oB8VDOI80iCQmfWF7n1Poirx47wuvHj3Oifxdj+SplmWM0X2VPdZCnWlccSmYttiSH9Uj3vi9Hqf2yBj76PTt3FqvV28u5EGFTpEiRXiooy3Iy2aBMTU6g3TiKT+eN3yuYzQg75qXAiBQlC4zuvZ0Dt8wyNHuBgYEhKuUyxUqFcqlEuVKlWi7RVylTqpQolsvkQ+eup/ZOcv7CJeauTTN3fZpGo9YTW9NeE9N4RFAY4csaLw0jfBfKJ06uab8FP0qPVllrCaKA4fFhJiYn2bPnABOTE0yNT7Bzzy5qtTqFQoFStcTAYJWR0QmmdtbZ3KyxtrHG6tIC+ShP5b79zO4uutFQbb3KgBs6o8erBi0FqdFYqzFWY4KAab3J7818jvfPPcO+4jAHqzs4UJ5grFCipttOIztDAyONyZtv+6oNHFSrrxoeHeqPhEEYTxTzmaTAbTWzfo2cFPSEVDKoR8ktWVLhH6ryKjvgVr0XBkYY3n8H7cY6U1MT9Pf3UyrlqBQHyBUKhFEAUpESsbCpmW+FhMVhbp7YwY7hca6OT/LRzQ026+sE2TRFBjJkDfpsEMy/bibUkjEWv7THbP2MsdHQX+3njrvv5sC+/YxOTNBIW6jBHKKgGI6G6KtUqdUa1BtVNmt1GtU6leoAA/199FWKNAcVSwdytEtuT5PFElvbg1u11SQ20xPQWGuJrfaJnGOZWKlYsW0WG9N8oX6NIFXkfayX/oC4HMFic/KBoX/3Tyqr/+xX6l/RwJW+6kNjQxWUceddZhg5XvfKy+T3SEs+Tkhpe6tsJH69jfDjKUb0REjxMzr9u46xsTqLDdpElUFsFLGmQ2w7wHRDYhEhVB6iPAyNknQaLMVrjE3uYq22Qa224UKFF/iwbB+ScFohYbHoiOqpJvBTBNo4Qrz1YcZup09bR0xIkoR9e/ey+8herjeXOCeW6Oo5yjOXGJBVBmSFQVGgUA4Yzg/R16nQ7muzsprjemeFhf05aqMR2ourpBkmK63Tz8rUvKyb7NfC6Yc5CpGXVjICK1WvTZoqS0N2EUZtre+zbuGlyNl9m/mN24BH/1IDD77pHdV8Of9AKR+B0H6802dk3kDWGD8dmG01k735WrHtJiGsl+3Hc4Fd410Kp7we5orsvvlB2uvXWbYRxfwQIlcEGxIEilwU9baACSmhUCSJq9xoLvD0iy/RqDcQMnSyC9u4WyaxyDDH1N6dTExOglDE3cSJpQpFo7bJ3OwMGytrnuBnscqLv1hACxqNJmfnrrB2MGKmuEEnD1rBuom50l5CmUVkV5OPLcNUqMQ5hsIC62GLmZ2C5p4yse+C4aF3p0eie+pdqbUYrd1gBJAaJ86ipR9ak9YXH+4ZB17mwSt5uEaVFFhtSXNChqXuG76igcdGj94yONS3JxeYbUPRomdcp/ks/R4G0ZMQdJLCW7CxIJP138qgLbKneuNct6ZQHaBQHeix4oQSoJ0Lcrsc6G1pkcISFsssLiW8fOoltE0IgwBrfCLoqbQiUBw4fJADBw+xc9duqtU+4jRx4i1KMDNzg8GBAV584RS19TVk6DejZSmGFXSSDs9efImbv2WCpE+RJH7QW4CJBImCtCBYt5br8TqyawljSzzUodXXTxxYjE0RxpJ6QVVjzStubuo5Ydo6wzoDg9HuRmcars4lpV56M1sZxFZf2ViQCYThG3jHO/5/vPOd6V9o4EJ/5Q1DY4NSSYO1queahZtq9sPbJtMDdguO1VYrwKm7b1Fce/pXdgsTcHRluaVlmeljZbWntL2OSnaupHAMChOkXHj2cdbnrpHzAISQBmEs2rr3tPvQPm65/TZKpTJ7D+xjcmKMJE0RKnDyCVZTyhcwVvL0k18g6bSRgeiR+xCSEE1jfonm2iZRqQ+jnWKdlk6cJTXWqegg0JEgCaFhDVbkSY0lEbonSJOpcKT+EKVekIVMK1pbEi/o77QGdAYb+PbZ1nSQNZotgXM3j+VAcouNzM3l0ZmDDTj7Fxj4HUGlGH1LXynnxcmMX4Mq2GYNV2v6F1FKuB5AxlferoUl3TJGZ2jVS8oy42XJtesYZQshpZcrzITSnHcAgwoDNpbneenpR+m2OkTFnBvYMl6ayFimdu3mvntfxdjEOMu2zsVomcWkjU0NeH2P1VyTgYEBbrn1NlrNGqeefc7xs+RW4iVRxAs1Vs7NMjLZRyosqXDRMTEp1grSTC0H4ye0lJNCtMbZxUAq3c3Nbm/qVxToLMGy1k9lQqItVjqj95xnmnHEBcKkno3mDZwal3/4RkxaEMVOxGv4iwx8+AcP7B8cKJ0sRd6NZu5Vyh6ao+QWkV32+iF+NwFZMpZxbTyCmhnct92ktVtJ27bFGcqfUKfZ4QVYvLqZIkRISX19lXwAozsmnL5Vp43QhkRYhkdHedUDD7B/337WdIN4TGFGNA1bIwmdqo2wGr1bwkzMPjXCq+57kGatzqVzZ7AenhQekQqQNG+s0Rdr0rzTwEqswRjhyx2XPGkviZTgwoq2TlAllU7KIenpd9je3+PFV4w1GGGJvfqdMdv3Wm+JqwphPQfct1mzditZMe9X1YSdhwT8hv1ySNbk3T/w1n2H93xPf1/Ou1SnfGOMW7UqM40NYb2OhkuepMQnXaY3A+SlKHt6HEK6G51JZAmZTbU4YyvPcfLjQPi279b+JBw0GgioBDF7d00xOjpMpVpFhnlyhTz3P/hqbr31dlohLBQbiJ1FCHztKUBLg5YWcoqOjsl3FVOjOxgY6Gd2fo5uklDuH2R8bJy9+/ax/9AB5MEh7K4yWjpZQqOdNLWWTj8zEX5eONO9wqnGW+ESKCuyMRtP3BeuHk69HpZGu1vdE2Fj29bjDHlwCgI99qHRfpbYX3NrejiDSEV/4b77/zD55DPNP3eD+wb6H+rvqzj2X7YWB4mUpjc7JKzfN497+MpXuNkMb6ZWJwzIwDHmMimGzLMIsa1/LrYSKakUSjj3poSL39lwuatPLeVSP2N79jOkJum0Oqxv1lhZW2N1bYmbD99EWIyYTxaxUwWkhK4RGFK/gGvr4KdDIdfjNUaiQQ4dPsrNJ2+l2agxPDpGf98QQ4MD1GWHp0dW6ASWbtb4kF6Vzrgpf6fa7m5yNhjuJCC8EJrwgiwWrPByLMbraQlDag2pyJ7rllgp29qT28s/sgXZUmxt98iepjagGEuizt3Ah15h4PL9/3okXwzvq+RVLxlyYddkIK+PrW7RcaZtlXlj6VP2zHjCr2nvxW16fLOMA4+QTuHO3Va3jkdY0VsSLa3YpkHoYVEVUOnbgdTr9JUSitUyY6MjLK0MQE5wLV2iOyaROUjN1p1wijbZFL6bNaoPSc6vznJrfh+7du6lWMgzMDBAsVwgyAWcblynU3Q/x3iyX+aaNYZUuo6XFk5sJfEoVaZx2fv7zDULem4enDaW7jEuM8Ug28t/MGzd68wNC+3RGLu1fCSTgTRgc0LIwLz+zxl4z949d/b3VSaiyCJT506xxpHDRLZcyrlYiXO5zqYya46+QnZ/+0ifMtkmDrYBIU68VLIt2/Kq7E6QRXkZAydlYK1wguJSkhvbS9rtZ7H+ErFdpRRG6K7iameJdKqMKOV6JYcl8bHPLbDKZH61BZ0XzPe3sHPnGBorYSLFUtCgrTaZS+os5JvEhcBDiJZEOh50glOQNx6h0taQ+jU52ivVJdgtEVNret4j9vKGWZKVrdNBZgiW2NI03+a20XYLbsuk9e0rhkbczkYhMKF97YG/9/dyl37917s9AxeLuTeOjg86vRt/MrJYmmW6wkrH18Z41+v6dWIbmJG5YuVXwCKsU58VGqRyiZo1qG1Etiy9ln6OSQmJ8IfGte0kUgk/VWBQOUmSM8QVS4OQWjchrUpSSqj+sLcyzvok1PiHns3BWK+DaYwhzUkuVhtci+uYnKQpBXEe4sC4h2WF+z6fpSciS5Tstho2EzizaJHNGnus2WfP2nq0yguEG/9eJG5XIV57E+EUhtxmVJ8hb7+tvfbzK9ULbLa8xGpMJA9tTtojwKkA4Ed/9Pfy0/n8ayv5vHORIlsf4xAU5dXYhcxSculTcN+QdQtG/WCz9Yspe8m9D8gg/B5fqWzvdazHroVxYuLCI4/SS+2IrDdr3EYwIaDDJmv2Am277sqrnELlFBKNTs0r6k5tvKKcyFRonYNNteMlJ9KgRwrEaeKNI5yAjPYqsz6CG6xXrMNrX1kXR212G52YRepjphMVt1sAh3D60Jk2Ksb25q7oEd+dcY3Rvl6ToJNtYMe26Qr7JWwtnQH/GlGIckLq1/QMfDmJjvX1l4+Ucls91ixTCrKn3eMwyy2IQoBQWzCllAK0J6h7Yws/quHcugc+kL6Wdt8rPcYobEZm896jd4K9Ai0BWrZZ01eoySVS5Xb8aQ//2Z4BXVJjtLsF2lcSqY+QDvvVrpb1a121dH3dxC+5MWYLeIh7C+j8zRSZYXVPE1rjyyKrsTpbh+mMn1jjW4Vu1NSdd7MlnujRXmmN27oi3U3sLTUUduvG2r9A+1e6aTiJIg1TuvnkWyz21wKAoBy+utJXDXOhQmgnxWuxXuDbp+oejXIna3uCZB2zw6MqThlnq0QT/g/KG9hn81vbQ3sux4mAiYzQJrYqbeG/yQrNhpihJmedIaxwIp4I75K3alLjRzt7iafJpHx1T5c5RTvjWUOqIcHrN/ublfSioJcKNg5eNdZ6TcotnZcUuwUqZfqUFpLsEPilW2zztL7YdZ5R0+t2WUuPAdNb0/dVCDwLYXy+ZDAhd973jt8YCQByxcKt1b6i7+d6hIptCVDvUntAowc1CodV+rkfqba2epsMs7bCSQP7AXAROPcvexLvaiupEJKst9FTEjbSG9xQV7MspxeJZeIehU7dRMQ22E9nmzytwUqDzhZA+tsV+5uVWrN1M4UllgKrU1/mOONmes+pEBif+Wrv+t33eKgxW0hts7DgXHhszdZN3m7UXgi1HmYVvXX10sdyJ1G0TabPfGX9buEPoRBgpR5fNVePS7CiE+v91WrFx06bLaLbSoD8MmcpQARZiWR7uKMSrhmhfO1s/XIsJUBJ4xEsh8aIXgIoPY7l4Mgg8Ib0g3fK/561IGNZY0lfpCsbTtQza7NZ3Vu7kyFIiTGuE6OlA+6NRduUxF+KNLXE3n1qY4mNwdqUBPdvE2mI/c9P/G5FbS2p9UszcDfTYEkE2+SEndE17t+nGFKje0JsPSNlJU9WFvo/S69w6665hC+5YF+JM+1hJqyApJiKuNCdCl79k786JPIHx0o5J1FvRNas39o7L0xW7EonYyDc+IgV2aINuxUvcRIGstdRckmLElljQPSGzmwW2qWTE+5l6daACF1YEIaUBkvpeVqsopWHA822PQgeZHAAgo/CemsnrzGGRHpgwkCMc5vaurhrpY+T/rZZvQUhGvwiSf9ztcSNutitHq7Rvn/rr2bqb3oGjGTG/FL/LHGu2we6LbRqe3lh/zIDC/5cYPbtTp2zJAU1GRTE2KgolYajwHoqjmc7sNW4z6YJhN1K15UU/v6ZHuiRDVWpDLLMGB6ZMLQ/LELYra0sQvgtZW61jvDLaBAWYQRaJazp62wwSyJ8UgXbtnx7qfxMbFtmVCXrEhsMWmi6xrtc4TJarT3QIP0t8z9T+66OBgc1+jLf+kVWaa/0sWjftdO9LhA9DcveiI6xr/Sw1m5zp8b/XdaaNa+ogb+6e/vlbG4w0tKVZjJoCjU+XipUcmHQuxEyi++h8OWMy9Kk9mCE3AokPeTKQ4uqN5O/hUlaL7kgs/ah7x1vRQGx7UBIPwussUFKness6GvEMvG9VA/mG1c/egVDv+TCoI30xnblhsbSxaNRmXKztj6h8n1YX1hlNW3q1woY4eeWthk3tbon/m19ay/7O+2zaWuNZ2GIHrLcS6iUT6gyNglmK0MWW97tlTXvX3KB/9z3+e6T0hjaY0GayN3FUlEEQvYSH+EJ5RmOjJe5zfyuzEqkjPQls/ZfNh4pX9Ea7J02IXtU2940pcXpWvr1O2543iIDRUsssJhepKtqflnFFoiANGiTZbJ+D5HZ3lR33aPYx1Wb7SbKNJ6tYzkmxvbEua1PqqyPs0YYT3X1nSBP7DPZplD/frTN5PmtN5zcirPZ+zW+wPe1Vga22AzEwPS8HF/XhqRX1lwWS1skw0Eg1e5ivkAgt+qxLJXdGjhwJZHB9EobafB0ngwkd1Bar3/sfU2PeSmy5oNHwaRwmLai1zHprYgTglg0mE8vsGk3esbtTTx4N5pJ9zq40IuE+pWt2lq62e4E4QzpErBMSNRsW1Dlbl3qQQwHwOjeFENstX8tl2WbbbWvi88piedQbev1eaP5hMnnpLa3QMyTAeWXqXEzOBJBb0f9V/LQ9pX6slZYdEQhsFLsKBZzyEBgTBYXzRb1xgNVjsS2pTfqWrZb8r9SgjSyB2xgrFd+E5lOOBjt2Rlyy6336HJuilB5NfRFe4lVs+D6qr5utYARXoB7+4YTHyMTsZVZZzczES77NQgSA0Y6dXaD6/TE2s/4CJ9VS38LjXPLSYZDG4PJaK/+tVN/6DLcuYcVe+O6dUIuM3ZtV7OtX2TYvrT6lcb9usX4X2FvG6QEIheORYXtKZXprYjbor1u9W977tmvbXeAhfVo1NbpdTW1cjWx9FutpSfd9d7/1qZQKV3JoLGs2BkW9VW0iN3hzxZdeTzYGHqJjPFQYIrLbrX08RVNav2Nztyy3JL3TX1z3lhPw/FuPoPENNb9zKztJ+nBnqnNPIYzvisZ2WoWZJ7W856l9AhVL9Xa+v/SfpU4xl8YfP8SCweWIEQOFmTONzTcniO35yKDDn3sEAEK4xKsrEjP5mQzdMonSfQm7zKele9E4TPvTNKd1PeYhQNWlGTDLLKQXCKWHQcgWL/3IMs3PRyZZsY1WTfHxcbEMyiM39PrZA0zVXZPm8kgS+PLodSVSi6e695u6VTrXnfIWtmDRFPflUpf4SJdjW97Ik8e2vC9ddFby+fD1CtVjl8p5CO/THkkvbu2upewmq+wztBICMIwqOZzgQMpssaBceCFFQYpTU+jynhNZCFFD8lykg2e1or1HaVtFB38NtKer2ebB8hyL1dkNalzI7lAQyz12nomFSTCu3CblTKpGwC37uupz/8TNIn28goYjHaOMPYoUWZYB0NmbQe7VS97cMP4blT2vRqJtomvl6XHoc1Wc174RgrZfmTn8oXHJq3V7pb7ZsuXIlO95lBGgzHb6tSebJPtaTKK7bv6/pJfWkGgglAE0mt4b+EZZL0siUIFgkAaAitIrVvx6vhSzkhSZfWOQiHQUmOFJPSpf2//gjC+x7xVGElfL8V0uZGeY8XOYpTwiyRdHZtt8M5I5NrHPcBnyIZEQmJcIz/xdBjHlnCATDY1kGXQGRKWjbOYNIuxLganJnUNe+vpNW4JOMY6ZMqabVcvtT4X8qCFdbwza7dGX20PofKt2G0FZQZT4jP43vo3vgTw6GVq2xpQf5kXD1ICFUhkmAVcv9tIOxdrlGTMdJm8do7i8izkcmzuPMDcyF4aidgaZxHCj6EZctJSDPxDEoKW3sYO8biqCiRK+L6tjkEKltKrLKXXSG1MYpTHZd3DdIiTx4IzRAlBYjRaGL8y3R3QOFuWobPbmI2ICFer+mVUetuehNS4/UaJFb0Sy9FZPUPD48ppb5uZdTdi263K5JKMsQil3B+zWKshrwKGRIWKCGnolCXbdOrxUiCMZlgV2Z0boqgCrnQ3mO/WsGrLrgflAHfpKrmO5UyuzdN2Cd2Ti7RfPggLTRDmAoQwHqD2CyV9R2inrnPgY39C6cPvI1qroZVkYPcehr7/Rzh7+0NsptuyZjRCKEbSNXZ89P2wvMLGgw9x/cAtxJ5lIgSEgWWivkhpfpHW6ChL/WMs6TluJGdI6TCiixRTRSNKWbFtykGeQEhi48qURBi6JkVajRKSDgaTaLRNSaVGG+PYilK4JCurbb1b3Q5SYBwnqmvABG6802iX2Dmnatwkok2xxlCUEdWwgJUpa2mjx3MOgYOqwkQa0ggVZ+w6DZv2On23hMN8T2uQE+fXKC/XqA1VeOrIHv6ouMK1dA1rLQ/mJvgnpwWFRpffuG2Y36HRG3eJZMD3dod4+4evolY3+dh33MyFyQJrpv0XX2DryPyBzPhSQOBJdAZBMbDsffoLVP/4f1BYXcVIQWDAbryA7bbYMzLJud0n0Vr7WGuRSjEwfZ3iH/13WJpBRSHrR46zTuCBEkFOCSqff4T87/xnyve8iubPvp1pe5WGblEMIu64vMmhz5zh4gMH+cLNg9x5dpO952ZJlaSbU7RzAWkYYIoKZEQnH/LyVD+fDtfoxDGDssjJbo5qK2G1FPGYWmGTxA+i+XpaZEmWm7c/KqscqEOSD3gyqDOTNlxiJQyJcbV2QSp+JB3hdefaLOwY5j/0L3Al3gSgqnL81GIfb3hylou37uKf7u5yLm4ggAfCcX7+Yp5bP/gElWvziE5KnA+468R+dj18C+/s77DQbTDckRz47IsEy6v0778Xqj5QG0O/ynN8IWbw8y8SNDvcfHIP4ztKrNl2r+tmv8wNtkDgixnPhHI1qZGKoW6Ngc9/BrW5SvvYUfStdyFqG8gvfp7chcv0P/4IfVNHWRcRyic5BaEJL10grNfBQHLmJfIb68i+UceFtm5xpWy1yC+sID73ONGDR4hPFkmlBpGjOLtE6ROPURqJUMcH6Tt/nYk/eQRhUtJAIWONkhJTjDAqwJZKyL/zRh67SZCiubkV8CN/8gzFU5dYve8W2t+9j4+z7PcFunIt9XV91wpySvHQWsBb/uCL1A7vYuVbp7isN1AiWxzpQJFIhtxztc2bfvszXHzdbfz+t/VxBRcXQiEZnl5j8mNPsV5ShLvKIGMOqFH+4bU8d/7hZwlXNqjvmURHEYXZBcpPn+Zb8yFPf/9+fk+0fQzuIfHbeGqC8aDI/tkmsttFC03/1UX2372HM9vcs9g+fJd9VUOANQRA4EWuJZYolFTWlrGXL5LuPcjKz/xj5g7fRr7bZu/O9xL89rtQL79AtbPJenG4h6OWTUo0cxWdasLyAOHcNAMrc6wPjJEkwk33SelU1nM5ws0ao48+y+SRB1lWHrSXChk6DC1O4crt+0n6+kGljK52GP/Tz5AEihsP3claJSJUITPjJTrpBgWV4+65mMEnXkStrBEazW13TvHYVI5N03LENuE2eVsyhmJIpREzcXGWsFwgtOO+z2tJe8pnbn2OSWJE3EWkMdamXg3GdZusVAgVYJTw/dyI70yGuPujp5CbDS5/36v507sGWZWWt1zscvt7n6Dv2Qu86VV7+OBuNwGJkhiheq49K7P26ojB6zdA5bBBwMDCBofbig9H0lXrRmTV6SuSLKEUQRJ3fJPflTzWuBort7mBWVnBPvAgswduZt7miPIlyve9mvFP/Bm2tka+sYmqjPhhMkWpvkB07Sx6Yhhx6DB88Uly1y4SHjpJKt2uBZWtlAlSRBeKz7/MgenbOXsgJCHt6YdbCXXT5TOjFjUxTCIs374UMP7Jp4n7Cjz60DE+W40JETSTFrWky/FgiAPPnsHKCP3mb8d84QucPD3D/p17eUo0CXr8KUHiM2plLYlrXGOkq5eNv029ktVTkLINTtparJG+nMlQqywhEkDKCEUeOFejfG6apXtv5l2vGeIPzTSJ1lw6uZN/t3YrBz/0FLsagnFVwWqXoUcZnpABRkJyqCYoza7Q3b8HWc2RvzLNTRuCgR051uIElPiyWXWQSKROXMEuESjf93Vtu9gtaGo0KcUxAZY0TVgdHKXxd36K7g/9BJ3qEMK4WjmnoLIxh7hyHXvwIPaeV2GEIjjzMuWk42QirXR7761FCkUyPopYXWPq8y8zoUM/+0MvVKTC0KDLalJnNW3TNF0/wyRYTZrMpZtc72ywYFoIEXDLimHwhQs0Du3gwlvuob1jhPGnz3P7pkEJ4ZsBkCBIfC84EdkgmDNhksGWwinqZJvEs1thhQtpvYkw/UrsWKKw1nAwqLL/+ibSWF46PsYnmCPRCQjN0+k8H79vBx//6Tfwx0ciFtKmW9Jpla+8pevgAQNhgZM1SWFjg+bx3XTuOIpoNdm7UGeEyAmeejrzlybRJhVaJm2NTnQPjVJeykD3DcDAAOKFU0x9+v3say3QHxrqUT/n7voOzjzwHSwV+nrGKChNfvYKotmAwydoHTxOWq0QXDlPpbbqZ3Mt2nRJdIs0yiFe/wBM7WDwC6c4cr1FKIIeApR1ibSf+3WNeJXNHDoqtvE5A5pBlefm80uE82tcuWU3fzhcY/7Wg+RmFrnz/BrjQYGO0aTWkNjUtSP9xAHG9LDhLSEVf9SMdv/pnhK5vy0GTOq7wXoblGxJEEykEcMrLXS1xOWhAms68Z5AUdcJvxZe5Wf2rfAueYUVXXPData/Xtb4F5ZhIvbMtwm6Kdf3VDk9kSMNAkYuLzGaBj1Q6c+hWlIghFiVQhu6cdorY4R0tWNzcAy9bx/hxgrF3/8v7PmP7+DYI+9l79pVQmHopK65F/jdggWdEp49i0DS2bWfzckpgp07kDeuUZifJZI5UpUym5ynaTYRQrK5d4Tag7cSLC5x8MmLTNjAP2LhESQ3hpng5oCs9VtJe50kx3hMjeFInGPPC1cRI/2cPb6DJ8U6F27bg6lWOPjkRW5pl9BSEJN6bUqDURmW5Y+p2eIb94qpNLuhvqUvtpHRsxQ2G/r1I7ZKSkptjajVMeUyzUrkULdshAjFQlxnWW+6zeBCOWpaj37smQQiYHeSZ/jiPEkYcqpi+Xw5Jh7sZ3BmnWO27JKrbWNK2yh4WG0XpCBJ2p0uUjnCm3Qrtdks9NG+50EoFMlt1Ck+9kUq//d/YPJf/zyHHv0go7qDDLLpw4BCexN19TJxf4XGxA7qxQocPAK1JuH5l8nrDkvJNFeTi8QiRWKZMy0u3X2EZHSEocee5fhcTCAjP9kgSIBUbDXctUi3CgLjtC200RSCiBPzTcpnL5MODbA3zvHDNwJ2tQW2WqV87ir3Xe/QL/y2M2+TxBjnonuktS3ScUYi72WzPQNtnzwQPT5yNvwupVuKlU8MNDtIYZ1W17ZyxghHSJTGIxnCOLjfuhFUI1QPsjxmigzMr9Mdr3K60OZ0rk1n9zil9QbHGpK8zHmWiHrFjgzHwAlmAoFd6XZSZ3E/bS0NdHTI8p2vo/DGF+HjHyGIU6J2G154AeZm2AUkr30LDSSBMhTXV2BhFqZ2Eo9N0Q5KtA8do6ACwosXiLvXudh9GSFbvYZE22hOTeTY88CtDL734xz64hWSgUoPZ3UGdPJHidC9njAZnGgNKSm7bYVjF1YI1jZINhuc+JVlbg1DlBQE6zXYbHDiuRsc2b2Lx2iANS4O49bXkNF/s52hRnvM1skDIwzahmileuRyd8KcnxHZciylPPxp6BRyyFIBUe8QJhYZ+F2F3gM4cXA/oOuhWCMglMpxtSyUVcT++Zjc6iaLd+znasWyJNssjPcx9HSDqesNRk7mmJadbbtOPYxsBMKqGzLAzHU7qW/w+tERr6IzXxngxo//LPW3/0M6J0+QlkpYFREtLVP62AcYWZtHSkkoIH/jCnZlnejAUYJSSNm0CHZMoAaGUJfPUZ95noate2QvdYp1RnA1aHHxvsOkQ31UPv0Fhi7PIqX0/CZNrC1JavzN8y5SCFLhhrANipubkvFnzpJW+5l93d288OqDPPnQTXz+zbfx0o+8gc7eHYy+cInXrDqItOMbCtpYSL0AsLAESPpFjqrKU5QhoU+aMK5H3S7n0BGUOwnlbWLXOaEodDQmTUkCQaxjWnlFd7CMbbUoNTpEQvlwIJBGMZUbYjzo28KoPffcV2RYqxmTEQcXWgTNhLWpMdZyggXb4fp4EWsFexbb7LJ50PYVVbDBYDqJkR19I4gKwZW1zSZpaggC6RV0HOCtCbhRGqf2lh9i9P7X0Pfis4Sf/hjRM08hL10gf+080fhucrqFunCOqNslvHqeyd99F8lGA7W6TNBsY9p1hmfmCIarrqdqHZokBDSTLs/tKHPw/lsZ+dDnMOsNlCe76ayxICzaOgEkKwLXIRKWGE2fynP79QbVyzMsPnCC//K3buEps0GiUrpac1T08wvLR9j/7se479QCB19b4mnb8ipAuuceSWDgxipvf6bO63Nl6spSKwo6hZBrffBpVpipCLqVEoPTS7ypsZ9z5SrLusO+oMzkxjJSW5phQMO0mFFNVgcr9Dc67FxN6BvN07QxWEEOxY/rPRxe6fDe/hIfN8uOJmQNyjh6MQp2ywK759fApAysd/nbl/pYLQ6yiwgdhAxeX2F3eoDHA9XjWW/t8Ata1ItXg74oOtfYrBGnllwu8KC5JgoMReG6G02juDK8h/LrdzN57FYGfuWdBKefJbeySE4FlNsdwhvTyDSFJ55FfP5JcqlzYyLIIXOSoSvzVE/0U1emR2DQ1qJTy/mow/n7jjH45Dny03OYYuQlEtxsrwYS4T6ESDUyNRitiIXmgM1x+MWroALO3rKTR8wCi6bj5ZISNlWLL9w5yfDcLVRNxFE5wDN6w3OVhWscViK6+6dQS6uceN8XOdntuoQzn4dQcebbbuPsLSU+X27z/XcfZc+fPc7b3v8iO193nItlyx3XLXtOz2BzAUvVHA1b53Jc49LuIfbLkOMXl7n72BTvt3WwMbvz47z21DK3/dnT7Pyuu7l0vN8T1rNeYoBCcFNcpHrjEqRdJj/2eX7g0Ry2WEAYUJ0W4cIS+5uHiKqK2CZb9B4pkDqc618pLgYFIy8ubtY6cTfJB+WQVGhKSrLz2mmKzzxGfOJurh25i04iaKWwOrGPyk03EbzwLKrdRUnIra6gZmaxQtDt60eWi5jBPtL+InQ6FF48R+nlq0y86SY2ShmD2PqpPaibBk/s6ufQfccZn5lF6thNGVjjxy1d18coQTo+Sjw2SFwQCG3pz5eZuXU/V48M8+EDRTaSJaTy8VEK6knCbw92+NwP7gdrOGs2el0egaCbaP5nuc36j99GtWPoizVD9ZhKKyZfjynWWsz154hNl6f0Mn98/35+Yv0OBh4/zXeenYNCEbvRgvoa63fdzHO7czSShIYQPHogz31HdjL+uXP8b4cmsMf2cUW0eFutj8OPPQczC5AkdG02POa5VDKhKAT751oUFtcQxhIkXcJ2DCubbrJRWgr1NvuWU/qqOZaJybYoCqWQMRcWf/Xft4ITB/qnF86uza1vNPZNjoQkwhIpQfXZJwl/8zcIftQQHb2drpK+0W+wiUvtdSFARJrczGXMwhz69tvp/sCPokd3sFEWnFfTTMwuc/O/XaNwbYYdi3WuHCr5+RkPZliD1SkvyTqnXnWE/qfOEq2uYEoFUumnFoyA1HCqCsEP38NSWXA2X0d0LF8Q8zy919LFsq5X6foY4KbsXSfpXLrGKeXGW0i8Sq1xBLPEGh7T8zxRClAlS4AgmpDkraCgBUOqDy1rTCcbdIzmt4IbrL5liu+6aZJ952epzK4iooDavYf42Ov28sFwHqMdDPqRcJnXPHSU11xZ4Jb/9ln+3b0nWB8oMXHuRaqnLtDdOc4X9xa4ka4ixIDbKCwF2sBkfoAjmwaxVmPj5BFWb9uPabTIrTbId2Mqc8vk5lbYv9xl4kiJ5W4NIQMnEmslQSd6MUHY4Cf/7n1rP/rzH76wsFTbd+TAAMpKUgnJYD95GcKZlxiqLdMZ3kloBYMr1ymcPwtRQDwwTJhAaWYG2k3MvfexdP+3sya7vLTxBGc7c9w8XmDPnkmqjz3N+KVlCvsrmMSNlWhAyxQtDHHc5tPjOfp++s2YeoMn91TY0JvY1J3qVKU8o5f44oigY7sQC4SCZd30uLFbrOE2y2ejLI6pkW6fzlNutPMVs5jSKeckVvsM2ddB1nA5zdb/KBCWVdvk9+Q0nzhe5dDN40x1d1BIBPNFwRfsLAu6BoRIo7iqN3nXnhID33cvJz/wBJMfeJydIgCdoqsFrrz+OB/r79BJuluaNZ6tsisusfvGHFIITj94lH9/h6CZwpAZYETk+IHLhlf9508wMb3GzrsmOO3npyQG0SqimuFTOFoWVCLxRGOt+aZ221DOCxIhae8+RLl/kNzpU4y+9w/JvfqNBKmm9JmPwksvYvbswuw5SK7VRp6/iMzlSPYcomsTpjdPM904j7Uxy1FE8+ge+p59idyNFfqTI9SOTDH/va9mev8IqW44wEEILpka79pXINYRG3qTjokduUGYLe6zdhvEMtxY2ozxpbGpfeWcgPVDZMaPiWTzt1+icSG9oo2126iNfirB1b1uEF0agUWRGLgWb3DNrjkWak6417YWRNAjFVoreTRewJwc5yeHX8ttz83Qd8NtTb96225+7/YqX0yu9fjhwmhsmiKE4GBdUT03j+6vcnlPlcc7F4htt4dPj44f4JbBEoUbSxxu7uKjZQcSGQmyTk3Ffad7Eg67d/Z9/umza3at1hX9xSKJNrSn9iJO3ob95EcJ3/tuhj79GTApwcoSNtF0XvUaWlN7yS/Moc+/CJV+OmM7mItnuNg8Q9skoCSraZuX797P8vDDLO0YZYGYa/sj7O4DzNGlq1PPuwIrYmpp18cYr2+hfLlpMgjCeINLz3gUTgHOOvJfajNtDMe70taXVtuox5nanvVUImuNZ0SabQw4s6U2br3+hfI/x2gnNSHprdwRTlqnJzToqMGua/VYOsv5nRVOTo2yJ95FGlpOq01Ox9PEInaYQF6weXAHUT5POVdkT1tSWa2zOTzA6aBFoo1XnHO7H8+rNpvDfYxeWuREN0epL6KexkgCgmZwfvPMbdM9A989Xnnu2ZcWb8zMre7aP1FCGs1msULjO76T0tkXCWZuENZraCuwQY7u/fex8W1voR7kKSUtOHoAs2M38yN5TtWfZ02vI1RIiiU2MZ8cENjbh2iaNu14nURCKh2txkhFmkKiJd3EkqZuzjbVGhu4tbVCakQkSa12BwFBqjVIS+KZj8L3BLoiI7Q7io4nSL2CfiwyD52ptWq9RVnKenXZ4K+QXgHHYBKFSiS2FSLjENkNEGnoZ6otVhlMpDFhii2miMhiZYpQisW0wSdsHZTXdTJ+0oMAg+GzyQLp/f1MmgGuVCy5fJ7Tb7mL9lCZF3NNdwDF1sG7HsY0D+wgOn2FqekVxsYK1G0bmebJt4uPdd7zNs32TQl//x0f/91mvvzjb3nTzeRyLpiViZl64tNEH/0QankZWyqSHD9G41u/h6WJQ1hgwLaIum0aecujrVOc6VxwUJwOSKQmsdpznYxnP2ri1NJpSDprgngdTF0QtSJC7WT8K/kcqbFstBp0TEIcdGlWErp9XWx/FyoaG/oEzArixIB0r7M1Y+S1HqUfGvYAtsxQJA/nGZNs4656vFDrLXGfVBHWc4SrRcq1PsZ0Pzvyw1RFgTCRhCLf09DWNqYlYuKgy0K8wZJeZ7PUpFmpk/TF2EIMge7Zyd0v25OKtPgxWmOoUmJClclJw4Vkg5rdth7NGsbDPn6htpP7H7/MytHd/OLBJl/sThNtVG31wth3rPzKr3ykd4MtsHuy/KfPXln/8dnlBgd2D0Biacg80w98OwMn7yFs1rD5iEbfCG3pZHJDodhURXS+yNn6s1xuXnUr6KwiFilJj1Xp4lurJqnNSdIFQbld5kChn8PjO9i7a5CxoQr9xYhyqUClHKINbNY71BttVv7f5s40yLKzvO+/dznn3K33ZVbNplk0I6EFCSQkFZFAJRmwEMYEDDHlqlQlH+ws5aqUsROXKcplYkwc2wmuJC47MQ44xmC8xEFxsEW0IM8IrWhGSLOoh9Esvd/uvus5513y4T339u3RSAg0Qzifuqur+p777u/zPP/ff63L2foqR8+/wosXLnCGZVYmVnFbM1w5OGWbYnk0RRaqX1VuBxTXhZSlJ40Nxej0a8r6S7MEmWr0Qo3xhXH2spVbt+zjpmt3sn/rBFs3DZPEPcdzGUqGvQ/ZKRdcxRfqXc7OrXF6YZlnXpnh+VNnOC3mWB5bIh/pImoZTpvgfYHsYy9Moa1eZI3FbnNdWjKI9heKpbzNZ2uv8JUfn6SkDafTFfCaZLV6bnJ27MjiRQJTjn7jaO03//epJzbv3XvwXXfuRTiDF74op12XkCorUIW3r9BB+D2TnuBbK4+y6rtop8mEIZM5zktS46lfcLTOCIZWh9hX3czb9+7k+v2b2bV9gtHhBB2JN6TFaHQM5y6s8uyJczx89ATfXDrBmYkF8p1dTCWUtRtrNuqDegp5H0w7JPLVB6p+qTsoEyPnS2w5u5nbytfwnuuu57brdrBr5xilkvweIiFxyT+1WoYz5+s8PzPHYy8d58jCCV4unWd1uo4dSnFx70Dgkf1SSlOgFYMVgut/kXUApPNmXb8kITZDDB+d+MLir/3mx7nUG/38rzz4S3Vf/fQD77+BseGoGOFyXRCuRBFKC/9QKsWSucBji4+y6ObwIlx9jII09dTPCJovGzal49yxez/vvGk3B/dOMzKSXNS4cqCJBhrroh8HX7axmvH08+f48pNH+duFo5zdOke2rY1RKX2njh6fq9iTQ+WFK5boohLD2aC+8IKoUWJoZpqb7QF+5m238q5b97F5U3XjB1+iL/1AXdRrD4Dwt2Yz5+TZJR5+6iRff/k7PO1eYmlqiXy8DVGOFwppe/xOtxGbNZgt8j1HtmLLkZLhuSkmX5j+yZc/96mvXrKD/+MfP7X18cNnn7rtnddtvvH6bThnQgmPkGgVsiSyYB1JKWm5JofrjzPTPYWVOUI72nnMyllYPe7Y1p3inhuu5d1vv5o9V42iNK890r8vYdW6RLXRMPz909/l848d4evmKCt7lrHDnfWP6ansXa/wwgyMLRPqv60kmatx9dnd/NTud/Cxe2/h6p2jb1b/9fqqAwvnZhs88vQp/urpp/h7c5z5LQvk4y2EcsWADOIC399U/LowrZczED0pS4mJY5u/u//JvTc99r9+tn5JW50H/+z3Gm+7/cPVla69e8/eTSQ6NKOSheK+UPVrJLnM+HbrKY43v4NXFqcUy0uKC085hk+P8IEDN/OzP3En97xjDxPj5dCQrAPW3swj+qpySBLF1bvGece+PUyujXD6hSVWRIqpGYR0fUCLcK44Lbv1kkNl8HmJ0suj3L5wHf/mnvv56fvfxqapEgMf8abf9xK6P4T0jA4nXL9/C3ceOMABvZ30lKC+kJHGOZQtXsoBmsNFy0jP5lYo0J7yyiiTMxP//dkv/sKfv65v0h13vffo3GL+wU1bpsY3T1UDFFMUjCsn0EJilONU+wTfXvs2qTakHcW5Y9B9rsy9W67jX37gH/Bj7zzA+HgZIUW/SqOnZXqzM3iwmiLULnmGh2JuvmY7B0pbmTvaZrbZIBtNA0ahyB+vA8WKCv9MUTs5xXvM2/jkh97Pu2/fQxSJDdvB5e3cjTQDX1gODQ3FXLdvE3fu3c+2bIrVk5bltQ5pOYPErLtibpSWIYTCS4uymrGZ6WzX4pafP/PMg+de9Wnee3HkxNLQrfsmWkIIe99Hfu+Bq6/f/6UP/+StSZIEa99AJAjEnNn8At+sP8KsXWFp1rL8jONQtJOP3PVW7rxtF6VE0VesvaE96s3NB1EUAvQ649iL8/y7v3yIP8+P0Ni/iNcW4QuPYFdUUGSa0ZOb+IC6nU986G4O7J/qi8lEf9e7gmt0IQCXiMGmwjk4dnyOLz3yFH925ggz0+cxmxtYWaD3VCFO68PZPUl9iquO7vzaid/55fcJ4POHjw//9K37GkII3+/gLz3z8i2nVv0nUlnyq8udY0888tLH3//uG/ccunqMqpSUI0WiYNUu8/jSwxxfPcf5lzzRTIUHrr+Rn7jvLWyarvZf3YZU+Q/5Wa/JPHNmjd/+i//LH689zNKeWWw5x9twOBS5ZPjFKT5cuot//dH72LWjVsSfxBUZhP2h4igKFuh7rG0cSK6PHko7joeffJn/+vDjfINnqW9fwpRz8Ko4aZfBl5F2CL04za7G3q/e9NYDr5A1D11Vkr/76+879Ff9Du499//hkWvnuuJzTT161+xSkyHt2TRSYqwSM53ETJYjunKOme4LnPtOk4mzFT7xkTu4987dRdmm69mODQiyZH91CfYDriDI+8u8BLoBBoUDFPNLHf79l/+W/zb7d8wfmIdSDlZTOTXG+7M7+JWPvpeDe8cooHkMosEuy+riB/D7vcuNHzyHuIvQvOsU/9xCaj1Hjs3xya8c5mhlHrPZ420FfBVlqqGTXYTIE5KkyoTr5LFu/dMX/tmdn2cjjGn9OfTJo7Hf1PmFehb90oqJKs6ZcDXCobVCiBwpc1wDdtfK3HvDBNtHFJuHY7bVykwkguFEU40VlUhd2pipvx+KKziZw9VhebnLb3z57/j9hf/D8v5Z4tkq9y2+nV/9qQ9y/aHpkGcWAwYhP6Qnd7CaGdrW0kody6nn7GqX+WbKQitloelY7BjOt1JmFh1N67FKIESw5VMovFU4l1Eta7ZX87PTgp/5+j++8aFLkbRe9dz3B0/fc6aj/sOcjQ92rAnF4S6kn4TscUUcwlgSCaVYUtMwnCgmy4KtVcX20QpbhkpMVWOmKoqtFc1QoqhEmnL86s6/rHu1X585C4sdfvVPHuQLZx5lv9/Gv/3Ah7j79t2hbKhA8V7uc7IF0tzRyQyN3LKQeubaGfVWxnLHMLuW8t2VlIWuo961rOXQznJaJlzberhEhMLroDbBFN5ORf16EmmuGoq4YdI/d3Ay/vgv3r7j+ddCpV3y+Vd/PbP58ELjM2c77v4s92PoKmlBeesF+X3R8U6Ct4bAzhEIHyC8JSWpRJJyDOPKM1VL2DZRYlstYqqkmSwrto2UODRRZqSkrsA+GPaLk2dW+d0vPsLNB7fy0fvfGtxirsCs9cC3LrT4m5PLnG8Z5te6zDUz6kbSSB2ptaS5JLcGryR4FWTjQiKFKdKYsg9yUVKRRJokgppSVHzbjZfUUjXSp0vCHbtpe+X5j12z63/smhYXXo+F95qPBD72ly/uNim7DWpPO0+vtcZekyJ3WCe2Wy+Hmw46XtJKDe1ujkNjZMjA4jyiUCf0h7ayKG/QUlFSsLXs+dRdO7n/msmBg5K8bA1OQXFdXMoolzTVagRXpHvD1/v1x87w6UfPg0zwQgWkQ4EPFMUUoIewAPAKgcdKQznSTCSSEe0Z1tiS5vxkSc0MlaNjI6X4mVqcv7R/rHbigwenFoQQ5nu9j34jR5cvPHDNDDADPNQPEHlf/ZNnZ6damdqxZluHjFL765k79LUXV+8+vkKsi1rfnvlRscjgZe9yUCLD0TGStJEyn6Z9yo0Ql+96IvrdK5mcKBesLX8F7rfhyZxnoWMxKiZWEo8K0ahe7UDBA+tjoEUQtCoEynt7y7h+6K5d1WeGI56fGomP3rhl+tyhEbFgfkA4mv6BFz0hWkALOA08AvBKt7vv22dbz76wkse6oOR53+NVFrZzhX+hFRAVaTbwdJ3uu7ZsFEKKi6aj6xeqFy+CL7wlNrxjQYjv/SspeujFYvnzrm85JKTcGPf2rl/NIwYsdF+9qlxiFfCebpYR+POBU9KPiPkex0P2C9V7NgZGRMRZvnL4iQsf/pt/dPfK5Rpw+nKO3npDvD1KkkpuO4g4QrteHl3hhAlRrQF0v0MglcRayeGzDQ5uqjAWKcp4tPZEQqKlDAoFragkGt0z8ugbhHDJq4aQ624t4uKxMhBNE/LV40iIYo71aLPFluGALPd0c0PubLCws4LMhVx3x3rm2zmn1sJeqgh+yQjZp+aJgpHji2pRHwwXseREziQ/955t7/30b/vjwFIxgdpAWwjh/r938FAs3rmlGrEl8qTeBZRgz6BX9ALmstAgh1kn8DgR89cn13jslSY1rVBSUFKOspaUtSCWUIkV40MVqrFHF6rOciSpxRoVPH3QSgYzLjwakIU1q2Td26JnVuKLxvWeQNjplQEVeWNb8LjWsoxOAFdiLDTajtVOh461dI2kYzxtGzgfbevp5hkrJgKvCwxTD48XflNCoL0g0ZaKVpQ0jEUwPiTYWhmt3bt/6ovFVp4BK0DdQr1j/XInzedXc3vh7Go6+8JyOnumni0lLq/fe8PumdsmxdobOmQJ4LY/enZ6vuH2prm70VqZ4t1ZKzhvclMfRTc+3rm58alPbRxRkRTMNLJnO44bTsw1mW10ON82LLUcK+2c2VbOUtew1jW0c0dqFZmXOGPoEvD7zoIjGGIGQrzvh+NEwXsUwvYnoZSSWBREoAJA3ndcE+CkKqzow3kgGH/4DUjmsFoPHAL7WKogTM1sYRFYAMT78e8eSbY3U71FApGUlCNBohyJEJS1ppYoxhLJVC1mrKKYrigmSoptQ2UmqhETFc1oRVLTGusFc82c1dSw1Mmodx1ruWC5Y6mnhqWGYT7NWGzmrDYzYuU700PRuVIsvp4g/ud0uXz4P/34zvqrOviz3zy285FT7Y+crOf3rLjoxrasTlkZh1og0wXnrMeuScGi9HLJebXgMOekd68IJ85IjP4Xt0x87pfftacaD6iRc6CTe1rdnGZuWTaWRupZ6ziWWynLjS6zrS4N61jtSFYzQeos7TynlToyK0LZjw1kdhBYFzhaFlmI04KdDaLY311BnvfrQNQB/GeR9OilHYMnkyigqkKI4mxgEdKifajcKGuBUg6tJCUVUYsESSypaMloKaKmLaMxTNQqjFYTJiqS0VgzGkuGiqBPNdaUYknyOhGzrx5f5jceOU09k7RST9cWhtLCYYUMvGwRJoKSMUp6Ii2olRJG8ybTUfrC1SPxF99x1c7//E9uH13uL9HxalQfqiRfqazyhFFiX0229+Lygx3n9uVkm4iSsTyqjVknx6wU+5wD4YMKz1lITcrjsx2em2uzZzxhWIe9MxKCKBIMR/Frn9S9J/PQNtDJHJm1dIyhkzty40itp2kMLevoWkc3g27qaeaWZpqT52EmGdPzapAYG7iU9O2UZR9Upgh7uiz0UVpKVFG9UtERQ3FEOZaUYkiUp6QVo7EkkQqlIVGKWqyItCLWikokKKuw372R03lP3G68p2Gh3s5Z7WQsdTIenFnjubrAF0xtgUSoQF3QWqGFIPYOnae2VGovlGN1viTkiwnmO+VhdXyI+OToSGVBp/X297wHS+Dnvva15PTi+NaOj3d0vT7Q7Jq3dK3fZ53c0/Vsy5yvOF2hYwUlmbKjLNhelWyraqaqCZtHS2wfSZguS8aSiKGSphIrkkiSvMmbaN+zqFhvfWE7h1intF9MguwdrwazloF6W+CkCiC5+AFvF4YQQ06dp5s52p2cljEsp4Z61zHXssw1u7TynOVWzkJXsNA2tLqGlczRsBInI7SUJBgirEuUWysrTpe1nKlF0YvVkn6+ZPJTO0c489n3XTsvhXD+dZOT3+cjgd86vDj8jZkLU6nN96c+2Z9l4uBip/OWVzrilsyqWKqAPoyUoCRzxsuakVgxVtGMxoLJqmI80UzWSkyUYkYriuFEU06gojUlGQ5XZS1JioOXEOsM6ytxi/UDsRjvwdogW+1aR9eFwr5O5ukYQ9cLmqlhtWvoppZ627DUTlmzlnrHsZZDK4VGu8tq7mhmlm7uybwk60EfnMR5iROOSGiE9GwuufpkyR8ZiaKjifQvlRPx4vZyNPMPbygv37FjR+f7vQ5f1nb6L0+eGvm1x5tPLeXy6j4CWRQ6XIo8rPEbuOOR9ERSUFaCREOsoKYjKlpQUpaxcsRQOaaSKLT0VLWiFgsSrVFArCRKhUNRb4lVcuMXFAPxsZbJyU2xlxe1eNY6cgNdb2imOV0f6rSz1NLODctpRiuH3Co6eU4rt+RekztLJw8UeGMJ7i1CYK3csNf3+Bjr5p69YE+BzCBY64yXIt59lfrFP3pg/2fcj+I9GKASeeZzhRKmYCELoiIZKlAQ9XmcQbwpoOuhkYHIipSDtwVr2SNEDr5VsKkdyoMW6y6XUhZ55yJdqb0M6kJ/Uc8K+kZWVgyAwwoEcM/nwfSZ3sWVTrgBp7cAFveyMNX1inXqkQ82vEKFEic8zhcucWIjosz5woKzX6sdLnLSZjmi9pC7jP1xWTu4FmtZkj6ROsJ6j7KBeu5FIRj1hZUdPY/D0ICicHYJqHuJkwK8LqJcFo/sGZyCW/dtCAXkBc8Ki/S6sFdXRUDMFydk0ZeviL5ZxkWBj8LxpRfpCvuyKlQNvh+V8z0vxl46t9ivjZfr5Z8FWjngPQYcvPvjTha401AG5bAIGWPonhybjI7yo9rBu0dF96qh+E9btv1Wa8yU8W7YOjHilRw2MiJHY4pO9raQ8FK4ikmPt+GLSyGKeHEQfLmizbwLvsTCiQE7AYdXIJzuV3v24GXY4LDWs5H3esDEscctUhKK4nNFb3URA2QdHQZoEXFyMphK9ihLfmAz6Dme0pOyFJ2rhAjpaSFRMgRktIbYeyIEsfJUahHVLH70t27f0bn8FWBXoKzsW08+GX3mOTlazxjNIz/ihZ5yKt7czTubrfWbsoxJKxgzTo4ZyShejGbWV5wXkXcuslJEXkVIpXAiRJGCQYkfsKQJ16PQaSFqFCSUwdxKbMgLD2LUe1UfxUCSRYRYhEoQnEeonuRUIpQKdrfFzVnLYIHrPGgliArhthYeiUE5i/bOJlrnkfKmHIlMe9+MlFitRHJlOIpWyqV4pabFYiT8fKTzhaFyPDfkxdP//M6d53/kO/j7OY0/8eST0TeWdPxyLuPZuq/qpDzcWeuOtLBDRumhDDdkjKhleTaMVDUctdzZmpSqgvdVIWRZCFEGV/JCliyipLyLQSZSiMgJIuOczq2QAqMC3yCs1MorF2vhlfDOWW+9srn02jjv80iTKU9mves6QUc41xXQ1YhOrEUHaAloD1XiZiJl0/m8EUsalbJqVUTSiDGNiVq1MVKL1sa0a2wZStJ79oxlQK6FMPaH1Mb/DzaiohgLf1ofAAAAAElFTkSuQmCC" alt="Logo IES Santa Lucía"><span>Tecnológico de Santa Lucía – Por terminar</span></div>
      </div>
      <div class="item">
        <div class="item-head"><span data-type data-speed="30">Educación básica</span></div>
        <div class="lugar">I.E. José Carlos Mariátegui</div>
      </div>
    </div>

  </main>
</div>

<div class="sugerencia">Haz clic para ver todo de inmediato</div>

<script>
  const cv = document.getElementById("cv");
  const elementos = Array.from(cv.querySelectorAll("[data-type]"));
  let saltar = false;

  elementos.forEach(el => {
    el.dataset.texto = el.textContent;
    el.textContent = "";
  });

  function escribir(el, velocidad) {
    return new Promise(resolve => {
      const texto = el.dataset.texto;
      el.classList.add("typing");
      let i = 0;
      const timer = setInterval(() => {
        if (saltar) {
          clearInterval(timer);
          el.textContent = texto;
          el.classList.remove("typing");
          return resolve();
        }
        el.textContent += texto[i++];
        if (i >= texto.length) {
          clearInterval(timer);
          el.classList.remove("typing");
          resolve();
        }
      }, velocidad);
    });
  }

  function esperar(ms) {
    return new Promise(r => setTimeout(r, ms));
  }

  async function iniciar() {
    cv.classList.add("escribiendo");
    await esperar(800);
    for (const el of elementos) {
      const velocidad = Number(el.dataset.speed) || 30;
      await escribir(el, velocidad);
      await esperar(saltar ? 0 : 180);
    }
    mostrarTodo();
  }

  function mostrarTodo() {
    saltar = true;
    elementos.forEach(el => {
      el.textContent = el.dataset.texto;
      el.classList.remove("typing");
    });
    cv.classList.add("listo");
    cv.classList.remove("escribiendo");
  }

  cv.addEventListener("click", () => {
    if (!cv.classList.contains("listo")) mostrarTodo();
  });

  iniciar();
</script>
</body>
</html>
