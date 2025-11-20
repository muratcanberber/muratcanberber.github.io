---
layout: default
title: CodeWithMCB – Industrial IoT & Software
---

<style>
  /* THEME TOKENS – LIGHT DEFAULT */
  :root {
    --mcb-page-bg: #f3f4f6;
    --mcb-bg: #f9fafb;
    --mcb-bg-soft: rgba(249, 250, 251, 0.96);
    --mcb-card: rgba(255, 255, 255, 0.96);
    --mcb-border: rgba(148, 163, 184, 0.35);
    --mcb-accent: #16a34a;
    --mcb-accent-soft: rgba(22, 163, 74, 0.08);
    --mcb-text: #020617;
    --mcb-text-soft: #4b5563;
    --mcb-radius-lg: 20px;
    --mcb-radius-xl: 28px;
    --mcb-shadow-soft: 0 20px 55px rgba(15, 23, 42, 0.18);
    --mcb-transition: 200ms ease-out;
  }

  /* DARK PREFERENCES (EĞER TEMA ATANMAMIŞSA) */
  @media (prefers-color-scheme: dark) {
    :root {
      --mcb-page-bg: #020617;
      --mcb-bg: #020617;
      --mcb-bg-soft: rgba(15, 23, 42, 0.9);
      --mcb-card: rgba(15, 23, 42, 0.96);
      --mcb-border: rgba(148, 163, 184, 0.25);
      --mcb-accent: #22c55e;
      --mcb-accent-soft: rgba(34, 197, 94, 0.12);
      --mcb-text: #e5e7eb;
      --mcb-text-soft: #9ca3af;
      --mcb-shadow-soft: 0 24px 70px rgba(15, 23, 42, 0.8);
    }
  }

  /* EXPLICIT OVERRIDE: data-theme="light|dark" */
  :root[data-theme="light"] {
    --mcb-page-bg: #f3f4f6;
    --mcb-bg: #f9fafb;
    --mcb-bg-soft: rgba(249, 250, 251, 0.96);
    --mcb-card: rgba(255, 255, 255, 0.96);
    --mcb-border: rgba(148, 163, 184, 0.35);
    --mcb-accent: #16a34a;
    --mcb-accent-soft: rgba(22, 163, 74, 0.08);
    --mcb-text: #020617;
    --mcb-text-soft: #4b5563;
    --mcb-shadow-soft: 0 20px 55px rgba(15, 23, 42, 0.18);
  }

  :root[data-theme="dark"] {
    --mcb-page-bg: #020617;
    --mcb-bg: #020617;
    --mcb-bg-soft: rgba(15, 23, 42, 0.9);
    --mcb-card: rgba(15, 23, 42, 0.96);
    --mcb-border: rgba(148, 163, 184, 0.25);
    --mcb-accent: #22c55e;
    --mcb-accent-soft: rgba(34, 197, 94, 0.12);
    --mcb-text: #e5e7eb;
    --mcb-text-soft: #9ca3af;
    --mcb-shadow-soft: 0 24px 70px rgba(15, 23, 42, 0.8);
  }

  /* GLOBAL OVERRIDES (white bar sorununu çözer) */
  html,
  body {
    margin: 0;
    padding: 0;
    min-height: 100%;
    background-color: var(--mcb-page-bg);
    color: var(--mcb-text);
    font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
      sans-serif;
  }

  .site-header,
  .site-footer,
  .page-content {
    background: transparent !important;
    border: 0 !important;
  }

  .page-content {
    padding-top: 0 !important;
  }

  .site-title,
  a.site-title {
    color: var(--mcb-text) !important;
  }

  .skip-link {
    background: var(--mcb-bg);
    color: var(--mcb-text);
  }

  a {
    color: var(--mcb-accent);
  }

  /* THEME TOGGLE (sağ üst) */
  .mcb-theme-toggle {
    position: fixed;
    top: 10px;
    right: 16px;
    z-index: 999;
    border-radius: 999px;
    border: 1px solid var(--mcb-border);
    background: rgba(15, 23, 42, 0.04);
    padding: 4px 8px;
    display: inline-flex;
    align-items: center;
    gap: 4px;
    cursor: pointer;
    font-size: 0.8rem;
    backdrop-filter: blur(16px);
  }

  :root[data-theme="dark"] .mcb-theme-toggle {
    background: rgba(15, 23, 42, 0.92);
  }

  .mcb-theme-toggle-label {
    font-size: 0.7rem;
    color: var(--mcb-text-soft);
  }

  .mcb-theme-toggle-icon {
    font-size: 1rem;
    transition: opacity var(--mcb-transition), transform var(--mcb-transition);
  }

  .mcb-theme-toggle[data-theme="light"] .mcb-theme-toggle-icon.sun {
    opacity: 1;
    transform: translateY(0);
  }

  .mcb-theme-toggle[data-theme="light"] .mcb-theme-toggle-icon.moon {
    opacity: 0;
    transform: translateY(4px);
  }

  .mcb-theme-toggle[data-theme="dark"] .mcb-theme-toggle-icon.sun {
    opacity: 0;
    transform: translateY(-4px);
  }

  .mcb-theme-toggle[data-theme="dark"] .mcb-theme-toggle-icon.moon {
    opacity: 1;
    transform: translateY(0);
  }

  /* PAGE LAYOUT */
  .mcb-page {
    min-height: 100vh;
    padding: 40px 16px 28px;
    background:
      radial-gradient(circle at top left, rgba(34, 197, 94, 0.14), transparent 55%),
      radial-gradient(circle at bottom right, rgba(59, 130, 246, 0.14), transparent 55%),
      var(--mcb-bg);
    color: var(--mcb-text);
    display: flex;
    justify-content: center;
    box-sizing: border-box;
  }

  :root[data-theme="light"] .mcb-page {
    background:
      radial-gradient(circle at top left, rgba(34, 197, 94, 0.18), transparent 55%),
      radial-gradient(circle at bottom right, rgba(59, 130, 246, 0.14), transparent 55%),
      var(--mcb-page-bg);
  }

  .mcb-container {
    width: 100%;
    max-width: 1100px;
    margin: 0 auto;
  }

  /* HERO */
  .mcb-hero {
    display: grid;
    grid-template-columns: minmax(0, 1.6fr) minmax(0, 1.1fr);
    gap: 32px;
    align-items: center;
    margin-bottom: 40px;
  }

  .mcb-pill {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 4px 10px;
    border-radius: 999px;
    background: rgba(15, 23, 42, 0.04);
    border: 1px solid var(--mcb-border);
    font-size: 0.75rem;
    color: var(--mcb-text-soft);
    backdrop-filter: blur(16px);
  }

  :root[data-theme="dark"] .mcb-pill {
    background: rgba(15, 23, 42, 0.9);
  }

  .mcb-name {
    font-size: clamp(2.4rem, 4vw, 2.9rem);
    letter-spacing: 0.06em;
    text-transform: uppercase;
    margin: 14px 0 4px;
  }

  .mcb-role {
    font-size: 1rem;
    font-weight: 500;
    color: var(--mcb-text-soft);
    margin: 0 0 12px;
  }

  .mcb-hero-lead {
    font-size: 0.98rem;
    color: var(--mcb-text-soft);
    max-width: 560px;
    margin-bottom: 18px;
  }

  .mcb-hero-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    align-items: center;
    margin-bottom: 4px;
  }

  .mcb-hero-meta {
    font-size: 0.78rem;
    color: var(--mcb-text-soft);
    margin-top: 4px;
  }

  .mcb-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 10px 18px;
    border-radius: 999px;
    font-size: 0.9rem;
    font-weight: 500;
    text-decoration: none;
    border: 1px solid transparent;
    cursor: pointer;
    white-space: nowrap;
    transition:
      transform var(--mcb-transition),
      box-shadow var(--mcb-transition),
      background var(--mcb-transition),
      border-color var(--mcb-transition),
      color var(--mcb-transition);
  }

  .mcb-btn-primary {
    background: linear-gradient(135deg, #22c55e, #4ade80);
    color: #022c22;
    box-shadow: 0 18px 40px rgba(34, 197, 94, 0.35);
  }

  .mcb-btn-primary:hover {
    transform: translateY(-1px);
    box-shadow: 0 22px 60px rgba(34, 197, 94, 0.45);
  }

  .mcb-btn-secondary {
    background: rgba(15, 23, 42, 0.04);
    border-color: var(--mcb-border);
    color: var(--mcb-text-soft);
  }

  :root[data-theme="dark"] .mcb-btn-secondary {
    background: rgba(15, 23, 42, 0.92);
  }

  .mcb-btn-secondary:hover {
    border-color: rgba(148, 163, 184, 0.7);
  }

  .mcb-btn-ghost {
    background: transparent;
    border-color: rgba(148, 163, 184, 0.4);
    color: var(--mcb-text-soft);
  }

  .mcb-btn-ghost:hover {
    background: rgba(15, 23, 42, 0.06);
  }

  .mcb-hero-card {
    background: var(--mcb-bg-soft);
    border-radius: var(--mcb-radius-xl);
    border: 1px solid var(--mcb-border);
    box-shadow: var(--mcb-shadow-soft);
    padding: 18px 18px;
    backdrop-filter: blur(18px);
  }

  .mcb-hero-card-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 8px;
  }

  .mcb-hero-card-title {
    font-size: 0.8rem;
    font-weight: 500;
    color: var(--mcb-text-soft);
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .mcb-status-dot {
    width: 7px;
    height: 7px;
    border-radius: 999px;
    background: #22c55e;
    box-shadow: 0 0 10px rgba(34, 197, 94, 0.8);
  }

  .mcb-hero-card-body h3 {
    font-size: 0.95rem;
    margin: 4px 0 4px;
  }

  .mcb-hero-card-body p {
    font-size: 0.78rem;
    color: var(--mcb-text-soft);
    margin: 0 0 8px;
  }

  .mcb-badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .mcb-pill-soft {
    font-size: 0.7rem;
    padding: 4px 8px;
    border-radius: 999px;
    background: rgba(15, 23, 42, 0.03);
    border: 1px solid rgba(148, 163, 184, 0.4);
    color: var(--mcb-text-soft);
  }

  :root[data-theme="dark"] .mcb-pill-soft {
    background: rgba(15, 23, 42, 0.92);
  }

  .mcb-pill-soft--accent {
    border-color: rgba(34, 197, 94, 0.7);
    background: var(--mcb-accent-soft);
  }

  .mcb-section {
    margin-top: 32px;
  }

  .mcb-section-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 10px;
    margin-bottom: 18px;
  }

  .mcb-section-header h2 {
    font-size: 1.2rem;
    margin: 0;
  }

  .mcb-section-header p {
    font-size: 0.85rem;
    color: var(--mcb-text-soft);
    margin: 0;
    max-width: 420px;
  }

  .mcb-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 18px;
  }

  .mcb-card,
  .mcb-project-card {
    background: var(--mcb-card);
    border-radius: var(--mcb-radius-lg);
    border: 1px solid var(--mcb-border);
    padding: 16px 16px 14px;
    box-shadow: var(--mcb-shadow-soft);
    position: relative;
    overflow: hidden;
  }

  .mcb-card::before {
    content: "";
    position: absolute;
    inset: 0;
    opacity: 0;
    background: radial-gradient(circle at top left, rgba(34, 197, 94, 0.16), transparent 60%);
    transition: opacity var(--mcb-transition);
    pointer-events: none;
  }

  .mcb-card:hover::before {
    opacity: 1;
  }

  .mcb-card-icon {
    width: 28px;
    height: 28px;
    border-radius: 999px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background: rgba(34, 197, 94, 0.1);
    margin-bottom: 6px;
    font-size: 1.15rem;
  }

  .mcb-card h3 {
    font-size: 1rem;
    margin: 0 0 6px;
  }

  .mcb-card ul {
    list-style: none;
    padding: 0;
    margin: 0;
    font-size: 0.8rem;
    color: var(--mcb-text-soft);
  }

  .mcb-card ul li {
    margin-bottom: 4px;
  }

  .mcb-card ul li strong {
    color: var(--mcb-text);
  }

  .mcb-projects {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 18px;
  }

  .mcb-project-card {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .mcb-project-title-row {
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .mcb-project-card h3 {
    font-size: 0.95rem;
    margin: 0;
  }

  .mcb-project-card p {
    font-size: 0.8rem;
    color: var(--mcb-text-soft);
    margin: 2px 0 4px;
  }

  .mcb-tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 2px;
  }

  .mcb-tag {
    font-size: 0.7rem;
    padding: 3px 7px;
    border-radius: 999px;
    border: 1px solid rgba(148, 163, 184, 0.4);
    color: var(--mcb-text-soft);
  }

  .mcb-tag--accent {
    border-color: rgba(34, 197, 94, 0.7);
    background: var(--mcb-accent-soft);
  }

  .mcb-split {
    display: grid;
    grid-template-columns: minmax(0, 1.4fr) minmax(0, 1fr);
    gap: 18px;
    margin-top: 8px;
  }

  .mcb-highlight-card {
    background: radial-gradient(circle at top left, rgba(34, 197, 94, 0.16), rgba(15, 23, 42, 0.96));
    border-radius: var(--mcb-radius-lg);
    border: 1px solid var(--mcb-border);
    padding: 14px 16px;
    box-shadow: var(--mcb-shadow-soft);
    font-size: 0.8rem;
  }

  :root[data-theme="light"] .mcb-highlight-card {
    background: radial-gradient(circle at top left, rgba(34, 197, 94, 0.14), rgba(255, 255, 255, 0.98));
  }

  .mcb-highlight-card h3 {
    font-size: 0.9rem;
    margin: 0 0 4px;
  }

  .mcb-highlight-metrics {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 8px;
  }

  .mcb-metric {
    padding: 6px 8px;
    border-radius: 12px;
    background: rgba(15, 23, 42, 0.03);
    border: 1px solid rgba(148, 163, 184, 0.35);
  }

  :root[data-theme="dark"] .mcb-metric {
    background: rgba(15, 23, 42, 0.9);
  }

  .mcb-metric-label {
    font-size: 0.7rem;
    color: var(--mcb-text-soft);
  }

  .mcb-metric-value {
    font-size: 0.85rem;
    font-weight: 600;
  }

  /* YOUTUBE – BIG CAROUSEL */
  .mcb-youtube {
    margin-top: 6px;
  }

  .mcb-carousel {
    background: var(--mcb-card);
    border-radius: var(--mcb-radius-xl);
    border: 1px solid var(--mcb-border);
    box-shadow: var(--mcb-shadow-soft);
    padding: 16px;
  }

  .mcb-slide {
    display: none;
    grid-template-columns: minmax(0, 2fr) minmax(0, 1.4fr);
    gap: 18px;
    align-items: stretch;
  }

  .mcb-slide-active {
    display: grid;
  }

  .mcb-video-frame {
    position: relative;
    padding-top: 56.25%;
    border-radius: 18px;
    overflow: hidden;
    background: #000;
  }

  .mcb-video-frame iframe {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border: 0;
  }

  .mcb-slide-meta {
    font-size: 0.82rem;
    color: var(--mcb-text-soft);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .mcb-slide-meta h3 {
    font-size: 0.95rem;
    margin: 0 0 4px;
    color: var(--mcb-text);
  }

  .mcb-slide-meta p {
    margin: 0 0 10px;
  }

  .mcb-carousel-controls {
    margin-top: 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 6px;
    font-size: 0.78rem;
    color: var(--mcb-text-soft);
  }

  .mcb-carousel-arrow {
    border-radius: 999px;
    border: 1px solid var(--mcb-border);
    background: rgba(15, 23, 42, 0.04);
    padding: 5px 10px;
    cursor: pointer;
    font-size: 0.78rem;
  }

  :root[data-theme="dark"] .mcb-carousel-arrow {
    background: rgba(15, 23, 42, 0.9);
  }

  .mcb-carousel-arrow:hover {
    border-color: rgba(148, 163, 184, 0.7);
  }

  .mcb-dots {
    display: flex;
    gap: 6px;
    align-items: center;
    justify-content: center;
    flex: 1;
  }

  .mcb-dot {
    width: 8px;
    height: 8px;
    border-radius: 999px;
    border: 1px solid rgba(148, 163, 184, 0.5);
    background: transparent;
    padding: 0;
    cursor: pointer;
  }

  .mcb-dot.active {
    background: var(--mcb-accent);
    border-color: var(--mcb-accent);
  }

  /* CONTACT */
  .mcb-contact {
    margin-top: 32px;
    text-align: center;
    padding: 20px 18px 10px;
    background: rgba(15, 23, 42, 0.04);
    border-radius: var(--mcb-radius-xl);
    border: 1px solid var(--mcb-border);
    box-shadow: var(--mcb-shadow-soft);
  }

  :root[data-theme="dark"] .mcb-contact {
    background: rgba(15, 23, 42, 0.94);
  }

  .mcb-contact p {
    font-size: 0.86rem;
    color: var(--mcb-text-soft);
    max-width: 520px;
    margin: 6px auto 16px;
  }

  .mcb-contact-actions {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 6px;
  }

  .mcb-footer {
    text-align: center;
    font-size: 0.75rem;
    color: #6b7280;
    margin-top: 10px;
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    .mcb-hero {
      grid-template-columns: minmax(0, 1fr);
    }

    .mcb-hero-card {
      order: -1;
    }

    .mcb-grid,
    .mcb-projects {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .mcb-slide {
      grid-template-columns: minmax(0, 1fr);
    }
  }

  @media (max-width: 640px) {
    .mcb-page {
      padding-top: 32px;
    }

    .mcb-section {
      margin-top: 24px;
    }

    .mcb-section-header {
      flex-direction: column;
      align-items: flex-start;
    }

    .mcb-grid,
    .mcb-projects {
      grid-template-columns: minmax(0, 1fr);
    }

    .mcb-split {
      grid-template-columns: minmax(0, 1fr);
    }

    .mcb-contact {
      padding: 18px 14px 10px;
    }
  }
</style>

<button class="mcb-theme-toggle" type="button" aria-label="Tema değiştir">
  <span class="mcb-theme-toggle-label">Tema</span>
  <span class="mcb-theme-toggle-icon sun">☀</span>
  <span class="mcb-theme-toggle-icon moon">🌙</span>
</button>

<div class="mcb-page">
  <div class="mcb-container">
    <!-- HERO -->
    <section class="mcb-hero">
      <div>
        <div class="mcb-pill">
          <span>🧠</span> Industrial IoT · Yazılım · Otomasyon
        </div>
        <h1 class="mcb-name">Murat Can BERBER</h1>
        <p class="mcb-role">Industrial IoT &amp; Software Engineer</p>
        <p class="mcb-hero-lead">
          Üretim hatlarından enerji izlemeye kadar; gerçek zamanlı veri, sağlam yazılım
          mimarisi ve güvenilir altyapı ile
          <strong>ölçeklenebilir IIoT çözümleri</strong> tasarlıyorum.
        </p>

        <div class="mcb-hero-actions">
          <a href="https://www.youtube.com/@CodeWithMCB"
             class="mcb-btn mcb-btn-primary"
             target="_blank" rel="noopener">
            ▶ YouTube – CodeWithMCB
          </a>
          <a href="https://www.linkedin.com/in/"
             class="mcb-btn mcb-btn-secondary"
             target="_blank" rel="noopener">
            in LinkedIn Profilim
          </a>
        </div>
        <div class="mcb-hero-meta">
          +10 yıl IIoT &amp; PTC ekosistemi · ThingWorx · Kepware · PostgreSQL / TimescaleDB
        </div>
      </div>

      <aside class="mcb-hero-card">
        <div class="mcb-hero-card-header">
          <div class="mcb-hero-card-title">
            <span class="mcb-status-dot"></span>
            Şu an odaklandığım başlıklar
          </div>
          <span style="font-size: 0.72rem; color: var(--mcb-text-soft);">
            2025 roadmap
          </span>
        </div>
        <div class="mcb-hero-card-body">
          <h3>Smart factory, veri ve otomasyon</h3>
          <p>
            Endüstriyel veriyi; <strong>ThingWorx</strong>, <strong>Kepware</strong>,
            <strong>PostgreSQL/TimescaleDB</strong> ve modern web teknolojileri
            ile <em>işe yarar</em> dashboardlara dönüştürüyorum.
          </p>
          <div class="mcb-badge-row">
            <span class="mcb-pill-soft mcb-pill-soft--accent">Gerçek zamanlı izleme</span>
            <span class="mcb-pill-soft">Enerji &amp; üretim verisi</span>
            <span class="mcb-pill-soft">Endüstriyel entegrasyon</span>
          </div>
        </div>
      </aside>
    </section>

    <!-- UZMANLIK ALANLARI -->
    <section class="mcb-section">
      <div class="mcb-section-header">
        <h2>Uzmanlık Alanlarım</h2>
        <p>
          Saha verisinden buluta; <strong>IoT platformları</strong>, <strong>backend geliştirme</strong>
          ve <strong>veri mühendisliği</strong> ekseninde uçtan uca çözümler tasarlıyorum.
        </p>
      </div>

      <div class="mcb-grid">
        <article class="mcb-card">
          <div class="mcb-card-icon">🏭</div>
          <h3>Industrial IoT &amp; Otomasyon</h3>
          <ul>
            <li><strong>ThingWorx</strong> uygulama geliştirme</li>
            <li>Kepware ile saha entegrasyonları</li>
            <li>Gerçek zamanlı üretim &amp; enerji izleme</li>
            <li>Alarm, event &amp; condition monitoring</li>
          </ul>
        </article>

        <article class="mcb-card">
          <div class="mcb-card-icon">💻</div>
          <h3>Yazılım Mimarisi &amp; Backend</h3>
          <ul>
            <li><strong>Python</strong> &amp; modern web stack</li>
            <li>REST API &amp; entegrasyon katmanları</li>
            <li>Mikroservis ve container tabanlı yapılar</li>
            <li>Endüstriyel sistemler için sağlam backend</li>
          </ul>
        </article>

        <article class="mcb-card">
          <div class="mcb-card-icon">🗄️</div>
          <h3>Veri &amp; Database Mühendisliği</h3>
          <ul>
            <li><strong>PostgreSQL / TimescaleDB</strong> tasarımı</li>
            <li>Zaman serisi veri modelleme</li>
            <li>Performans &amp; partitioning optimizasyonu</li>
            <li>High-availability &amp; replikasyon</li>
          </ul>
        </article>
      </div>
    </section>

    <!-- YOUTUBE – BÜYÜK BÖLÜM -->
    <section class="mcb-section">
      <div class="mcb-section-header">
        <h2>YouTube – CodeWithMCB</h2>
        <p>
          Gerçek projelerden beslenen, IIoT, veri ve modern geliştirici araçları odaklı
          Türkçe içerikler. Öne çıkan birkaç videom:
        </p>
      </div>

      <div class="mcb-youtube">
        <div class="mcb-carousel" data-active="0">
          <div class="mcb-slide mcb-slide-active" data-index="0">
            <div class="mcb-video-frame">
              <iframe
                src="https://www.youtube.com/embed/gUchx_a3V3Q"
                title="PostgreSQL Partitioning"
                loading="lazy"
                allowfullscreen
              ></iframe>
            </div>
            <div class="mcb-slide-meta">
              <div>
                <h3>PostgreSQL Partitioning – Gerçek Dünya Kullanımı</h3>
                <p>
                  Büyük veri setleriyle çalışan sistemler için partitioning stratejileri,
                  performans karşılaştırmaları ve TimescaleDB bağlantısı.
                </p>
              </div>
              <div class="mcb-tag-row">
                <span class="mcb-tag mcb-tag--accent">PostgreSQL</span>
                <span class="mcb-tag">TimescaleDB</span>
                <span class="mcb-tag">Performans</span>
              </div>
            </div>
          </div>

          <div class="mcb-slide" data-index="1">
            <div class="mcb-video-frame">
              <iframe
                src="https://www.youtube.com/embed/fgWlqZIBotY"
                title="Node-RED CRUD & HTTP"
                loading="lazy"
                allowfullscreen
              ></iframe>
            </div>
            <div class="mcb-slide-meta">
              <div>
                <h3>Node-RED ile HTTP &amp; CRUD Uygulaması</h3>
                <p>
                  Endüstriyel veri ve Postgres’i birleştiren, Node-RED tabanlı pratik
                  backend akışı. Low-code ile hızlı prototip ve entegrasyon örnekleri.
                </p>
              </div>
              <div class="mcb-tag-row">
                <span class="mcb-tag mcb-tag--accent">Node-RED</span>
                <span class="mcb-tag">PostgreSQL</span>
                <span class="mcb-tag">Low-Code</span>
              </div>
            </div>
          </div>

          <div class="mcb-slide" data-index="2">
            <div class="mcb-video-frame">
              <iframe
                src="https://www.youtube.com/embed/Dzo8hJpKqxw"
                title="20 Dakikada Docker"
                loading="lazy"
                allowfullscreen
              ></iframe>
            </div>
            <div class="mcb-slide-meta">
              <div>
                <h3>20 Dakikada Docker – Temelden Pratiğe</h3>
                <p>
                  Geliştiriciler ve DevOps tarafı için Docker’a hızlı giriş:
                  temel kavramlar, CLI kullanımı ve pratik konteyner senaryoları.
                </p>
              </div>
              <div class="mcb-tag-row">
                <span class="mcb-tag mcb-tag--accent">Docker</span>
                <span class="mcb-tag">DevOps</span>
                <span class="mcb-tag">Konteyner</span>
              </div>
            </div>
          </div>
        </div>

        <div class="mcb-carousel-controls">
          <button class="mcb-carousel-arrow" data-dir="prev">← Önceki</button>
          <div class="mcb-dots">
            <button class="mcb-dot active" data-index="0"></button>
            <button class="mcb-dot" data-index="1"></button>
            <button class="mcb-dot" data-index="2"></button>
          </div>
          <button class="mcb-carousel-arrow" data-dir="next">Sonraki →</button>
        </div>
      </div>
    </section>

    <!-- PROJELER -->
    <section class="mcb-section">
      <div class="mcb-section-header">
        <h2>Seçili Projeler</h2>
        <p>
          Ağırlıklı olarak üretim, enerji ve endüstriyel veri odaklı projelerde; hem
          sahadaki PLC’lere hem de buluttaki veri katmanına dokunan çözümler geliştiriyorum.
        </p>
      </div>

      <div class="mcb-projects">
        <article class="mcb-project-card">
          <div class="mcb-project-title-row">
            <div class="mcb-card-icon">🔍</div>
            <h3>Smart Factory Monitoring</h3>
          </div>
          <p>
            Üretim hattı için <strong>gerçek zamanlı OEE &amp; duruş izleme</strong> sistemi.
            ThingWorx dashboardları, Kepware üzerinden PLC entegrasyonları ve alarm yönetimi.
          </p>
          <div class="mcb-tag-row">
            <span class="mcb-tag mcb-tag--accent">ThingWorx</span>
            <span class="mcb-tag">Kepware</span>
            <span class="mcb-tag">Gerçek zamanlı veri</span>
          </div>
        </article>

        <article class="mcb-project-card">
          <div class="mcb-project-title-row">
            <div class="mcb-card-icon">🔄</div>
            <h3>Endüstriyel Data Pipeline</h3>
          </div>
          <p>
            Yüksek hacimli sensör verisi için <strong>Python tabanlı ETL</strong> süreçleri,
            optimize edilmiş PostgreSQL şemaları ve zaman serisi analitiği.
          </p>
          <div class="mcb-tag-row">
            <span class="mcb-tag mcb-tag--accent">Python</span>
            <span class="mcb-tag">PostgreSQL</span>
            <span class="mcb-tag">TimescaleDB</span>
          </div>
        </article>

        <article class="mcb-project-card">
          <div class="mcb-project-title-row">
            <div class="mcb-card-icon">📊</div>
            <h3>IoT Analytics &amp; Dashboarding</h3>
          </div>
          <p>
            Üretim ve enerji verilerini görselleştiren <strong>özelleştirilmiş dashboardlar</strong>,
            uyarı sistemleri ve KPI raporlamaları. Operasyon ekipleri için sade ama güçlü arayüzler.
          </p>
          <div class="mcb-tag-row">
            <span class="mcb-tag mcb-tag--accent">Analytics</span>
            <span class="mcb-tag">Visualization</span>
            <span class="mcb-tag">Alerting</span>
          </div>
        </article>
      </div>
    </section>

    <!-- İÇERİK & TOPLULUK -->
    <section class="mcb-section">
      <div class="mcb-section-header">
        <h2>İçerik &amp; Topluluk</h2>
        <p>
          YouTube ve diğer kanallarda; endüstriyel IoT, veri mühendisliği ve modern geliştirici
          araçları üzerine pratik ve sahaya dönük içerikler üretiyorum.
        </p>
      </div>

      <div class="mcb-split">
        <div>
          <p style="font-size: 0.85rem; color: var(--mcb-text-soft); margin-bottom: 10px;">
            Amacım; <strong>“gerçek projelerde kullanılan”</strong> yaklaşımları, sade ama
            detaycı bir anlatımla paylaşmak. Teoride kalmayan, doğrudan işe uygulanabilir içerikler…
          </p>

          <div class="mcb-tag-row" style="margin-top: 6px;">
            <span class="mcb-tag">IIoT mimarileri</span>
            <span class="mcb-tag">PostgreSQL &amp; TimescaleDB</span>
            <span class="mcb-tag">Python &amp; otomasyon</span>
            <span class="mcb-tag">Observability &amp; monitoring</span>
          </div>

          <p style="font-size: 0.8rem; color: var(--mcb-text-soft); margin-top: 10px;">
            YouTube kanalım üzerinden yeni videoları takip edebilir veya LinkedIn üzerinden
            tartışmalara katılabilirsiniz.
          </p>

          <div style="margin-top: 8px; display: flex; flex-wrap: wrap; gap: 8px;">
            <a href="https://www.youtube.com/@CodeWithMCB"
               class="mcb-btn mcb-btn-secondary"
               target="_blank" rel="noopener">
              ▶ YouTube’da izle
            </a>
            <a href="https://www.linkedin.com/in/"
               class="mcb-btn mcb-btn-ghost"
               target="_blank" rel="noopener">
              in LinkedIn’de bağlantı kur
            </a>
          </div>
        </div>

        <aside class="mcb-highlight-card">
          <h3>Kimlerle konuşmalıyız?</h3>
          <p style="margin: 4px 0 6px;">
            Aşağıdaki başlıklardan biri gündemindeyse, konuşacak çok şeyimiz var:
          </p>

          <ul style="list-style: none; padding: 0; margin: 0; font-size: 0.78rem; color: var(--mcb-text-soft);">
            <li>• Mevcut üretim hattınızı gerçek zamanlı izlemek istiyorsanız,</li>
            <li>• Enerji tüketiminizi veri odaklı yönetmek istiyorsanız,</li>
            <li>• ThingWorx, Kepware veya PostgreSQL tarafında mimari desteğe ihtiyacınız varsa.</li>
          </ul>

          <div class="mcb-highlight-metrics">
            <div class="mcb-metric">
              <div class="mcb-metric-label">Saha deneyimi</div>
              <div class="mcb-metric-value">10+ yıl</div>
            </div>
            <div class="mcb-metric">
              <div class="mcb-metric-label">Odak</div>
              <div class="mcb-metric-value">IIoT &amp; veri</div>
            </div>
            <div class="mcb-metric">
              <div class="mcb-metric-label">Çalışma şekli</div>
              <div class="mcb-metric-value">Uzaktan &amp; hibrit</div>
            </div>
          </div>
        </aside>
      </div>
    </section>

    <!-- İLETİŞİM -->
    <section class="mcb-contact">
      <h2>Birlikte Çalışalım</h2>
      <p>
        Yeni bir IIoT projesi, mevcut bir ThingWorx / Kepware mimarisinin iyileştirilmesi
        veya veri katmanınızın yeniden tasarlanması gündeminizdeyse; kısaca projeyi özetleyin,
        beraber en verimli yolu çıkaralım.
      </p>
      <div class="mcb-contact-actions">
        <a href="mailto:contact@codewithmcb.com" class="mcb-btn mcb-btn-primary">
          ✉ E-posta ile ulaş
        </a>
        <a href="https://www.linkedin.com/in/" class="mcb-btn mcb-btn-secondary" target="_blank" rel="noopener">
          in LinkedIn üzerinden bağlantı kur
        </a>
      </div>
      <p style="font-size: 0.78rem; color: var(--mcb-text-soft); margin-top: 4px;">
        Tercihen: kısa proje özeti, mevcut durum ve hedefleriniz.
      </p>
    </section>

    <footer class="mcb-footer">
      © {{ site.time | date: "%Y" }} CodeWithMCB · Murat Can Berber
    </footer>
  </div>
</div>

<script>
  // Tema başlatma
  (function () {
    var STORAGE_KEY = "mcb-theme";
    var root = document.documentElement;
    var stored = localStorage.getItem(STORAGE_KEY);
    var prefersDark =
      window.matchMedia &&
      window.matchMedia("(prefers-color-scheme: dark)").matches;

    var initial = stored || (prefersDark ? "dark" : "light");
    root.setAttribute("data-theme", initial);

    var toggle = document.querySelector(".mcb-theme-toggle");
    if (!toggle) return;

    var updateToggle = function () {
      var theme = root.getAttribute("data-theme");
      toggle.setAttribute("data-theme", theme);
    };
    updateToggle();

    toggle.addEventListener("click", function () {
      var current = root.getAttribute("data-theme") === "dark" ? "dark" : "light";
      var next = current === "dark" ? "light" : "dark";
      root.setAttribute("data-theme", next);
      localStorage.setItem(STORAGE_KEY, next);
      updateToggle();
    });
  })();

  // YouTube carousel
  (function () {
    var carousel = document.querySelector(".mcb-carousel");
    if (!carousel) return;

    var slides = Array.prototype.slice.call(
      carousel.querySelectorAll(".mcb-slide")
    );
    if (!slides.length) return;

    var dots = Array.prototype.slice.call(
      document.querySelectorAll(".mcb-dot")
    );
    var index = 0;

    function show(i) {
      slides[index].classList.remove("mcb-slide-active");
      index = (i + slides.length) % slides.length;
      slides[index].classList.add("mcb-slide-active");
      dots.forEach(function (d, idx) {
        d.classList.toggle("active", idx === index);
      });
    }

    var prev = document.querySelector('.mcb-carousel-arrow[data-dir="prev"]');
    var next = document.querySelector('.mcb-carousel-arrow[data-dir="next"]');

    if (prev) {
      prev.addEventListener("click", function () {
        show(index - 1);
        resetTimer();
      });
    }
    if (next) {
      next.addEventListener("click", function () {
        show(index + 1);
        resetTimer();
      });
    }

    dots.forEach(function (dot, idx) {
      dot.addEventListener("click", function () {
        show(idx);
        resetTimer();
      });
    });

    var timer = setInterval(function () {
      show(index + 1);
    }, 12000);

    function resetTimer() {
      clearInterval(timer);
      timer = setInterval(function () {
        show(index + 1);
      }, 12000);
    }
  })();
</script>
