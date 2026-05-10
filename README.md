[index.html](https://github.com/user-attachments/files/27574901/index.html)<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mapão — Educação Especial — E.E. Dr. Álvaro Guião — 2026</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700&family=Playfair+Display:wght@700;800&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #f5f0eb;
  --surface: #ffffff;
  --surface-alt: #faf7f4;
  --ink: #1a1a2e;
  --ink-soft: #5a5a72;
  --ink-muted: #9999ab;
  --accent: #2d5a8e;
  --accent-light: #e8f0fa;
  --accent-dark: #1a3d66;
  --tea: #1b7a6e; --tea-light: #e6f5f2;
  --di: #8e5a2d; --di-light: #faf0e6;
  --df: #6b3fa0; --df-light: #f3eefa;
  --surdez: #b8860b; --surdez-light: #fdf6e3;
  --visao: #c45a3c; --visao-light: #fdf0ec;
  --ah: #2e7d32; --ah-light: #e8f5e9;
  --multipla: #c62828; --multipla-light: #fce4ec;
  --oj-bg: #fff8e1; --oj-border: #f9a825;
  --radius: 12px;
  --radius-sm: 8px;
  --shadow-sm: 0 1px 3px rgba(26,26,46,0.06);
  --shadow-md: 0 4px 20px rgba(26,26,46,0.08);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:'DM Sans',sans-serif; background:var(--bg); color:var(--ink); line-height:1.6; -webkit-font-smoothing:antialiased; }

.hero {
  background:linear-gradient(135deg,#1a3d66 0%,#2d5a8e 40%,#1b7a6e 100%);
  padding:2.5rem 1.5rem 2rem; color:white; position:relative; overflow:hidden;
}
.hero::before { content:''; position:absolute; top:-50%; right:-20%; width:500px; height:500px; background:radial-gradient(circle,rgba(255,255,255,0.06) 0%,transparent 70%); border-radius:50%; }
.hero-inner { max-width:1200px; margin:0 auto; position:relative; z-index:1; }
.hero h1 { font-family:'Playfair Display',serif; font-size:2rem; font-weight:800; letter-spacing:-0.02em; }
.hero .sub { font-size:0.95rem; opacity:0.85; margin-top:2px; }
.toolbar { display:flex; gap:6px; margin-top:12px; flex-wrap:wrap; align-items:center; }
.pill {
  display:inline-flex; align-items:center; gap:4px;
  padding:4px 14px; border-radius:20px; font-size:12px; font-weight:600;
  cursor:pointer; border:1px solid rgba(255,255,255,0.2);
  background:rgba(255,255,255,0.1); color:white; transition:all 0.2s;
  user-select:none;
}
.pill:hover { background:rgba(255,255,255,0.2); }
.pill.active { background:rgba(255,200,0,0.3); border-color:rgba(255,200,0,0.5); }
.pill.green { background:rgba(76,175,80,0.25); border-color:rgba(76,175,80,0.4); }
.pill.red { background:rgba(244,67,54,0.25); border-color:rgba(244,67,54,0.4); }
.pill.blue { background:rgba(33,150,243,0.25); border-color:rgba(33,150,243,0.4); }

.stats-bar { max-width:1200px; margin:-1.2rem auto 1.5rem; padding:0 1.5rem; position:relative; z-index:2; }
.stats-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(140px,1fr)); gap:8px; }
.stat-card { background:var(--surface); border-radius:var(--radius); padding:12px 8px; box-shadow:var(--shadow-sm); text-align:center; }
.stat-num { font-family:'Playfair Display',serif; font-size:1.8rem; font-weight:800; color:var(--accent); }
.stat-lbl { font-size:0.7rem; color:var(--ink-soft); font-weight:600; text-transform:uppercase; letter-spacing:0.05em; }

.container { max-width:1200px; margin:0 auto; padding:0 1.5rem 3rem; }

.search-bar {
  display:flex; align-items:center; gap:8px; background:var(--surface);
  border-radius:var(--radius); padding:8px 14px; box-shadow:var(--shadow-sm);
  margin-bottom:12px; border:2px solid transparent; transition:border-color 0.2s;
}
.search-bar:focus-within { border-color:var(--accent); }
.search-bar input { flex:1; border:none; outline:none; font-family:inherit; font-size:14px; background:transparent; }
.search-count { font-size:12px; color:var(--ink-muted); font-weight:600; white-space:nowrap; }

.tabs { display:flex; gap:3px; background:var(--surface); border-radius:var(--radius); padding:4px; box-shadow:var(--shadow-sm); margin-bottom:16px; overflow-x:auto; }
.tab {
  padding:8px 16px; border:none; background:transparent; border-radius:var(--radius-sm);
  font-family:inherit; font-size:13px; font-weight:600; color:var(--ink-soft);
  cursor:pointer; white-space:nowrap; transition:all 0.2s;
}
.tab:hover { color:var(--ink); background:var(--surface-alt); }
.tab.active { background:var(--accent); color:white; box-shadow:0 2px 8px rgba(45,90,142,0.3); }

.tab-content { display:none; animation:fadeIn 0.3s ease; }
.tab-content.active { display:block; }
@keyframes fadeIn { from{opacity:0;transform:translateY(6px)} to{opacity:1;transform:translateY(0)} }

.edit-banner {
  background:var(--oj-bg); border:1px solid var(--oj-border); border-radius:var(--radius);
  padding:10px 16px; margin-bottom:12px; font-size:13px; color:#5d4037;
}

