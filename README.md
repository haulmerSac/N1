<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portal de Enlaces y Paneles - Centro de Ayuda Ejecutivo</title>
  <style>
    :root {
      --primary: #2563eb;
      --primary-hover: #1d4ed8;
      --bg-main: #f8fafc;
      --card-bg: #ffffff;
      --text-main: #0f172a;
      --text-muted: #64748b;
      --border-color: #e2e8f0;
      
      /* Colores por Categoría */
      --tag-rrhh: #0284c7;
      --tag-plataformas: #7c3aed;
      --tag-formularios: #059669;
      --tag-herramientas: #d97706;
      --tag-notion: #e11d48;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background-color: var(--bg-main);
      color: var(--text-main);
      line-height: 1.5;
      padding-bottom: 40px;
    }

    header {
      background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
      color: #fff;
      padding: 2rem 1.5rem 1.5rem;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    .header-container {
      max-width: 1200px;
      margin: 0 auto;
    }

    .header-container h1 {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 0.25rem;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .header-container p {
      color: #94a3b8;
      font-size: 0.95rem;
    }

    /* Container */
    .main-container {
      max-width: 1200px;
      margin: 1.5rem auto 0;
      padding: 0 1.5rem;
    }

    /* Tabs */
    .tabs-nav {
      display: flex;
      gap: 8px;
      border-bottom: 2px solid var(--border-color);
      overflow-x: auto;
      padding-bottom: 2px;
      margin-bottom: 1.5rem;
    }

    .tab-btn {
      background: transparent;
      border: none;
      padding: 10px 18px;
      font-size: 0.95rem;
      font-weight: 600;
      color: var(--text-muted);
      cursor: pointer;
      border-radius: 8px 8px 0 0;
      transition: all 0.2s ease;
      white-space: nowrap;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .tab-btn:hover {
      background-color: #f1f5f9;
      color: var(--primary);
    }

    .tab-btn.active {
      color: var(--primary);
      border-bottom: 3px solid var(--primary);
      background-color: #eff6ff;
    }

    .tab-badge {
      background: var(--border-color);
      color: var(--text-main);
      font-size: 0.75rem;
      padding: 2px 7px;
      border-radius: 12px;
    }

    .tab-btn.active .tab-badge {
      background: var(--primary);
      color: #fff;
    }

    /* Quick Search Bar Section */
    .search-box-container {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 1.25rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.04);
      margin-bottom: 1.5rem;
    }

    .search-input-wrapper {
      position: relative;
      display: flex;
      align-items: center;
    }

    .search-icon {
      position: absolute;
      left: 14px;
      font-size: 1.2rem;
      color: #94a3b8;
    }

    .search-input {
      width: 100%;
      padding: 12px 16px 12px 42px;
      font-size: 1rem;
      border: 2px solid var(--border-color);
      border-radius: 8px;
      outline: none;
      transition: border-color 0.2s ease;
    }

    .search-input:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
    }

    .search-hint {
      margin-top: 8px;
      font-size: 0.85rem;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    /* Cards Grid */
    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 1rem;
    }

    .card {
      background: var(--card-bg);
      border: 1px solid var(--border-color);
      border-radius: 10px;
      padding: 1.25rem;
      transition: transform 0.15s ease, box-shadow 0.15s ease;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      text-decoration: none;
      color: inherit;
    }

    .card:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 16px rgba(0,0,0,0.06);
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 8px;
      gap: 8px;
    }

    .card-title {
      font-size: 1.05rem;
      font-weight: 700;
      color: var(--text-main);
    }

    .badge {
      font-size: 0.72rem;
      font-weight: 600;
      padding: 3px 8px;
      border-radius: 6px;
      color: #fff;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      white-space: nowrap;
    }

    .badge-rrhh { background-color: var(--tag-rrhh); }
    .badge-plataformas { background-color: var(--tag-plataformas); }
    .badge-formularios { background-color: var(--tag-formularios); }
    .badge-herramientas { background-color: var(--tag-herramientas); }
    .badge-notion { background-color: var(--tag-notion); }

    .card-subcategory {
      font-size: 0.8rem;
      font-weight: 600;
      color: #64748b;
      background-color: #f1f5f9;
      display: inline-block;
      padding: 2px 6px;
      border-radius: 4px;
      margin-bottom: 8px;
    }

    .card-desc {
      font-size: 0.9rem;
      color: #475569;
      flex-grow: 1;
      margin-bottom: 12px;
    }

    .subcat-section {
      margin-bottom: 2rem;
    }

    .subcat-title {
      font-size: 1.2rem;
      font-weight: 700;
      color: #334155;
      padding-bottom: 6px;
      border-bottom: 2px solid var(--border-color);
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .no-results {
      text-align: center;
      padding: 3rem 1rem;
      color: var(--text-muted);
      background: var(--card-bg);
      border-radius: 12px;
      border: 1px dashed var(--border-color);
    }

    .no-results h3 {
      margin-bottom: 8px;
      color: var(--text-main);
    }
  </style>
</head>
<body>

  <header>
    <div class="header-container">
      <h1>🚀 Portal de Accesos & Consultas SAC</h1>
      <p>Buscador inteligente y directorio unificado de enlaces, herramientas y documentaciones.</p>
    </div>
  </header>

  <main class="main-container">
    
    <!-- Navegación por Pestañas -->
    <nav class="tabs-nav">
      <button class="tab-btn active" onclick="switchTab('search')">
        🔍 Consulta Rápida
      </button>
      <button class="tab-btn" onclick="switchTab('RRHH')">
        👥 Recursos Humanos <span class="tab-badge" id="count-RRHH">0</span>
      </button>
      <button class="tab-btn" onclick="switchTab('Plataformas')">
        🖥️ Plataformas <span class="tab-badge" id="count-Plataformas">0</span>
      </button>
      <button class="tab-btn" onclick="switchTab('Formularios')">
        📝 Formularios <span class="tab-badge" id="count-Formularios">0</span>
      </button>
      <button class="tab-btn" onclick="switchTab('Herramientas')">
        🛠️ Herramientas <span class="tab-badge" id="count-Herramientas">0</span>
      </button>
      <button class="tab-btn" onclick="switchTab('Notion')">
        📚 Notion <span class="tab-badge" id="count-Notion">0</span>
      </button>
    </nav>

    <!-- Barra de Búsqueda -->
    <section class="search-box-container">
      <div class="search-input-wrapper">
        <span class="search-icon">🔎</span>
        <input type="text" id="searchInput" class="search-input" placeholder="Escribe cualquier palabra (ej. comision, turno, sim, ecert, garantia, etc.)..." oninput="handleSearch()">
      </div>
      <div class="search-hint">
        <span>💡 Búsqueda flexible (asociación de palabras, insensible a tildes y mayúsculas).</span>
        <span id="searchStats">Visualizando todo el catálogo</span>
      </div>
    </section>

    <!-- Contenido dinámico -->
    <section id="contentArea">
      <!-- Los resultados o tarjetas se inyectan aquí por Javascript -->
    </section>

  </main>

  <script>
    // Datos cargados con sus enlaces reales
    const rawData = [
      // RRHH
      { category: "RRHH", subcategory: "", title: "Turnos", description: "Planilla de turnos", url: "https://docs.google.com/spreadsheets/d/1M5PA08e81QS7-TmmWZfyeeTBh2-tRq9Ki3qaJm165ww/edit?gid=706085746#gid=706085746" },
      { category: "RRHH", subcategory: "", title: "Academy Haulmer", description: "Plataforma de Cursos haulmer", url: "https://academy.haulmer.com/" },
      { category: "RRHH", subcategory: "", title: "Buk", description: "Plataforma BUK para solicitud de permisos, liquidaciones , etc", url: "https://haulmer.buk.cl/" },
      { category: "RRHH", subcategory: "", title: "Beneficios y Reembolsos", description: "Plataforma para generar reembolsos gastos médicos , otros y beneficios Haulmer", url: "https://haulmer.atlassian.net/servicedesk/customer/portal/2313" },
      { category: "RRHH", subcategory: "", title: "Estados de agente", description: "Plataforma para registrar estados de agentes durante el día a día", url: "https://sites.google.com/haulmer.com/estadoagente/inicio?pli=1&authuser=0" },

      // Plataformas
      { category: "Plataformas", subcategory: "", title: "Workspace", description: "Panel de trabajo principal para revisar información del comercio", url: "https://workspace-backend-panel-admin.azurewebsites.net/admin/contribuyente-summary" },
      { category: "Plataformas", subcategory: "", title: "WHMCS", description: "Panel para revisar ficha cliente productos contratados, facturas, etc", url: "https://my.haulmer.com/27admin/supportcenter.php" },
      { category: "Plataformas", subcategory: "", title: "Panel de Pagos", description: "Panel para revisión más detallada, ya sean conciliaciones, reportes, integración pagos, etc.", url: "https://panel-admin-pci.payment.haulmer.com/admin/dashboard" },
      { category: "Plataformas", subcategory: "", title: "Nuevo PanelPagos", description: "Reporte de Abono Flexible, Detalle de transacciones online y descarga de comprobantes, etc", url: "#" },
      { category: "Plataformas", subcategory: "", title: "KDH", description: "Plataforma para bloqueo de POS y soft delete", url: "https://panel-kdh.payment.haulmer.com/admin/dashboard" },
      { category: "Plataformas", subcategory: "", title: "Espacio de trabajo", description: "Plataforma de espacio de trabajo para revisar espacios de clientes y ayudar en consulta y guía para los clientes.", url: "https://espacio.haulmer.com/" },
      { category: "Plataformas", subcategory: "", title: "Movistar", description: "Plataforma para revisar estados de sim Movistar", url: "https://movistar-cl.iotkiteplatform.com/#/site/app/dashboard" },
      { category: "Plataformas", subcategory: "", title: "Entel", description: "Plataforma para revisar estados de sim Entel", url: "https://entel.jasperwireless.com/provision/ui/m2mhome/m2mhome.html" },
      { category: "Plataformas", subcategory: "", title: "Jira", description: "Plataforma para revisión de tablero de trabajo", url: "https://haulmer.atlassian.net/jira/servicedesk/projects/SAC/queues/custom/1142" },
      { category: "Plataformas", subcategory: "", title: "Soporte R2", description: "Plataforma para seguimiento de casos escalados a R2", url: "https://haulmer.support.r2.co/portal/es/signin" },
      { category: "Plataformas", subcategory: "", title: "Keycloak", description: "Plataforma para cambios de contraseñas en espacio de trabajo", url: "https://accounts.haulmer.com/realms/master/protocol/openid-connect/auth?client_id=security-admin-console&redirect_uri=https%3A%2F%2Faccount-haulmer-backend-core.azurewebsites.net%2Fadmin%2Fmaster%2Fconsole%2F%23%2Fhaulmer-users&state=14684f66-0141-4540-8c42-4087fc6d2a3a&response_mode=fragment&response_type=code&scope=openid&nonce=df528e37-dc86-4874-98c6-84d71891e555&code_challenge=o6MS3w4qxMSn-nwtZuawqVXEInOtLot41iKpgjOFDaQ&code_challenge_method=S256" },
      { category: "Plataformas", subcategory: "", title: "Ringover", description: "Plataforma de Centro de llamadas", url: "https://app.ringover.com/call-logs" },
      { category: "Plataformas", subcategory: "", title: "Ecert:", description: "Plataforma para escalamiento de casos Ecert, de firma electrónica", url: "https://ecertla.atlassian.net/servicedesk/customer/portal/8/group/36/create/110" },
      { category: "Plataformas", subcategory: "", title: "Estados R2", description: "Plataforma para revisar los diferentes estados en R2 desde la aplicación, financiamiento, Conciliaciones, ETC.", url: "https://partners.r2.co/financings/financing-merchant-cash-advance" },
      { category: "Plataformas", subcategory: "", title: "BackOffice", description: "Plataforma BackOffice para Gestión de clientes AndCo.", url: "https://bank-frontend-backoffice.prod.haulmer-bank.com/" },

      // Formularios
      { category: "Formularios", subcategory: "", title: "Cambio de Comisión", description: "Formulario para cambio de comisión tarifario solamente para clientes TUU", url: "https://form.typeform.com/to/zl7eEe9Y?typeform-source=www.google.com" },
      { category: "Formularios", subcategory: "", title: "Cambio de Razón social o Creación de servicios", description: "Formularío para cambio de razón social o creación de servicio exclusivo para cliente TUU", url: "https://survey.typeform.com/to/WSDNBhOE?typeform-source=www.google.com" },
      { category: "Formularios", subcategory: "", title: "Escalamiento R2", description: "Formularío de escalamiento para R2", url: "https://forms.zohopublic.com/r2capital/form/Formulariosoportepartner4/formperma/bYnl2_OtZPtDPNloPi-Me5_IhKmsGxcTNZiZj0LJT_8" },
      { category: "Formularios", subcategory: "", title: "Escalamiento de tu reserva o tu evento.", description: "Formulario de escalamiento para casos, tu reserva o tu evento.", url: "https://docs.google.com/forms/d/e/1FAIpQLSc1u6bnUzGU4PDTcC0UPsSNZgAAAZX2xebqLtBU5zx_w7r_eg/viewform" },
      { category: "Formularios", subcategory: "", title: "Solicitud de creación de contenido", description: "Formularí opera solicitud de creación de contenido.", url: "https://form.typeform.com/to/P6cD47iA?typeform-source=www.google.com" },

      // Herramientas
      { category: "Herramientas", subcategory: "SIM", title: "Listado sim de Baja", description: "Listado de Sim dados de baja", url: "https://docs.google.com/spreadsheets/d/1Gx2klhGlLXBperjSymj7_lctNTZ53Mf-dBl68RLJXyw/edit?gid=466786900#gid=466786900" },
      { category: "Herramientas", subcategory: "SIM", title: "Legacy Movistar", description: "Listado de Sim Legacy.", url: "https://docs.google.com/spreadsheets/d/1VAt9SW53apuviRqw19YyfVktBM8GAAquzuJFiefcdhA/edit?gid=0#gid=0" },
      { category: "Herramientas", subcategory: "Firma Electronica", title: "Validador de firmas", description: "Link para validar documentos firmados con firma ecert", url: "https://api.ecertchile.cl/WebSignValidator/public/signature-validator" },
      { category: "Herramientas", subcategory: "Firma Electronica", title: "Chilefirmas", description: "pagina para compra de firma y revisar valores", url: "https://www.chilefirmas.cl/autoatencion/" },
      { category: "Herramientas", subcategory: "Predeterminados y Mix", title: "Mix Tipificados", description: "Ayuda como guía de como se tiene que tipificar y en qué casos", url: "https://docs.google.com/spreadsheets/d/1lqiD0cjTbzLC0ZXz9vdkENpBbiGXF5YIAPSHG7BYZGY/edit?gid=54992419#gid=54992419" },
      { category: "Herramientas", subcategory: "Predeterminados y Mix", title: "Predeterminados Telefono", description: "Correos predeterminados para enviar, de acuerdo a cada tipificado", url: "https://docs.google.com/document/d/1Gcg1saemSdMUodeP846FI8qE5L5autsWL4NAwmQFdzE/edit?pli=1&tab=t.0#heading=h.n9667htqukpr" },
      { category: "Herramientas", subcategory: "Predeterminados y Mix", title: "Predeterminados chats", description: "Correos predeterminados para enviar, de acuerdo a cada tipificado", url: "https://docs.google.com/document/d/1eB0lLcIbr5hpCNElPFT7rxhfgKq7P_-hAlNk-sFlpFw/edit?tab=t.0#heading=h.wonfgz6unneg" },
      { category: "Herramientas", subcategory: "SII", title: "Consulta Situación tributaria Terceros", description: "Ayuda para revisar información del comercio en el sii", url: "https://www2.sii.cl/stc/noauthz" },
      { category: "Herramientas", subcategory: "SII", title: "Consulta contribuyentes", description: "Permite revisar qué documentos tiene autorizado y si está afiliado al sistema de boletas del SII", url: "https://palena.sii.cl/cvc/dte/ee_empresas_dte.html" },
      { category: "Herramientas", subcategory: "Despacho", title: "Alasxpress", description: "Link para hacer seguimiento pedido alas con SHP (Se agrega SHP-XXXX al final del link)", url: "https://tracking.alasxpress.com/api/SHP-" },
      { category: "Herramientas", subcategory: "Status", title: "Status Haulmer", description: "Status de sistemas Haulmer operativos", url: "https://status.haulmer.com/" },
      { category: "Herramientas", subcategory: "Status", title: "Status Transbank", description: "Status de sistemas transbanck operativos", url: "https://status.transbankdevelopers.cl/" },
      { category: "Herramientas", subcategory: "Status", title: "Status Kushki", description: "Status de sistemas Kushki operativos", url: "https://status.kushkipagos.com/" },
      { category: "Herramientas", subcategory: "Partner", title: "Catastro Revendedores", description: "Listados de revendedores", url: "https://docs.google.com/spreadsheets/d/1ekW5bjPvFF5LHQqmAErQEWXylzXpHSSCr0gRqw_FCi8/edit?gid=0#gid=0" },
      { category: "Herramientas", subcategory: "Partner", title: "Catastro Partner", description: "Listados de Partner", url: "https://docs.google.com/spreadsheets/d/1uhzy2BNFnlRsJaqbNKaTvvi7o0byxALzW5Rie_7ctVk/edit?pli=1&gid=0#gid=0" },
      { category: "Herramientas", subcategory: "Desk y POS", title: "Consolidado de errores POS", description: "Consolidado de errores en pos , Transaccional, Pago, DTE.", url: "https://app.notion.com/p/haulmer/Errores-de-dispositivos-POS-y-otros-HP-OF-3ac7ccd6b624809fadfdd329b8b9fb51" },
      { category: "Herramientas", subcategory: "Desk y POS", title: "Error Hp-MR-180 Desk", description: "Error HP-MR-180 en desk , por mas de 5 pagos pendiente en pos", url: "https://app.notion.com/p/haulmer/Error-HP-MR-180-en-Desk-39f7ccd6b6248022b378dfe71d1db4c5" },
      { category: "Herramientas", subcategory: "Desk y POS", title: "Sincronizar Desk", description: "Sincronizar desk con pos de pago", url: "https://app.notion.com/p/haulmer/Sincronizaci-n-TUU-desk-con-APP-PAGO-1f37ccd6b62480f8a712cb7dd8d83bbb" },
      { category: "Herramientas", subcategory: "Desk y POS", title: "Actualizacion de ROM", description: "Actualizar ROM en POS", url: "https://app.notion.com/p/haulmer/ROM-desk-2-3ab7ccd6b62480aab171f08a6938dc51" },
      { category: "Herramientas", subcategory: "Desk y POS", title: "Cuotas TUU", description: "Información de cuotas tu funcionamiento.", url: "https://docs.google.com/presentation/d/16X7xZCtmszXNNn_7tXUs1rKmoC6oj0kLUjazXF5Fzmg/edit?slide=id.g2f0293ecc37_0_159#slide=id.g2f0293ecc37_0_159" },
      { category: "Herramientas", subcategory: "Contenidos", title: "Biblioteca de contenidos para compartir con clientes.", description: "Acá encontrarás una biblioteca de contenidos que podemos compartir con los clientes con video para aquellos los puedan revisar.", url: "https://docs.google.com/spreadsheets/d/1ZiVXXDpvdeA7AFmD-k9klgrSzL2PLRYsb2ONKhgVvwY/edit?gid=0#gid=0" },
      { category: "Herramientas", subcategory: "Contenidos", title: "Biblioteca de contenidos para Agentes-SAC-N1", description: "Biblioteca de contenidos para agentes SAC no compartir con cliente.", url: "https://drive.google.com/drive/folders/1W6yeRpNFxfGQufvG14vztf22wIvk1VeO" },
      { category: "Herramientas", subcategory: "Abonos", title: "Listado abono Flexible (ex abono inmediato)", description: "Listado de comercios con abono flexible activo", url: "https://docs.google.com/spreadsheets/d/15eCambeXkkHlhgvi6Xqy5o56uOiJj4NPrl5C_R7rgnc/edit?gid=1287904134#gid=1287904134" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "Filtro Jira", description: "Filtros Jira", url: "https://haulmer.atlassian.net/issues/?jql=created%20%3E%3D%202021-12-14%0Aand%20created%20%3C%3D%202021-12-15%0Aand%20text%20~%20%22MARIA%20MAGDALENA%20KRAUSS%20ECHEVERRIA%20FRUTERIA%20TUTTI%20FRUTTI%22%0Aand%20project%20%3D%20OIE%0AORDER%20BY%20created%20DESC" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "Vigencia de Cédula de identidad", description: "Pagina registro civil para consulta documentos C.I", url: "https://www.registrocivil.cl/principal/servicios-en-linea/consulta-vigencia-documento-1" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "Actividades Restringidas", description: "Listado de Actividades Restringidas", url: "https://docs.google.com/spreadsheets/d/1bMwrqHFBaXMQWiTGtdu9J77aNEiG7nDEw_4WP4BleBc/edit?gid=912907488#gid=912907488" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "Help.TUU", description: "Tutoriales de autoayuda para agentes y clientes con paso a paso", url: "https://help.tuu.cl/" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "Revise estado de tu certificación.", description: "Link se puede compartir con el cliente para que pueda revisar el estado de su certificación.", url: "https://www.tuu.cl/seguimiento" },
      { category: "Herramientas", subcategory: "Otras Herramientas", title: "capacitacion prioritaria SAC", description: "Link se puede compartir con cliente para agendar capacitación.", url: "https://calendly.com/agenda-haulmer/sac-derivacion-onb?month=2026-09&date=2026-09-22&utm_source=chatgpt.com" },

      // Notion
      { category: "Notion", subcategory: "Guia Interactivas", title: "Guías Interactivas para SAC", description: "Guía interactiva para Sac con modelo de emisión, ferias libre, generador de certificados, flujos de atención de integraciones, estados de firma electrónica y calculadora de comisión.", url: "https://app.notion.com/p/haulmer/Gu-a-Interactiva-de-Diagn-stico-y-Operaci-n-SII-3b37ccd6b62480e8b65bd41e25c8b1cc" },
      { category: "Notion", subcategory: "Actualizacion", title: "Actualizacion de ROM", description: "Actualizar ROM en POS", url: "https://app.notion.com/p/haulmer/ROM-desk-2-3ab7ccd6b62480aab171f08a6938dc51" },
      { category: "Notion", subcategory: "SIM", title: "Guía de revisión de sim en movistar y entel", description: "Guía para poder revisar e reactivar SIM movista y entel", url: "https://app.notion.com/p/haulmer/Gu-a-de-revisi-n-de-SIM-Entel-Movistar-3ce7ccd6b624806a84efd85b6fd5f242" },
      { category: "Notion", subcategory: "Protocolos en Llamada", title: "Protocolo de corte de llamadas", description: "Guía de Protocolo de Corte llamada.", url: "https://app.notion.com/p/haulmer/Problema-de-activaci-n-PAGO-4aae53379bd84281a53146264558060f" },
      { category: "Notion", subcategory: "Protocolos en Llamada", title: "Protocolo de liberación de llamadas.", description: "Guía de paso a paso del protocolo de liberación de llamada.", url: "https://app.notion.com/p/haulmer/Protocolo-Liberaci-n-de-llamada-31f7ccd6b624809a835fef37e096fd40" },
      { category: "Notion", subcategory: "Protocolos en Llamada", title: "Speech de derivación encuestas.", description: "Speech de derivación encuesta.", url: "https://app.notion.com/p/haulmer/Speech-de-atenci-n-con-derivaci-n-a-encuesta-33b7ccd6b6248034a5c9de5a0442e32e" },
      { category: "Notion", subcategory: "Validacion de seguridad", title: "Validación de Seguridad – Canal TUU Chat", description: "Proceso de Validación de Seguridad – Canal TUU Chat", url: "https://app.notion.com/p/haulmer/Validaci-n-de-Seguridad-Canal-TUU-Chat-3c67ccd6b6248031ac74fa536f475bbf" },
      { category: "Notion", subcategory: "Validacion de seguridad", title: "Protocolo de Validación de Seguridad – AndCo. | SAC", description: "Proceso de Validación de Seguridad – AndCo", url: "https://app.notion.com/p/haulmer/Protocolo-de-Validaci-n-de-Seguridad-AndCo-SAC-3957ccd6b624803f81a4eac18ae8d4ac" },
      { category: "Notion", subcategory: "Validacion de seguridad", title: "Validación de seguridad - Canal telefónico.", description: "Proceso de Validación de Seguridad – Canal Telefonico", url: "https://app.notion.com/p/haulmer/Generar-speech-del-check-de-seguridad-para-agentes-SAC-1f37ccd6b62480dcb053f90b63144ae8" },
      { category: "Notion", subcategory: "Gastronomia", title: "[Gastronomía] Documentos en historial de atención", description: "acceder a un detalle completo de cada atención cerrada, incluyendo sus cuentas, productos, pagos y comprobantes", url: "https://app.notion.com/p/haulmer/Gastronom-a-Documentos-en-historial-de-atenci-n-33d7ccd6b62482a1919b81c914cef603" },
      { category: "Notion", subcategory: "Gastronomia", title: "Actualización de botones y nombre Gastronomía Workspace", description: "Actualización de pantalla de bienvenida de Gastronomía", url: "https://app.notion.com/p/haulmer/WS-Actualizaci-n-de-botones-y-nombre-Gastronom-a-Workspace-ddd7ccd6b6248389bcf50169700df7cd" },
      { category: "Notion", subcategory: "Gastronomia", title: "[Gastronomía] Movimientos de Caja", description: "Movimientos de Caja en Gastronomía", url: "https://app.notion.com/p/haulmer/Gastronom-a-Movimientos-de-Caja-3817ccd6b62481128801da9e85f2ec61" },
      { category: "Notion", subcategory: "Gastronomia", title: "[Gastronomía] Cajas y Arqueos", description: "Cajas y Arqueos en Gastronomía", url: "https://app.notion.com/p/haulmer/Gastronom-a-Cajas-y-Arqueos-3817ccd6b6248127a010fe228715a701" },
      { category: "Notion", subcategory: "Gastronomia", title: "[Gastronomía] Turnos de Trabajo", description: "configurar y filtrar mis ventas por Turnos de Trabajo, para organizar y analizar la información histórica de ventas", url: "https://app.notion.com/p/haulmer/Gastronom-a-Turnos-de-Trabajo-3817ccd6b62481009aace973258cdf4b" },
      { category: "Notion", subcategory: "Gastronomia", title: "Gastronomía en PRO 2 S (P8 con scanner)", description: "enviar una comanda, cada producto se imprima automáticamente en el área de impresión que le corresponde según su configuración", url: "https://app.notion.com/p/haulmer/Pending-Gastronom-a-en-PRO-2-S-P8-con-scanner-d137ccd6b6248370a10d017b411c2b26" },
      { category: "Notion", subcategory: "Gastronomia", title: "Gastronomía v1.0.", description: "Introducción al módulo gastronomía.", url: "https://app.notion.com/p/haulmer/Gastronom-a-v1-0-ae472a8260684477bf534e6de93b7878" },
      { category: "Notion", subcategory: "Gastronomia", title: "Manuales de funcionalidades Gastronomía", description: "Manuales de funcionalidades Gastronomía", url: "https://app.notion.com/p/haulmer/Manuales-de-funcionalidades-Gastronom-a-3217ccd6b62480d98fcddeb1e8cf8e77" },
      { category: "Notion", subcategory: "Jira", title: "Glosario de proyectos Jira", description: "Glosario de proyectos Jira - Haulmer", url: "https://app.notion.com/p/haulmer/Glosario-de-proyectos-Jira-Haulmer-3db7ccd6b62480a492d3f5c0663db045" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "[Kiosco] Actualización Flujo de activación de Pinpad", description: "Guia de paso a paso Actualización Flujo de activación de Pinpad (Kiosco)", url: "https://app.notion.com/p/haulmer/Kiosco-Actualizaci-n-Flujo-de-activaci-n-de-Pinpad-8b87ccd6b6248325bd3401145f64b47b" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "(Catálogo) Edición de producto en catálogo", description: "Guía de paso a paso de cómo editar la información de un producto específico de mi catálogo.", url: "https://app.notion.com/p/haulmer/WS-Cat-logo-Edici-n-de-producto-en-cat-logo-9047ccd6b6248347810b014a45026c8b" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "Movimientos de producto en catálogo", description: "Guía de paso a paso de cómo consultar la información de movimientos de un producto sin perder de vista la lista de productos.", url: "https://app.notion.com/p/haulmer/WS-Cat-logo-Tab-Movimientos-de-producto-en-cat-logo-3697ccd6b62483b8a7ed016bd5c1b4d2" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "General de producto en catálogo", description: "Para revisar sus datos generales, propiedades y stock de forma más rápida y mantener el contexto de navegación mientras gestiono el producto.", url: "https://app.notion.com/p/haulmer/WS-Cat-logo-Tab-General-de-producto-en-cat-logo-a327ccd6b62482918f51018777276940" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "Catálogo] Nuevo layout de card de producto + ajuste funcionamiento multi tag", description: "Nuevo layout para listado de productos y mejora en visualización de múltiples tags", url: "https://app.notion.com/p/haulmer/WS-Cat-logo-Nuevo-layout-de-card-de-producto-ajuste-funcionamiento-multi-tag-3ce7ccd6b62480d2b2b7e5e07b9ee86b" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "Mejoras Misceláneas de Catálogo", description: "Optimización de Búsqueda de Productos, Gestión de Recetas e Ingredientes y Consistencia de UI", url: "https://app.notion.com/p/haulmer/WS-Catalogo-Mejoras-Miscel-neas-de-Cat-logo-0a37ccd6b62482b1938c01610fb82d22" },
      { category: "Notion", subcategory: "Kiosco / Catálogo", title: "Kiosco como punto de red", description: "kiosco pueda compartir su conexión a internet con otros dispositivos del pack (en particular la Pinpad),", url: "https://app.notion.com/p/haulmer/Kiosco-Kiosco-como-punto-de-red-3977ccd6b62483a4a7248182a67573bc" },
      { category: "Notion", subcategory: "AndCo", title: "Guía Interactiva AndCo.", description: "Guilla interactiva de flujo de atención y más AndCo.", url: "https://app.notion.com/p/haulmer/Inducci-n-AndCo-Agentes-SAC-3d67ccd6b6248016a3d8eadefed7f36a" },
      { category: "Notion", subcategory: "AndCo", title: "Apoyo AndCo Face beta.", description: "Guía de introducción de AndCo.", url: "https://app.notion.com/p/haulmer/Apoyo-AndCo-Fase-Beta-3b47ccd6b6248027a614f90f9dd2be91" },
      { category: "Notion", subcategory: "Firma Electronica", title: "Guía de estado de firma electrónica.", description: "Guía de los diferentes estados de la firma electrónica para revisar los errores en con cliente.", url: "https://app.notion.com/p/haulmer/Gu-a-de-estados-de-Firma-Electr-nica-3cf7ccd6b62480749dd5fe3482bf541b" },
      { category: "Notion", subcategory: "Firma Electronica", title: "Cómo reemplazar firma vencida", description: "Guía del paso a paso de cómo reemplazar la firma vencida.", url: "https://app.notion.com/p/haulmer/Top-Tipificados-C-mo-reemplazar-firma-vencida-3487ccd6b62480d9ba84e63ee50b2f68" },
      { category: "Notion", subcategory: "Firma Electronica", title: "Escalamientos E-cert", description: "Del paso a paso de cómo generar un escalamiento a E-Cert", url: "https://app.notion.com/p/haulmer/Escalaci-n-de-casos-E-cert-2e87ccd6b6248073a066f078b3d2a174" },
      { category: "Notion", subcategory: "Errores en POS", title: "Consolidado de errores POS", description: "Consolidado de errores en pos , Transaccional, Pago, DTE.", url: "https://app.notion.com/p/haulmer/Errores-de-dispositivos-POS-y-otros-HP-OF-3ac7ccd6b624809fadfdd329b8b9fb51" },
      { category: "Notion", subcategory: "Errores en POS", title: "Errores app pago", description: "Códigos de error de App Pago.", url: "https://app.notion.com/p/haulmer/Errores-Inicio-APP-Pagos-1a57ccd6b62480ec83bde2b4544ac3cf" },
      { category: "Notion", subcategory: "Errores en POS", title: "Error HP-45 app PAGO", description: "Guia Error HP-45 app PAGO", url: "https://app.notion.com/p/haulmer/Error-HP-45-app-PAGO-eae65bcd74ba4e789db86ae1af53153c" },
      { category: "Notion", subcategory: "Errores en POS", title: "Errores Transaccionales", description: "Codigos de error transaccionales", url: "https://app.notion.com/p/haulmer/Errores-Transaccionales-1a57ccd6b624803a8407debf75b4a8b6" },
      { category: "Notion", subcategory: "Errores en POS", title: "Key Corruptas", description: "Codigo de error Key Corruptas", url: "https://app.notion.com/p/haulmer/Key-Corruptas-9fcab151c85548fc994bb5e6b8ddc1ea" },
      { category: "Notion", subcategory: "Errores en POS", title: "Error HP-401", description: "Notion de ayuda con error HP-401", url: "https://app.notion.com/p/haulmer/Top-Tipificado-Pagos-Electr-nicos-Error-HP-401-1e47ccd6b624808fa4f9cf59af0a1dab" },
      { category: "Notion", subcategory: "Errores en POS", title: "Error en emisión documento electrónico.", description: "Listado de códigos de error de documento electrónico en pos", url: "https://app.notion.com/p/haulmer/Errores-Emision-de-Documentos-Electronicos-1a77ccd6b62480bcb546f37a3ad24542" },
      { category: "Notion", subcategory: "DESK", title: "Error Hp-MR-180 Desk", description: "Error HP-MR-180 en desk , por mas de 5 pagos pendiente en pos", url: "https://app.notion.com/p/haulmer/Error-HP-MR-180-en-Desk-39f7ccd6b6248022b378dfe71d1db4c5" },
      { category: "Notion", subcategory: "DESK", title: "Sincronizar Desk", description: "Sincronizar desk con pos de pago", url: "https://app.notion.com/p/haulmer/Sincronizaci-n-TUU-desk-con-APP-PAGO-1f37ccd6b62480f8a712cb7dd8d83bbb" },
      { category: "Notion", subcategory: "Consultas Abono", title: "Validación de cuenta de Abono", description: "Notion de ayuda para la gestión de validación de cuenta de abono.", url: "https://app.notion.com/p/haulmer/Top-Tipificado-Validaci-n-de-cuenta-de-abono-1e77ccd6b624806aa895d242c36e9844" },
      { category: "Notion", subcategory: "Consultas Abono", title: "Consulta por abono fecha de abono, depósito.", description: "Guía de paso a paso cómo gestionar e ingresar consulta por abono específicamente fecha de abono y depósito.", url: "https://app.notion.com/p/haulmer/Top-Tipificados-Consulta-por-abono-Fecha-pago-del-abono-dep-sito-3497ccd6b624806db792ced6a30c93d9" },
      { category: "Notion", subcategory: "Consultas Abono", title: "Consulta por abono monto.", description: "Guía de paso a paso de como gestionar consultas por abono monto.", url: "https://app.notion.com/p/haulmer/Top-Tipificados-Consulta-por-abono-Monto-3457ccd6b624803b865efdb7316dc153" },
      { category: "Notion", subcategory: "Consultas por transaccion", title: "Consulta por una transacción.", description: "Guia de paso a paso de cómo detectamos un caso correspondiente a una consulta por transacción y cómo se gestiona.", url: "https://app.notion.com/p/haulmer/Top-Tipificados-Consulta-por-una-transacci-n-3437ccd6b624802ab76ee3fd11b966a6" },
      { category: "Notion", subcategory: "Documentos Electronicos", title: "Cómo activar documentos electrónico", description: "Notion de ayuda en cómo activar los documentos electrónicos.", url: "https://app.notion.com/p/haulmer/Top-Tipificados-N-1-C-mo-activar-documentos-electr-nicos-1e47ccd6b62480328ac5da30135bb4bc" },
      { category: "Notion", subcategory: "Documentos Electronicos", title: "Bloqueo de timbre.", description: "Guía a paso a paso de la gestión por consulta de bloqueo de timbraje", url: "https://app.notion.com/p/haulmer/Top-Tipificados-Bloqueo-de-timbraje-3457ccd6b62480c49b69c9ae5258b30a" },
      { category: "Notion", subcategory: "Documentos Electronicos", title: "Error al definir modelo de emisión.", description: "Error al definir un modelo de emision paso a paso explicado.", url: "https://app.notion.com/p/haulmer/Error-al-definir-modelo-de-emisi-n-0860aaf6a8c54e2e9977031ea98aecfe" },
      { category: "Notion", subcategory: "Documentos Electronicos", title: "Anulación de folios vencidos.", description: "Manual de cómo realizar la anulación de folios en WorkSpace.", url: "https://app.notion.com/p/haulmer/Anulaci-n-de-folios-vencidos-b5a3c8ad0e164442ad1197691bf0c9f7" },
      { category: "Notion", subcategory: "Documentos Electronicos", title: "Problemas para visualizar registro de compra y venta.", description: "Manual para sincronizar registro compra y venta cuando existe inconveniente la visualización.", url: "https://app.notion.com/p/haulmer/Problemas-al-visualizar-registro-de-compra-o-venta-b85657d0ee92435d931585c1bbd4a6cd" },
      { category: "Notion", subcategory: "Integracion", title: "Guía de integración.", description: "Guía completa de integración y conceptos claves.", url: "https://app.notion.com/p/haulmer/Gu-a-de-Integraciones-para-SAC-3c87ccd6b6248001b34ac4627982282e" },
      { category: "Notion", subcategory: "Paneles", title: "Panel Keycloak", description: "Guía de paso a paso de panel Keycloak", url: "https://app.notion.com/p/haulmer/Gu-a-de-uso-panel-Keycloak-32c7ccd6b624806eb4a8c929e54cb80b" },
      { category: "Notion", subcategory: "Paneles", title: "Uso panel KDH.", description: "Guía del uso del panel KDH para bloqueos softdelete y más en dispositivos pos", url: "https://app.notion.com/p/haulmer/Gu-a-de-uso-panel-KDH-3ce7ccd6b62480c4a527c99b32478665" },
      { category: "Notion", subcategory: "Paneles", title: "Uso del panel Admin Swipe N1", description: "Guía de paso a paso de cómo utilizar el panel de pago swipe.", url: "https://app.notion.com/p/haulmer/Uso-del-panel-admin-Swipe-nivel-1Uso-del-panel-admin-Swipe-N-uno-9c2ae748c98242e4ae0f52a09756e241" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Garantia a todo evento", description: "Guía de paso a paso de cuando corresponde garantía a tu evento.", url: "https://app.notion.com/p/haulmer/Garant-a-a-todo-evento-3f37ccd6b62480259b13fa250320f789" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Nuevas gestiones N1", description: "De paso a paso de las nuevas gestiones de N1.", url: "https://app.notion.com/p/haulmer/Gu-a-Nuevas-Gestiones-N1-3227ccd6b62480b28811ee86d5d73846" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Flujo economía circular.", description: "Guía paso a paso para el flujo de economía circular.", url: "http://app.notion.com/p/haulmer/GUIA-Flujo-Economia-Circular-3507ccd6b624800a8521face23941a68" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Información general.", description: "Información general de los y sus principales canales.", url: "https://app.notion.com/p/haulmer/Informacion-General-Bajadas-3bc7ccd6b62480c9a364f63d47416430" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Guía de uso Teams - Sunmi", description: "Guía del paso a paso con errores por actualización de Rom y Error Attack.", url: "https://app.notion.com/p/haulmer/Gu-a-de-uso-Teams-Sunmi-3ce7ccd6b62480f9bf35e38cb4e7fc8d" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Guía de cambio de correo.", description: "Guía paso a paso de cambio de correo", url: "https://app.notion.com/p/haulmer/Gu-a-de-Cambios-de-Correo-3827ccd6b62480bf9869c70b7687d811" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Procedimiento de revision de derivación tue reserva.", description: "Guía con el paso a paso para poder generar una correcta revisión y derivación de casos de tuu reserva.", url: "https://app.notion.com/p/haulmer/TUU-Reserva-Procedimiento-revision-405d32b3c5bc448295671ec019343e07" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Sernac, procedimiento y revisión", description: "Guía de paso a paso de cómo revisar casos Sernac, solamente agente es autorizado.", url: "https://app.notion.com/p/haulmer/Sernac-Procedimiento-revisi-n-26c7ccd6b6248007a8cefeb7904472b0" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Obtención de enlace de autoservicio.", description: "Este link podrán emitir su boleta o generar su factura por un servicio contratado.", url: "https://app.notion.com/p/haulmer/Obtenci-n-de-enlace-de-autoservicio-8d988334d8b443cc9a43c534fba7967d" },
      { category: "Notion", subcategory: "Otros Procedimientos", title: "Activación App PAGO", description: "Guia de paso a paso de activación de App PAGO", url: "https://app.notion.com/p/haulmer/Problema-de-activaci-n-PAGO-4aae53379bd84281a53146264558060f" }
    ];

    let currentTab = "search";

    // Función para normalizar texto (Elimina tildes, convierte a minúsculas)
    function normalizeStr(str) {
      if (!str) return "";
      return str.toLowerCase().normalize("NFD").replace(/[\u0300-\u036f]/g, "");
    }

    // Inicializar los contadores
    function initCounts() {
      const categories = ["RRHH", "Plataformas", "Formularios", "Herramientas", "Notion"];
      categories.forEach(cat => {
        const count = rawData.filter(item => item.category === cat).length;
        document.getElementById(`count-${cat}`).innerText = count;
      });
    }

    // Cambiar de Pestaña
    function switchTab(tabName) {
      currentTab = tabName;
      document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
      
      const activeIndex = ["search", "RRHH", "Plataformas", "Formularios", "Herramientas", "Notion"].indexOf(tabName);
      document.querySelectorAll('.tab-btn')[activeIndex].classList.add('active');

      handleSearch();
    }

    // Ejecutar Búsqueda y Renderizado
    function handleSearch() {
      const queryRaw = document.getElementById('searchInput').value.trim();
      const queryNorm = normalizeStr(queryRaw);
      const contentArea = document.getElementById('contentArea');
      const stats = document.getElementById('searchStats');

      // Filtrar datos según la pestaña y la búsqueda
      let filtered = rawData.filter(item => {
        const matchCategory = currentTab === "search" || item.category === currentTab;
        
        if (!queryNorm) return matchCategory;

        const titleNorm = normalizeStr(item.title);
        const descNorm = normalizeStr(item.description);
        const subNorm = normalizeStr(item.subcategory);
        const catNorm = normalizeStr(item.category);

        const matchQuery = titleNorm.includes(queryNorm) || 
                           descNorm.includes(queryNorm) || 
                           subNorm.includes(queryNorm) || 
                           catNorm.includes(queryNorm);

        return matchCategory && matchQuery;
      });

      // Actualizar Texto de Estado
      if (queryRaw) {
        stats.innerText = `Resultados encontrados: ${filtered.length}`;
      } else {
        stats.innerText = currentTab === "search" 
          ? `Mostrando ${filtered.length} recursos disponibles` 
          : `Sección ${currentTab}: ${filtered.length} items`;
      }

      if (filtered.length === 0) {
        contentArea.innerHTML = `
          <div class="no-results">
            <h3>No se encontraron coincidencias</h3>
            <p>Intenta buscando con palabras más generales o revisa si la opción pertenece a otra categoría.</p>
          </div>
        `;
        return;
      }

      // Renderizar por Subcategorías o Tarjetas Directas
      if (currentTab !== "search" && (currentTab === "Herramientas" || currentTab === "Notion") && !queryNorm) {
        // Agrupar por subcategoría en pestañas completas
        const grouped = {};
        filtered.forEach(item => {
          const sub = item.subcategory || "General";
          if (!grouped[sub]) grouped[sub] = [];
          grouped[sub].push(item);
        });

        let html = "";
        for (let sub in grouped) {
          html += `
            <div class="subcat-section">
              <h2 class="subcat-title">📌 ${sub}</h2>
              <div class="cards-grid">
                ${grouped[sub].map(item => renderCard(item, queryNorm)).join('')}
              </div>
            </div>
          `;
        }
        contentArea.innerHTML = html;
      } else {
        // Vista en Grid estándar para Búsqueda y Pestañas Simples
        contentArea.innerHTML = `
          <div class="cards-grid">
            ${filtered.map(item => renderCard(item, queryNorm)).join('')}
          </div>
        `;
      }
    }

    // Renderizar tarjeta individual con la etiqueta <a> activa
    function renderCard(item, queryNorm) {
      const badgeClass = `badge-${item.category.toLowerCase()}`;
      
      let displayTitle = item.title;
      let displayDesc = item.description || "Sin descripción adicional.";
      let itemUrl = item.url || "#";

      return `
        <a href="${itemUrl}" target="_blank" class="card">
          <div>
            <div class="card-header">
              <span class="card-title">${displayTitle}</span>
              <span class="badge ${badgeClass}">${item.category}</span>
            </div>
            ${item.subcategory ? `<span class="card-subcategory">📁 ${item.subcategory}</span>` : ''}
            <p class="card-desc">${displayDesc}</p>
          </div>
        </a>
      `;
    }

    // Inicializar
    window.onload = () => {
      initCounts();
      handleSearch();
    };
  </script>
</body>
</html>
