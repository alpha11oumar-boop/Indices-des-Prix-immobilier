<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Indices de prix immobiliers — Hauts-de-France</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,300&display=swap');

  :root {
    --navy:   #0F1F3D;
    --teal:   #0B7A75;
    --teal2:  #0D9488;
    --gold:   #C9A84C;
    --cream:  #F5F0E8;
    --warm:   #EDE8DC;
    --text:   #1A1A2E;
    --muted:  #6B7280;
    --border: #D4C9B0;
    --code:   #1E293B;
    --codebg: #F0EDE6;
    --white:  #FFFFFF;
    --red:    #991B1B;
    --green:  #065F46;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    font-weight: 300;
    background: var(--cream);
    color: var(--text);
    line-height: 1.75;
    font-size: 15px;
  }

  /* ── COVER ── */
  .cover {
    background: var(--navy);
    padding: 80px 0 0;
    position: relative;
    overflow: hidden;
  }

  .cover::before {
    content: '';
    position: absolute;
    top: -120px; right: -120px;
    width: 500px; height: 500px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(11,122,117,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  .cover-inner {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 48px;
  }

  .cover-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(201,168,76,0.15);
    border: 1px solid rgba(201,168,76,0.4);
    color: var(--gold);
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 6px 14px;
    border-radius: 2px;
    margin-bottom: 36px;
  }

  .cover-badge::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--gold);
    border-radius: 50%;
  }

  .cover-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(40px, 5vw, 62px);
    color: var(--white);
    line-height: 1.1;
    margin-bottom: 12px;
  }

  .cover-title em {
    color: var(--teal2);
    font-style: normal;
  }

  .cover-subtitle {
    font-size: 16px;
    color: rgba(255,255,255,0.55);
    font-weight: 300;
    margin-bottom: 48px;
    letter-spacing: 0.02em;
  }

  .cover-meta {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.08);
    border-top: 1px solid rgba(255,255,255,0.1);
    margin-top: 60px;
  }

  .cover-meta-item {
    padding: 24px 28px;
    background: var(--navy);
  }

  .cover-meta-label {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.35);
    margin-bottom: 6px;
  }

  .cover-meta-value {
    font-size: 14px;
    color: var(--white);
    font-weight: 400;
    line-height: 1.3;
  }

  /* ── LAYOUT ── */
  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 0 48px;
  }

  /* ── SECTION ── */
  .section {
    padding: 64px 0 0;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 36px;
    padding-bottom: 20px;
    border-bottom: 1px solid var(--border);
  }

  .section-num {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--teal2);
    letter-spacing: 0.12em;
    background: rgba(11,122,117,0.08);
    border: 1px solid rgba(11,122,117,0.2);
    padding: 4px 10px;
    border-radius: 2px;
    flex-shrink: 0;
  }

  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: 26px;
    color: var(--navy);
    line-height: 1.2;
  }

  /* ── TYPOGRAPHY ── */
  p {
    margin-bottom: 16px;
    color: var(--text);
    font-size: 15px;
  }

  strong { font-weight: 600; color: var(--navy); }

  h3 {
    font-family: 'DM Serif Display', serif;
    font-size: 18px;
    color: var(--navy);
    margin: 32px 0 12px;
  }

  h4 {
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--teal);
    margin: 24px 0 10px;
  }

  ul, ol {
    padding-left: 0;
    list-style: none;
    margin-bottom: 16px;
  }

  ul li, ol li {
    position: relative;
    padding-left: 22px;
    margin-bottom: 8px;
    font-size: 15px;
    color: var(--text);
  }

  ul li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--teal2);
    font-weight: 500;
  }

  ol { counter-reset: item; }
  ol li { counter-increment: item; }
  ol li::before {
    content: counter(item) '.';
    position: absolute;
    left: 0;
    color: var(--gold);
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    font-weight: 500;
    top: 2px;
  }

  /* ── CODE ── */
  code {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    background: var(--codebg);
    color: var(--teal);
    padding: 2px 6px;
    border-radius: 2px;
    border: 1px solid var(--border);
  }

  pre {
    background: var(--navy);
    padding: 24px 28px;
    border-radius: 4px;
    overflow-x: auto;
    margin: 20px 0 28px;
    border-left: 3px solid var(--teal2);
  }

  pre code {
    background: none;
    border: none;
    color: #93C5FD;
    font-size: 13px;
    padding: 0;
    line-height: 1.7;
  }

  /* ── FORMULA ── */
  .formula-box {
    background: var(--warm);
    border: 1px solid var(--border);
    border-left: 4px solid var(--navy);
    padding: 22px 28px;
    margin: 24px 0;
    border-radius: 0 4px 4px 0;
  }

  .formula-main {
    font-family: 'DM Mono', monospace;
    font-size: 15px;
    color: var(--navy);
    font-weight: 500;
    letter-spacing: 0.02em;
    display: block;
    margin-bottom: 6px;
  }

  .formula-caption {
    font-size: 12px;
    color: var(--muted);
    font-style: italic;
  }

  /* ── TABLES ── */
  .table-wrap {
    overflow-x: auto;
    margin: 20px 0 28px;
    border-radius: 4px;
    border: 1px solid var(--border);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13.5px;
  }

  thead th {
    background: var(--navy);
    color: var(--white);
    font-family: 'DM Sans', sans-serif;
    font-weight: 500;
    font-size: 11px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 12px 16px;
    text-align: left;
  }

  tbody tr:nth-child(even) { background: var(--warm); }
  tbody tr:nth-child(odd)  { background: var(--white); }

  td {
    padding: 10px 16px;
    border-bottom: 1px solid var(--border);
    vertical-align: middle;
    font-size: 13.5px;
    color: var(--text);
  }

  td:first-child {
    font-family: 'DM Mono', monospace;
    font-size: 12.5px;
    color: var(--teal);
    font-weight: 500;
  }

  .sig-stars { color: var(--green); font-weight: 700; font-family: 'DM Mono', monospace; font-size: 12px; }
  .sig-ns    { color: var(--muted); font-family: 'DM Mono', monospace; font-size: 12px; }
  .sig-star  { color: #065F46; font-weight: 600; font-family: 'DM Mono', monospace; font-size: 12px; }

  /* ── STAT CARDS ── */
  .stat-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin: 20px 0 28px;
  }

  .stat-card {
    background: var(--white);
    border: 1px solid var(--border);
    border-top: 3px solid var(--navy);
    padding: 18px 16px;
    border-radius: 0 0 4px 4px;
  }

  .stat-card.teal  { border-top-color: var(--teal2); }
  .stat-card.gold  { border-top-color: var(--gold);  }

  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 6px;
  }

  .stat-value {
    font-family: 'DM Serif Display', serif;
    font-size: 22px;
    color: var(--navy);
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-sub {
    font-size: 11px;
    color: var(--muted);
  }

  /* ── CALLOUT ── */
  .callout {
    background: var(--warm);
    border: 1px solid var(--border);
    border-left: 4px solid var(--teal2);
    padding: 18px 22px;
    margin: 20px 0;
    border-radius: 0 4px 4px 0;
    font-size: 14px;
    color: var(--text);
  }

  .callout-title {
    font-weight: 600;
    color: var(--teal);
    font-size: 12px;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .callout-title::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--teal2);
    border-radius: 50%;
  }

  .callout.warning { border-left-color: var(--gold); }
  .callout.warning .callout-title { color: #92400E; }
  .callout.warning .callout-title::before { background: var(--gold); }

  /* ── REGIME TABLE ── */
  .regime-grid {
    display: grid;
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
    margin: 20px 0 28px;
  }

  .regime-row {
    display: grid;
    grid-template-columns: 140px 1fr;
    background: var(--white);
  }

  .regime-period {
    background: var(--navy);
    color: var(--white);
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    padding: 14px 16px;
    display: flex;
    align-items: center;
  }

  .regime-desc {
    padding: 14px 20px;
    font-size: 13.5px;
    display: flex;
    align-items: center;
  }

  /* ── PIPELINE ── */
  .pipeline {
    margin: 20px 0 28px;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .pipeline-step {
    display: grid;
    grid-template-columns: 52px 1fr;
    position: relative;
  }

  .pipeline-step:not(:last-child)::after {
    content: '';
    position: absolute;
    left: 25px;
    top: 52px;
    bottom: 0;
    width: 2px;
    background: var(--border);
  }

  .pipeline-num {
    width: 50px; height: 50px;
    background: var(--navy);
    color: var(--white);
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    font-weight: 500;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    flex-shrink: 0;
    z-index: 1;
    position: relative;
  }

  .pipeline-content {
    padding: 12px 0 28px 20px;
  }

  .pipeline-title {
    font-weight: 600;
    color: var(--navy);
    font-size: 14px;
    margin-bottom: 4px;
  }

  .pipeline-desc {
    font-size: 13.5px;
    color: var(--muted);
    line-height: 1.6;
  }

  .pipeline-formula {
    font-family: 'DM Mono', monospace;
    font-size: 12.5px;
    color: var(--teal);
    background: var(--codebg);
    border: 1px solid var(--border);
    padding: 6px 10px;
    border-radius: 2px;
    margin-top: 8px;
    display: inline-block;
  }

  /* ── REPO TREE ── */
  .tree {
    background: var(--navy);
    border-radius: 4px;
    padding: 24px 28px;
    margin: 20px 0 28px;
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    line-height: 2;
  }

  .tree-root { color: var(--gold); font-weight: 500; }
  .tree-dir  { color: #93C5FD; }
  .tree-file { color: rgba(255,255,255,0.7); }
  .tree-note { color: rgba(255,255,255,0.35); }
  .tree-line { color: rgba(255,255,255,0.2); }

  /* ── FOOTER ── */
  .footer {
    margin-top: 80px;
    background: var(--navy);
    padding: 36px 48px;
  }

  .footer-inner {
    max-width: 860px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .footer-left {
    font-family: 'DM Serif Display', serif;
    font-size: 18px;
    color: var(--white);
  }

  .footer-right {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: rgba(255,255,255,0.4);
    text-align: right;
    line-height: 1.6;
  }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
    margin: 48px 0;
  }

  /* ── PACKAGE LIST ── */
  .pkg-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin: 16px 0 24px;
  }

  .pkg-item {
    background: var(--white);
    border: 1px solid var(--border);
    padding: 10px 14px;
    border-radius: 3px;
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .pkg-name {
    font-family: 'DM Mono', monospace;
    font-size: 13px;
    color: var(--teal);
    font-weight: 500;
  }

  .pkg-desc {
    font-size: 11px;
    color: var(--muted);
  }

  @media (max-width: 700px) {
    .cover-meta { grid-template-columns: repeat(2, 1fr); }
    .stat-grid  { grid-template-columns: repeat(2, 1fr); }
    .pkg-grid   { grid-template-columns: repeat(2, 1fr); }
    .container, .cover-inner { padding: 0 24px; }
    .footer { padding: 32px 24px; }
  }

  @media print {
    .cover { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  }
</style>
</head>
<body>

<!-- ══ COVER ═══════════════════════════════════════════ -->
<header class="cover">
  <div class="cover-inner">
    <div class="cover-badge">Master 1 Statistique &amp; Économétrie · UE Conduite de Projet 2025/26</div>
    <h1 class="cover-title">
      Indices de prix<br>
      <em>immobiliers</em>
    </h1>
    <p class="cover-subtitle">Hauts-de-France · 2010–2025 · Modèle hédonique sur données DVF+ / DV3F</p>
  </div>
  <div class="cover-meta">
    <div class="cover-meta-item">
      <div class="cover-meta-label">Région</div>
      <div class="cover-meta-value">Hauts-de-France<br>5 départements</div>
    </div>
    <div class="cover-meta-item">
      <div class="cover-meta-label">Données brutes</div>
      <div class="cover-meta-value">1 418 289 lignes<br>2010–2025</div>
    </div>
    <div class="cover-meta-item">
      <div class="cover-meta-label">Après nettoyage</div>
      <div class="cover-meta-value">1 074 908 ventes<br>effectives</div>
    </div>
    <div class="cover-meta-item">
      <div class="cover-meta-label">Méthode</div>
      <div class="cover-meta-value">OLS · fixest (R)<br>Effets fixes absorbés</div>
    </div>
  </div>
</header>

<!-- ══ MAIN ════════════════════════════════════════════ -->
<main>

<!-- ── I. OBJECTIF ───────────────────────────────────── -->
<div class="container">
<section class="section">
  <div class="section-header">
    <span class="section-num">01</span>
    <h2 class="section-title">Objectif du projet</h2>
  </div>

  <p>Ce projet construit des <strong>indices de prix immobiliers à qualité constante</strong> au niveau <strong>commune × mois</strong> pour la région Hauts-de-France sur la période 2010–2025, en distinguant les appartements et les maisons.</p>

  <div class="callout">
    <div class="callout-title">Pourquoi un modèle hédonique ?</div>
    Le prix moyen observé varie lorsque la composition des biens vendus change — plus de logements neufs, de grandes surfaces, de biens mieux situés — sans que le marché lui-même n'ait évolué. Le modèle hédonique corrige ce biais de composition et produit un indicateur comparable dans le temps et entre communes.
  </div>

  <h4>Livrables</h4>
  <ul>
    <li>Table d'indices de prix par commune et par mois (appartements &amp; maisons séparément)</li>
    <li>Courbes temporelles de l'indice régional et communal</li>
    <li>Cartes choroplèthes des niveaux de prix et des effets fixes communaux</li>
    <li>Heatmaps commune × temps pour visualiser la dynamique spatiotemporelle</li>
  </ul>
</section>

<!-- ── II. DONNÉES ───────────────────────────────────── -->
<section class="section">
  <div class="section-header">
    <span class="section-num">02</span>
    <h2 class="section-title">Données</h2>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr><th>Source</th><th>Période</th><th>Observations</th><th>Format</th><th>Accès</th></tr>
      </thead>
      <tbody>
        <tr>
          <td>DVF+</td>
          <td>2014–2025</td>
          <td>1 181 643</td>
          <td>CSV (sep. <code>|</code>)</td>
          <td>data.gouv.fr — open data</td>
        </tr>
        <tr>
          <td>DV3F</td>
          <td>2010–2013</td>
          <td>236 646</td>
          <td>Parquet</td>
          <td>Fourni par l'enseignant (Moodle)</td>
        </tr>
      </tbody>
    </table>
  </div>

  <p><strong>Départements couverts :</strong> Aisne (02 · 127 198 obs.), Nord (59 · 620 446), Oise (60 · 193 253), Pas-de-Calais (62 · 329 071), Somme (80 · 148 321).</p>

  <h4>Nettoyage appliqué</h4>
  <ul>
    <li>Restriction aux ventes effectives uniquement (<code>libnatmut == "Vente"</code>)</li>
    <li>Suppression des lignes sans surface bâtie ni valeur foncière</li>
    <li>Filtre prix au m² entre <strong>200 et 20 000 €/m²</strong> — statistiques : Min=200 · Q1=1 176 · Médiane=1 691 · Moyenne=1 880 · Q3=2 335 · Max=20 000</li>
    <li>Transformation log : <code>log_p_m2 = log(p_m2)</code> pour stabiliser la variance</li>
  </ul>

  <p><strong>Base finale :</strong> 1 074 908 ventes effectives.</p>
</section>

<!-- ── III. MÉTHODOLOGIE ─────────────────────────────── -->
<section class="section">
  <div class="section-header">
    <span class="section-num">03</span>
    <h2 class="section-title">Méthodologie</h2>
  </div>

  <h3>Le modèle hédonique log-linéaire</h3>
  <p>Deux modèles sont estimés séparément — appartements et maisons — par OLS via le package <code>fixest</code> :</p>

  <div class="formula-box">
    <span class="formula-main">log(pᵢ) = α + xᵢ′β + γ_{t(i)} + δ_{d(i)} + μ_{c(i)} + θ_{d(i),a(i)} + εᵢ</span>
    <span class="formula-caption">Estimation OLS · effets fixes absorbés par l'algorithme de Mundlak dans feols()</span>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr><th>Terme</th><th>Rôle</th></tr>
      </thead>
      <tbody>
        <tr><td>xᵢ′β</td><td>Variables de qualité : log(surface), VEFA (0/1), typologies T1/T3/T4/T5 — T2 est la référence. Ces termes sont neutralisés pour obtenir le prix net.</td></tr>
        <tr><td>γ_t</td><td>Effet fixe temps (mois × année) — capte la tendance globale du marché à qualité constante. Base de l'indice régional.</td></tr>
        <tr><td>δ_d</td><td>Effet fixe département — contrôle les écarts de niveau entre les cinq départements.</td></tr>
        <tr><td>μ_c</td><td>Effet fixe commune — mesure le prix absolu local, toutes choses égales par ailleurs. Non estimé pour les 100 communes les moins liquides.</td></tr>
        <tr><td>θ_{d,a}</td><td>Interaction département × année — permet des tendances temporelles différenciées par département.</td></tr>
      </tbody>
    </table>
  </div>

  <h3>Pipeline en 7 étapes</h3>

  <div class="pipeline">
    <div class="pipeline-step">
      <div class="pipeline-num">1</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Estimation OLS</div>
        <div class="pipeline-desc">Le modèle est estimé sur l'ensemble des données via <code>feols()</code>. L'objectif est la prédiction, non l'inférence causale — la multicolinéarité entre dummies n'est pas un problème.</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">2</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Prix net à qualité constante</div>
        <div class="pipeline-desc">On soustrait la contribution des variables de qualité à chaque valeur ajustée.</div>
        <div class="pipeline-formula">log P^net_i = ŷᵢ − Σ_{k∈H} β̂_k · x_{ik}</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">3</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Correction des petites communes</div>
        <div class="pipeline-desc">Les 100 communes les moins liquides (en transactions) ne reçoivent pas d'effet fixe direct — trop peu de données. Correction par moyenne des résidus : <code>log P^net_i ← log P^net_i + ē_c</code>.</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">4</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Agrégation commune × mois</div>
        <div class="pipeline-desc">Médiane du log prix net par (commune, période) — robuste aux valeurs extrêmes. Seuil minimum : 3 transactions.</div>
        <div class="pipeline-formula">log P^net_{c,t} = médiane{ log P^net_i : c(i)=c, t(i)=t }</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">5</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Complétion des périodes manquantes</div>
        <div class="pipeline-desc">Mois sans transaction → prédiction via les coefficients estimés. Condition : tous les effets fixes doivent être disponibles (<code>n_fe_manquants == 0</code>). Prédictions hors ±3 écarts-types éliminées.</div>
        <div class="pipeline-formula">log P̂^net_{c,t} = α̂ + fe_temps + fe_commune + fe_dép + fe_dép×année</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">6</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Garde-fous sur l'indice final</div>
        <div class="pipeline-desc">Filtre <code>|diff_log| ≤ log(5)</code> sur l'indice final (variations max d'un facteur 5). Les communes dont la base est hors ±4 écarts-types sont exclues.</div>
      </div>
    </div>
    <div class="pipeline-step">
      <div class="pipeline-num">7</div>
      <div class="pipeline-content">
        <div class="pipeline-title">Indice base 100</div>
        <div class="pipeline-desc">Période de référence t₀ commune à toutes les communes — garantit la comparabilité intercommunale.</div>
        <div class="pipeline-formula">Index_{c,t} = 100 × exp( log P^net_{c,t} − log P^net_{c,t₀} )</div>
      </div>
    </div>
  </div>
</section>

<!-- ── IV. RÉSULTATS ─────────────────────────────────── -->
<section class="section">
  <div class="section-header">
    <span class="section-num">04</span>
    <h2 class="section-title">Résultats</h2>
  </div>

  <h3>Appartements</h3>

  <div class="stat-grid">
    <div class="stat-card">
      <div class="stat-label">Observations</div>
      <div class="stat-value">38 282</div>
      <div class="stat-sub">430 communes</div>
    </div>
    <div class="stat-card teal">
      <div class="stat-label">R² ajusté</div>
      <div class="stat-value">0.505</div>
      <div class="stat-sub">Within R² = 0.109</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">RMSE</div>
      <div class="stat-value">0.302</div>
      <div class="stat-sub">En log du prix au m²</div>
    </div>
    <div class="stat-card gold">
      <div class="stat-label">Indice médian</div>
      <div class="stat-value">94.6</div>
      <div class="stat-sub">Min=86.3 · Max=100.1</div>
    </div>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr><th>Paramètre</th><th>Estimate</th><th>Std. Error</th><th>Signif.</th><th>Interprétation</th></tr>
      </thead>
      <tbody>
        <tr>
          <td>log_sbati</td>
          <td>−0.2320</td>
          <td>0.0060</td>
          <td><span class="sig-stars">***</span></td>
          <td>−0.23 % de prix/m² par +1 % de surface (économies d'échelle)</td>
        </tr>
        <tr>
          <td>vefa_num</td>
          <td>+0.3569</td>
          <td>0.0398</td>
          <td><span class="sig-stars">***</span></td>
          <td>Prime neuf ≈ <strong>+42,9 %</strong> (normes, personnalisation)</td>
        </tr>
        <tr>
          <td>T1</td>
          <td>−0.0214</td>
          <td>0.0055</td>
          <td><span class="sig-stars">***</span></td>
          <td>Relatif au T2 de référence</td>
        </tr>
        <tr>
          <td>T3</td>
          <td>+0.0143</td>
          <td>0.0047</td>
          <td><span class="sig-stars">**</span></td>
          <td>Prime pour la taille intermédiaire</td>
        </tr>
        <tr>
          <td>T4</td>
          <td>−0.0225</td>
          <td>0.0063</td>
          <td><span class="sig-stars">***</span></td>
          <td>Décote par rapport au T2</td>
        </tr>
        <tr>
          <td>T5</td>
          <td>+0.0116</td>
          <td>0.0094</td>
          <td><span class="sig-ns">ns</span></td>
          <td>Non significatif au seuil 5 %</td>
        </tr>
      </tbody>
    </table>
  </div>

  <h3>Maisons</h3>

  <div class="stat-grid">
    <div class="stat-card">
      <div class="stat-label">Observations</div>
      <div class="stat-value">806 942</div>
      <div class="stat-sub">4 192 communes</div>
    </div>
    <div class="stat-card teal">
      <div class="stat-label">R² ajusté</div>
      <div class="stat-value">0.425</div>
      <div class="stat-sub">Within R² = 0.023</div>
    </div>
    <div class="stat-card">
      <div class="stat-label">RMSE</div>
      <div class="stat-value">0.395</div>
      <div class="stat-sub">En log du prix au m²</div>
    </div>
    <div class="stat-card gold">
      <div class="stat-label">Indice médian</div>
      <div class="stat-value">88.9</div>
      <div class="stat-sub">Min=78.4 · Max=109.1</div>
    </div>
  </div>

  <div class="table-wrap">
    <table>
      <thead>
        <tr><th>Paramètre</th><th>Estimate</th><th>Std. Error</th><th>Signif.</th><th>Interprétation</th></tr>
      </thead>
      <tbody>
        <tr>
          <td>log_sbati</td>
          <td>−0.1657</td>
          <td>0.0012</td>
          <td><span class="sig-stars">***</span></td>
          <td>Élasticité plus faible que pour les appartements (composante foncière)</td>
        </tr>
        <tr>
          <td>vefa_num</td>
          <td>+0.2108</td>
          <td>0.0910</td>
          <td><span class="sig-star">*</span></td>
          <td>Prime neuf ≈ <strong>+23,5 %</strong> — inférieure à celle des appartements</td>
        </tr>
      </tbody>
    </table>
  </div>

  <div class="callout warning">
    <div class="callout-title">Note sur le R² des maisons</div>
    Le R² structurellement plus faible (0.425 vs 0.505) est attendu : la plus grande hétérogénéité des maisons (terrain, configuration, état) ne peut être captée par les seules variables disponibles dans DVF. Le within R² de 0.023 indique que l'essentiel de la variance est expliquée par les effets fixes.
  </div>

  <h3>Régimes temporels (2010–2025)</h3>

  <div class="regime-grid">
    <div class="regime-row">
      <div class="regime-period">2010–2013</div>
      <div class="regime-desc">Marché post-crise de 2008 · stagnation ou légère baisse sous l'effet de la contraction du crédit</div>
    </div>
    <div class="regime-row">
      <div class="regime-period">2014–2019</div>
      <div class="regime-desc">Stabilisation puis reprise modérée portée par la baisse des taux et la demande dans la métropole lilloise</div>
    </div>
    <div class="regime-row">
      <div class="regime-period">2020–2022</div>
      <div class="regime-desc">Accélération post-Covid · préférences résidentielles et taux au plancher · surperformance des maisons</div>
    </div>
    <div class="regime-row">
      <div class="regime-period">2023–2025</div>
      <div class="regime-desc">Retournement consécutif à la remontée des taux BCE · ralentissement marqué voire correction</div>
    </div>
  </div>

  <h3>Hétérogénéité spatiale</h3>
  <ul>
    <li><strong>Lille (59350)</strong> — marché le plus tendu, trajectoire haussière supérieure à la moyenne régionale sur toute la période. Effet métropole structurel.</li>
    <li><strong>Roubaix (59512)</strong> — niveaux absolus plus faibles (capturés par μ̂_c) mais dynamique de rattrapage visible sur certaines sous-périodes. Phénomène de gentrification partielle.</li>
    <li><strong>Arras (62041)</strong> — marché moins liquide, plus sensible à l'emploi industriel local. Trajectoire proche du cycle régional.</li>
    <li><strong>Gradient centre-périphérie</strong> — les effets fixes exp(μ̂_c) décroissent à mesure que l'on s'éloigne de Lille. Exceptions : Le Touquet-Paris-Plage (résidence secondaire), communes côtières.</li>
  </ul>
</section>

<!-- ── V. STRUCTURE DU DÉPÔT ─────────────────────────── -->
<section class="section">
  <div class="section-header">
    <span class="section-num">05</span>
    <h2 class="section-title">Structure du dépôt</h2>
  </div>

  <div class="tree">
    <div><span class="tree-root">indices-prix-immo-hdf/</span></div>
    <div><span class="tree-line">├── </span><span class="tree-file">README.md</span> <span class="tree-note">← ce fichier</span></div>
    <div><span class="tree-line">├── </span><span class="tree-file">analyse_immo_hdf.Rmd</span> <span class="tree-note">← pipeline complet (code + interprétations)</span></div>
    <div><span class="tree-line">├── </span><span class="tree-dir">data/</span></div>
    <div><span class="tree-line">│   └── </span><span class="tree-file">README.md</span> <span class="tree-note">← instructions de téléchargement</span></div>
    <div><span class="tree-line">└── </span><span class="tree-dir">outputs/</span></div>
    <div><span class="tree-line">    └── </span><span class="tree-file">README.md</span> <span class="tree-note">← description des fichiers produits</span></div>
  </div>
</section>

<!-- ── VI. REPRODUCTION ──────────────────────────────── -->
<section class="section">
  <div class="section-header">
    <span class="section-num">06</span>
    <h2 class="section-title">Reproduire les résultats</h2>
  </div>

  <h4>Packages R requis</h4>

  <div class="pkg-grid">
    <div class="pkg-item"><div class="pkg-name">data.table</div><div class="pkg-desc">Manipulation des grandes bases</div></div>
    <div class="pkg-item"><div class="pkg-name">arrow</div><div class="pkg-desc">Lecture du format Parquet</div></div>
    <div class="pkg-item"><div class="pkg-name">fixest</div><div class="pkg-desc">OLS avec effets fixes (feols)</div></div>
    <div class="pkg-item"><div class="pkg-name">ggplot2</div><div class="pkg-desc">Visualisations</div></div>
    <div class="pkg-item"><div class="pkg-name">sf + giscoR</div><div class="pkg-desc">Données spatiales et fonds de carte</div></div>
    <div class="pkg-item"><div class="pkg-name">classInt · scales</div><div class="pkg-desc">Cartes choroplèthes</div></div>
  </div>

  <pre><code>install.packages(c(
  "data.table", "arrow", "fixest", "ggplot2",
  "sf", "giscoR", "classInt", "scales", "tidyr"
))</code></pre>

  <h4>Étapes</h4>
  <ol>
    <li>Télécharger <strong>DVF+</strong> pour les Hauts-de-France depuis data.gouv.fr (format CSV, séparateur <code>|</code>).</li>
    <li>Récupérer <strong>DV3F 2010–2013</strong> (Parquet) depuis Moodle.</li>
    <li>Adapter les chemins dans le chunk <code>lecture_donnees</code> du fichier <code>.Rmd</code>.</li>
    <li>Knitter : <code>rmarkdown::render("analyse_immo_hdf.Rmd")</code>.</li>
  </ol>

  <div class="callout warning">
    <div class="callout-title">Note sur la mémoire</div>
    Le modèle maisons porte sur ~807 000 observations avec ~4 200 effets fixes communaux. Prévoir au moins <strong>8 Go de RAM disponible</strong>. Tester d'abord sur un sous-échantillon (<code>dt[sample(.N, 50000)]</code>) avant de lancer sur la base complète.
  </div>

  <div class="divider"></div>
</section>
</div><!-- /container -->

</main>

<!-- ══ FOOTER ══════════════════════════════════════════ -->
<footer class="footer">
  <div class="footer-inner">
    <div class="footer-left">Indices de prix<br>immobiliers · HdF</div>
    <div class="footer-right">
      Master 1 Statistique &amp; Économétrie<br>
      Université de Strasbourg · UE Conduite de Projet 2025/26<br>
      Source : DVF+ / DV3F · Méthode : OLS hédonique (fixest)
    </div>
  </div>
</footer>

</body>
</html>