.section-title { display:flex; align-items:center; gap:10px; margin:20px 0 10px; }
.section-title h2 { font-family:'Playfair Display',serif; font-size:1.2rem; }
.badge {
  display:inline-block; padding:2px 8px; border-radius:6px; font-size:11px;
  font-weight:600; white-space:nowrap; margin:1px 2px;
}
.b-tea{background:var(--tea-light);color:var(--tea)} .b-di{background:var(--di-light);color:var(--di)}
.b-df{background:var(--df-light);color:var(--df)} .b-surdez{background:var(--surdez-light);color:var(--surdez)}
.b-visao{background:var(--visao-light);color:var(--visao)} .b-ah{background:var(--ah-light);color:var(--ah)}
.b-multipla{background:var(--multipla-light);color:var(--multipla)}
.b-oj{background:var(--oj-bg);color:#e65100;border:1px solid var(--oj-border)}
.b-aee{background:#e0f2f1;color:#00695c} .b-cnt{background:var(--accent-light);color:var(--accent)}

.turma-group { background:var(--surface); border-radius:var(--radius); margin-bottom:10px; box-shadow:var(--shadow-sm); overflow:hidden; border:1px solid rgba(0,0,0,0.04); }
.turma-header {
  padding:10px 14px; background:var(--surface-alt); border-bottom:1px solid rgba(0,0,0,0.05);
  display:flex; justify-content:space-between; align-items:center; cursor:pointer; user-select:none;
}
.turma-header:hover { background:#f0ece7; }

table { width:100%; border-collapse:collapse; font-size:13px; }
thead th {
  background:var(--accent); color:white; padding:7px 10px; text-align:left;
  font-size:11px; font-weight:600; letter-spacing:0.04em; text-transform:uppercase;
  position:sticky; top:0; z-index:1;
}
tbody tr { border-bottom:1px solid rgba(0,0,0,0.04); transition:background 0.12s; }
tbody tr:hover { background:var(--accent-light); }
tbody tr.oj-row { background:var(--oj-bg); }
tbody tr.oj-row:hover { background:#fff3c4; }
td { padding:6px 10px; vertical-align:middle; }
.col-num { width:35px; text-align:center; color:var(--ink-muted); font-weight:600; }
.col-center { text-align:center; }

.editable {
  cursor:pointer; padding:3px 6px; border-radius:6px; min-height:22px;
  border:1px dashed transparent; transition:all 0.15s;
}
.editable:hover { background:#f0f7ff; border-color:#bdd4ef; }
.edit-input {
  width:100%; border:2px solid var(--accent); border-radius:6px;
  padding:3px 6px; font-size:13px; font-family:inherit;
  background:#f0f7ff; outline:none;
}

/* Student detail panel */
.detail-panel {
  position:fixed; top:0; right:0; width:min(460px,100vw); height:100vh;
  background:var(--surface); box-shadow:-4px 0 30px rgba(0,0,0,0.15);
  z-index:1000; overflow-y:auto; transition:transform 0.3s ease;
  transform:translateX(100%);
}
.detail-panel.open { transform:translateX(0); }
.detail-overlay {
  position:fixed; top:0; left:0; width:100vw; height:100vh;
  background:rgba(0,0,0,0.3); z-index:999; opacity:0; pointer-events:none;
  transition:opacity 0.3s;
}
.detail-overlay.open { opacity:1; pointer-events:auto; }
.detail-header {
  padding:20px; background:linear-gradient(135deg,#1a3d66,#2d5a8e);
  color:white; position:sticky; top:0; z-index:1;
}
.detail-close { position:absolute; top:16px; right:16px; background:rgba(255,255,255,0.15); border:none; color:white; width:32px; height:32px; border-radius:50%; font-size:18px; cursor:pointer; }
.detail-body { padding:20px; }
.detail-field { margin-bottom:16px; }
.detail-label { font-size:11px; font-weight:700; text-transform:uppercase; letter-spacing:0.06em; color:var(--ink-muted); margin-bottom:4px; }
.detail-value { font-size:14px; padding:8px 10px; background:var(--surface-alt); border-radius:8px; border:1px solid rgba(0,0,0,0.06); }
.detail-input {
  width:100%; border:2px solid #ddd; border-radius:8px; padding:8px 10px;
  font-size:14px; font-family:inherit; background:white; outline:none; transition:border-color 0.2s;
}
.detail-input:focus { border-color:var(--accent); }
.detail-textarea {
  width:100%; min-height:160px; border:2px solid #ddd; border-radius:8px;
  padding:10px 12px; font-size:13px; font-family:inherit; line-height:1.6;
  background:white; outline:none; resize:vertical; transition:border-color 0.2s;
}
.detail-textarea:focus { border-color:var(--accent); }

.history-entry {
  padding:10px 12px; background:var(--surface-alt); border-radius:8px;
  margin-bottom:8px; border-left:3px solid var(--accent); font-size:13px;
}
.history-date { font-size:11px; color:var(--ink-muted); font-weight:600; }
.history-text { margin-top:4px; color:var(--ink-soft); }

.btn {
  padding:8px 16px; border:none; border-radius:8px; font-family:inherit;
  font-size:13px; font-weight:600; cursor:pointer; transition:all 0.2s;
}
.btn-primary { background:var(--accent); color:white; }
.btn-primary:hover { background:var(--accent-dark); }
.btn-danger { background:#ffebee; color:#c62828; }
.btn-danger:hover { background:#ffcdd2; }
.btn-ghost { background:transparent; color:var(--ink-soft); border:1px solid rgba(0,0,0,0.1); }
.btn-ghost:hover { background:var(--surface-alt); }

.toast {
  position:fixed; bottom:24px; left:50%; transform:translateX(-50%);
  background:var(--accent-dark); color:white; padding:10px 24px; border-radius:10px;
  font-size:14px; font-weight:600; z-index:9999; box-shadow:0 4px 20px rgba(0,0,0,0.2);
  animation:fadeIn 0.3s ease;
}

/* Cards for AEE and Aux */
.card-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(320px,1fr)); gap:12px; }
.card {
  background:var(--surface); border-radius:var(--radius); box-shadow:var(--shadow-sm);
  overflow:hidden; border:1px solid rgba(0,0,0,0.04); transition:box-shadow 0.2s;
}
.card:hover { box-shadow:var(--shadow-md); }
.card-head { padding:14px 16px; display:flex; justify-content:space-between; align-items:flex-start; }
.card-head.tea { background:linear-gradient(135deg,var(--tea-light),#d4ede9); border-bottom:2px solid var(--tea); }
.card-head.di { background:linear-gradient(135deg,var(--di-light),#f0e0d0); border-bottom:2px solid var(--di); }
.card-head.aux { background:var(--surface-alt); border-bottom:1px solid rgba(0,0,0,0.05); border-left:4px solid var(--accent); }
.card-code { font-family:'Playfair Display',serif; font-size:22px; font-weight:800; }
.card-code.tea { color:var(--tea); } .card-code.di { color:var(--di); }
.card-meta { text-align:right; }
.card-meta .prof { font-weight:600; font-size:14px; }
.card-meta .sched { font-size:12px; color:var(--ink-soft); }
.card-body { padding:8px 14px; }
.card-row {
  display:flex; justify-content:space-between; align-items:center;
  padding:6px 0; border-bottom:1px solid rgba(0,0,0,0.04); font-size:13px;
}
.card-row:last-child { border-bottom:none; }

.resumo-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(260px,1fr)); gap:12px; margin-bottom:16px; }
.resumo-card { background:var(--surface); border-radius:var(--radius); padding:16px; box-shadow:var(--shadow-sm); }
.resumo-card h3 { font-size:12px; text-transform:uppercase; color:var(--ink-muted); font-weight:700; margin-bottom:10px; letter-spacing:0.06em; }
.resumo-row { display:flex; justify-content:space-between; padding:5px 0; border-bottom:1px solid rgba(0,0,0,0.04); font-size:14px; }
.resumo-row .rl { color:var(--ink-soft); } .resumo-row .rv { font-weight:700; }
.resumo-total { display:flex; justify-content:space-between; padding:8px 0 0; border-top:2px solid var(--accent); margin-top:4px; font-size:14px; font-weight:700; color:var(--accent); }

.note-icon { cursor:pointer; font-size:16px; opacity:0.4; transition:opacity 0.15s; }
.note-icon:hover { opacity:1; }
.note-icon.has-notes { opacity:0.8; }

@media print {
  .hero { padding:1.5rem; print-color-adjust:exact; -webkit-print-color-adjust:exact; }
  .toolbar,.search-bar,.tabs,.edit-banner,.detail-panel,.detail-overlay,.toast { display:none !important; }
  .tab-content { display:block !important; page-break-before:always; }
  .tab-content:first-of-type { page-break-before:avoid; }
}
@media(max-width:768px) {
  .hero h1 { font-size:1.4rem; }
  .stats-grid { grid-template-columns:repeat(2,1fr); }
  .card-grid,.resumo-grid { grid-template-columns:1fr; }
  .detail-panel { width:100vw; }
}
</style>
</head>
<body>

<div id="app"></div>

<script>
// ═══ DATA ═══
const INITIAL = [
  {
    "id": 1,
    "n": "Beatriz de Mattos Rodrigues",
    "ra": "116250222",
    "turma": "1ª A",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": [
      {
        "data": "10/05/2026, 19:00",
        "texto": "Reuniao"
      }
    ]
  },
  {
    "id": 2,
    "n": "Davyd Fernandes Duarte",
    "ra": "111159980",
    "turma": "1ª B",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TG",
    "profAee": "Ana Carolina Pilla",
    "diasAee": "Seg e Qui",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 3,
    "n": "Estela Caitano Furtado",
    "ra": "111927107",
    "turma": "1ª B",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 4,
    "n": "Maria Eduarda Costa",
    "ra": "111463142",
    "turma": "1ª B",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 5,
    "n": "Eduardo Lima Pereira",
    "ra": "110797067",
    "turma": "1ª C",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "IB",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 6,
    "n": "Gustavo da Costa",
    "ra": "113818252",
    "turma": "1ª C",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TG",
    "profAee": "Ana Carolina Pilla",
    "diasAee": "Seg e Qui",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 7,
    "n": "Maria Luisa Matubaro Mareschachi",
    "ra": "111961617",
    "turma": "1ª C",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 8,
    "n": "Clara Accioli Baroni",
    "ra": "114923194",
    "turma": "1ª D",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 9,
    "n": "Diego Gabriel Santos Marciano",
    "ra": "112875851",
    "turma": "1ª D",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 10,
    "n": "Giuseppe Martins Isaac",
    "ra": "113092494",
    "turma": "1ª D",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TH",
    "profAee": "Ana Carolina Pilla",
    "diasAee": "Qua e Sex",
    "horAee": "12h40–15h10",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 11,
    "n": "Henrique Marques de Oliveira",
    "ra": "110645377",
    "turma": "1ª D",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TG",
    "profAee": "Ana Carolina Pilla",
    "diasAee": "Seg e Qui",
    "horAee": "12h40–15h10",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 12,
    "n": "Kauã Vinícius Rodrigues",
    "ra": "115981224",
    "turma": "1ª D",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "IB",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 13,
    "n": "Maria Eduarda Souza Porto",
    "ra": "111516453",
    "turma": "1ª D",
    "def": "Surdez Leve ou Moderada",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 14,
    "n": "Vitória Accioli Baroni",
    "ra": "114923311",
    "turma": "1ª D",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 15,
    "n": "Yasmin de Camargo Miguel Teixeira",
    "ra": "111932757",
    "turma": "1ª D",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "IB",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "Natalia Cristina Santana",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 16,
    "n": "Jhulia Victoria da Silva",
    "ra": "113912798",
    "turma": "2ª A",
    "def": "Múltipla, Física (PC), Intelectual",
    "etapa": "EM",
    "aee": "IC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Qua",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 17,
    "n": "Rafael Henrique de Méo",
    "ra": "114138304",
    "turma": "2ª A",
    "def": "Física - Outros",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 18,
    "n": "Dhavy Alves da Silva",
    "ra": "111898614",
    "turma": "2ª B",
    "def": "Síndrome de Asperger",
    "etapa": "EM",
    "aee": "TE",
    "profAee": "Allan",
    "diasAee": "Ter e Sex",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 19,
    "n": "Joaquim do Prado Esiquiel",
    "ra": "113850732",
    "turma": "2ª B",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Natali Dias de O. Baldan",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 20,
    "n": "Lorena Gabrielle T. de Souza",
    "ra": "112642815",
    "turma": "2ª B",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "IC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Qua",
    "horAee": "12h40–15h10",
    "profAux": "Natali Dias de O. Baldan",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 21,
    "n": "Maria Eduarda Gaona",
    "ra": "115173561",
    "turma": "2ª B",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EM",
    "aee": "TE",
    "profAee": "Allan",
    "diasAee": "Ter e Sex",
    "horAee": "12h40–15h10",
    "profAux": "Natali Dias de O. Baldan",
    "profColab": "Raphael / Ana Júlia",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 22,
    "n": "Maria Eduarda Napolitano do Rio",
    "ra": "112047107",
    "turma": "2ª B",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TF",
    "profAee": "Ana Júlia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "Natali Dias de O. Baldan",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 23,
    "n": "Giovana Martucci Baena",
    "ra": "112638427",
    "turma": "2ª C",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TF",
    "profAee": "Ana Júlia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 24,
    "n": "Miguel Silva Ferreira",
    "ra": "109674691",
    "turma": "2ª C",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "IC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Qua",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 25,
    "n": "Samuel Assis de Castro",
    "ra": "111512786",
    "turma": "2ª C",
    "def": "Intelectual, Sínd. de Asperger",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 26,
    "n": "Brayan Aguiar Teixeira",
    "ra": "111627030",
    "turma": "2ª D",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 27,
    "n": "Kaua Vinicius de A. M. da Silva",
    "ra": "110431858",
    "turma": "2ª D",
    "def": "Física - Outros",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 28,
    "n": "Ryan Emanoel Silva de Lima",
    "ra": "112879704",
    "turma": "2ª E",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TH",
    "profAee": "Ana Carolina Pilla",
    "diasAee": "Qua e Sex",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 29,
    "n": "Manuela Longo do Amaral",
    "ra": "111965486",
    "turma": "2ª F",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Andreia Vitorino de Souza",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 30,
    "n": "Rafaela Carolina Pomponio Vieira",
    "ra": "111512676",
    "turma": "2ª F",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Andreia Vitorino de Souza",
    "profColab": "Raphael / Ana Júlia",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 31,
    "n": "Bruno Vinícius Rigo Espinoza",
    "ra": "124971997",
    "turma": "3ª A",
    "def": "Surdez Severa ou Profunda",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 32,
    "n": "Murilo Carlos Del Ponte",
    "ra": "113075348",
    "turma": "3ª A",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 33,
    "n": "Vinícius Augusto Alves",
    "ra": "110127742",
    "turma": "3ª A",
    "def": "Surdez Leve ou Moderada",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 34,
    "n": "Hian Cipriano de Albuquerque",
    "ra": "110843400",
    "turma": "3ª B",
    "def": "Baixa Visão",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 35,
    "n": "Pedro Henrique Z. Zoccolotti",
    "ra": "110827045",
    "turma": "3ª B",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 36,
    "n": "Anna Julia Corrêa Ríos",
    "ra": "109912167",
    "turma": "3ª C",
    "def": "Autista Infantil",
    "etapa": "EM",
    "aee": "TE",
    "profAee": "Allan",
    "diasAee": "Ter e Sex",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 37,
    "n": "Isaque Oliveira Varandas",
    "ra": "111987632",
    "turma": "3ª C",
    "def": "Sínd. Asperger, Altas Habilidades",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 38,
    "n": "Gabriel de Alcântara S. Silvestre",
    "ra": "111111476",
    "turma": "3ª D",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 39,
    "n": "Gabriel Moreira Gatto",
    "ra": "110985696",
    "turma": "3ª D",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 40,
    "n": "Marshall Bortolotti Elias",
    "ra": "110762633",
    "turma": "3ª D",
    "def": "Síndrome de Asperger",
    "etapa": "EM",
    "aee": "TF",
    "profAee": "Ana Júlia",
    "diasAee": "Ter e Qui",
    "horAee": "12h40–15h10",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 41,
    "n": "Julia Martinez Villari Ferreira",
    "ra": "110769573",
    "turma": "3ª F",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 42,
    "n": "Vitória Oliveira dos Prazeres",
    "ra": "109101228",
    "turma": "3ª F",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 43,
    "n": "Kauã Carvalho de Alencar",
    "ra": "116261394",
    "turma": "3ª G (N)",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 44,
    "n": "Nicoli Nicoletti de Souza",
    "ra": "109802821",
    "turma": "3ª G (N)",
    "def": "Baixa Visão",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 45,
    "n": "Sabrina Nepomuceno Camargo",
    "ra": "108121358",
    "turma": "3ª G (N)",
    "def": "Intelectual",
    "etapa": "EM",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Raphael / Ana Júlia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 46,
    "n": "Cauã do Prado Firmino",
    "ra": "116258988",
    "turma": "6° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 47,
    "n": "Felipe Massao Lins Bunno",
    "ra": "114321548",
    "turma": "6° A",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EF",
    "aee": "IA",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "09h30–12h00",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 48,
    "n": "Ismael Eduardo Vieira Fernandes",
    "ra": "120323935",
    "turma": "6° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 49,
    "n": "Leonardo Baglioni de Campos",
    "ra": "114332245",
    "turma": "6° A",
    "def": "Surdez Leve ou Moderada",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 50,
    "n": "Samuel Guilherme Vicente Cunha",
    "ra": "115396785",
    "turma": "6° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 51,
    "n": "Vicente Sutil dos Santos",
    "ra": "115091371",
    "turma": "6° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Gabrieli dos S. Catoia",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 52,
    "n": "Ana Carolina Lopes da Silva",
    "ra": "115585416",
    "turma": "6° B",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Ter",
    "horAee": "09h30–12h00",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 53,
    "n": "Felipe Leonardo Lorza",
    "ra": "120216224",
    "turma": "6° B",
    "def": "Surdez Leve ou Moderada",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 54,
    "n": "Onel Gabriel Columbie Fernandez",
    "ra": "124989060",
    "turma": "6° B",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 55,
    "n": "Vitoria Gandara Pande",
    "ra": "115092660",
    "turma": "6° B",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 56,
    "n": "Eduardo Creofas G. de Oliveira",
    "ra": "115261567",
    "turma": "6° D",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 57,
    "n": "Isabella Moreira Bento",
    "ra": "120398756",
    "turma": "6° D",
    "def": "Física - Outros",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 58,
    "n": "Nicolas Davi Goncalves Sobral",
    "ra": "116467221",
    "turma": "6° D",
    "def": "Física - Outros",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 59,
    "n": "Pedro Henrique de Oliveira Garcia",
    "ra": "114427374",
    "turma": "6° D",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 60,
    "n": "Thiago Lorenzo de A. Donofrio",
    "ra": "115252444",
    "turma": "7° A",
    "def": "Física - Outros",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 61,
    "n": "Alice Quio Bertolini Geraldino",
    "ra": "115621923",
    "turma": "7° B",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 62,
    "n": "Gabriel Costa Peres",
    "ra": "120162240",
    "turma": "7° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Sthéfany A. C. M. Oliveira",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 63,
    "n": "Jady da Silva Rocha",
    "ra": "125677097",
    "turma": "7° C",
    "def": "Intelectual, Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Sthéfany A. C. M. Oliveira",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 64,
    "n": "João Alves Ferreira da Costa",
    "ra": "114904805",
    "turma": "7° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TB",
    "profAee": "Raphael",
    "diasAee": "Seg e Ter",
    "horAee": "07h00–09h30",
    "profAux": "Sthéfany A. C. M. Oliveira",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 65,
    "n": "Pedro da Costa Amedi Ribeiro",
    "ra": "124998664",
    "turma": "7° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Ter",
    "horAee": "09h30–12h00",
    "profAux": "Sthéfany A. C. M. Oliveira",
    "profColab": "Ana Carolina Pilla",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 66,
    "n": "Rosana Gabriella Vico Rivas",
    "ra": "121994006",
    "turma": "7° D",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TB",
    "profAee": "Raphael",
    "diasAee": "Seg e Ter",
    "horAee": "07h00–09h30",
    "profAux": "—",
    "profColab": "Ana Carolina Pilla",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 67,
    "n": "Alexandre Bernaldes Marcelino Jr.",
    "ra": "112509212",
    "turma": "8° A",
    "def": "Intelectual",
    "etapa": "EF",
    "aee": "IA",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "09h30–12h00",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 68,
    "n": "Ana Julia do Nascimento",
    "ra": "113248171",
    "turma": "8° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TA",
    "profAee": "Raphael",
    "diasAee": "Qua e Qui",
    "horAee": "08h40–11h10",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 69,
    "n": "Rafael Davi Parizotto Godoy",
    "ra": "113322215",
    "turma": "8° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 70,
    "n": "Cassio Roberth Craveiro Cavaletto",
    "ra": "113200355",
    "turma": "8° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Lucilene Cristina Pompeu",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 71,
    "n": "Kewen Taborda",
    "ra": "114038010",
    "turma": "8° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Lucilene Cristina Pompeu",
    "profColab": "Ana Claudia",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 72,
    "n": "Matheus Henrique F. da Silva",
    "ra": "114014260",
    "turma": "8° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Lucilene Cristina Pompeu",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 73,
    "n": "Douglas Miguel Parizotto Godoy",
    "ra": "113322252",
    "turma": "8° D",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 74,
    "n": "Eiky Lucas Cardoso Costa",
    "ra": "112652381",
    "turma": "8° D",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TA",
    "profAee": "Raphael",
    "diasAee": "Qua e Qui",
    "horAee": "08h40–11h10",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 75,
    "n": "Juliana da Silva E. de Carvalho",
    "ra": "114899638",
    "turma": "9° A",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 76,
    "n": "Guilherme Henrique Faitanini",
    "ra": "114335065",
    "turma": "9° B",
    "def": "Autista Infantil, Sínd. Asperger",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 77,
    "n": "Andrey Amaral Tenorio",
    "ra": "113088374",
    "turma": "9° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TC",
    "profAee": "Ana Júlia",
    "diasAee": "Seg e Ter",
    "horAee": "09h30–12h00",
    "profAux": "Silene Fernandes",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 78,
    "n": "Daniel Isac Moreira dos Santos",
    "ra": "113103037",
    "turma": "9° C",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Silene Fernandes",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 79,
    "n": "Enzo Miguel Sanches Coutinho",
    "ra": "112642329",
    "turma": "9° C",
    "def": "Intelectual",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "Silene Fernandes",
    "profColab": "Ana Claudia",
    "oj": true,
    "obs": "",
    "historico": []
  },
  {
    "id": 80,
    "n": "Gabrielle Vitória Fonseca",
    "ra": "113054379",
    "turma": "9° D",
    "def": "Intelectual",
    "etapa": "EF",
    "aee": "IA",
    "profAee": "Ana Claudia",
    "diasAee": "Ter e Qui",
    "horAee": "09h30–12h00",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 81,
    "n": "Joanna Oliver Batista",
    "ra": "112580168",
    "turma": "9° D",
    "def": "Surdez Leve ou Moderada",
    "etapa": "EF",
    "aee": "—",
    "profAee": "—",
    "diasAee": "—",
    "horAee": "—",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  },
  {
    "id": 82,
    "n": "Davi Augusto Ferreira da Silva",
    "ra": "126247639",
    "turma": "9° E",
    "def": "Autista Infantil",
    "etapa": "EF",
    "aee": "TB",
    "profAee": "Raphael",
    "diasAee": "Seg e Ter",
    "horAee": "07h00–09h30",
    "profAux": "—",
    "profColab": "Ana Claudia",
    "oj": false,
    "obs": "",
    "historico": []
  }
];

// ═══ STATE ═══
let data = [];
let activeTab = 'mapao';
let search = '';
let detailId = null;
let editMode = false;
let editingCell = null;

const KEY = 'mapao_ed_especial_2026';
function save() { try { localStorage.setItem(KEY, JSON.stringify(data)); toast('💾 Salvo!'); } catch(e) { toast('❌ Erro ao salvar'); } }
function load() {
  // Check if data version changed (new upload)
  const version = '98987';
  try { if (localStorage.getItem(KEY+'_v') !== version) { localStorage.removeItem(KEY); localStorage.setItem(KEY+'_v', version); } } catch(e) {}
  try { const s = localStorage.getItem(KEY); if (s) { const p = JSON.parse(s); if (Array.isArray(p) && p.length) return p.map(a => ({...a, obs: a.obs||'', historico: a.historico||[]})); } } catch(e) {}
  return INITIAL.map(a => ({...a}));
}

function toast(msg) {
  const old = document.querySelector('.toast'); if (old) old.remove();
  const t = document.createElement('div'); t.className='toast'; t.textContent=msg;
  document.body.appendChild(t); setTimeout(()=>t.remove(), 2000);
}

function defBadges(d) {
  let h=''; const l=d.toLowerCase();
  if(l.includes('autist')) h+='<span class="badge b-tea">TEA</span>';
  if(l.includes('asperger')) h+='<span class="badge b-tea">Asperger</span>';
  if(l.includes('intelectual')) h+='<span class="badge b-di">DI</span>';
  if(l.includes('físic')||l.includes('fisic')) h+='<span class="badge b-df">DF</span>';
  if(l.includes('surdez')) h+='<span class="badge b-surdez">Surdez</span>';
  if(l.includes('baixa vis')) h+='<span class="badge b-visao">Baixa Visão</span>';
  if(l.includes('altas hab')||l.includes('superdot')) h+='<span class="badge b-ah">AH/SD</span>';
  if(l.includes('múltipla')||l.includes('multipla')) h+='<span class="badge b-multipla">Múltipla</span>';
  return h;
}

function dateStr() { return new Date().toLocaleDateString('pt-BR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'}); }

function filtered() {
  if (!search) return data;
  const q = search.toLowerCase();
  return data.filter(a => [a.n,a.ra,a.turma,a.def,a.aee,a.profAux,a.profColab,a.obs].some(v=>(v||'').toLowerCase().includes(q)));
}

function turmasOf(list) {
  const m = {}; list.forEach(a => { if(!m[a.turma]) m[a.turma]=[]; m[a.turma].push(a); });
  return Object.entries(m);
}

// ═══ RENDER ═══
function render() {
  const f = filtered();
  const em = f.filter(a=>a.etapa==='EM');
  const ef = f.filter(a=>a.etapa==='EF');
  const stats = { total:data.length, em:data.filter(a=>a.etapa==='EM').length, ef:data.filter(a=>a.etapa==='EF').length, aee:data.filter(a=>a.aee!=='—').length, aux:new Set(data.filter(a=>a.profAux!=='—').map(a=>a.profAux)).size, oj:data.filter(a=>a.oj).length };

  document.getElementById('app').innerHTML = `
    <header class="hero"><div class="hero-inner">
      <h1>Educação Especial</h1>
      <p class="sub">E.E. Dr. Álvaro Guião — São Carlos, SP</p>
      <div class="toolbar">
        <span class="pill" style="cursor:default">ANO LETIVO 2026</span>
        <span class="pill ${editMode?'active':''}" onclick="toggleEdit()">${editMode?'✏️ EDIÇÃO ATIVA':'🔒 Ativar Edição'}</span>
        ${editMode?`<span class="pill green" onclick="addAluno()">➕ Novo Aluno</span><span class="pill red" onclick="resetAll()">🔄 Restaurar</span><span class="pill blue" onclick="exportData()">📥 Exportar JSON</span><span class="pill blue" onclick="document.getElementById('importFile').click()">📤 Importar JSON</span><input type="file" id="importFile" accept=".json" style="display:none" onchange="importData(event)">`:''}
      </div>
    </div></header>

    <div class="stats-bar"><div class="stats-grid">
      ${[{n:stats.total,l:'Alunos PAEE'},{n:stats.em,l:'Ensino Médio'},{n:stats.ef,l:'Ens. Fundamental'},{n:stats.aee,l:'Com AEE'},{n:stats.aux,l:'Prof. Auxiliares'},{n:stats.oj,l:'Ordens Judiciais'}].map(s=>`<div class="stat-card"><div class="stat-num">${s.n}</div><div class="stat-lbl">${s.l}</div></div>`).join('')}
    </div></div>

    <div class="container">
      <div class="search-bar">
        <span>🔍</span>
        <input value="${search}" oninput="search=this.value;render()" placeholder="Buscar aluno por nome, RA, turma, deficiência...">
        ${search?`<span class="search-count">${f.length} de ${data.length}</span>`:''}
      </div>

      <div class="tabs">
        ${['mapao:📋 Mapão','aee:🧩 AEE','aux:👩‍🏫 Auxiliares','resumo:📊 Resumo'].map(t=>{const[id,lb]=t.split(':');return`<button class="tab ${activeTab===id?'active':''}" onclick="activeTab='${id}';render()">${lb}</button>`;}).join('')}
      </div>

      ${editMode?'<div class="edit-banner">✏️ <strong>Modo edição ativo</strong> — Clique em qualquer campo para editar. Clique no 📝 para abrir o painel de histórico. Tudo salva automaticamente.</div>':''}

      <div class="tab-content ${activeTab==='mapao'?'active':''}">
        ${renderMapao(em, ef)}
      </div>
      <div class="tab-content ${activeTab==='aee'?'active':''}">
        ${renderAee(f)}
      </div>
      <div class="tab-content ${activeTab==='aux'?'active':''}">
        ${renderAux(f)}
      </div>
      <div class="tab-content ${activeTab==='resumo'?'active':''}">
        ${renderResumo()}
      </div>
    </div>

    <div class="detail-overlay ${detailId?'open':''}" onclick="closeDetail()"></div>
    <div class="detail-panel ${detailId?'open':''}">
      ${detailId ? renderDetail(data.find(a=>a.id===detailId)) : ''}
    </div>
  `;
}

function renderMapao(em, ef) {
  return [
    {label:'📘 Ensino Médio',list:em,total:data.filter(a=>a.etapa==='EM').length},
    {label:'📗 Ensino Fundamental',list:ef,total:data.filter(a=>a.etapa==='EF').length}
  ].map(sec => `
    <div class="section-title"><h2>${sec.label}</h2><span class="badge b-cnt">${sec.total} alunos</span></div>
    ${turmasOf(sec.list).map(([turma, als]) => `
      <div class="turma-group">
        <div class="turma-header"><span style="font-weight:700;font-size:14px;color:var(--accent-dark)">${turma}</span><span class="badge b-cnt">${als.length}</span></div>
        <div style="overflow-x:auto">
          <table><thead><tr>
            <th style="width:35px">Nº</th><th>Nome</th><th>RA</th><th>Deficiência</th><th>AEE</th><th>Prof. Aux.</th><th>OJ</th><th style="width:35px">📝</th>
            ${editMode?'<th style="width:35px">🗑️</th>':''}
          </tr></thead><tbody>
          ${als.map((a,i) => `
            <tr class="${a.oj?'oj-row':''}">
              <td class="col-num">${i+1}</td>
              <td style="font-weight:500">${editMode?`<div class="editable" onclick="startEdit(${a.id},'n')">${a.n}</div>`:`<span style="cursor:pointer;text-decoration:underline dotted;text-underline-offset:3px" onclick="openDetail(${a.id})">${a.n}</span>`}</td>
              <td style="font-family:monospace;font-size:12px;color:var(--ink-soft)">${editMode?`<div class="editable" onclick="startEdit(${a.id},'ra')">${a.ra}</div>`:a.ra}</td>
              <td>${editMode?`<div class="editable" onclick="startEdit(${a.id},'def')">${a.def}</div>`:defBadges(a.def)}</td>
              <td class="col-center">${editMode?`<div class="editable" onclick="startEdit(${a.id},'aee')">${a.aee}</div>`:(a.aee!=='—'?`<span class="badge b-aee">${a.aee}</span>`:'<span style="color:#ccc">—</span>')}</td>
              <td style="font-size:12px">${editMode?`<div class="editable" onclick="startEdit(${a.id},'profAux')">${a.profAux}</div>`:(a.profAux!=='—'?a.profAux:'<span style="color:#ccc">—</span>')}</td>
              <td class="col-center">${editMode?`<span style="cursor:pointer;font-size:18px" onclick="toggleOJ(${a.id})">${a.oj?'⚖️':'◻️'}</span>`:(a.oj?'<span class="badge b-oj">OJ</span>':'')}</td>
              <td class="col-center"><span class="note-icon ${(a.obs||a.historico.length)?'has-notes':''}" onclick="openDetail(${a.id})">${(a.obs||a.historico.length)?'📝':'📄'}</span></td>
              ${editMode?`<td class="col-center"><span class="note-icon" onclick="removeAluno(${a.id})">🗑️</span></td>`:''}
            </tr>
          `).join('')}
          </tbody></table>
        </div>
      </div>
    `).join('')}
  `).join('');
}

function renderAee(f) {
  const turmas = [
    {code:"IA",type:"DI",cat:"di",prof:"Ana Claudia",dias:"Ter e Qui",hor:"09h30–12h00"},
    {code:"IB",type:"DI",cat:"di",prof:"Ana Claudia",dias:"Ter e Qui",hor:"12h40–15h10"},
    {code:"IC",type:"DI",cat:"di",prof:"Ana Júlia",dias:"Seg e Qua",hor:"12h40–15h10"},
    {code:"TA",type:"TEA",cat:"tea",prof:"Raphael",dias:"Qua e Qui",hor:"08h40–11h10"},
    {code:"TB",type:"TEA",cat:"tea",prof:"Raphael",dias:"Seg e Ter",hor:"07h00–09h30"},
    {code:"TC",type:"TEA",cat:"tea",prof:"Ana Júlia",dias:"Seg e Ter",hor:"09h30–12h00"},
    {code:"TE",type:"TEA",cat:"tea",prof:"Allan",dias:"Ter e Sex",hor:"12h40–15h10"},
    {code:"TF",type:"TEA",cat:"tea",prof:"Ana Júlia",dias:"Ter e Qui",hor:"12h40–15h10"},
    {code:"TG",type:"TEA",cat:"tea",prof:"Ana Carolina Pilla",dias:"Seg e Qui",hor:"12h40–15h10"},
    {code:"TH",type:"TEA",cat:"tea",prof:"Ana Carolina Pilla",dias:"Qua e Sex",hor:"12h40–15h10"},
  ];
  return ['di','tea'].map(cat => {
    const title = cat==='di'?'📋 Turmas DI':'🧩 Turmas TEA';
    return `<div class="section-title"><h2>${title}</h2></div><div class="card-grid">
      ${turmas.filter(t=>t.cat===cat).map(t=>{
        const als = f.filter(a=>a.aee===t.code);
        if(!als.length) return '';
        return `<div class="card"><div class="card-head ${cat}">
          <span class="card-code ${cat}">${t.code}</span>
          <div class="card-meta"><div class="prof">${t.prof}</div><div class="sched">${t.dias} · ${t.hor}</div><div class="sched">${als.length} aluno${als.length>1?'s':''}</div></div>
        </div><div class="card-body">
          ${als.map(a=>`<div class="card-row"><span style="cursor:pointer" onclick="openDetail(${a.id})">${a.n}</span><span style="font-size:12px;color:var(--ink-soft)">${a.turma}</span></div>`).join('')}
        </div></div>`;
      }).join('')}
    </div>`;
  }).join('');
}

function renderAux(f) {
  const m = {}; f.filter(a=>a.profAux!=='—').forEach(a=>{ if(!m[a.profAux]) m[a.profAux]={turma:a.turma,als:[]}; m[a.profAux].als.push(a); });
  return `<div class="section-title"><h2>👩‍🏫 Professoras Auxiliares</h2><span class="badge b-cnt">${Object.keys(m).length} profissionais</span></div>
    <div class="card-grid">${Object.entries(m).map(([prof,d])=>`
      <div class="card"><div class="card-head aux" style="border-left:4px solid var(--accent)">
        <div><div style="font-weight:700;font-size:15px;color:var(--accent-dark)">👩‍🏫 ${prof}</div><div style="font-size:13px;color:var(--ink-soft)">Sala: ${d.turma} · ${d.als.length} aluno${d.als.length>1?'s':''}</div></div>
      </div><div class="card-body">
        ${d.als.map(a=>`<div class="card-row"><span style="cursor:pointer" onclick="openDetail(${a.id})">${a.oj?'⚖️ ':''}${a.n}</span><span>${defBadges(a.def)}${a.oj?'<span class="badge b-oj">OJ</span>':''}</span></div>`).join('')}
      </div></div>
    `).join('')}</div>`;
}

function renderResumo() {
  const cnt = (fn) => data.filter(fn).length;
  return `<div class="section-title"><h2>📊 Resumo Geral</h2></div>
    <div class="resumo-grid">
      <div class="resumo-card"><h3>Por Etapa</h3>
        <div class="resumo-row"><span class="rl">Ensino Médio</span><span class="rv">${cnt(a=>a.etapa==='EM')}</span></div>
        <div class="resumo-row"><span class="rl">Ensino Fundamental</span><span class="rv">${cnt(a=>a.etapa==='EF')}</span></div>
        <div class="resumo-total"><span>Total Geral</span><span>${data.length}</span></div>
      </div>
      <div class="resumo-card"><h3>Atendimentos</h3>
        <div class="resumo-row"><span class="rl">Com turma AEE</span><span class="rv">${cnt(a=>a.aee!=='—')}</span></div>
        <div class="resumo-row"><span class="rl">Sem turma AEE</span><span class="rv">${cnt(a=>a.aee==='—')}</span></div>
        <div class="resumo-row"><span class="rl">Com Prof. Auxiliar</span><span class="rv">${cnt(a=>a.profAux!=='—')}</span></div>
        <div class="resumo-row"><span class="rl">Com Ordem Judicial</span><span class="rv">${cnt(a=>a.oj)}</span></div>
        <div class="resumo-row"><span class="rl">Com Histórico/Obs.</span><span class="rv">${cnt(a=>a.obs||a.historico.length)}</span></div>
      </div>
      <div class="resumo-card"><h3>Por Modalidade *</h3>
        ${[['TEA — Autismo',a=>/autist/i.test(a.def)],['TEA — Asperger',a=>/asperger/i.test(a.def)],['Def. Intelectual',a=>/intelectual/i.test(a.def)],['Def. Física',a=>/físic|fisic/i.test(a.def)],['Surdez',a=>/surdez/i.test(a.def)],['Baixa Visão',a=>/baixa vis/i.test(a.def)],['Altas Habilidades',a=>/altas hab/i.test(a.def)]].map(([l,fn])=>{const c=cnt(fn);return c?`<div class="resumo-row"><span class="rl">${l}</span><span class="rv">${c}</span></div>`:''}).join('')}
        <p style="font-size:11px;color:#999;font-style:italic;margin-top:8px">* Aluno pode contar em mais de uma</p>
      </div>
    </div>
    <div class="section-title"><h2>👥 Quadro de Profissionais</h2></div>
    <div class="resumo-grid">
      <div class="resumo-card"><h3>Ensino Colaborativo</h3>
        ${[['Raphael Manzini','1ª–3ª EM'],['Ana Júlia','1ª–3ª EM'],['Ana Carolina Pilla','6º–7º EF'],['Ana Claudia','8º–9º EF']].map(([p,s])=>`<div class="resumo-row"><span class="rl">${p}</span><span class="rv" style="font-size:12px">${s}</span></div>`).join('')}
      </div>
      <div class="resumo-card"><h3>AEE</h3>
        ${[['Raphael Manzini','TA, TB'],['Ana Júlia','IC, TC, TF'],['Ana Carolina Pilla','TG, TH'],['Ana Claudia','IA, IB'],['Allan','TE']].map(([p,s])=>`<div class="resumo-row"><span class="rl">${p}</span><span class="rv" style="font-size:12px">${s}</span></div>`).join('')}
      </div>
      <div class="resumo-card"><h3>Totais</h3>
        <div class="resumo-row"><span class="rl">Prof. Auxiliares</span><span class="rv">7</span></div>
        <div class="resumo-row"><span class="rl">Ensino Colaborativo</span><span class="rv">4</span></div>
        <div class="resumo-row"><span class="rl">AEE</span><span class="rv">5</span></div>
        <div class="resumo-total"><span>Total (sem repetição)</span><span>12</span></div>
        <p style="font-size:11px;color:#999;font-style:italic;margin-top:8px">4 atuam em dupla função</p>
      </div>
    </div>`;
}

function renderDetail(a) {
  if (!a) return '';
  const isEdit = editMode;
  return `
    <div class="detail-header">
      <button class="detail-close" onclick="closeDetail()">✕</button>
      <h2 style="font-family:'Playfair Display',serif;font-size:1.3rem;margin-bottom:4px">${a.n}</h2>
      <div style="opacity:0.85;font-size:14px">${a.turma} · ${a.etapa==='EM'?'Ensino Médio':'Ensino Fundamental'}</div>
      <div style="margin-top:8px">${defBadges(a.def)} ${a.oj?'<span class="badge b-oj">Ordem Judicial</span>':''}</div>
    </div>
    <div class="detail-body">
      <div class="detail-field"><div class="detail-label">RA</div><div class="detail-value">${a.ra}</div></div>
      <div class="detail-field"><div class="detail-label">Deficiência</div><div class="detail-value">${a.def}</div></div>
      <div class="detail-field"><div class="detail-label">Turma AEE</div><div class="detail-value">${a.aee!=='—'?a.aee+' — '+a.profAee+' ('+a.diasAee+', '+a.horAee+')':'Sem turma AEE atribuída'}</div></div>
      <div class="detail-field"><div class="detail-label">Professor(a) Auxiliar</div><div class="detail-value">${a.profAux!=='—'?a.profAux:'Sem prof. auxiliar'}</div></div>
      <div class="detail-field"><div class="detail-label">Ensino Colaborativo</div><div class="detail-value">${a.profColab}</div></div>

      <hr style="border:none;border-top:2px solid var(--accent-light);margin:20px 0">

      <div class="detail-field">
        <div class="detail-label">📌 Observações Gerais</div>
        <textarea class="detail-textarea" placeholder="Informações importantes sobre o aluno, laudos, medicações, contatos da família..." oninput="updateObs(${a.id},this.value)">${a.obs||''}</textarea>
      </div>

      <div class="detail-field">
        <div class="detail-label" style="display:flex;justify-content:space-between;align-items:center">
          <span>📜 Histórico de Acompanhamento</span>
          <span class="badge b-cnt">${a.historico.length} registro${a.historico.length!==1?'s':''}</span>
        </div>
        <div style="margin-top:8px">
          <textarea class="detail-textarea" id="newHistEntry" style="min-height:80px" placeholder="Registre aqui uma observação, ocorrência ou evolução do aluno..."></textarea>
          <div style="display:flex;gap:8px;margin-top:8px">
            <button class="btn btn-primary" onclick="addHistorico(${a.id})">➕ Adicionar ao Histórico</button>
          </div>
        </div>
        <div style="margin-top:16px">
          ${a.historico.length?a.historico.slice().reverse().map((h,i)=>`
            <div class="history-entry">
              <div style="display:flex;justify-content:space-between;align-items:center">
                <span class="history-date">📅 ${h.data}</span>
                ${editMode?`<span class="note-icon" onclick="removeHistorico(${a.id},${a.historico.length-1-i})">🗑️</span>`:''}
              </div>
              <div class="history-text">${h.texto.replace(/\n/g,'<br>')}</div>
            </div>
          `).join(''):'<p style="color:var(--ink-muted);font-size:13px;font-style:italic;padding:12px 0">Nenhum registro no histórico ainda. Use o campo acima para adicionar.</p>'}
        </div>
      </div>
    </div>
  `;
}

// ═══ ACTIONS ═══
function toggleEdit() { editMode=!editMode; render(); }
function toggleOJ(id) { const a=data.find(x=>x.id===id); a.oj=!a.oj; save(); render(); }
function openDetail(id) { detailId=id; render(); }
function closeDetail() { detailId=null; render(); }

function startEdit(id, field) {
  if (!editMode) return;
  const a = data.find(x=>x.id===id);
  const el = event.currentTarget;
  const val = a[field];
  el.innerHTML = `<input class="edit-input" value="${val.replace(/"/g,'&quot;')}" onblur="finishEdit(${id},'${field}',this.value)" onkeydown="if(event.key==='Enter'){this.blur()}if(event.key==='Escape'){this.value='${val.replace(/'/g,"\\'")}';this.blur()}" autofocus>`;
  el.querySelector('input').focus();
}
function finishEdit(id, field, val) { const a=data.find(x=>x.id===id); if(a[field]!==val){a[field]=val;save();} render(); }

function updateObs(id, val) { const a=data.find(x=>x.id===id); a.obs=val; clearTimeout(window._obsSave); window._obsSave=setTimeout(()=>{save()},800); }

function addHistorico(id) {
  const el = document.getElementById('newHistEntry');
  const text = el.value.trim();
  if (!text) { toast('⚠️ Escreva algo antes de adicionar'); return; }
  const a = data.find(x=>x.id===id);
  a.historico.push({ data: dateStr(), texto: text });
  save(); render(); openDetail(id);
}

function removeHistorico(id, idx) {
  if (!confirm('Remover este registro do histórico?')) return;
  const a = data.find(x=>x.id===id);
  a.historico.splice(idx, 1);
  save(); render(); openDetail(id);
}

function addAluno() {
  const newId = Math.max(...data.map(a=>a.id))+1;
  data.push({id:newId,n:"Novo Aluno",ra:"000000000",turma:"—",def:"—",etapa:"EM",aee:"—",profAee:"—",diasAee:"—",horAee:"—",profAux:"—",profColab:"—",oj:false,obs:"",historico:[]});
  save(); render(); toast('➕ Aluno adicionado!');
}

function removeAluno(id) {
  const a = data.find(x=>x.id===id);
  if (!confirm(`Remover ${a.n}?`)) return;
  data = data.filter(x=>x.id!==id);
  save(); render(); toast('🗑️ Aluno removido');
}

function resetAll() {
  if (!confirm('Restaurar TODOS os dados ao original? Observações e históricos serão perdidos.')) return;
  data = INITIAL.map(a=>({...a}));
  save(); render(); toast('🔄 Dados restaurados!');
}

function exportData() {
  const blob = new Blob([JSON.stringify(data, null, 2)], {type:'application/json'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a'); a.href=url; a.download='mapao_educacao_especial_backup.json'; a.click();
  URL.revokeObjectURL(url);
  toast('📥 Arquivo exportado!');
}

function importData(event) {
  const file = event.target.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    try {
      const imported = JSON.parse(e.target.result);
      if (!Array.isArray(imported)) throw new Error();
      data = imported.map(a=>({...a, obs:a.obs||'', historico:a.historico||[]}));
      save(); render(); toast('📤 Dados importados com sucesso!');
    } catch(err) { toast('❌ Erro: arquivo inválido'); }
  };
  reader.readAsText(file);
  event.target.value = '';
}

// ═══ INIT ═══
data = load();
render();
</script>
</body>
</html>
