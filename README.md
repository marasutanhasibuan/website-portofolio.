<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Marasutan Hasibuan — Automotive Engineering</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Space+Grotesk:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080810;
    --bg2: #0f0f1a;
    --bg3: #14141f;
    --border: #1e1e30;
    --border2: #2a2a42;
    --accent: #6c5ce7;
    --accent2: #a29bfe;
    --accent3: #0984e3;
    --text: #e8e8f0;
    --text2: #9090b0;
    --text3: #55556a;
    --gear: #1a1a2e;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inter', sans-serif;
    font-size: 15px;
    line-height: 1.6;
    min-height: 100vh;
  }

  /* background decoration */
  body::before {
    content: '';
    position: fixed;
    top: -200px; left: 50%; transform: translateX(-50%);
    width: 800px; height: 600px;
    background: radial-gradient(ellipse, rgba(108,92,231,0.07) 0%, transparent 65%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 720px;
    margin: 0 auto;
    padding: 3rem 1.5rem 5rem;
    position: relative; z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 3.5rem 2rem 2.5rem;
    background: var(--bg2);
    border: 0.5px solid var(--border2);
    border-radius: 20px;
    margin-bottom: 2rem;
    position: relative;
    overflow: hidden;
  }

  /* gear decoration */
  .hero::after {
    content: '';
    position: absolute;
    bottom: -60px; right: -60px;
    width: 180px; height: 180px;
    border: 18px solid var(--gear);
    border-radius: 50%;
    opacity: 0.5;
  }

  .avatar {
    width: 100px; height: 100px;
    border-radius: 50%;
    background: linear-gradient(135deg, #6c5ce7, #a29bfe, #0984e3);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Space Grotesk', sans-serif;
    font-size: 32px; font-weight: 600;
    color: #fff;
    margin-bottom: 1.25rem;
    box-shadow: 0 0 0 4px rgba(108,92,231,0.15);
  }

  .hero h1 {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 28px;
    font-weight: 600;
    color: #f0f0ff;
    letter-spacing: -0.02em;
    margin-bottom: 6px;
  }

  .tagline {
    font-size: 13px;
    color: var(--accent2);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    font-weight: 500;
    margin-bottom: 1rem;
  }

  .bio {
    font-size: 14px;
    color: var(--text2);
    max-width: 380px;
    line-height: 1.75;
    margin-bottom: 1.25rem;
  }

  .meta {
    display: flex;
    gap: 1.25rem;
    justify-content: center;
    flex-wrap: wrap;
  }

  .meta-item {
    display: flex; align-items: center; gap: 5px;
    font-size: 13px; color: var(--text3);
  }

  .meta-item svg { width: 14px; height: 14px; color: var(--accent); flex-shrink: 0; }

  /* ── SECTION ── */
  .section { margin-bottom: 1.5rem; }

  .section-label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 0.5px;
    background: var(--border);
  }

  .card {
    background: var(--bg2);
    border: 0.5px solid var(--border);
    border-radius: 14px;
    padding: 1.5rem;
  }

  /* ── EDUCATION ── */
  .edu-item {
    display: flex;
    gap: 1rem;
    align-items: flex-start;
  }

  .edu-icon {
    width: 42px; height: 42px;
    background: var(--bg3);
    border: 0.5px solid var(--border2);
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }

  .edu-icon svg { width: 20px; height: 20px; color: var(--accent); }

  .edu-name { font-size: 15px; font-weight: 500; color: #e0e0f0; margin-bottom: 3px; }
  .edu-school { font-size: 13px; color: var(--accent2); margin-bottom: 3px; }
  .edu-detail { font-size: 12px; color: var(--text3); }

  /* ── EMPTY STATE (pengalaman) ── */
  .empty-state {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
    gap: 10px;
    text-align: center;
  }

  .empty-icon {
    width: 48px; height: 48px;
    background: var(--bg3);
    border: 0.5px solid var(--border2);
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
  }

  .empty-icon svg { width: 22px; height: 22px; color: var(--text3); }
  .empty-text { font-size: 14px; color: var(--text3); }
  .empty-sub { font-size: 12px; color: #3a3a52; }

  /* ── SKILLS ── */
  .skills-wrap { display: flex; flex-wrap: wrap; gap: 8px; }

  .skill {
    padding: 6px 16px;
    border-radius: 999px;
    font-size: 13px;
    font-weight: 500;
    border: 0.5px solid var(--border2);
    background: var(--bg3);
    color: var(--accent2);
  }

  .skill.main {
    background: rgba(108,92,231,0.12);
    border-color: rgba(108,92,231,0.4);
    color: #c4b5fd;
  }

  /* ── CONTACTS ── */
  .contacts { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; }

  .contact-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 7px;
    padding: 1rem 0.75rem;
    background: var(--bg3);
    border: 0.5px solid var(--border);
    border-radius: 12px;
    text-decoration: none;
    transition: border-color 0.15s, background 0.15s;
  }

  .contact-link:hover {
    border-color: var(--accent);
    background: rgba(108,92,231,0.07);
  }

  .contact-link svg { width: 22px; height: 22px; color: var(--accent); }
  .contact-label { font-size: 11px; color: var(--text3); }
  .contact-val { font-size: 13px; color: var(--accent2); font-weight: 500; word-break: break-all; text-align: center; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 2rem;
    font-size: 12px;
    color: var(--text3);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 500px) {
    .hero { padding: 2.5rem 1.25rem 2rem; }
    .hero h1 { font-size: 22px; }
    .contacts { grid-template-columns: repeat(2, 1fr); }
  }
</style>
</head>
<body>
<main class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar">MH</div>
    <h1>Marasutan Hasibuan</h1>
    <div class="tagline">Automotive Engineering · Learner & Coder</div>
    <p class="bio">Saya masih berkuliah di Politeknik Astra, mendalami dunia otomotif sambil belajar coding secara otodidak. Percaya bahwa teknik dan teknologi bisa berjalan beriringan.</p>
    <div class="meta">
      <span class="meta-item">
        <svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5S10.62 6.5 12 6.5s2.5 1.12 2.5 2.5S13.38 11.5 12 11.5z"/></svg>
        Bogor, Indonesia
      </span>
      <span class="meta-item">
        <svg fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M22 10.5V6a2 2 0 0 0-2-2H4a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h8"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        marasutanhasibuan5@gmail.com
      </span>
    </div>
  </div>

  <!-- PENDIDIKAN -->
  <div class="section">
    <div class="section-label">Pendidikan</div>
    <div class="card">
      <div class="edu-item">
        <div class="edu-icon">
          <svg fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><path d="M22 10v6M2 10l10-5 10 5-10 5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>
        </div>
        <div>
          <div class="edu-name">D3 Teknik Mesin Otomotif</div>
          <div class="edu-school">Politeknik Astra</div>
          <div class="edu-detail">Sedang berjalan · Jakarta</div>
        </div>
      </div>
    </div>
  </div>

  <!-- PENGALAMAN KERJA -->
  <div class="section">
    <div class="section-label">Pengalaman kerja</div>
    <div class="card">
      <div class="empty-state">
        <div class="empty-icon">
          <svg fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="7" width="20" height="14" rx="2"/><path d="M16 7V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v2"/></svg>
        </div>
        <div class="empty-text">Belum ada pengalaman kerja</div>
        <div class="empty-sub">Masih aktif berkuliah — pengalaman sedang dibangun!</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section">
    <div class="section-label">Skills & keahlian</div>
    <div class="card">
      <div class="skills-wrap">
        <span class="skill main">Komunikasi</span>
        <span class="skill">Teknik Otomotif</span>
        <span class="skill">Belajar Mandiri</span>
        <span class="skill">Coding (pemula)</span>
        <span class="skill">Problem Solving</span>
        <span class="skill">Kerja Tim</span>
      </div>
    </div>
  </div>

  <!-- KONTAK -->
  <div class="section">
    <div class="section-label">Kontak & sosial media</div>
    <div class="contacts">

      <a class="contact-link" href="mailto:marasutanhasibuan5@gmail.com">
        <svg fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        <span class="contact-label">Email</span>
        <span class="contact-val">marasutanhasibuan5@gmail.com</span>
      </a>

      <a class="contact-link" href="https://instagram.com/marasutanhsb_" target="_blank" rel="noopener">
        <svg fill="none" stroke="currentColor" stroke-width="1.8" viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="0.5" fill="currentColor"/></svg>
        <span class="contact-label">Instagram</span>
        <span class="contact-val">@marasutanhsb_</span>
      </a>

      <a class="contact-link" href="https://linkedin.com/in/marasutan-hasibuan" target="_blank" rel="noopener">
        <svg fill="currentColor" viewBox="0 0 24 24"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
        <span class="contact-label">LinkedIn</span>
        <span class="contact-val">Marasutan Hasibuan</span>
      </a>

    </div>
  </div>

  <div class="footer">
    Dibuat dengan semangat belajar · Bogor 2025
  </div>

</main>
</body>
</html>
