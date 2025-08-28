# -web<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>JJCargo - Transporte de Cargas</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;400&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"/>
  <style>
    :root {
      --primary: #68a4fb;
      --secondary: #203a43;
      --accent: #ffd700;
      --background: #f6faff;
      --white: #fff;
      --shadow: 0 8px 32px rgba(32,58,67,0.15);
      --footer-bg: #18232d;
    }
    body {
      margin: 0;
      padding: 0;
      min-height: 100vh;
      font-family: 'Montserrat', Arial, sans-serif, Negrita;
      /* Fondo de carretera + gradiente para legibilidad */
      background:
        linear-gradient(120deg, rgba(104,164,251,0.7), rgba(32,58,67,0.75)),
        url('https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1400&q=80') no-repeat center center fixed;
      background-size: cover;
      color: var(--secondary);
    }
    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(255,255,255,0.95);
      padding: 18px 40px;
      box-shadow: 0 2px 8px #203a4322;
      position: sticky;
      top: 0;
      z-index: 99;
      backdrop-filter: blur(5px);
    }
    .navbar .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .navbar .logo svg {
      width: 38px;
      height: 38px;
      fill: var(--accent);
      animation: truckMove 3s infinite linear alternate;
    }
    @keyframes truckMove {
      0% { transform: translateX(0);}
      100% { transform: translateX(20px);}
    }
    .navbar .brand {
      font-size: 1.5em;
      font-weight: 700;
      color: var(--secondary);
      letter-spacing: 1px;
      text-shadow: 0 2px 6px #68a4fb33;
    }
    .navbar nav a {
      color: var(--secondary);
      font-weight: 500;
      text-decoration: none;
      margin-left: 28px;
      font-size: 1em;
      transition: color 0.2s, border-bottom 0.2s;
      border-bottom: 2px solid transparent;
      padding-bottom: 3px;
      position: relative;
    }
    .navbar nav a:hover {
      color: var(--primary);
      border-bottom: 2px solid var(--primary);
      font-weight: 700;
    }
    .hero {
      width: 100vw;
      padding: 40px 0 0 0;
      text-align: center;
      animation: fadeIn 1.4s;
    }
    .hero-title {
      font-size: 2.7em;
      color: var(--white);
      font-weight: 700;
      text-shadow: 0 2px 18px #203a43bb;
      letter-spacing: 2px;
      margin-bottom: 12px;
    }
    .hero-desc {
      font-size: 1.25em;
      color: var(--accent);
      margin-bottom: 32px;
      font-weight: 500;
      text-shadow: 0 2px 6px #68a4fb88;
    }
    .hero-img {
      width: 90vw;
      max-width: 800px;
      margin: 0 auto 22px auto;
      border-radius: 20px;
      box-shadow: 0 8px 32px #203a4340;
      overflow: hidden;
    }
    .main-card {
      background: rgba(255,255,255,0.98);
      box-shadow: var(--shadow);
      border-radius: 18px;
      padding: 36px 28px;
      width: 100%;
      max-width: 440px;
      text-align: center;
      margin: 0 auto 30px auto;
      animation: fadeIn 1.2s;
      position: relative;
      overflow: hidden;
    }
    .main-card::after {
      content: "";
      position: absolute;
      right: -60px;
      top: -60px;
      width: 120px;
      height: 120px;
      background: radial-gradient(circle at center, var(--primary) 30%, transparent 80%);
      opacity: 0.15;
      z-index: 0;
      pointer-events: none;
    }
    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(-40px);}
      100% { opacity: 1; transform: translateY(0);}
    }
    h1 {
      font-size: 2.2em;
      margin: 0 0 8px 0;
      font-weight: 700;
      color: var(--secondary);
      letter-spacing: 2px;
      text-shadow: 0 2px 6px #68a4fb22;
      position: relative;
      z-index: 1;
    }
    .subtitle {
      font-size: 1.18em;
      color: var(--primary);
      margin-bottom: 20px;
      font-weight: 600;
      letter-spacing: 1px;
      position: relative;
      z-index: 1;
    }
    .info {
      margin-bottom: 26px;
      font-size: 1.03em;
      color: var(--secondary);
      text-align: left;
      position: relative;
      z-index: 1;
    }
    .info p {
      margin: 7px 0;
      font-size: 1.06em;
      display: flex;
      align-items: center;
      gap: 7px;
    }
    .info i {
      color: var(--primary);
      font-size: 1em;
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 13px;
      margin-top: 10px;
      position: relative;
      z-index: 1;
    }
    label {
      font-size: 1em;
      color: var(--secondary);
      text-align: left;
      margin-bottom: 3px;
      font-weight: 500;
    }
    input, textarea {
      padding: 12px 14px;
      border-radius: 8px;
      border: 1.5px solid var(--primary);
      font-size: 1.08em;
      background: var(--background);
      color: var(--secondary);
      outline: none;
      transition: box-shadow 0.2s, border-color 0.2s;
      margin-bottom: 3px;
    }
    input:focus, textarea:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 2px #ffd70033;
    }
    textarea {
      resize: vertical;
      min-height: 70px;
    }
    button {
      padding: 13px 0;
      background: linear-gradient(90deg, var(--accent) 0%, var(--primary) 100%);
      color: var(--secondary);
      font-weight: 700;
      font-size: 1.13em;
      border: none;
      border-radius: 7px;
      cursor: pointer;
      transition: background 0.2s, color 0.2s, box-shadow 0.2s, transform 0.2s;
      margin-top: 10px;
      box-shadow: 0 2px 6px #203a4322;
      letter-spacing: 1px;
    }
    button:hover {
      background: linear-gradient(90deg, var(--primary) 0%, var(--accent) 100%);
      color: var(--white);
      box-shadow: 0 4px 12px #68a4fb88;
      transform: scale(1.04);
    }
    .services {
      max-width: 1000px;
      margin: 30px auto 40px auto;
      display: flex;
      flex-wrap: wrap;
      gap: 28px;
      justify-content: center;
      animation: fadeIn 1.5s;
    }
    .service-card {
      background: rgba(255,255,255,0.96);
      border-radius: 22px;
      box-shadow: 0 8px 24px #203a4322;
      padding: 40px 22px 30px 22px;
      width: 270px;
      text-align: center;
      transition: transform 0.2s, box-shadow 0.2s, background 0.2s;
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }
    .service-card .icon-service {
      font-size: 2.7em;
      margin-bottom: 14px;
      color: var(--primary);
      transition: color 0.2s;
      text-shadow: 0 3px 10px #68a4fb33;
      animation: iconBounce 2.5s infinite alternate;
    }
    @keyframes iconBounce {
      0% { transform: translateY(0);}
      100% { transform: translateY(-7px);}
    }
    .service-card:hover .icon-service {
      color: var(--accent);
      animation: none;
    }
    .service-card::before {
      content: '';
      position: absolute;
      left: 12px; top: 16px;
      width: 36px; height: 36px;
      background: var(--primary);
      border-radius: 50%;
      opacity: 0.07;
      z-index: 0;
      pointer-events: none;
    }
    .service-card:hover {
      transform: translateY(-8px) scale(1.05);
      box-shadow: 0 12px 32px #68a4fb66;
      background: rgba(245,250,255,1);
    }
    .service-card h3 {
      margin: 0 0 15px 0;
      color: var(--secondary);
      font-size: 1.23em;
      font-weight: 700;
      position: relative;
      z-index: 1;
      letter-spacing: 1px;
    }
    .service-card p {
      font-size: 1.07em;
      color: #222;
      position: relative;
      z-index: 1;
      margin-bottom: 0;
      font-weight: 500;
    }
    /* --- confianza section --- */
    .trust-section {
      max-width: 900px;
      margin: 40px auto 0 auto;
      text-align: center;
      padding: 0 15px;
      animation: fadeIn 1.3s;
    }
    .trust-title {
      font-size: 1.7em;
      font-weight: 700;
      color: var(--secondary);
      margin-bottom: 25px;
      letter-spacing: 2px;
    }
    .trust-title i {
      color: var(--accent);
      margin-right: 10px;
    }
    .trust-cards {
      display: flex;
      gap: 30px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .trust-card {
      background: var(--background);
      border-radius: 16px;
      box-shadow: 0 6px 24px #203a4333;
      padding: 28px 22px 18px 22px;
      flex: 1 1 220px;
      max-width: 260px;
      margin-bottom: 25px;
      transition: transform 0.2s, box-shadow 0.2s;
      position: relative;
    }
    .trust-card i {
      font-size: 2.2em;
      color: var(--primary);
      margin-bottom: 14px;
      transition: color 0.2s;
    }
    .trust-card h3 {
      font-size: 1.15em;
      font-weight: 700;
      margin: 0 0 10px 0;
      color: var(--secondary);
    }
    .trust-card p {
      color: #203a43;
      font-size: 1em;
      margin: 0;
    }
    .trust-card:hover {
      transform: translateY(-6px) scale(1.04);
      box-shadow: 0 10px 30px #68a4fb44;
    }
    @media (max-width: 700px) {
      .trust-cards { flex-direction: column; gap: 12px;}
      .trust-card { max-width: 99vw; }
    }
    /* Beneficios */
    .benefits-section {
      max-width: 1000px;
      margin: 44px auto 0 auto;
      text-align: center;
      padding: 0 15px;
    }
    .benefits-title {
      font-size: 1.5em;
      font-weight: 700;
      color: var(--primary);
      margin-bottom: 28px;
      letter-spacing: 1px;
    }
    .benefits-list {
      display: flex;
      gap: 35px;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 20px;
    }
    .benefit-card {
      background: #fff;
      border-radius: 14px;
      box-shadow: 0 4px 16px #203a4311;
      padding: 22px 18px;
      max-width: 250px;
      font-size: 1em;
      color: var(--secondary);
      transition: transform 0.2s, box-shadow 0.2s;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-bottom: 18px;
    }
    .benefit-card i {
      font-size: 2em;
      color: var(--primary);
      margin-bottom: 7px;
    }
    .benefit-card strong {
      font-size: 1.07em;
      margin-bottom: 7px;
      display: block;
      color: var(--primary);
    }
    .benefit-card:hover {
      transform: translateY(-4px) scale(1.04);
      box-shadow: 0 8px 24px #68a4fb33;
      background: #f9f9ff;
    }
    @media (max-width: 900px) {
      .benefits-list { flex-direction: column; gap: 12px; }
      .benefit-card { max-width: 99vw;}
    }
    .footer {
      background: var(--footer-bg);
      color: var(--accent);
      text-align: center;
      padding: 23px 0 15px 0;
      font-size: 1.13em;
      letter-spacing: 1px;
      margin-top: 50px;
      box-shadow: 0 -2px 8px #203a4333;
    }
    .footer .social {
      margin: 10px 0 18px 0;
      display: flex;
      justify-content: center;
      gap: 24px;
      flex-wrap: wrap;
    }
    .footer .social a {
      color: var(--accent);
      font-size: 1.85em;
      margin: 0 8px;
      transition: color 0.2s, transform 0.2s;
      text-decoration: none;
      display: inline-block;
    }
    .footer .social a:hover {
      color: var(--primary);
      transform: scale(1.2) rotate(-7deg);
    }
    .footer .whatsapp {
      color: #25d366;
      font-size: 1.85em;
      margin: 0 8px;
      vertical-align: middle;
    }
    @media (max-width: 1020px) {
      .services {
        gap: 18px;
      }
      .service-card {
        width: 90vw;
        max-width: 340px;
      }
    }
    @media (max-width: 600px) {
      .main-card {
        padding: 20px 7px;
        max-width: 97vw;
      }
      h1, .hero-title {
        font-size: 1.4em;
      }
      .navbar {
        flex-direction: column;
        padding: 10px 5vw;
        gap: 10px;
      }
      .navbar nav a {
        margin-left: 16px;
        font-size: 0.95em;
      }
      .services {
        gap: 14px;
      }
      .footer {
        font-size: 0.95em;
        padding: 17px 0 10px 0;
      }
    }
  </style>
</head>
<body>
  <div class="navbar">
    <div class="logo">
      <svg viewBox="0 0 50 50">
        <rect x="7" y="22" width="30" height="16" rx="3"/>
        <rect x="37" y="27" width="10" height="11" rx="2"/>
        <circle cx="14" cy="41" r="4"/>
        <circle cx="38" cy="41" r="4"/>
        <circle cx="42" cy="38" r="3"/>
      </svg>
      <span class="brand">JJCargo</span>
    </div>
    <nav>
      <a href="#inicio">Inicio</a>
      <a href="#servicios">Servicios</a>
      <a href="#confianza">Confianza y Garantía</a>
      <a href="#beneficios">Beneficios</a>
      <a href="#contacto">Contacto</a>
    </nav>
  </div>

  <div class="hero">
    <div class="hero-title">JJCargo</div>
    <div class="hero-desc">Soluciones modernas en transporte de carga</div>
    <div class="hero-img">
      <img src="https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=900&q=80" alt="Camión en ruta" style="width:100%;display:block;">
    </div>
  </div>

  <div class="services" id="servicios">
    <div class="service-card">
      <div class="icon-service"><i class="fas fa-truck"></i></div>
      <h3>Transporte nacional</h3>
      <p>Movemos tu carga a cualquier punto del país con seguridad y puntualidad.</p>
    </div>
    <div class="service-card">
      <div class="icon-service"><i class="fas fa-boxes"></i></div>
      <h3>Logística integral</h3>
      <p>Asesoría y gestión de todo el proceso logístico, desde el origen hasta el destino.</p>
    </div>
    <div class="service-card">
      <div class="icon-service"><i class="fas fa-truck-moving"></i></div>
      <h3>Nuestra Flota</h3>
      <p>Vehículos equipados y monitoreo satelital para máxima eficiencia y protección.</p>
    </div>
    <div class="service-card">
      <div class="icon-service"><i class="fas fa-shield-alt"></i></div>
      <h3>Seguridad garantizada</h3>
      <p>Control y Seguimiento en cada envío para tu tranquilidad.</p>
    </div>
  </div>

  <!-- SECCIÓN CONFIANZA Y GARANTÍA -->
  <div class="trust-section" id="confianza">
    <h2 class="trust-title"><i class="fas fa-shield-alt"></i> Confianza y Garantía</h2>
    <div class="trust-cards">
      <div class="trust-card">
        <i class="fas fa-user-shield"></i>
        <h3>Seguridad total</h3>
        <p>Tu carga protegida con monitoreo en tiempo real y seguro completo.</p>
      </div>
      <div class="trust-card">
        <i class="fas fa-handshake"></i>
        <h3>Compromiso</h3>
        <p>Cumplimos plazos y mantenemos comunicación transparente en cada envío.</p>
      </div>
    </div>
  </div>

  <!-- SECCIÓN BENEFICIOS -->
  <div class="benefits-section" id="beneficios">
    <h2 class="benefits-title"><i class="fas fa-thumbs-up"></i> Beneficios de elegir JJCargo</h2>
    <div class="benefits-list">
      <div class="benefit-card">
        <i class="fas fa-clock"></i>
        <strong>Rapidez</strong>
        <span>Despachos ágiles y entregas a tiempo.</span>
      </div>
      <div class="benefit-card">
        <i class="fas fa-dollar-sign"></i>
        <strong>Precio justo</strong>
        <span>Tarifas competitivas y presupuestos claros.</span>
      </div>
      <div class="benefit-card">
        <i class="fas fa-globe"></i>
        <strong>Cobertura nacional</strong>
        <span>Llegamos a todo el país.</span>
      </div>
      <div class="benefit-card">
        <i class="fas fa-user-tie"></i>
        <strong>Atención personalizada</strong>
        <span>Un asesor dedicado para tu empresa.</span>
      </div>
    </div>
  </div>

  <!-- CONTACTO -->
  <div class="main-card" id="contacto">
    <h1>Contáctanos</h1>
    <div class="subtitle">¡Estamos listos para mover tu negocio!</div>
    <div class="info">
      <p><i class="fas fa-envelope"></i><strong>Correo:</strong> contactojjcargo@gmail.com</p>
      <p><i class="fas fa-map-marker-alt"></i><strong>Dirección:</strong> San Francisco de Mostazal</p>
      <p><i class="fas fa-phone"></i><strong>WhatsApp:</strong> +56 9 7305 0668</p>
    </div>
    <form action="mailto:contactojjcargo@gmail.com.com" method="POST" enctype="text/plain">
      <label for="nombre">Nombre</label>
      <input type="text" id="nombre" name="Nombre" required>
      <label for="correo">Contacto</label>
      <input type="email" id="correo" name="Correo" required>
      <label for="mensaje">Mensaje</label>
      <textarea id="mensaje" name="Mensaje" rows="3" required></textarea>
      <button type="submit"><i class="fas fa-paper-plane"></i> Enviar mensaje</button>
    </form>
  </div>

  <div class="footer">
    <div class="social">
      <a href="https://wa.me/+56973050668" target="_blank" title="WhatsApp"><i class="fab fa-whatsapp whatsapp"></i></a>
      
    </div>
    &copy; 2023 JJCargo · Todos los derechos reservados
  </div>
</body>
</html>