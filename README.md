<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>CV - Alexis Michael Mamani Colque</title>
  <style>
    :root {
      --color-principal: #1f2937;
      --color-acento: #2563eb;
      --color-texto: #374151;
      --color-suave: #6b7280;
      --fondo: #f9fafb;
      --blanco: #ffffff;
    }
    @media (prefers-color-scheme: dark) {
      :root:not([data-theme="light"]) {
        --color-principal: #f3f4f6;
        --color-acento: #60a5fa;
        --color-texto: #d1d5db;
        --color-suave: #9ca3af;
        --fondo: #111827;
        --blanco: #1f2937;
      }
    }
    :root[data-theme="dark"] {
      --color-principal: #f3f4f6;
      --color-acento: #60a5fa;
      --color-texto: #d1d5db;
      --color-suave: #9ca3af;
      --fondo: #111827;
      --blanco: #1f2937;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background: var(--fondo);
      color: var(--color-texto);
      line-height: 1.6;
    }

    .contenedor {
      max-width: 820px;
      margin: 40px auto;
      background: var(--blanco);
      padding: 48px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
    }

    header {
      display: flex;
      align-items: center;
      gap: 28px;
      border-bottom: 3px solid var(--color-acento);
      padding-bottom: 20px;
      margin-bottom: 28px;
    }

    header h1 { font-size: 2.1rem; color: var(--color-principal); }

    header .cargo {
      font-size: 1.1rem;
      color: var(--color-acento);
      font-weight: 600;
      margin-top: 4px;
    }

    .contacto {
      margin-top: 14px;
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      font-size: 0.95rem;
      color: var(--color-suave);
    }

    .contacto a { color: var(--color-acento); text-decoration: none; }
    .contacto a:hover { text-decoration: underline; }

    section { margin-bottom: 30px; }

    section h2 {
      font-size: 1.25rem;
      color: var(--color-principal);
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-bottom: 14px;
      padding-bottom: 6px;
      border-bottom: 1px solid #e5e7eb;
    }

    .item { margin-bottom: 18px; }

    .item-header {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 8px;
    }

    .item-header h3 { font-size: 1.05rem; color: var(--color-principal); }

    .institucion {
      font-weight: 600;
      color: var(--color-acento);
      font-size: 0.95rem;
    }

    .habilidades { display: flex; flex-wrap: wrap; gap: 8px; }

    .habilidades span {
      background: #eff6ff;
      color: var(--color-acento);
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 0.9rem;
      font-weight: 500;
    }

    .idiomas { list-style: none; }
    .idiomas li { margin-bottom: 6px; }

    @media (max-width: 600px) {
      .contenedor { margin: 0; border-radius: 0; padding: 28px 20px; }
      header { flex-direction: column; align-items: flex-start; gap: 16px; }
      header h1 { font-size: 1.7rem; }
    }

    @media print {
      body { background: white; }
      .contenedor { box-shadow: none; margin: 0; padding: 20px; }
    }
  </style>
</head>
<body>

  <div class="contenedor">

    <header>
      <div>
      <div>
        <h1>Alexis Michael Mamani Colque</h1>
        <p class="cargo">Joven en búsqueda de su primer empleo</p>
        <div class="contacto">
          <span>📍 Santa Lucía, Lampa, Puno</span>
          <span>📱 932 015 690</span>
          <span>📧 <a href="mailto:alexismamanicolque69@gmail.com">alexismamanicolque69@gmail.com</a></span>
        </div>
        </div>
      </div>
    </header>

    <section>
      <h2>Perfil</h2>
      <p>Joven responsable con gran capacidad de adaptación a nuevos entornos y ganas de aprender. Busco mi primera oportunidad laboral para crecer profesionalmente y aportar con compromiso y dedicación.</p>
    </section>

    <section>
      <h2>Prácticas preprofesionales</h2>
      <div class="item">
        <div class="item-header">
          <h3>Prácticas técnicas</h3>
          <span class="fecha">08/2025</span>
        </div>
        <p class="institucion">Tecnológico de Santa Lucía – Perú</p>
        <ul>
          <li>Ofimática</li>
          <li>Mantenimiento</li>
          <li>Fibra óptica</li>
          <li>Diseño en AutoCAD</li>
          <li>Excel</li>
          <li>Uso de guantes y kit de herramientas</li>
        </ul>
      </div>
    </section>

    <section>
      <h2>Formación académica</h2>
      <div class="item">
        <div class="item-header">
          <h3>Estudios técnicos en curso</h3>
          <span class="fecha">2024 – 2026</span>
        </div>
        <p class="institucion">Tecnológico de Santa Lucía – Por terminar</p>
      </div>
      <div class="item">
        <div class="item-header">
          <h3>Educación básica regular</h3>
        </div>
        <p class="institucion">I.E. José Carlos Mariátegui</p>
      </div>
    </section>

    <section>
      <h2>Habilidades</h2>
      <div class="habilidades">
        <span>Adaptación rápida</span>
        <span>Responsabilidad</span>
        <span>Ganas de aprender</span>
      </div>
    </section>

    <section>
      <h2>Idiomas</h2>
      <ul class="idiomas">
        <li><strong>Español:</strong> Nativo</li>
        <li><strong>Inglés:</strong> Básico</li>
      </ul>
    </section>

  </div>

</body>
</html>
