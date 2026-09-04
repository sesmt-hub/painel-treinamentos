[index.html](https://github.com/user-attachments/files/31834071/index.html)
<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Painel Treinamentos Rede HG</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link id="fonts" rel="stylesheet" href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500;600;700&amp;family=IBM+Plex+Sans+Condensed:wght@500;600;700&amp;family=IBM+Plex+Mono:wght@400;500;600&amp;display=swap">
<style id="css-painel">
:root{
  color-scheme: light;
  --bg:#D7E3F5; --surface:#FFFFFF; --surface-2:#F3F7FD; --surface-3:#E3EBF7;
  --ink:#0C1A2E; --ink-2:#41536D; --muted:#73849D;
  --grid:#DCE5F2; --hair:rgba(12,26,46,.14); --hair-soft:rgba(12,26,46,.07);
  --accent:#14488F; --accent-ink:#FFFFFF; --accent-soft:#E4EDFA;
  --good:#0ca30c; --warn:#b07800; --crit:#d03b3b;
  --bar:#2a78d6; --pend:#C9D6E8;
  --s100:#cde2fb; --s200:#9ec5f4; --s300:#6da7ec; --s450:#2a78d6; --s550:#1c5cab; --s650:#104281;
  --shadow:0 1px 2px rgba(12,26,46,.07), 0 10px 28px -18px rgba(12,26,46,.40);
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    color-scheme: dark;
    --bg:#060E1B; --surface:#101B2C; --surface-2:#16233A; --surface-3:#1F2F49;
    --ink:#E8EEF7; --ink-2:#A9B8CD; --muted:#7A8AA3;
    --grid:#22334F; --hair:rgba(255,255,255,.14); --hair-soft:rgba(255,255,255,.07);
    --accent:#6BA6F0; --accent-ink:#06101F; --accent-soft:#152643;
    --good:#0ca30c; --warn:#e0a72a; --crit:#e05c5c;
    --bar:#3987e5; --pend:#26374F;
    --s100:#104281; --s200:#184f95; --s300:#256abf; --s450:#3987e5; --s550:#6da7ec; --s650:#9ec5f4;
    --shadow:0 1px 2px rgba(0,0,0,.5), 0 10px 28px -18px rgba(0,0,0,.9);
  }
}
:root[data-theme="dark"]{
  color-scheme: dark;
  --bg:#060E1B; --surface:#101B2C; --surface-2:#16233A; --surface-3:#1F2F49;
  --ink:#E8EEF7; --ink-2:#A9B8CD; --muted:#7A8AA3;
  --grid:#22334F; --hair:rgba(255,255,255,.14); --hair-soft:rgba(255,255,255,.07);
  --accent:#6BA6F0; --accent-ink:#06101F; --accent-soft:#152643;
  --good:#0ca30c; --warn:#e0a72a; --crit:#e05c5c;
  --bar:#3987e5; --pend:#26374F;
  --s100:#104281; --s200:#184f95; --s300:#256abf; --s450:#3987e5; --s550:#6da7ec; --s650:#9ec5f4;
  --shadow:0 1px 2px rgba(0,0,0,.5), 0 10px 28px -18px rgba(0,0,0,.9);
}

*{box-sizing:border-box}
body{
  margin:0; background:var(--bg); color:var(--ink);
  font-family:"IBM Plex Sans", system-ui, -apple-system, "Segoe UI", sans-serif;
  font-size:14px; line-height:1.45; -webkit-font-smoothing:antialiased;
}
.wrap{max-width:1280px; margin:0 auto; padding:20px 20px 64px}

.top{
  display:flex; flex-wrap:wrap; align-items:center; gap:18px;
  padding-bottom:14px; margin-bottom:16px; border-bottom:2px solid var(--accent);
}
.logo{
  height:62px; width:auto; display:block; flex:none;
  background:#FFFFFF; padding:8px 12px; border-radius:11px;
  border:1px solid var(--hair); box-shadow:var(--shadow);
}
.brandmark{
  font-family:"IBM Plex Sans Condensed", sans-serif; font-weight:700;
  font-size:11px; letter-spacing:.16em; text-transform:uppercase; color:var(--accent);
}
h1{
  font-family:"IBM Plex Sans Condensed", sans-serif; font-weight:700;
  font-size:clamp(22px,3.2vw,30px); line-height:1.05; margin:4px 0 2px; letter-spacing:-.01em;
  text-wrap:balance;
}
.sub{color:var(--ink-2); font-size:13px; margin:0}
.top .meta{margin-left:auto; text-align:right; color:var(--ink-2); font-size:11.5px;
  font-family:"IBM Plex Mono", monospace; line-height:1.6}

.filters{
  background:var(--surface); border:1px solid var(--hair); border-radius:10px;
  padding:12px 14px; margin-bottom:16px; box-shadow:var(--shadow);
  display:flex; flex-wrap:wrap; gap:16px; align-items:flex-end;
}
.fgroup{display:flex; flex-direction:column; gap:6px; min-width:0}
.flabel{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:10.5px; font-weight:600;
  letter-spacing:.12em; text-transform:uppercase; color:var(--muted);
}
.seg{display:flex; flex-wrap:wrap; gap:4px; background:var(--surface-3); padding:3px; border-radius:8px}
.seg button{
  font:inherit; font-size:12.5px; font-weight:500; border:0; cursor:pointer;
  background:transparent; color:var(--ink-2); padding:6px 11px; border-radius:6px;
  white-space:nowrap; transition:background .12s, color .12s;
}
.seg button:hover{background:var(--surface)}
.seg button[aria-pressed="true"]{background:var(--accent); color:var(--accent-ink); font-weight:600}
select, input[type="search"]{
  font:inherit; font-size:13px; color:var(--ink); background:var(--surface);
  border:1px solid var(--hair); border-radius:7px; padding:7px 10px; min-width:180px; max-width:100%;
}
:focus-visible{outline:2px solid var(--accent); outline-offset:2px}

.tabs{display:flex; gap:2px; margin-bottom:14px; border-bottom:1px solid var(--hair); overflow-x:auto}
.tabs button{
  font:inherit; font-family:"IBM Plex Sans Condensed",sans-serif; font-size:13.5px; font-weight:600;
  letter-spacing:.03em; background:none; border:0; cursor:pointer; color:var(--ink-2);
  padding:9px 14px; border-bottom:2px solid transparent; margin-bottom:-1px; white-space:nowrap;
}
.tabs button:hover{color:var(--ink)}
.tabs button[aria-selected="true"]{color:var(--accent); border-bottom-color:var(--accent)}

.card{
  background:var(--surface); border:1px solid var(--hair); border-radius:10px;
  padding:16px 18px; box-shadow:var(--shadow); min-width:0;
}
.card h2{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:14px; font-weight:700;
  letter-spacing:.02em; margin:0 0 2px;
}
.card .hint{color:var(--muted); font-size:11.5px; margin:0 0 14px}
.grid{display:grid; gap:14px}
.kpis{grid-template-columns:repeat(auto-fit,minmax(190px,1fr)); margin-bottom:14px}
.cols2{grid-template-columns:repeat(auto-fit,minmax(380px,1fr)); margin-bottom:14px; align-items:start}

.kpi .klabel{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:10.5px; font-weight:600;
  letter-spacing:.12em; text-transform:uppercase; color:var(--muted); margin-bottom:8px;
}
.kpi .kval{font-size:34px; font-weight:600; line-height:1; letter-spacing:-.02em}
.kpi .kfoot{font-size:12px; color:var(--ink-2); margin-top:8px}
.meter{height:6px; background:var(--surface-3); border-radius:3px; overflow:hidden; margin-top:12px}
.meter span{display:block; height:100%; background:var(--good); border-radius:3px}

.rows{display:flex; flex-direction:column; gap:9px}
.rows.scroll{max-height:436px; overflow-y:auto; padding-right:6px}
.rows.scroll::-webkit-scrollbar{width:8px}
.rows.scroll::-webkit-scrollbar-thumb{background:var(--surface-3); border-radius:4px}
.row{display:grid; grid-template-columns:1fr 46px; gap:10px; align-items:center}
.row .rname{
  font-size:12.5px; color:var(--ink); display:flex; justify-content:space-between; gap:8px;
  margin-bottom:4px; align-items:baseline;
}
.row .rname em{font-style:normal; color:var(--muted); font-size:11px; font-family:"IBM Plex Mono",monospace}
.row .rname .ord{
  font-family:"IBM Plex Mono",monospace; font-size:10.5px; color:var(--muted);
  margin-right:7px; font-weight:600;
}
.track{height:16px; background:var(--surface-3); border-radius:4px; position:relative; overflow:hidden}
.track i{display:block; height:100%; background:var(--bar); border-radius:0 4px 4px 0; min-width:2px; transition:width .3s ease}
.row .rpct{
  font-family:"IBM Plex Mono",monospace; font-size:12.5px; font-weight:600; text-align:right;
  font-variant-numeric:tabular-nums; color:var(--ink);
}
.row.zero .rpct{color:var(--muted)}
.barwrap{min-width:0}

.matrix-scroll{overflow-x:auto; margin:0 -18px; padding:0 18px}
table.mx{border-collapse:separate; border-spacing:2px; font-size:12px; min-width:100%}
table.mx th{font-weight:600; color:var(--ink-2); text-align:left; padding:4px 6px; vertical-align:bottom}
table.mx thead th{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:10.5px; letter-spacing:.06em;
  text-transform:uppercase; color:var(--muted); white-space:normal; width:86px; line-height:1.25;
}
table.mx thead th .ord{display:block; color:var(--accent); font-family:"IBM Plex Mono",monospace; font-size:10px}
table.mx tbody th{white-space:nowrap; font-size:12px; position:sticky; left:0; background:var(--surface); z-index:1; padding-right:12px}
table.mx td{
  text-align:center; padding:7px 4px; border-radius:4px; font-family:"IBM Plex Mono",monospace;
  font-variant-numeric:tabular-nums; font-weight:600; font-size:12px; color:var(--ink);
}
table.mx tr.totrow th, table.mx tr.totrow td{border-top:1px solid var(--hair); font-weight:700}
table.mx tr.grouprow th{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:10.5px; font-weight:700;
  letter-spacing:.12em; text-transform:uppercase; color:var(--accent);
  padding:14px 6px 4px; position:static; background:transparent;
}
table.mx tr.filrow{cursor:pointer}
table.mx tr.filrow:hover th, table.mx tr.filrow:focus-visible th{color:var(--accent); text-decoration:underline}
table.mx tr.filrow:hover td{box-shadow:inset 0 0 0 1px var(--hair)}
.legend{display:flex; align-items:center; gap:8px; flex-wrap:wrap; margin-top:14px; font-size:11.5px; color:var(--muted)}
.legend .chips{display:flex; gap:2px}
.legend .chips b{display:block; width:26px; height:12px; border-radius:2px}

.listhead{display:flex; flex-wrap:wrap; gap:12px; align-items:center; margin-bottom:12px}
.listhead .count{
  font-family:"IBM Plex Mono",monospace; font-size:12px; color:var(--ink-2);
  background:var(--surface-2); border:1px solid var(--hair); padding:5px 10px; border-radius:6px;
}
.btn{
  font:inherit; font-size:12.5px; font-weight:600; cursor:pointer; color:var(--ink);
  background:var(--surface-2); border:1px solid var(--hair); border-radius:7px; padding:7px 13px;
}
.btn:hover{background:var(--surface-3)}
.btn.primary{background:var(--accent); color:var(--accent-ink); border-color:var(--accent)}
.btn.primary:hover{filter:brightness(1.08)}
.btn:disabled{opacity:.5; cursor:not-allowed}
.tablewrap{overflow-x:auto; border:1px solid var(--hair); border-radius:8px}
table.list{border-collapse:collapse; width:100%; font-size:12.5px}
table.list th{
  font-family:"IBM Plex Sans Condensed",sans-serif; font-size:10.5px; font-weight:600;
  letter-spacing:.1em; text-transform:uppercase; color:var(--muted); text-align:left;
  padding:9px 12px; background:var(--surface-2); border-bottom:1px solid var(--hair); white-space:nowrap;
}
table.list td{padding:8px 12px; border-bottom:1px solid var(--hair-soft); vertical-align:top}
table.list tbody tr:last-child td{border-bottom:0}
table.list tbody tr:hover{background:var(--surface-2)}
.pill{
  display:inline-flex; align-items:center; gap:5px; font-size:11px; font-weight:600;
  padding:2px 8px 2px 6px; border-radius:20px; background:var(--surface-3); color:var(--ink-2);
  white-space:nowrap; margin:1px 2px 1px 0;
}
.pill::before{content:""; width:6px; height:6px; border-radius:50%; background:var(--crit)}
.nm{font-weight:600; color:var(--ink); white-space:nowrap}
.mono{font-family:"IBM Plex Mono",monospace; font-variant-numeric:tabular-nums}
.empty{padding:34px 16px; text-align:center; color:var(--muted); font-size:13px}
.more{padding:10px 12px; font-size:12px; color:var(--muted); background:var(--surface-2)}
.note{font-size:11.5px; color:var(--muted); margin-top:12px; line-height:1.6}
.note b{color:var(--ink-2); font-weight:600}
footer{margin-top:26px; padding-top:14px; border-top:1px solid var(--hair); font-size:11.5px; color:var(--ink-2)}

/* upload */
.drop{
  border:2px dashed var(--hair); border-radius:10px; padding:30px 20px; text-align:center;
  background:var(--surface-2); transition:border-color .15s, background .15s;
}
.drop.over{border-color:var(--accent); background:var(--accent-soft)}
.drop .big{font-family:"IBM Plex Sans Condensed",sans-serif; font-size:16px; font-weight:700; margin-bottom:4px}
.drop .small{font-size:12.5px; color:var(--muted); margin-bottom:16px}
.drop input[type="file"]{display:none}
.upstatus{margin-top:16px; font-size:13px}
.upstatus .linha{
  display:flex; gap:9px; align-items:flex-start; padding:7px 0;
  border-bottom:1px solid var(--hair-soft);
}
.upstatus .linha:last-child{border-bottom:0}
.upstatus .marca{
  font-family:"IBM Plex Mono",monospace; font-size:11px; font-weight:700; flex:none;
  width:20px; text-align:center; line-height:1.5;
}
.ok{color:var(--good)} .er{color:var(--crit)} .av{color:var(--warn)}
.lock{
  max-width:430px; margin:6px auto 10px; text-align:center;
  background:var(--surface-2); border:1px solid var(--hair); border-radius:11px; padding:26px 24px;
}
.lock .icone{font-size:26px; line-height:1; margin-bottom:10px}
.lock h3{font-family:"IBM Plex Sans Condensed",sans-serif; font-size:16px; font-weight:700; margin:0 0 5px}
.lock p{font-size:12.5px; color:var(--muted); margin:0 0 16px; line-height:1.5}
.lock form{display:flex; gap:8px; justify-content:center; flex-wrap:wrap}
.lock input{
  font:inherit; font-size:14px; color:var(--ink); background:var(--surface);
  border:1px solid var(--hair); border-radius:7px; padding:9px 12px; width:190px;
  letter-spacing:.08em;
}
.lock .erro{color:var(--crit); font-size:12.5px; margin:12px 0 0; font-weight:600; min-height:1em}
.salvar{margin-top:18px; background:var(--surface-2); border:1px solid var(--hair); border-radius:10px; padding:16px 18px}
.salvar h4{font-family:"IBM Plex Sans Condensed",sans-serif; font-size:14px; font-weight:700; margin:0 0 5px}
.salvar p{font-size:12px; color:var(--muted); margin:0 0 12px; line-height:1.55}
.salvar form{display:flex; gap:8px; align-items:center; flex-wrap:wrap}
.salvar input[type="password"]{font:inherit; font-size:13px; color:var(--ink); background:var(--surface); border:1px solid var(--hair); border-radius:7px; padding:8px 11px; width:250px}
.salvar .chk{display:flex; align-items:center; gap:6px; font-size:12px; color:var(--ink-2); cursor:pointer}
.salvar .msg{font-size:12.5px; margin:12px 0 0; min-height:1em; font-weight:600; color:var(--ink-2)}
.salvar .msg.ok{color:var(--good)}
.salvar .msg.er{color:var(--crit)}
.salvar .msg.av{color:var(--warn)}
.passos{display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:12px; margin:4px 0 18px}
.passo{background:var(--surface-2); border:1px solid var(--hair); border-radius:9px; padding:13px 15px}
.passo b{
  display:block; font-family:"IBM Plex Mono",monospace; font-size:11px; color:var(--accent);
  margin-bottom:5px; font-weight:700;
}
.passo span{font-size:12.5px; color:var(--ink-2); line-height:1.5}
.colunas{
  font-family:"IBM Plex Mono",monospace; font-size:11.5px; color:var(--ink-2);
  background:var(--surface-2); border:1px solid var(--hair); border-radius:7px;
  padding:10px 13px; margin:0 0 4px; overflow-x:auto; white-space:nowrap;
}
[hidden]{display:none !important}
@media (prefers-reduced-motion: reduce){*{transition:none !important}}
@media (max-width:640px){
  .wrap{padding:14px 12px 48px}
  .kpi .kval{font-size:28px}
  .top .meta{margin-left:0; text-align:left; width:100%}
}
</style>
</head>
<body>
<div class="wrap" id="app">

  <div id="conteudo">
  <header class="top">
    <img class="logo" src="data:image/png;base64,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" alt="Rede HG" width="116" height="140">
    <div>
      <div class="brandmark">SESMT · Rede HG</div>
      <h1>Treinamentos de Segurança do Trabalho</h1>
      <p class="sub">Andamento por regional, filial e curso — base exportada da plataforma de cursos</p>
    </div>
    <div class="meta" id="meta"></div>
  </header>

  <section class="filters" aria-label="Filtros">
    <div class="fgroup" style="flex:1 1 100%">
      <span class="flabel" id="lbl-reg">Regional</span>
      <div class="seg" id="segReg" role="group" aria-labelledby="lbl-reg"></div>
    </div>
    <div class="fgroup">
      <label class="flabel" for="selFil">Filial</label>
      <select id="selFil"></select>
    </div>
    <div class="fgroup">
      <label class="flabel" for="selCur">Curso</label>
      <select id="selCur"></select>
    </div>
    <div class="fgroup">
      <button class="btn" type="button" id="btnReset" hidden="">Limpar filtros</button>
    </div>
  </section>

  <nav class="tabs" role="tablist" aria-label="Visões">
    <button role="tab" id="tab-vg" aria-controls="p-vg" aria-selected="true" data-p="vg">Visão geral</button>
    <button role="tab" id="tab-mx" aria-controls="p-mx" aria-selected="false" data-p="mx">Matriz curso × filial</button>
    <button role="tab" id="tab-pd" aria-controls="p-pd" aria-selected="false" data-p="pd">Quem ainda não fez</button>
    <button role="tab" id="tab-up" aria-controls="p-up" aria-selected="false" data-p="up">Atualizar base</button>
  </nav>

  <div id="p-vg" role="tabpanel" aria-labelledby="tab-vg">
    <div class="grid kpis" id="kpis"></div>
    <div class="grid cols2">
      <section class="card">
        <h2>Conclusão por filial</h2>
        <p class="hint">Percentual de matrículas concluídas em cada filial, da menor para a maior</p>
        <div class="rows scroll" id="barFil"></div>
      </section>
      <section class="card">
        <h2>Conclusão por curso</h2>
        <p class="hint">Na sequência oficial dos treinamentos</p>
        <div class="rows" id="barCur"></div>
      </section>
    </div>
    <section class="card">
      <h2>Comparativo entre as regionais</h2>
      <p class="hint">Independe do filtro de regional — serve para o ranking geral da rede</p>
      <div class="rows" id="barReg"></div>
    </section>
  </div>

  <div id="p-mx" role="tabpanel" aria-labelledby="tab-mx" hidden="">
    <section class="card">
      <h2>Matriz curso × filial</h2>
      <p class="hint">Percentual concluído. Célula clara = atraso maior; clique numa linha para abrir os nomes.</p>
      <div class="matrix-scroll">
        <table class="mx" id="mx"></table>
      </div>
      <div class="legend">
        <span>0%</span>
        <span class="chips" id="legChips"></span>
        <span>100%</span>
        <span style="margin-left:10px">Cada célula mostra o percentual; o total da linha é o desempenho da filial.</span>
      </div>
    </section>
  </div>

  <div id="p-pd" role="tabpanel" aria-labelledby="tab-pd" hidden="">
    <section class="card">
      <h2>Colaboradores com treinamento pendente</h2>
      <p class="hint">Lista nominal para cobrança do gerente da filial</p>
      <div class="listhead">
        <input type="search" id="busca" placeholder="Buscar por empresa…" aria-label="Buscar por empresa (filial)">
        <span class="count" id="cnt"></span>
        <button class="btn" id="btnCopy" type="button">Baixar lista filtrada</button>
      </div>
      <div class="tablewrap">
        <table class="list" id="tbl">
          <thead><tr>
            <th>Colaborador</th><th>Filial</th><th>Regional</th>
            <th style="text-align:center">Pend.</th><th>Cursos pendentes</th>
          </tr></thead>
          <tbody id="tbody"></tbody>
        </table>
        <div class="more" id="more" hidden=""></div>
      </div>
      <p class="note"><b>Como usar:</b> selecione a regional, depois a filial, e a lista já sai pronta para enviar ao gerente. O filtro de curso isola uma exigência específica (ex.: só NR 20).</p>
    </section>
  </div>

  <div id="p-up" role="tabpanel" aria-labelledby="tab-up" hidden="">
    <section class="card">
      <h2>Atualizar a base do painel</h2>
      <p class="hint">Suba a planilha exportada da plataforma de cursos — o painel se recalcula na hora</p>

      <div class="lock" id="lock">
        <div class="icone" aria-hidden="true">🔒</div>
        <h3>Área restrita ao SESMT</h3>
        <p>Só quem administra o painel atualiza a base. A equipe acompanha os números pelas outras abas.</p>
        <form id="formSenha">
          <input type="password" id="senha" placeholder="Senha" aria-label="Senha de administrador" autocomplete="current-password">
          <button class="btn primary" type="submit">Entrar</button>
        </form>
        <p class="erro" id="erroSenha" role="status"></p>
      </div>

      <div id="areaUpload" hidden="">
      <div class="passos">
        <div class="passo"><b>1</b><span>Exporte o relatório de treinamentos da plataforma em .xlsx ou .csv.</span></div>
        <div class="passo"><b>2</b><span>Escolha o arquivo abaixo. A leitura é feita no seu navegador, nada é enviado para fora.</span></div>
        <div class="passo"><b>3</b><span id="passo3">Com o token guardado e a publicação automática ligada, a planilha já sobe para a equipe sozinha. Sem token, escolha um dos botões do resumo.</span></div>
      </div>

      <p class="colunas">Colunas esperadas: PARTICIPANTE &nbsp;|&nbsp; EMPRESA &nbsp;|&nbsp; CURSO &nbsp;|&nbsp; APROVAÇÃO &nbsp;|&nbsp; SITUAÇÃO NO AMBIENTE &nbsp;&nbsp;(REGIONAL é opcional)</p>
      <p class="note" style="margin-top:0">Aceita a mesma exportação de hoje. A ordem das colunas não importa — o painel procura pelo nome do cabeçalho.</p>

      <div class="drop" id="drop">
        <div class="big">Arraste a planilha aqui</div>
        <div class="small">ou escolha o arquivo — .xlsx, .xlsm ou .csv</div>
        <label class="btn primary" for="arquivo" style="display:inline-block">Escolher arquivo</label>
        <input type="file" id="arquivo" accept=".xlsx,.xlsm,.csv,.txt">
      </div>

      <div class="upstatus" id="upStatus"></div>

      <div class="salvar" id="areaGh">
        <h4>Salvar para a equipe (GitHub)</h4>
        <p>Grava a base nova direto no repositorio publicado, sem baixar e substituir arquivo. Precisa de um token do GitHub com permissao de escrita apenas neste repositorio. O token fica guardado so neste navegador e nunca entra no arquivo publicado.</p>
        <form id="formGh" autocomplete="off">
          <input type="password" id="ghToken" placeholder="Token do GitHub" aria-label="Token do GitHub" autocomplete="off">
          <label class="chk"><input type="checkbox" id="ghLembrar"> Lembrar neste navegador</label>
          <label class="chk"><input type="checkbox" id="ghAuto" checked=""> Publicar sozinho ao subir a planilha</label>
          <button class="btn" type="submit">Guardar token</button>
          <button class="btn" type="button" id="ghEsquecer">Esquecer</button>
        </form>
        <p class="msg av" id="ghMsg" role="status"></p>
      </div>

      <p class="note" id="notaAcesso"><b>Como a equipe enxerga:</b> este painel é um arquivo único e fechado — quem abre navega, filtra e copia listas, mas não altera nada para os outros. Ao subir uma planilha nova você tem com o token do GitHub guardado e a opção <b>Publicar sozinho ao subir a planilha</b> marcada, basta escolher o arquivo: o painel lê, aplica e grava no repositório, e cerca de um minuto depois todo mundo passa a ver os números novos. Se preferir conferir antes, desmarque essa opção e use <b>Usar e salvar neste navegador</b> (fica só para você), <b>Salvar para a equipe</b> ou <b>Baixar painel atualizado</b>.</p>
      </div>
    </section>
  </div>

  <footer id="foot"></footer>
  </div>
</div>
<script id="dados" type="application/json">{"regionais":["REGIONAL 1","REGIONAL 2 - TIAGO CARDOSO","REGIONAL 3 - BRUNO VIANA","REGIONAL 4 - FABIO ARAUJO","CORPORATIVO / SEM REGIONAL"],"filiais":[{"n":"CASA BRANCA","r":0},{"n":"CHEROKEE","r":0},{"n":"FALÇÃO","r":0},{"n":"FERRARI","r":0},{"n":"ILHA BRAVA","r":0},{"n":"JR","r":0},{"n":"LAJINHA","r":0},{"n":"PAPA LEGUAS 1","r":0},{"n":"PERIQUITO","r":0},{"n":"PINHEIROS","r":0},{"n":"PISCINA","r":0},{"n":"PLANALTO II","r":0},{"n":"RAVENA","r":0},{"n":"ALAGOAS 101","r":1},{"n":"BENDEGO","r":1},{"n":"CARAVELAS","r":1},{"n":"COLONIAL 101","r":1},{"n":"FEIRA 101","r":1},{"n":"ITABUNA","r":1},{"n":"LINHARES","r":1},{"n":"PARCEIRO","r":1},{"n":"SALVADOR","r":1},{"n":"SANTO ANTONIO","r":1},{"n":"BALANÇA","r":2},{"n":"CAMPOS ALTOS","r":2},{"n":"CENTENARIO","r":2},{"n":"EUCALIPTOS","r":2},{"n":"FLASH","r":2},{"n":"MINAS GERAIS","r":2},{"n":"MOC","r":2},{"n":"MOC 135","r":2},{"n":"NORTE DE MINAS","r":2},{"n":"QUILOMETRAGEM","r":2},{"n":"TURMALINA III","r":2},{"n":"ANEL VIARIO","r":3},{"n":"BARREIRAS","r":3},{"n":"CANDIDO SALES","r":3},{"n":"GRANDE VALE","r":3},{"n":"GRAO DE OURO","r":3},{"n":"GURUPI","r":3},{"n":"MARACANA","r":3},{"n":"NOVO PONTO","r":3},{"n":"PAPA LEGUAS III","r":3},{"n":"PQ DOS COQUEIROS","r":3},{"n":"SÃO MARCOS","r":3},{"n":"TALISMA","r":3},{"n":"UIRAPURU","r":3},{"n":"ULTRA","r":3},{"n":"TECNO ARLA MARACANA","r":4},{"n":"TECNO ARLA MATRIZ","r":4}],"cursos":["SEGURANÇA DO TRABALHO","EPI","BENZENO","NR 20 INTERMEDIARIO","PLANO DE MANUTENÇÃO","CODIGO DE ETICA","APERFEIÇÕE FRENTISTA CAIXA","GESTAO AUDITORIA","APERFEIÇOE FRENTISTA"],"participantes":["ACASSIANO SOARES RODRIGUES","ACASSIO ROBERTO REIS SANTOS","ACASSIO SILVA OLIVEIRA","ADAILTON DO CARMO DOS SANTOS","ADAILTON LIMA GALVAO","ADAIR JOSE PIRES","ADAO JOSE DOS SANTOS","ADAUTO BARBOSA COUTINHO","ADEILSON RODRIGUES DE OLIVEIRA","ADELCIO DE OLIVEIRA FERREIRA","ADELMO FIGUEIREDO SILVA","ADELSON DE SOUZA SANTOS","ADEMARIO DAS VIRGENS VIEIRA","ADENICIO PEREIRA SANTANA","ADENILSON CARDOSO DE OLIVEIRA","ADENOR RIBEIRO DA SILVA","ADERVISON DOS SANTOS","ADILTON JUNIOR SANTOS DE JESUS","ADIMILSON MODESTO BERNARDINO","ADIMON SOUZA DE ARAUJO","ADRIANO DOS SANTOS SILVA","ADRIANO JUNIOR PEREIRA","ADRIANO OLIVEIRA SILVA","ADRIANO RIBEIRO DE SOUZA","ADRIANO SANTOS DE JESUS","ADRIANO SOUSA GOMES FILHO","ADRIANO VIEIRA DA SILVA","ADRIANY NEVES SILVA","ADRYAN PEREIRA DA SILVA","ADSON BATISTA DOS SANTOS","ADSON RENAN SANTOS MEDINA","AEMER CALEK SALMEN","AGNALDO CONCEICAO DOS SANTOS","AGUINALDO MARTINS SILVA","AILTON SILVA PRADO","ALAN ADORNO COSTA","ALCINO SILVA DE JESUS","ALDAIR LOPES DE OLIVEIRA","ALDO JOSE NOGUEIRA DOS SANTOS","ALECIO SANTOS BRITO","ALEF CERQUEIRA SANTOS","ALESSANDRO LUIS BARBOSA MEIRA","ALESSANDRO RIBEIRO VARJAO ALMEIDA","ALESSANDRO SOUZA AMERICANO","ALEX GOMES ALVES","ALEX JÚNIOR DA SILVA","ALEX PACHECO DOS SANTOS OLIVEIRA","ALEX PASSOS","ALEX SANTOS COELHO","ALEXANDRE LIMA DOS SANTOS","ALEXANDRO ALVES DA SILVA","ALEXSANDRO JESUS DA SILVA","ALFREDO FERREIRA DO VALE JUNIOR","ALICE APARECIDA PINTO LEMOS","ALINE FONSECA OLIVEIRA","ALINE SOARES DOS SANTOS","ALIOMAR DE JESUS LIMA","ALISSON PATRIK FIGUEIREDO SILVA","ALISSON PEREIRA MEDINA","ALISSON VIRISSIMO DA SILVA","ALLAN JESUS DOS SANTOS","ALLEX AUGUSTO DOS SANTOS","ALMITO GONCALVES DA ROCHA","ALTAMIRANDO PORTO DE SOUZA","ALVARO VINICIUS SANTOS DE OLIVEIRA","AMADEU FRANCISCO DOS SANTOS","AMAURI SANTOS ALMEIDA","AMAURI SOUSA ABADE","AMAURY BOTELHO DE NOVAES","ANA PAULA DE MORAIS COSTA","ANA PAULA LOPES DE SOUZA","ANDECLEI SOUZA NOVAIS","ANDERSON DOS SANTOS LOUZADO","ANDERSON FERREIRA DE JESUS LIMA","ANDERSON SOARES SANTOS","ANDRE CARDOSO ALVES","ANDRE DA COSTA SANTOS","ANDRE FERREIRA DA SILVA","ANDRE LUIZ MARTINS SOLAR","ANDRE RICARDO SILVA DOS SANTOS","ANDRE SILVA SANTOS","ANDRE SOUSA DE OLIVEIRA","ANDREA FERRARI CHAVES","ANGELO ANTONIO MARINHO ROCHA","ANIEL OLIVEIRA SOARES","ANSELMO JOSE DE SOUZA","ANTONIO AMORIM COIMBRA","ANTONIO CARDOSO ALVES","ANTONIO CARLOS DA SILVA CONCEICAO","ANTONIO CARLOS DE LIMA","ANTONIO CARLOS RODRIGUES DA SILVA","ANTONIO CARLOS SANTOS LIMA","ANTONIO DE SOUZA","ANTONIO ESTEVAO DOS SANTOS AVILA FERRO","ANTÔNIO LUCAS PEREIRA SANDRES","ANTONIO MARCOS CARDOSO DE SOUZA","ANTONIO MARCOS FERREIRA SOUSA DOS SANTOS","ANTONIO MARCOS SOUZA DE OLIVEIRA","ANTONIO MORAES DOS SANTOS RODRIGUES","ANTONIO QUEIROZ DA SILVA","ANTONIO ROBERTO ALVES DA SILVA","ANTONIO RODRIGUES DE SOUZA","ANTONIO SILVERIO RAMOS","ANTONIO VICTOR SANTANA BARRETO","ANTONIO VIEIRA LIMA FILHO","ANTONIO XAVIER ROCHA","APARECIDO JOSE DE SANTANA","ARGEU DE OLIVEIRA","ARIANE DE SOUZA DAMASCENO","ARICLENES CRUZ SANTOS","ARIEL PIRES DIAS","ARLINDO CONCEICAO SANTOS","ARLINDO DA MOTA SILVA","ARMANDO RIBEIRO FILHO","ARTUR DEIVID SILVA SANTOS","AUGUSTO HENRIQUE SANTOS CONCEIÇÃO","AUGUSTO LEOCADIO DA SILVA","AUGUSTO VIEIRA DA CRUZ","AURINO VIEIRA PORTO JUNIOR","AZAPH CARLOS SILVA DE OLIVEIRA","BALTAZAR SOARES VIEIRA","BARBARA OLIVEIRA SANTOS","BEATRIZ SOUZA DA ROCHA","BERNEVAL ARCANJO SANTANA","BRENO DA SILVA OITICICA","BRENO GUSTAVO GONCALVES DOS REIS","BRUNA ROCHA","BRUNA ROCHA DA SILVA","BRUNO DE OLIVEIRA DUARTE","BRUNO DE SOUZA BARBOSA","BRUNO HENRIQUE ALMEIDA SILVA","BRUNO MENDES DA SILVA","BRUNO SANTOS VIANA","BRUNO VINICIUS SANTOS BONFIM","CAIO INACIO NERY BEZERRA","CARLITO SILVA ARAUJO","CARLOS ALBERTO DE SOUSA SANTANA","CARLOS ALBERTO DOS SANTOS","CARLOS ALEXANDRE DE LIMA ARAUJO","CARLOS ANDRE ALVES DOS SANTOS","CARLOS AUGUSTO DOS SANTOS SOUZA","CARLOS EDUARDO GOMES GARCIA","CARLOS HENRIQUE RODRIGUES DA SILVA","CARLOS NUNES DE ARAUJO","CARLOS ROBERTO ALVES MASCARENHAS","CARLOS SILVA DE QUEIROZ","CARLOS VENILSON PORTO DA SILVA","CAROLINE CARVALHO DA SILVA","CATIA SOUZA SANTOS","CAUA FERREIRA DOS SANTOS","CAUAN PRADO PORTUGAL","CELIO ALVES COELHO","CELIO PEREIRA DOS SANTOS","CELIO SOARES","CELSO CEZARIO DE SOUZA","CELSON SILVA RIBEIRO","CESAR GOMES PECANHA","CHARLEANE DE OLIVEIRA MOREIRA","CHARLES APARECIDO DE JESUS SOARES","CHRYSTIAN IVANEY GARCIA MOURA","CICERA DAYANE GONCALVES SANTANA","CICERO MORAES NOGUEIRA DOS SANTOS","CLAUDILENE GOMES TEIXEIRA","CLAUDINEI DE SOUZA","CLAUDINEI TORRES CANDIDO","CLAUDINO DE SOUZA ILDEFONSO GONÇALVES","CLAUDIO ADAO CRUZ DOS SANTOS","CLAUDIO ALVES DE JESUS","CLAUDIO LOPES DE OLIVEIRA","CLAUDIONOR AMERICO DE MOURA","CLAUDIR DOS SANTOS SILVA","CLAYDSON RODRIGUES SIQUEIRA","CLEBER DE ASSIS CAVALCANTE","CLEBIO DE JESUS CONCEICAO","CLEDIVALDO QUEIROZ NASCIMENTO","CLEIDSON DE JESUS SILVA","CLEITON FERREIRA SILVA","CLEITON PEREIRA DOS SANTOS","CLEMILDO BRANDAO DOS SANTOS","CLEVERSON EDUARDO DA SILVA GALDINO","CLEYTON MATEUS BORGES NUNES","CLEZIANE GOMES FERREIRA","CRISTIANE LOPES ESTEVES","DAIANA DOS SANTOS CARVALHO","DAILTON MACENA VELAME","DANIEL ALEX LOPES MOREIRA","DANIEL BARBOSA OLIVEIRA","DANIEL CARLOS MENDES DE PAULA","DANIEL DIAS SOLINOS","DANIEL HENRIQUE SILVA CRUZ","DANIEL LISBOA NUNES","DANIEL SANTOS BARBOSA","DANIEL SANTOS MACEDO","DANIEL SILVA SANTOS","DANIEL VANDERLEI DE SOUSA","DANIELA DOS SANTOS SANTANA","DANILO CORREIA SILVA","DANILO COUTO DE OLIVEIRA","DANILO DA ROCHA MATOS","DANILO HENRIQUE FAUSTINO CUSTODIO","DANILO HENRIQUE SOUZA PAULA","DANILO VIANA LIMA","DANUZIO VIANA GOMES","DARCIEL RODRIGUES DE SOUZA","DARDANE JORGE RAMOS SOUSA","DARLAN DE SOUZA SILVA","DARLON PEREIRA DUARTE","DAVI ARAUJO DAMASCENA","DAVI DE SOUZA SANTOS","DAVI MARCOS COELHO SILVA","DAVI QUEIROZ DOS SANTOS GONÇALVES","DAVID DA CONCEIÇÃO NASCIMENTO QUEIROZ","DAVID GABRIEL BUENO","DAVISON SIMAO CIDALINO","DAYVISON JUNIOR PINTO DOS SANTOS","DEILSON RIBEIRO DA SILVA","DEIVEITE MARIANO DA SILVA","DEIVISON FIRMINO DE SOUZA","DEIVSON SILVA SANTOS","DERIVALDO ALVES SAMPAIO","DERNEVAL AMARAL LIMA","DIASDAIVE NUNES DOS SANTOS","DIEGO ALEXANDRE DE MENDONÇA","DIEGO BARBOSA OLIVEIRA","DIEGO FERNANDES DOS SANTOS LIMA","DIEGO HENRIQUE BARBOSA SILVA","DIEGO MATOS DE OLIVEIRA","DIEGO SENA CAMPOS","DIOGO NUNES FOLGADO","DIOLENO DA PAIXAO MARTINS","DIONATHAN SENRA GOMES","DIRA MENDES DOS SANTOS","DIVANIO SOARES FERREIRA","DOMINGOS APARECIDO DE FREITAS","DONIZETE BATISTA SILVA","DOUGLAS CARDOSO OLIVEIRA","DOUGLAS FERREIRA LANA","DOUGLAS MACIEL VIEIRA","DOUGLAS REIS CARNEIRO","EDE CARLOS RAMOS","EDER CARDOSO DIAS","EDICARLO DA SILVA TEIXEIRA","EDILSON ALMEIDA ALVES","EDILSON DE OLIVEIRA SILVA","EDILSON MASCENA DE SOUZA","EDILSON REIS DA SILVA TEIXEIRA","EDILSON SANTOS GUEDES","EDIR JORGE MORONTE JÚNIOR","EDIVALDO CORREIA","EDMAR ALVES BATISTA","EDMAR FRANCISCO DE QUEIROZ","EDMARIO BARBOSA DE CARVALHO","EDMILSON BARBOSA DA SILVA","EDNAILSON NOVAIS DA SILVA ALMEIDA","EDNALDO CARDOSO DA SILVA","EDNEI GONÇALVES ARAUJO","EDNELSON DE SOUSA VILA NOVA","EDSON ALVES DE ANDRADE","EDSON ANDRADE ARAUJO","EDSON DA SILVA FERREIRA","EDSON LOPES FAGUNDES","EDSON NUNES DE OLIVEIRA","EDSON RIBEIRO NOVAIS","EDUARDO CARDOSO VELOSO","EDUARDO DE JESUS SILVA","EDUARDO LOPES SANTOS","EDUARDO RAMALHO DE OLIVEIRA MELO","EDVALD ESCOLASTICO PINTO DOS SANTOS","EDVALDO CARDOSO DA SILVA","EDVALDO CONCEICAO DA SILVA SACRAMENTO","EDVALDO COSTA ANDRADE","EDVALDO GOMES DO NASCIMENTO","EDVALDO HERCULANO CUNHA","EDVALDO OLIVEIRA PEREIRA","EDVAN CERQUEIRA DE OLIVEIRA","ELCI CANDIDO DE SOUZA","ELCIONE RODRIGUES LOPES","ELDER CONCEICAO DA CUNHA","ELDIBERTO PEREIRA FONSECA","ELDIMAR PEREIRA FONSECA","ELEN OLIVEIRA SILVA","ELI CARLOS REIS FERREIRA","ELIAS BORGES DA CONCEICAO","ELIAS DA COSTA SANTOS","ELIAS GUSTAVO LOPEZ","ELIELSON SANTANA DE DEUS","ELIVALDO DIAS SILVA","ELIZANDRO FERREIRA","ELLEN NOGUEIRA FERRAZ","ELSE DE JESUS OLIVEIRA","ELVIS DA SILVA","ELVIS OLIVEIRA DA SILVA","ELVIS SANTOS GOMES DA SILVA","ELZIRO RODRIGUES DOS SANTOS","EMELSON BISPO SANTIAGO","EMERSON BASTOS DOS SANTOS JUNIOR","EMILY AMARAL LIMA","ENES GONCALVES DE LIMA","ENIVALDO TEIXEIRA ESPINDOLA","ERENILDO DE MOURA SOUSA","ERENILSON ALVES DA FONSECA","ERICK JUNIO LEMOS","ERICK RODRIGO DANTAS SOARES","ERINALDO DA SILVA TEIXEIRA","ERIVALDO CARDOSO DA SILVA","ERIVALDO SANTOS DA SILVA","ERIVANDO DA SILVA NOGUEIRA","ERLANDSON FERREIRA DOS SANTOS","ERMIRO SANTIAGO MARQUES NETO","ERNANES MESSIAS DE AMACENA","EUCLIDES OLIVEIRA SILVA","EVANDRO FRANCA DE MORAIS","EVITON DA CRUZ SANTOS","FABIANA CRISTINA DE MORAIS DOS SANTOS","FABIANA REIS DA SILVA","FABIO ANDRADE DE SANTANA","FABIO ANTONIO XAVIER","FABIO CHAVES DE ANDRADE","FABIO JUNGER DA SILVA","FABIO PATRICK AVELINO FERREIRA SANTOS","FABIO PEREIRA FAGUNDES","FABIO TORRES DE ARAUJO","FABRICIO DE JESUS SILVA","FABRICIO DOS SANTOS VIEIRA","FAGNER ARCANJO LEMOS SANTOS","FAGNER ROBERTO OLIVEIRA DO CARMO","FARLEY CESAR PERES VELOSO","FELIPE BARRETO SILVA","FELIPE CARDOSO DE ANDRADE VELAME","FELIPE DAMACENA DA SILVA","FELIPE DOS SANTOS RODRIGUES SILVA","FELIPE MANOEL DOS SANTOS","FELIPE RODRIGUES DE SOUSA","FERNANDA VEIGA GONCALVES","FERNANDO ALVES SANTOS","FERNANDO DIEGO CARDIM SANTOS","FERNANDO GONCALVES DIAS","FERNANDO PEREIRA DA SILVA","FERNANDO SILVA DO PRADO","FILIPE JORDAN DA SILVA","FILIPE OLIVEIRA DOS SANTOS","FLAVIA RIBEIRO SANTOS","FLAVIA SILVA BATISTA","FLAVIANO DA SILVA CARVALHO","FLAVIO ANTONIO MIRANDA","FLAVIO SILVA PEREIRA","FRANCIELLY PAULA PEREIRA DE SOUZA","FRANCINALDO DE OLIVEIRA SILVA","FRANCIO DOMINGOS DA SILVA","FRANCISCO DE PAULA SIQUEIRA","FRANCISCO EUFRAZIO DA SILVA NETO","FRANCISCO MESSIAS ALVES","FRANCISCO PEREIRA NETO","FREDISON DOS SANTOS","GABRIEL ALVES DA CRUZ","GABRIEL ATAIDE ALVES PEREIRA","GABRIEL BARBOSA DOS SANTOS","GABRIEL CHAVES DE LIMA","GABRIEL DE ALMEIDA FERNANDES","GABRIEL DE PAIVA TEOFILO","GABRIEL EDUARDO MARQUES DOS SANTOS","GABRIEL GONCALVES DE OLIVEIRA","GABRIEL GONCALVES NERES","GABRIEL HENRIQUE SILVA SANTOS","GABRIEL HENRIQUE TUROLA SILVA","GABRIEL LUIZ ALVES MARANHO","GABRIEL OLIVEIRA DE MOURA","GABRIEL RODRIGUES SOARES","GABRIEL XAVIER DE ALMEIDA","GABRYEL ALAN FERREIRA SANTOS","GEAN CORDEIRO","GEAN DOS SANTOS BRITO","GEAN SENA ARAUJO","GENILDO OLIVEIRA NUNES","GENILSON APARECIDO FERREIRA","GENILSON ROCHA ANDRADE","GENIVAL ALVES ANDRADE","GENIVAL BISPO DOS SANTOS","GENIVAL PEREIRA DA SILVA","GENTIL MARTINS DOS SANTOS","GEORGE MOREIRA DA SILVA","GEOVANE DE SOUSA DOS SANTOS","GEOVANE LIMA DOS SANTOS","GERALDO DAVIDSON VITORIANO SANTOS","GERALDO DO CARMO","GERALDO MAGELA FLORENCIO","GERALDO MARCOS ALVES DOS SANTOS","GERALDO SANTOS SILVA","GERSON RODRIGO SANTOS SOUZA","GESIVALDO BARBOSA NASCIMENTO","GETULIO DE BRITO MOREIRA","GILBERTO AZI JUNIOR","GILBERTO COELHO BRANDAO","GILBERTO GIL SOUSA SANTOS","GILBERTO OLIVEIRA ROCHA","GILCIMAR SANTOS GONCALVES","GILDO BARBOSA DOS REIS","GILDO BARROS DE OLIVEIRA","GILLIARD AGUIAR DOS SANTOS JUNIOR","GILMAR ANTONIO DA COSTA","GILMAR DE ASSIS BARBOSA","GILMAR DOS SANTOS GONCALVES","GILMAR SANTANA DA SILVA","GILSON BASTOS DE JESUS ROCHA","GILSON DA SILVA SANTIAGO","GILSON PAES PEREIRA JUNIOR","GILSON QUEIROZ DA SILVA JUNIOR","GILSON RAIMUNDO DE BARROS","GILSON SANTANA NERI","GILSON SANTOS DE SOUZA","GILTON DOS SANTOS CARDOSO","GILVAN DA SILVA SOUSA","GILVANDO QUEIROZ","GIRLANDE FERREIRA SANTOS","GIVANALDO JESUS DOS SANTOS","GIVANILDO SANTOS SANTANA","GLEISON TELES SANTOS","GUILHERME DE MACEDO PEREIRA","GUILHERME DE SOUZA FRANCO","GUILHERME HENRIQUE MIRANDA DE SOUZA","GUILHERME HENRIQUE VINHA SILVA","GUSTAVO HENRIQUE DE MORAES","GUSTAVO PEREIRA SANDRES","HAMILTON NUNES ALECRIM","HAMILTON VIEIRA LIMA","HAROLDO CORDEIRO DA SILVA","HEBERT RODRIGUES DE OLIVEIRA","HELBER PEREIRA RAMOS","HELIO RODRIGUES DOS SANTOS FERREIRA","HENRIQUE DIAS FERREIRA","HENZO RODRIGUES FIGUEIREDO","HERBERT QUEIROZ DOS SANTOS AMARAL","HERBERT TIMOTEO LEITE","HERBERTH KENNEDY RODRIGUES DE SOUZA MARTINS","HILDEBERTO TEIXEIRA GONCALVES","HIURE LEAL RIBEIRO","IARA DE SOUZA SILVA","IARLEI EXPEDITO DE SOUZA COSTA","IDELVAN ANDRADE DE FREITAS","IEDA SILVA DE ALMEIDA","IGOR EDUARDO DOS SANTOS SILVA","IHAGO GERBSON RODRIGUES DA SILVA","ILDEMAR LUIZ PEREIRA","INACIO MARES NUNES","IRENE APARECIDA MARTINS GOMES","IRONI REIS ROSA","ISAAC JHONAS DOS SANTOS SILVA","ISAAC NILTON BISPO SILVA","ISLAN ALVES CERQUEIRA","ISNALDO NUNES DE ALMEIDA","ISRAEL SILVA NASCIMENTO","ISRAEL ZIMMERER CARDOSO","ITELMAR GONÇALVES DE QUEIROZ","IURI COSTA GOMES DA SILVA","IURY PEREIRA DOS SANTOS","IVANILSON DA SILVA SOUZA","IVESON OLIVEIRA SANTOS","IVO DIAS GONCALVES","IZAIAS TEIXEIRA DOS SANTOS","JACKSON MOTA DE JESUS","JACSON ANDRADE SILVA DOS SANTOS","JADIR REIS CARDOSO","JADSON CARVALHO BOMFIM","JADY VIANA SANTOS","JAERBSON LOPES DA SILVA","JAGUARACI DOS SANTOS FERREIRA","JAILSON DA SILVA NASCIMENTO SANTIAGO","JAILSON LIMA DOS SANTOS","JAILTON DE JESUS MENDES","JAILTON DE JESUS SANTANA","JAILTON DE JESUS SANTOS","JAIME MELO SILVA SOUZA","JAIR PEREIRA","JAIR PEREIRA ARAUJO","JAIR ROBERTO NOGUEIRA SANTOS","JAIRO GOMES DA SILVA","JAIRO SANTIAGO DA SILVA","JAKSON PEREIRA SILVA SA","JAMILSON DONIZETI DA SILVEIRA","JANFERSON BORGES GONÇALVES","JANIELE DE SOUZA SILVA","JANIO SILVA ALCANTARA","JARBAS DIEGO DIAS OLIVEIRA","JARBAS FERREIRA DOS SANTOS","JARLESON DOS SANTOS ARAUJO","JASON SOUZA MEIRA","JEAN LIMA MENDES","JEAN MARCOS SILVA","JEFERSON DA CONCEICAO SOUZA","JEFFERSON SOUZA DA SILVA","JEFFSON DE JESUS SALES","JEOVANE ALVES VIANA","JERFFSON JOSE NEVES DE CARVALHO","JERYSSON DE ALMEIDA DOLINO","JESIVALDO SILVA DE OLIVEIRA","JHONATAN DE PAULA NASCIMENTO","JHONY RIBEIRO MENDES ANDRADE","JIDEON BASTOS DE SOUZA JUNIOR","JILMAR GAMA DE OLIVEIRA","JIVANILDO DOS SANTOS GOUVEIA","JIVANILDO ROCHA BARBOSA","JOALISSON SANTANA CARLOS MACEDO","JOAO ALFREDO NICESIO MOREIRA","JOAO BATISTA COSTA ALVES","JOAO BRITO DE ARGOLO","JOAO CARLOS DA CRUZ NASCIMENTO","JOAO CARLOS DE JESUS DOS SANTOS","JOAO CARLOS VIEIRA JOAQUIM","JOAO CRISTIAN CORREIA GONCALVES","JOAO DE DEUS SOUZA ALVES","JOAO EDUARDO NUNES","JOAO FRANCISCO DOS SANTOS","JOAO LUCAS DE SANTANA PEIXINHO CARDOSO","JOAO MARCOS SANTOS SANTANA","JOAO MENDES DE SOUSA","JOAO PAULO ALVES FERNANDES","JOAO PAULO BRANDAO DOS SANTOS","JOAO PAULO CAMPOS SILVA","JOÃO PAULO JESUS DA SILVA DOS SANTOS","JOAO PEDRO FERREIRA PELEGRINI","JOAO SANTOS ROCHA","JOAO VITOR FERREIRA ALMEIDA","JOAO VITOR SILVA ANDRADE","JOAO VITOR TELES SILVA","JOEL JORGE DE OLIVEIRA CORREA","JOEL MARCOS DE SIQUEIRA","JOELSON CARVALHO DA ANUNCIACAO","JOHNNATA HENRIQUE SANTOS SOUZA","JOILSON MORAES SOUZA","JOILSON SARDINHA DE OLIVEIRA","JONAS MINERVINO DA SILVA","JONAS PEREIRA DE OLIVEIRA","JONATAS MAICO DA SILVA","JONATAS SILVA SANTOS","JONATHAN DAVID DOS SANTOS","JONATHAN ROBERTO DOS SANTOS","JONATHAS KEWIN ARAUJO RIBEIRO","JORDÃO FERREIRA DE SOUZA","JORDSON MARCOS COSTA REIS","JORGE PAULA DOS SANTOS","JOSANIA CRISTINA DA SILVA","JOSE ABADE SANTOS","JOSE ADRIANO VIEIRA LISBOA","JOSE ANGELO DOS SANTOS FILHO","JOSE ANTONIO FERNANDES DE SOUZA","JOSE ANTONIO LIRIO","JOSE ANTONIO MATIAS","JOSE ARNOBIO FERREIRA DA SILVA","JOSE AUGUSTO ALVES BORGES RAMOS","JOSE AUGUSTO DOS SANTOS","JOSE BISPO DA SILVA","JOSE CARLOS DE JESUS","JOSE CARLOS DE OLIVEIRA ALMEIDA","JOSE CARLOS DIAS","JOSE CARLOS FERREIRA","JOSE CLAUDIO PEREIRA DA SILVA","JOSÉ CLEBESTI PINTO DE SOUZA","JOSE DOS REIS OLIVEIRA","JOSE DOS SANTOS NUNES","JOSE EDILSON DA SILVA","JOSE EDUARDO DE SOUZA","JOSE FABIANO DA SILVA","JOSE FELICIO FILHO","JOSE FERNANDES DA SILVA","JOSE FERREIRA DA CRUZ","JOSE FRANKLIN FERREIRA DO CARMO FILHO","JOSE GERALDO RODRIGUES JUNIOR","JOSE HENRIQUE BRITO OLIVEIRA","JOSE HENRIQUE REIS LIMA","JOSE HILTON ALVES DA SILVA","JOSE JULIO CARDOSO DOS SANTOS","JOSE LUIZ SANTOS CERQUEIRA","JOSE MARCIEL PEREIRA DA SILVA","JOSE MARCOS RODRIGUES DA CRUZ","JOSE MARIA DE ASSIS MENDONCA","JOSE MARIA FERREIRA DOS SANTOS","JOSE NILTON DE SOUZA","JOSE NILTON SOUZA DE OLIVEIRA","JOSE PAULO DE JESUS SANTOS","JOSE RAIMUNDO DOS SANTOS SOUZA","JOSE RODRIGUES LORIANO MOREIRA","JOSE ROQUEM GONCALVES JUNIOR","JOSE VIEIRA DE SOUZA FILHO","JOSEMAR FERREIRA DOS SANTOS","JOSEMILTOM SOUZA DE ALMEIDA","JOSENILDO ALVES BASTOS","JOSENILTO DOS SANTOS SILVA","JOSENILTO SANTANA DE JESUS","JOSENILTON DE ALMEIDA CONCEIÇÃO","JOSIMAR WESLEY SILVA BESSA","JOSUE LIMA DA SILVA DE JESUS","JOSUE NASCIMENTO DOS SANTOS E SILVA FILHO","JOSUEL ISABEL DOS SANTOS","JUAN COSTA SILVA","JUAREZ QUEIROZ CERQUEIRA","JUCIAN CARDOSO REIS CARDOSO","JUDERSON DOURADO DE ARAUJO","JUDICAEL SANTANA DA ANUNCIAÇAO","JULIANA APARECIDA CLARENTINO SANTOS","JULIANE VIANA DE SOUSA","JULIANO DE JESUS MARTINS","JULIANO LIMA DOS ANJOS","JULIO CESAR ALMEIDA REGIS","JULIO CESAR DAS NEVES","JULIO CESAR MIRANDA DA ROCHA","JULIO CESAR PEREIRA DE ALMEIDA","JULIO CEZAR DOS SANTOS","JULIO CEZAR MENDES DOS SANTOS","JULIO LIMA JUNIOR","JULISSON VIEGA PEREIRA","JUNIOR CHAVES DO NASCIMENTO","JUNIOR DOS SANTOS SANTANA","JUNIOR MARTINS DOS SANTOS","JURACI TEIXEIRA BARROS","JURANDIR DE JESUS DOS SANTOS","JUSCELINO CERQUEIRA ARAUJO","JUSCELIO MOREIRA CHAVES","JUSCIMAR DE JESUS OLIVEIRA","JUSSARA ROBERTA ABREU DE CAMARGO","KÁLITA RAYSSA SOUZA COSTA","KAMILLO MOURA DE SOUZA","KARISSON ENRIQUE SIQUEIRA DE BRITO","KAUAN GABRIEL GOMES SILVA","KAWAM DA COSTA FREIRE","KEMERSON WALLA ROSA","KENNEDY SILVA EPIFANIO","KENNEDY VIEIRA DE SOUZA","KEROLAINE BATISTA NASCIMENTO","KEVIN SOUSA FERREIRA","KEYLLA SILVA LIMA","KLEVERSON TEODORO DA SILVA","LAUDIE BERNARDO ASSIS DE OLIVEIRA","LAURILENE SIRIANO BORGES","LAURO VINICIUS RAMOS SOBRINHO","LAZARO ENRICO CUPERTINO MAIA","LAZARO NEVES DOS SANTOS","LEANDRA SOUSA FIGUEIREDO CORDEIRO","LEANDRO BATISTA LIMA DOS SANTOS","LEANDRO DOS SANTOS GONÇALVES","LEANDRO GERALDO DA SILVA","LEANDRO OLIVEIRA FRANCO","LEANDRO PEREIRA LIMA","LEANDRO QUEIROZ DOS SANTOS","LEANDRO RODRIGUES DE ALMEIDA","LEANDRO SANTOS FRANCA","LEILA MARTINS DE OLIVEIRA","LEONAM LOPES FERNANDES","LEONARDO ALVES BOTELHO","LEONARDO AUGUSTO NOGUEIRA DE MIRANDA","LEONARDO DE MELO DA SILVA","LEONARDO FERREIRA DA SILVA","LEONARDO GOMES PEREIRA","LEONARDO HONORIO DE JESUS","LEONARDO MOREIRA ALVES","LEONARDO PINHEIRO BARBOSA DA SILVA","LEONES ASSUNCAO OLIVEIRA","LEVI PEREIRA DE SOUZA","LIDIO ALVES DE ALMEIDA FILHO","LIRIOVAN DOS SANTOS COUTO","LOREN GABRIELY CRUZ FIGUEIREDO","LORENA NOGUEIRA ROCHA","LOURIVAL DE JESUS SILVA","LOURIVAL JOSE BARRETO FILHO DO ESPIRITO SANTO","LUAM RICHARD PEREIRA DE SOUZA","LUAN ALVES SALOMAO","LUAN JORGE AGUIAR","LUANA OLIVEIRA COSTA","LUANA THAYLINE FERREIRA CRUZ","LUCAS ALVES RIBEIRO","LUCAS ANDRADE SOUZA","LUCAS DA PAIXAO SANTANA SANTOS","LUCAS ESTEVAO DA SILVA","LUCAS GOMES SANTANA","LUCAS SANTOS EVANGELISTA","LUCAS SILVA SANTOS","LUCAS VENANCIO GONCALO","LUCAS WASHINGTON SOARES","LUCIAN CAMPOS DE ASSIS","LUCIANO BRITO DOS SANTOS","LUCIANO FIRMINO DOS SANTOS","LUCIANO JESUS DOS SANTOS","LUCIANO MARTINS DE OLIVEIRA","LUCIANO MATEUS GONCALVES TEIXEIRA","LUCIANO PEREIRA MENDES","LUCIANO ROCHA DA SILVEIRA","LUCIANO SARDINHA EVANGELISTA","LUCIENE DUARTE SILVA","LUCIMAR GONCALVES","LUCIMAR SOARES DE MELO","LUCIO GABRIEL GUIMARAES MACIEL","LUDSON VIRIATO DA SILVA","LUIS CARLOS ALVES DA SILVA","LUIZ ALBERTO PEREIRA DOS SANTOS","LUIZ BRITO SILVA","LUIZ CARLOS CAMPOS DE ANDRADE","LUIZ CARLOS CORDEIRO DOS SANTOS","LUIZ CARLOS DOS SANTOS","LUIZ CARLOS PEREIRA BARBOSA","LUIZ CLAUDIO DOS SANTOS","LUIZ FELIPE RIBEIRO DE PAIVA","LUIZ HENRIQUE SOUZA FONSECA","LUIZ MOREIRA DOS SANTOS","LUIZ PAULO LOPES","LUKELINO SANTOS SAMPAIO","MACEDO PEREIRA DE LIMA","MACIEL SILVA ALVES","MAICON CHAVES BRAGA","MAICON PEREIRA LOPES","MALU MARIA DA SILVA ROCHA","MANOEL MISSIAS MARQUES DE SOUZA","MANOEL WERICO DOS SANTOS","MARCELO DE OLIVEIRA EVARISTO","MARCELO GOMES FERREIRA","MARCELO LIMA DE SOUZA","MARCELO MOREIRA LEMOS","MARCELO SPINOLA JUNIOR","MARCELO TEIXEIRA DE SANTANA","MARCIEL SERIANO BARBOSA","MARCIO DE SOUZA AMORIM","MARCIO GLEI ALMEIDA SANTOS","MARCIO HENRIQUE PEREIRA MARQUES","MARCIO JOSE DE SANTANA SANTOS","MARCIO OLIVEIRA DA SILVA","MARCIO RIVELINO DE LIMA","MARCO AURELIO FUNCHAL SANTOS","MARCONE GOMES DOS SANTOS","MARCONE RIBEIRO SANTOS","MARCONES CAETANO ALVES","MARCOS ARON NOGUEIRA CINTRA JUNIOR","MARCOS CHAVES CRUZ","MARCOS DOS SANTOS","MARCOS HENRIQUE GONCALVES DE ALMEIDA","MARCOS POLICARPO DA COSTA FILHO","MARCOS RAMALHO PARDIM","MARCOS ROBERTO GONCALVES FERREIRA","MARCOS SILVA SOUZA","MARCOS VINICIUS MENDES DE SOUZA","MARCOS VITOR SANTOS DE ALMEIDA","MARCOS WILLIAN DOS SANTOS VALERIO","MARCOS WINTER DE AGUIAR PINHEIRO","MARCUS PAULO LISBOA DA MOTA","MARCUS VINICIUS BARBOSA DE ARAUJO","MARIA CRISTINA OLIVEIRA DE JESUS","MARIA EDUARDA RIBEIRO ANDRADE","MARIA EDUARDA ROCHA VITORIA","MARIANA NAVES DE SOUZA","MARIANA SANTOS OLIVEIRA","MARILZA ALVES DOS SANTOS","MARINALDO COSTA DOS SANTOS","MARIO NOGUEIRA OLIVEIRA","MARIVAL BISPO DE JESUS","MARIVALDO SILVA MARTES","MARLON BRUNO DOS SANTOS","MARTINHO GAMA","MATEUS PEREIRA NERES","MATEUS VITOR ALMEIDA OLIVEIRA","MATHEUS DA SILVA DE JESUS","MATHEUS DA SILVA DOS SANTOS","MATHEUS DE LUCAS MESSIAS DA SILVA SANTANA","MATHEUS DE SOUZA RODRIGUES QUIRINO","MATHEUS HENRIQUE COSTA ALVES","MATHEUS JOSE DE PAULA CASSIANO","MATHEUS JUNIO FERREIRA SANTOS","MATHEUS SILVA SANTOS","MATOSALEM PEREIRA DE OLIVEIRA","MAUREDSON MIRANDA MELO DE SOUZA","MAURICIO DE JESUS SANTOS","MAURICIO NUNES DOS SANTOS","MAURICIO SENA CAMPOS","MAURO GOMES DA SILVA","MAX DE SOUZA DOS SANTOS","MAX OLIVEIRA ROCHA","MAXWELL SILVA MENDES","MESSIAS DE SANTANA SANTOS","MESSIAS JULIO NUNES SALOMAO","MESSIAS MARTINS DA SILVA","MICAEL PEREIRA REIS","MICAEL REGIS ALMEIDA","MICHEL WERLICH DE OLIVEIRA PORTILHO","MIGUEL GONCALVES MIRANDA NETO","MIKAEL NATA ALVES DE CARVALHO","MILTON MARTINS GONCALVES","MIRANDIR FERREIRA DA SILVA","MOISES CARDOSO DOS SANTOS","MOISES HENRIQUE PEREIRA BRANDAO","MOIZES DE CARVALHO CASAES","NADIR NELIA ALMEIDA DOS SANTOS","NAILTON ANDRADE DOS SANTOS","NALBERT SILVA BENTO","NARDSON FERREIRA ANDRADE","NATANAEL ALVES PEREIRA","NATHA ANDRADE DE OLIVEIRA","NAYANE SOUZA DE ANDRADE","NAYARA DA SILVA GONCALVES","NAYARA JULIA DE FARIA","NEIANDERSON FERREIRA DIAS","NEISON HENRIQUE QUEIROZ DE ALMEIDA","NEIVSON FABRICIO SILVA DA SILVA","NELIO VIEIRA DE SOUZA","NELSON CARDOSO DOS SANTOS NETO","NELTON ERICK ALMEIDA DUTRA","NICHOLAS INEZ BOAVENTURA SANTOS","NICODEMOS SILVA PAIXAO FILHO","NICOLAS JUNIO FIGUEREDO SANTOS","NIELSON COUTO MOTA","NILSON DA SILVA MAIA","NILSON FERNANDES LIMA","NILTON CESAR ALVES DE MACEDO","NIVALDO MOREIRA DE SOUZA JUNIOR","NIVALDO QUEIROZ NASCIMENTO","NIZALDO SANTOS DA SILVA","NOE ALVES SOUSA","NORIVAL OLIVEIRA DINIZ","ODAIR DO PRADO GONCALVES","ODILON SILVA SANTOS","OSCAR BRENER MARQUES DE MACEDO","OSEIAS JUNIOR DE SOUZA","OSMAN ROCHA BASTOS","OSMAR PEREIRA DA SILVA JUNIOR","OSVALDO LUCAS COSTA  ALVES","OTAVIANO LUIZ MAGALHAES PEREIRA","OTAVIO FABIAN FERREIRA DA COSTA","PABLO DIEGO RIBEIRO GONCALVES","PABLO HENRIQUE DE JESUS LAUREANO","PASCASSIO SOUZA DO COUTO","PASCOAL DOS SANTOS GONCALVES DE SOUZA","PATRICK DANIEL OLIVEIRA MOTA","PAULO AFONSO LEMOS SANTOS","PAULO DE ARAUJO OLIVEIRA","PAULO DONIZETTI DA SILVA","PAULO GOMES SILVA","PAULO HENRIQUE CHAVES","PAULO HENRIQUE SILVA LOURENCO","PAULO RICARDO SOARES SILVA","PAULO ROBERTO ANDRADE NASCIMENTO","PAULO ROBERTO DA COSTA REIS","PAULO ROSA DE LIMA","PAULO SERGIO DA COSTA","PAULO SERGIO SANTOS CORREIA","PAULO VITOR PIAUILINO MARINHO","PEDRO BRANDAO OLIVEIRA","PEDRO CAFE LOPES","PEDRO GARCIA DE SOUSA","PEDRO HENRIQUE CARVALHO DE OLIVEIRA","PEDRO HENRIQUE DA SILVA ARAUJO","PEDRO HENRIQUE MARQUES FERREIRA","PEDRO LUCAS RODRIGUES VIEIRA","PEDRO SANTOS DE OLIVEIRA","PETHERSON DIOGO SOARES DIAS","PHELIPE DE SOUZA SILVA","RAFAEL ALVES BRITO","RAFAEL DA SILVA MENDONCA","RAFAEL FERREIRA LEAL","RAFAEL LEMOS LIMA","RAFAEL PEREIRA","RAFAEL RIBEIRO GUEDES","RAFAEL SILVA ROCHA","RAFAELA LIMA DOS SANTOS","RAFAELA MACHADO DE SOUSA","RAIANE DE CASSIA SOUZA AUGUSTO","RAIMUNDO NASCIMENTO QUEIROZ","RAINILDO DOS SANTOS SILVA","RAMON DE ALMEIDA CARNEIRO","RAMON FERNANDES DO NASCIMENTO","RAMON LOPES DA CRUZ","RAMON SANTOS SOUSA","RAYLAN MOURA DOS SANTOS","REGINALDO SOARES SILVA","REGIVAL DE SOUZA SENA","REINAN DE ALMEIDA CARNEIRO","REINAN NOGUEIRA DOS SANTOS","REMILTON DE SOUZA GOMES","RENAN LIMA MENDES","RENATO DE JESUS","RENATO RODRIGUES MOREIRA","RENATO SANTOS FERNANDES","RENATO SANTOS LIMA","RENE FLAVIO PEREIRA ZUBA","RENILDO ALMEIDA DE QUEIROZ","RENILDO BRITO DOS SANTOS","RICARDO ALVES DOS SANTOS","RICARDO DE JESUS GOMES","RICARDO FREITAS DA SILVA","RICARDO LUCIANO PEREIRA","RICARDO PEREIRA DA SILVA JUNIOR","RICARDO RAMOS DOS SANTOS","RICARDO RODRIGUES DA SILVA","RICARDO SILVA BARBOSA","RICARDO VALENTIM FIUZA","RICK ALLAN DOS SANTOS","RIVIANE GUERREIRO NUNES","ROBENILSON DE JESUS MEDEIROS","ROBENILTON MAGALHAES LIMA","ROBERTA ABREU DE ALMEIDA","ROBERTO BATISTA DOS SANTOS","ROBERTO CARLOS LIMA CARDOSO","ROBERTO CARLOS TEIXEIRA DE OLIVEIRA","ROBERTO DE SOUZA PEREIRA","ROBERTO JOSE DOS SANTOS FILHO","ROBERTO LIMA DOS SANTOS","ROBERTO LOPES DA SILVA","ROBERTO QUEIROZ DA SILVA","ROBERTO SATURNINO GOMES","ROBSON BARRETO HELIODORIO","ROBSON MIRANDA FERREIRA","ROBSON PEREIRA DA SILVA","ROBSON RODRIGUES DOS SANTOS","RODINEY JESUS COSTA","RODRIGO CARDOSO DOS SANTOS","RODRIGO COSTA GRADIL SILVA","RODRIGO DA SILVA SOUSA","RODRIGO DE OLIVEIRA SILVA","RODRIGO DOS SANTOS","RODRIGO GOMES MARTINS","RODRIGO LEANDRO FERREIRA","RODRIGO SILVA DOS SANTOS","ROGERIO COUTO DE SOUZA","ROGERIO EDUARDO DOS SANTOS","ROMARIO GONCALVES LIMA","ROMILDO SANTOS DA ROCHA","ROMILSON CAETANO PIRES","ROMILSON DE JESUS SANTOS","ROMILSON DE SOUZA CERQUEIRA","RONALDO DA SILVA ANDRADE","RONALDO DE SOUZA DIAS","RONALDO FIGUEIREDO","RONALDO MENEZES MASCARENHAS","RONALDO PEREIRA LIMA","RONALDO RIBEIRO SOUSA","RONE VASCONCELOS","RONICLEI AVELINO DE SOUZA","RONILDO AURELIANO NASCIMENTO","RONIVAL JESUS DOS SANTOS","RONIVAN SILVA ARAUJO","ROQUE ANDRADE DOS SANTOS","ROSANGELA RUFINO FRANCISCO","RUAN CARLOS RODRIGUES DE OLIVEIRA","RYAN SILVA DE LIMA","SADY HUMBERTO COELHO NUNES","SALVIO WANDERLEY SOARES MACHADO","SAMUEL CORCINO","SAMUEL DOUGLAS QUEIROZ ARAUJO","SAMUEL PINTO SOARES","SAMUEL SANTOS DA SILVA","SAMUEL SOARES PEREIRA","SANDRO SOUZA GONCALVES","SANTIAGO LACERDA GUIMARAES","SAVIO ABADE DE JESUS","SEBASTIAO OPENHEIMER DE SOUZA","SEBASTIAO PEDRO DA SILVA","SEBASTIAO SOARES RAMOS","SELMO CARDOSO DA SILVA","SERGIO DE SOUZA ARAUJO JUNIOR","SHIRLEY MARINHO DE OLIVEIRA","SIDGREI SANTOS DA CONCEICAO","SIDNEI VIEIRA DOS SANTOS","SILAS DOS SANTOS GOMES","SILDEVAN SILVA DE FREITAS","SILVANDO SANTOS QUEIROZ","SILVIO EDUARDO MOURA OLIVEIRA","SINESIO RIBEIRO CERQUEIRA NETO","SORAIA SOARES FONSECA","TAILAN SILVA DE MENEZES","TAINAN VIANA OLIVEIRA","TALIS DA SILVA MARTINS","TALISSON ALVES DE SOUZA","TANCREDO AUGUSTO AMARAL DA CRUZ","TANURE CARLOS MASCARENHAS DOS SANTOS","TARCISIO MARCOS SOUSA SILVA","TARCISIO VIRISSIMO DA COSTA","TATIANA KELLEN DE CASTRO TEIXEIRA","TAWAN BARBOSA VIEIRA","TAYANE PRISCILA BRITO DE AVILA","THALES DA PAIXAO MIRANDA","THALES JOSE CORREIA AURELIO","THALES PINHEIRO CAMARA","THALISSON FERREIRA DE JESUS","THALLYS VINICIUS RAMOS XAVIER","THALLYS VINICIUS RODRIGUES FERNANDES COSTA","THAYNARA CRISTINA DA SILVA BARBOZA","THAYSA SANTOS AZEVEDO","THIAGO ANUNCIACAO DA CRUZ","THIAGO COSTA MACHADO","THIAGO ROGERIO DIAS RIBEIRO FERREIRA","THIAGO VIANA GOMES","THIARO SANTANA FIGUEIREDO","TIAGO CRISTIANO FARIAS","TIAGO DOS SANTOS MOREIRA","TIAGO HONORATO MARTINS","TIAGO ROCHA SILVA","UADSON AMARAL SANTANA","UBIRAJARA NUNES DA SILVA","UBIRATAN MASCENA DE SOUZA","UDSON GABRIEL RIBEIRO SOUZA","UEBESON GONÇALVES FERREIRA","UENDEL NUNES DE JESUS","UILHANS AMARAL LIMA","VAGUINER DA SILVA CAMOES","VALDEMIR BISPO DA CONCEICAO","VALDICK NOVAES DOS SANTOS","VALDINEY PEREIRA CARDOSO","VALDIR SERRA DO CARMO","VALDIRENE GERMANO DA SILVA","VALDIVINO ALAIR DIAS","VALNEI GOMES GUERRA","VALNEY EVANGELISTA SANTOS","VALTER MORAIS DOS ANJOS","VANDER SERVULO DA CRUZ","VANDERLANE BESSA DO SACRAMENTO SANTOS","VANDERLEI MOURA DA COSTA","VANESSA COSTA SANTANA","VANETE CANDIDA DE OLIVEIRA CUNHA","VANILSON SANTOS DE JESUS","VERONICA SOUZA OLIVEIRA","VICTOR EMANOEL NUNES","VILMAR JOSE MARTINS","VINICIUS FIGUEIREDO DOS SANTOS","VINICIUS NARCISO LADEIA","VITOR ALEXANDRE DOS SANTOS CRUZ","VITOR DE JESUS MARTINS EUGENIO","VITOR DOS SANTOS MAIA","VITOR GABRIEL ALVES AGUIAR","VITOR HENRIQUE FREITAS GOMES","VITOR HUGO SANTOS SCARCELA","VITOR POLICARPO DE ANDRADE","VITOR RODRIGUES SANTOS DAMASCENO","VITOR VIEIRA DE MELO DA SILVA","VITOR VIEIRA TEIXEIRA","VITORIA DOS SANTOS ATANASIO","VITÓRIA SILVA LIMA","WAGNER DOS SANTOS SILVA","WALACE ALVES FERREIRA","WALDIR BRITO DE MESQUITA","WALDIR RODRIGUES DE JESUS","WALDYR PEREIRA SILVA","WALTER RAMOS DUARTE NETO","WANDERLEY CHAVES DOS SANTOS","WANDERSON MEDRADE DE SOUZA","WANDRYO LARANJEIRA DO ESPIRITO SANTO","WANTUIL RESENDE DE MORAES","WARLEY DANIEL TEIXEIRA SANTOS","WARLEY EDUARDO DE JESUS MENDES","WASHINGTON FERREIRA MARINHO","WASHINGTON OLIVEIRA DA SILVA","WEDSON DE SANTANA SOARES","WELINGTON DE JESUS DIAS","WELLINGTON BARBOSA","WELVYS ALVES MOURA","WERLLON DE SOUZA COUTO","WESLEY LEONARDO ALVES PEREIRA","WEVERTTON PEREIRA OLIVEIRA","WILIAN PEREIRA RODRIGUES","WILKER MATEUS LIMA EVANGELISTA","WILLER MOREIRA FERNANDES","WILLIAM DE JESUS SALES","WILLIAM ESTEVAM DA COSTA","WILLIAN DHONEY CRUZ DE ANDRADE","WILSMARA RAQUEL DA SILVA REIS RODRIGUES","WILSON COSTA SANTOS","WILSON CRISTOVAO RODRIGUES DE QUEIROZ","WILSON DOS SANTOS OLIVEIRA MOURA","WILSON FERNANDES COTA LEITE","WILSON JOAO DE PAULA","YAGO DE MORAES SANTANA","YAN KLINIO DOS SANTOS FERNANDES DE SOUZA","YARA STHEFANI PEREIRA GONCALVES ARAUJO","YELANGELA COROMOTO MARTINEZ LUGO","YGOR FORTUNATO PIMENTA","YGOR RAMOS DE SOUZA","YHAN RHAGNER PEREIRA SIRIANO","ZENILDO CARDOSO ALVES"],"fatos":[[0,43,0,0],[1,34,0,0],[2,35,0,0],[3,43,0,0],[4,46,0,1],[5,11,0,0],[6,31,0,0],[7,21,0,0],[8,7,0,0],[9,31,0,0],[10,41,0,0],[11,43,0,0],[12,44,0,0],[13,43,0,1],[14,20,0,0],[15,40,0,0],[16,22,0,0],[17,46,0,0],[18,27,0,0],[19,40,0,0],[20,38,0,1],[21,31,0,1],[22,44,0,0],[23,5,0,1],[24,38,0,0],[25,18,0,0],[26,47,0,1],[27,30,0,0],[28,19,0,0],[29,46,0,1],[30,27,0,0],[31,1,0,0],[32,40,0,0],[33,24,0,0],[34,44,0,0],[35,17,0,1],[36,35,0,0],[37,44,0,0],[38,10,0,0],[39,36,0,0],[40,17,0,0],[41,29,0,0],[42,14,0,0],[43,47,0,0],[44,15,0,1],[45,24,0,0],[46,47,0,1],[47,19,0,0],[48,29,0,1],[49,44,0,0],[50,17,0,0],[51,46,0,0],[52,14,0,0],[53,24,0,0],[54,29,0,1],[55,1,0,0],[56,44,0,0],[57,30,0,0],[58,27,0,0],[59,45,0,0],[60,36,0,0],[61,10,0,0],[62,40,0,0],[63,44,0,0],[64,26,0,0],[65,40,0,0],[66,35,0,0],[67,36,0,0],[68,37,0,1],[69,28,0,0],[70,9,0,0],[71,15,0,0],[72,46,0,0],[73,21,0,0],[74,39,0,0],[75,43,0,1],[76,15,0,0],[77,29,0,0],[794,23,0,0],[79,21,0,0],[80,31,0,0],[81,34,0,1],[82,11,0,1],[83,44,0,0],[84,37,0,1],[85,11,0,1],[86,15,0,1],[87,43,0,1],[88,38,0,0],[89,33,0,0],[90,14,0,0],[91,41,0,0],[92,11,0,1],[93,13,0,0],[94,8,0,0],[95,21,0,0],[96,47,0,1],[97,14,0,0],[98,46,0,1],[99,38,0,0],[100,39,0,0],[101,1,0,1],[102,11,0,1],[103,20,0,0],[104,44,0,1],[105,47,0,1],[106,33,0,0],[107,10,0,0],[108,30,0,0],[109,20,0,1],[110,12,0,1],[111,38,0,0],[112,14,0,0],[113,25,0,0],[114,24,0,0],[115,26,0,0],[116,2,0,0],[117,11,0,0],[118,47,0,1],[119,28,0,0],[120,24,0,0],[121,29,0,0],[122,40,0,0],[123,35,0,0],[124,46,0,1],[125,26,0,0],[126,11,0,1],[127,44,0,0],[128,21,0,0],[129,14,0,0],[130,8,0,0],[131,11,0,0],[132,36,0,1],[133,20,0,0],[134,24,0,0],[135,47,0,1],[136,21,0,0],[137,21,0,0],[138,34,0,0],[139,46,0,0],[140,17,0,0],[141,45,0,0],[142,31,0,0],[143,29,0,0],[144,46,0,1],[145,46,0,1],[146,35,0,0],[147,34,0,0],[148,43,0,1],[149,44,0,0],[150,44,0,0],[151,11,0,1],[152,6,0,0],[153,9,0,1],[154,36,0,0],[155,46,0,0],[156,11,0,0],[157,20,0,1],[158,31,0,1],[159,27,0,0],[160,29,0,1],[161,43,0,1],[162,6,0,0],[846,23,0,0],[164,32,0,0],[165,15,0,0],[166,35,0,0],[167,21,0,0],[168,4,0,0],[169,19,0,0],[170,43,0,1],[171,12,0,0],[172,4,0,0],[173,15,0,1],[174,43,0,1],[175,18,0,1],[176,31,0,0],[177,29,0,0],[178,46,0,1],[179,27,0,0],[180,33,0,0],[181,13,0,0],[182,27,0,0],[183,17,0,0],[184,46,0,0],[185,29,0,1],[186,33,0,1],[187,32,0,1],[188,18,0,0],[189,15,0,1],[190,40,0,0],[191,43,0,0],[192,14,0,0],[193,36,0,1],[194,24,0,0],[195,20,0,1],[196,46,0,1],[197,46,0,1],[198,6,0,0],[199,24,0,0],[200,24,0,0],[201,36,0,0],[202,15,0,1],[203,1,0,1],[204,20,0,0],[205,31,0,1],[206,6,0,0],[207,49,0,0],[208,46,0,1],[209,11,0,1],[210,42,0,0],[211,21,0,0],[794,23,1,0],[213,24,0,0],[214,12,0,0],[215,10,0,0],[216,3,0,0],[217,28,0,0],[218,40,0,0],[219,46,0,0],[220,44,0,0],[221,43,0,0],[222,26,0,0],[223,15,0,1],[224,43,0,0],[846,23,1,0],[226,3,0,0],[227,44,0,0],[228,7,0,0],[229,22,0,0],[230,10,0,0],[231,21,0,0],[232,8,0,0],[233,29,0,0],[234,7,0,1],[235,14,0,0],[236,0,0,0],[237,35,0,0],[794,23,2,0],[239,1,0,1],[240,29,0,0],[241,46,0,1],[242,29,0,0],[243,44,0,0],[244,46,0,1],[245,40,0,0],[246,35,0,0],[247,26,0,0],[248,35,0,0],[249,12,0,1],[250,33,0,1],[251,14,0,0],[252,14,0,0],[253,47,0,0],[254,46,0,1],[255,32,0,0],[256,26,0,1],[257,32,0,0],[258,43,0,0],[259,21,0,1],[260,7,0,0],[261,47,0,1],[262,34,0,0],[263,29,0,0],[264,43,0,1],[265,15,0,1],[266,3,0,1],[267,12,0,1],[268,46,0,1],[269,37,0,1],[270,3,0,1],[271,1,0,0],[272,12,0,1],[273,41,0,0],[274,17,0,0],[275,32,0,1],[276,39,0,0],[277,40,0,0],[278,31,0,1],[279,31,0,1],[280,44,0,0],[281,4,0,0],[282,21,0,0],[283,4,0,0],[284,28,0,0],[285,41,0,0],[286,43,0,1],[287,1,0,1],[288,19,0,0],[289,29,0,0],[290,31,0,1],[291,41,0,0],[292,34,0,0],[293,9,0,1],[294,40,0,0],[295,43,0,1],[296,44,0,0],[297,28,0,0],[298,25,0,0],[299,46,0,0],[300,1,0,1],[301,0,0,1],[302,3,0,1],[303,43,0,1],[304,43,0,1],[305,35,0,0],[306,46,0,0],[307,38,0,1],[308,39,0,0],[309,1,0,0],[310,44,0,0],[311,37,0,1],[312,37,0,1],[313,13,0,0],[314,29,0,1],[315,43,0,1],[316,9,0,0],[317,2,0,0],[318,1,0,0],[319,31,0,0],[320,29,0,0],[321,32,0,0],[322,14,0,0],[323,27,0,0],[324,44,0,1],[325,40,0,0],[326,29,0,1],[327,40,0,0],[328,43,0,0],[329,43,0,0],[330,0,0,1],[331,13,0,1],[332,8,0,0],[333,32,0,0],[334,31,0,0],[335,21,0,0],[336,7,0,1],[337,5,0,1],[338,35,0,0],[339,12,0,0],[340,22,0,0],[341,7,0,0],[342,34,0,0],[343,9,0,0],[344,28,0,0],[345,30,0,0],[346,27,0,0],[347,35,0,0],[348,4,0,0],[349,30,0,0],[350,47,0,1],[846,23,2,0],[352,29,0,0],[353,16,0,0],[354,28,0,0],[355,30,0,0],[356,43,0,1],[357,44,0,0],[358,3,0,0],[359,28,0,0],[360,18,0,0],[361,11,0,0],[362,19,0,0],[363,26,0,0],[364,24,0,0],[365,30,0,0],[366,11,0,0],[367,12,0,0],[368,35,0,0],[369,25,0,0],[370,19,0,0],[371,40,0,0],[372,43,0,0],[373,40,0,0],[374,30,0,0],[375,40,0,0],[376,42,0,0],[377,38,0,1],[378,37,0,1],[379,29,0,0],[380,40,0,0],[381,39,0,0],[382,44,0,0],[383,30,0,0],[384,44,0,0],[385,29,0,0],[386,8,0,0],[387,11,0,0],[388,30,0,0],[389,30,0,0],[390,38,0,0],[391,8,0,0],[392,11,0,0],[393,44,0,0],[394,47,0,1],[395,43,0,1],[396,11,0,0],[397,35,0,0],[398,16,0,0],[399,29,0,0],[400,27,0,0],[401,43,0,1],[402,43,0,1],[403,30,0,1],[404,43,0,1],[405,10,0,0],[406,43,0,0],[407,6,0,0],[408,46,0,1],[409,21,0,0],[410,46,0,1],[411,36,0,1],[412,41,0,0],[413,7,0,0],[414,43,0,0],[415,46,0,0],[416,47,0,1],[417,14,0,0],[418,28,0,0],[419,46,0,1],[420,5,0,0],[421,24,0,0],[422,8,0,0],[423,34,0,0],[424,44,0,0],[425,29,0,1],[426,32,0,1],[427,33,0,1],[428,21,0,1],[429,36,0,1],[430,7,0,0],[431,38,0,1],[432,31,0,0],[433,29,0,0],[434,21,0,0],[435,46,0,1],[436,25,0,0],[437,32,0,0],[438,14,0,0],[439,32,0,0],[440,13,0,0],[441,32,0,0],[442,9,0,1],[443,7,0,1],[444,29,0,1],[445,42,0,1],[446,29,0,0],[447,17,0,0],[448,40,0,0],[449,8,0,0],[450,17,0,0],[451,20,0,0],[452,29,0,0],[453,11,0,0],[454,0,0,0],[455,40,0,0],[456,21,0,0],[457,42,0,0],[458,8,0,0],[459,31,0,0],[460,42,0,1],[461,43,0,1],[462,20,0,0],[463,44,0,0],[464,29,0,1],[465,21,0,0],[466,40,0,0],[467,44,0,0],[468,44,0,0],[469,40,0,0],[470,16,0,0],[471,29,0,0],[472,0,0,1],[473,37,0,1],[474,43,0,1],[475,5,0,1],[476,19,0,0],[477,29,0,1],[794,23,3,0],[479,7,0,0],[480,25,0,0],[481,34,0,0],[482,33,0,0],[483,1,0,0],[484,13,0,0],[485,47,0,1],[486,34,0,0],[487,24,0,0],[488,43,0,1],[489,39,0,0],[490,40,0,0],[491,34,0,0],[492,22,0,0],[493,6,0,0],[494,35,0,0],[495,29,0,0],[496,11,0,1],[497,35,0,0],[498,18,0,0],[499,18,0,1],[500,29,0,0],[501,18,0,1],[502,12,0,1],[503,31,0,0],[504,46,0,0],[505,40,0,0],[506,13,0,0],[507,44,0,0],[508,27,0,0],[509,42,0,1],[510,30,0,0],[511,11,0,0],[512,14,0,0],[513,27,0,0],[514,44,0,0],[515,11,0,0],[516,46,0,0],[517,47,0,0],[518,22,0,0],[519,28,0,0],[520,11,0,0],[521,13,0,0],[522,40,0,0],[523,4,0,0],[524,27,0,0],[525,12,0,0],[526,37,0,1],[527,31,0,0],[528,43,0,1],[529,20,0,0],[530,13,0,0],[531,17,0,0],[532,19,0,0],[533,21,0,0],[534,26,0,1],[535,10,0,0],[536,48,0,0],[537,29,0,0],[538,31,0,0],[539,46,0,1],[540,3,0,1],[541,36,0,0],[542,7,0,0],[543,16,0,1],[544,32,0,0],[545,12,0,0],[546,2,0,0],[547,13,0,0],[548,29,0,0],[549,13,0,0],[550,40,0,0],[551,19,0,0],[552,41,0,0],[553,2,0,0],[554,9,0,0],[555,2,0,0],[556,39,0,0],[557,31,0,1],[558,40,0,0],[559,11,0,1],[560,45,0,0],[561,9,0,0],[562,21,0,0],[563,47,0,1],[564,29,0,0],[565,21,0,0],[566,33,0,1],[567,44,0,1],[568,44,0,0],[569,39,0,0],[570,29,0,0],[571,1,0,0],[572,22,0,0],[573,8,0,0],[574,5,0,0],[575,12,0,0],[576,31,0,0],[577,42,0,0],[578,34,0,1],[579,16,0,0],[580,1,0,1],[581,5,0,1],[582,11,0,1],[583,7,0,0],[584,43,0,0],[585,42,0,0],[586,46,0,1],[587,46,0,0],[588,40,0,0],[589,26,0,0],[590,43,0,1],[591,46,0,0],[592,18,0,0],[593,39,0,0],[594,41,0,1],[595,46,0,1],[596,45,0,0],[597,37,0,1],[598,25,0,0],[599,44,0,0],[600,29,0,0],[601,44,0,0],[602,25,0,0],[603,10,0,1],[604,6,0,0],[605,26,0,1],[606,43,0,1],[607,1,0,0],[608,21,0,0],[609,1,0,1],[610,0,0,1],[611,41,0,0],[612,19,0,0],[613,44,0,0],[614,46,0,1],[615,41,0,0],[616,7,0,0],[617,38,0,1],[618,28,0,1],[619,45,0,0],[620,20,0,1],[621,35,0,0],[622,33,0,1],[623,25,0,0],[624,29,0,1],[625,5,0,0],[626,1,0,1],[627,32,0,0],[628,18,0,1],[629,45,0,0],[630,4,0,0],[631,25,0,0],[632,45,0,0],[633,45,0,0],[634,8,0,0],[635,16,0,0],[636,29,0,0],[637,34,0,1],[638,40,0,0],[639,11,0,0],[640,0,0,0],[641,44,0,0],[642,22,0,1],[643,11,0,0],[644,44,0,0],[645,10,0,0],[646,10,0,1],[647,31,0,0],[846,23,3,0],[649,24,0,0],[650,29,0,1],[651,33,0,1],[652,1,0,0],[653,1,0,1],[654,43,0,1],[655,34,0,0],[656,21,0,1],[657,11,0,0],[658,16,0,0],[659,30,0,0],[794,23,4,0],[661,46,0,0],[662,19,0,0],[663,27,0,1],[664,7,0,0],[665,39,0,0],[666,39,0,0],[667,30,0,0],[668,46,0,1],[669,31,0,1],[670,40,0,0],[671,1,0,1],[672,19,0,0],[673,15,0,1],[674,16,0,0],[675,12,0,1],[676,29,0,0],[677,19,0,0],[678,16,0,0],[679,22,0,0],[680,21,0,1],[681,39,0,0],[682,28,0,0],[683,31,0,0],[684,35,0,0],[685,40,0,0],[686,29,0,1],[687,32,0,1],[688,0,0,1],[689,27,0,0],[690,9,0,0],[691,43,0,1],[692,43,0,1],[693,21,0,0],[694,46,0,1],[695,25,0,0],[696,8,0,0],[697,40,0,0],[698,10,0,0],[699,28,0,0],[700,37,0,1],[701,1,0,1],[702,24,0,0],[703,40,0,0],[704,29,0,0],[705,47,0,1],[706,7,0,1],[707,28,0,0],[708,25,0,0],[709,24,0,0],[710,31,0,0],[711,26,0,0],[712,1,0,0],[713,3,0,1],[714,34,0,0],[715,29,0,1],[716,40,0,0],[717,45,0,0],[718,20,0,0],[719,26,0,0],[720,32,0,0],[721,46,0,1],[722,29,0,1],[723,33,0,1],[846,23,4,0],[725,19,0,0],[726,46,0,0],[727,11,0,1],[728,17,0,0],[729,21,0,0],[730,19,0,0],[731,11,0,0],[732,1,0,0],[733,5,0,1],[734,30,0,0],[735,20,0,0],[736,29,0,1],[737,40,0,0],[738,21,0,0],[739,33,0,0],[740,29,0,0],[741,11,0,1],[742,27,0,0],[743,12,0,0],[744,29,0,1],[745,25,0,0],[746,44,0,0],[747,27,0,1],[748,46,0,1],[749,43,0,1],[750,43,0,1],[751,46,0,0],[752,4,0,0],[753,21,0,0],[754,12,0,0],[755,40,0,0],[756,20,0,0],[757,16,0,0],[758,45,0,0],[759,4,0,0],[760,3,0,0],[794,23,5,0],[762,25,0,0],[763,14,0,0],[764,6,0,0],[765,11,0,0],[766,22,0,0],[767,38,0,0],[768,44,0,0],[769,2,0,0],[770,22,0,0],[771,8,0,0],[772,44,0,0],[773,38,0,0],[774,7,0,0],[775,28,0,0],[776,37,0,1],[777,14,0,0],[778,10,0,1],[779,46,0,0],[780,29,0,0],[781,3,0,1],[782,11,0,0],[783,43,0,1],[784,11,0,0],[785,38,0,0],[786,43,0,1],[787,40,0,0],[788,34,0,0],[789,7,0,1],[790,11,0,0],[791,46,0,1],[792,43,0,1],[793,24,0,0],[846,23,5,0],[795,36,0,0],[796,24,0,0],[797,42,0,1],[798,12,0,0],[799,40,0,0],[800,3,0,0],[801,4,0,0],[802,18,0,1],[803,3,0,1],[804,21,0,0],[805,8,0,0],[806,31,0,0],[807,17,0,0],[808,36,0,0],[809,42,0,1],[810,35,0,0],[811,44,0,0],[846,23,6,0],[813,28,0,1],[814,29,0,0],[815,45,0,0],[816,4,0,0],[817,43,0,0],[818,32,0,0],[819,31,0,0],[820,8,0,0],[821,24,0,0],[822,29,0,0],[823,15,0,0],[824,46,0,1],[825,40,0,0],[826,11,0,0],[827,44,0,0],[828,46,0,1],[829,26,0,0],[830,24,0,0],[831,1,0,1],[832,46,0,1],[78,23,0,0],[834,43,0,1],[835,10,0,0],[836,2,0,0],[837,3,0,0],[838,43,0,1],[839,39,0,0],[840,43,0,1],[841,22,0,0],[842,11,0,1],[843,28,0,1],[844,37,0,1],[845,13,0,0],[163,23,0,0],[847,47,0,0],[848,31,0,0],[849,26,0,0],[850,44,0,0],[851,5,0,0],[852,31,0,0],[853,44,0,0],[854,32,0,0],[855,33,0,1],[856,12,0,1],[857,44,0,0],[858,8,0,0],[212,23,0,0],[860,43,0,1],[861,46,0,1],[862,40,0,0],[863,0,0,1],[864,11,0,0],[865,44,0,0],[866,40,0,0],[867,29,0,0],[868,38,0,0],[869,40,0,0],[870,35,0,0],[871,46,0,1],[872,34,0,1],[873,43,0,1],[874,30,0,1],[875,11,0,0],[876,44,0,0],[877,31,0,1],[878,41,0,0],[879,40,0,0],[880,47,0,1],[881,44,0,0],[882,12,0,0],[883,24,0,0],[225,23,0,0],[885,35,0,0],[886,31,0,1],[887,30,0,0],[888,1,0,0],[889,39,0,0],[890,18,0,0],[891,43,0,1],[892,46,0,0],[893,11,0,0],[894,46,0,1],[895,21,0,0],[896,11,0,0],[897,9,0,1],[898,22,0,1],[899,34,0,0],[900,0,0,1],[901,43,0,1],[902,0,0,0],[903,22,0,1],[904,31,0,0],[905,31,0,0],[906,2,0,0],[907,19,0,0],[908,46,0,0],[909,41,0,1],[910,8,0,0],[911,42,0,0],[912,13,0,0],[913,0,0,0],[914,2,0,0],[915,41,0,0],[916,42,0,0],[917,12,0,0],[918,44,0,0],[919,22,0,0],[920,47,0,1],[921,22,0,0],[922,42,0,0],[923,42,0,1],[924,43,0,1],[925,27,0,0],[926,46,0,1],[927,25,0,0],[928,44,0,0],[929,40,0,0],[930,24,0,0],[931,13,0,0],[932,37,0,1],[933,47,0,1],[934,46,0,0],[935,19,0,0],[936,31,0,0],[937,11,0,0],[938,3,0,1],[939,29,0,1],[940,0,0,0],[941,29,0,1],[238,23,0,0],[943,15,0,1],[944,33,0,1],[945,34,0,0],[946,39,0,0],[947,36,0,0],[351,23,0,0],[949,5,0,0],[950,33,0,0],[951,29,0,1],[952,19,0,0],[953,9,0,0],[954,40,0,0],[955,44,0,0],[956,6,0,0],[957,35,0,0],[958,43,0,0],[959,29,0,0],[960,43,0,0],[961,29,0,1],[962,46,0,1],[963,44,0,0],[964,10,0,0],[965,9,0,1],[966,31,0,0],[967,41,0,1],[968,22,0,0],[969,12,0,0],[970,24,0,0],[971,44,0,0],[972,29,0,1],[973,43,0,1],[974,6,0,0],[975,19,0,0],[976,14,0,0],[977,35,0,0],[978,12,0,0],[979,27,0,1],[980,13,0,0],[981,25,0,0],[982,34,0,0],[983,36,0,1],[984,34,0,0],[985,41,0,1],[986,9,0,0],[987,37,0,1],[988,9,0,0],[989,47,0,0],[990,13,0,0],[991,38,0,1],[992,43,0,1],[993,29,0,0],[994,11,0,0],[995,15,0,1],[996,44,0,0],[997,21,0,0],[998,38,0,1],[999,21,0,0],[1000,29,0,0],[1001,40,0,0],[1002,0,0,0],[1003,33,0,0],[1004,43,0,1],[1005,21,0,0],[1006,46,0,1],[1007,11,0,0],[1008,38,0,1],[1009,11,0,0],[1010,21,0,0],[1011,25,0,0],[1012,43,0,1],[1013,46,0,1],[1014,9,0,0],[1015,2,0,0],[1016,11,0,1],[1017,31,0,0],[1018,40,0,0],[1019,10,0,0],[1020,43,0,1],[1021,30,0,0],[1022,6,0,0],[1023,33,0,0],[1024,1,0,0],[1025,29,0,0],[1026,26,0,1],[1027,24,0,0],[1028,37,0,1],[1029,44,0,0],[1030,21,0,0],[1031,0,0,1],[1032,25,0,0],[1033,0,0,1],[1034,29,0,0],[1035,8,0,0],[1036,1,0,1],[1037,39,0,0],[1038,19,0,0],[1039,24,0,0],[1040,29,0,0],[1041,31,0,1],[1042,34,0,0],[1043,21,0,0],[1044,21,0,0],[1045,11,0,0],[1046,19,0,0],[1047,45,0,0],[1048,21,0,0],[1049,27,0,0],[1050,40,0,0],[1051,7,0,0],[1052,46,0,1],[1053,2,0,0],[1054,40,0,0],[1055,26,0,0],[1056,46,0,0],[478,23,0,0],[1058,37,0,1],[1059,21,0,0],[1060,41,0,0],[1061,1,0,1],[1062,12,0,1],[1063,34,0,0],[1064,10,0,0],[1065,27,0,0],[1066,28,0,0],[1067,11,0,1],[1068,1,0,1],[1069,45,0,1],[1070,46,0,1],[0,43,1,0],[1,34,1,0],[2,35,1,0],[3,43,1,0],[4,46,1,1],[5,11,1,0],[6,31,1,0],[7,21,1,0],[8,7,1,0],[9,31,1,0],[10,41,1,0],[11,43,1,0],[12,44,1,0],[13,43,1,1],[14,20,1,0],[15,40,1,0],[16,22,1,0],[17,46,1,0],[18,27,1,0],[19,40,1,0],[20,38,1,0],[21,31,1,1],[22,44,1,0],[23,5,1,1],[24,38,1,0],[25,18,1,0],[26,47,1,1],[27,30,1,0],[28,19,1,0],[29,46,1,1],[30,27,1,0],[31,1,1,0],[32,40,1,0],[33,24,1,0],[34,44,1,0],[35,17,1,1],[36,35,1,0],[37,44,1,0],[38,10,1,0],[39,36,1,0],[40,17,1,0],[41,29,1,0],[42,14,1,0],[43,47,1,0],[44,15,1,1],[45,24,1,0],[46,47,1,1],[47,19,1,0],[48,29,1,1],[49,44,1,0],[50,17,1,0],[51,46,1,0],[52,14,1,0],[53,24,1,0],[54,29,1,1],[55,1,1,0],[56,44,1,0],[57,30,1,0],[58,27,1,0],[59,45,1,0],[60,36,1,0],[61,10,1,0],[62,40,1,0],[63,44,1,0],[64,26,1,0],[65,40,1,0],[66,35,1,0],[67,36,1,0],[68,37,1,1],[69,28,1,0],[70,9,1,0],[71,15,1,0],[72,46,1,0],[73,21,1,0],[74,39,1,0],[75,43,1,1],[76,15,1,0],[77,29,1,0],[648,23,0,0],[79,21,1,0],[80,31,1,0],[81,34,1,1],[82,11,1,1],[83,44,1,0],[84,37,1,1],[85,11,1,1],[86,15,1,1],[87,43,1,1],[88,38,1,0],[89,33,1,0],[90,14,1,0],[91,41,1,0],[92,11,1,1],[93,13,1,0],[94,8,1,0],[95,21,1,0],[96,47,1,1],[97,14,1,0],[98,46,1,1],[99,38,1,0],[100,39,1,0],[101,1,1,1],[102,11,1,1],[103,20,1,0],[104,44,1,1],[105,47,1,1],[106,33,1,0],[107,10,1,0],[108,30,1,0],[109,20,1,1],[110,12,1,1],[111,38,1,0],[112,14,1,0],[113,25,1,0],[114,24,1,0],[115,26,1,0],[116,2,1,0],[117,11,1,0],[118,47,1,0],[119,28,1,0],[120,24,1,0],[121,29,1,0],[122,40,1,0],[123,35,1,0],[124,46,1,1],[125,26,1,0],[126,11,1,1],[127,44,1,0],[128,21,1,0],[129,14,1,0],[130,8,1,0],[131,11,1,0],[132,36,1,1],[133,20,1,0],[134,24,1,0],[135,47,1,1],[136,21,1,0],[137,21,1,0],[138,34,1,0],[139,46,1,0],[140,17,1,0],[141,45,1,0],[142,31,1,0],[143,29,1,0],[144,46,1,1],[145,46,1,0],[146,35,1,0],[147,34,1,0],[148,43,1,1],[149,44,1,0],[150,44,1,0],[151,11,1,1],[152,6,1,0],[153,9,1,0],[154,36,1,0],[155,46,1,0],[156,11,1,0],[157,20,1,1],[158,31,1,1],[159,27,1,0],[160,29,1,1],[161,43,1,1],[162,6,1,0],[660,23,0,0],[164,32,1,0],[165,15,1,0],[166,35,1,0],[167,21,1,0],[168,4,1,0],[169,19,1,0],[170,43,1,1],[171,12,1,0],[172,4,1,0],[173,15,1,1],[174,43,1,1],[175,18,1,0],[176,31,1,0],[177,29,1,0],[178,46,1,1],[179,27,1,0],[180,33,1,0],[181,13,1,0],[182,27,1,0],[183,17,1,0],[184,46,1,0],[185,29,1,0],[186,33,1,1],[187,32,1,1],[188,18,1,0],[189,15,1,1],[190,40,1,0],[191,43,1,0],[192,14,1,0],[193,36,1,1],[194,24,1,0],[195,20,1,1],[196,46,1,0],[197,46,1,0],[198,6,1,0],[199,24,1,0],[200,24,1,0],[201,36,1,0],[202,15,1,1],[203,1,1,1],[204,20,1,0],[205,31,1,1],[206,6,1,0],[207,49,1,0],[208,46,1,1],[209,11,1,1],[210,42,1,0],[211,21,1,0],[724,23,0,0],[213,24,1,0],[214,12,1,0],[215,10,1,0],[216,3,1,0],[217,28,1,0],[218,40,1,0],[219,46,1,0],[220,44,1,0],[221,43,1,0],[222,26,1,0],[223,15,1,1],[224,43,1,0],[761,23,0,0],[226,3,1,0],[227,44,1,0],[228,7,1,0],[229,22,1,0],[230,10,1,0],[231,21,1,0],[232,8,1,0],[233,29,1,0],[234,7,1,1],[235,14,1,0],[236,0,1,0],[237,35,1,0],[812,23,0,0],[239,1,1,1],[240,29,1,0],[241,46,1,1],[242,29,1,0],[243,44,1,0],[244,46,1,1],[245,40,1,0],[246,35,1,0],[247,26,1,0],[248,35,1,0],[249,12,1,1],[250,33,1,1],[251,14,1,0],[252,14,1,0],[253,47,1,0],[254,46,1,1],[255,32,1,0],[256,26,1,1],[257,32,1,0],[258,43,1,0],[259,21,1,0],[260,7,1,0],[261,47,1,1],[262,34,1,0],[263,29,1,0],[264,43,1,1],[265,15,1,1],[266,3,1,1],[267,12,1,1],[268,46,1,1],[269,37,1,1],[270,3,1,1],[271,1,1,0],[272,12,1,1],[273,41,1,0],[274,17,1,0],[275,32,1,1],[276,39,1,0],[277,40,1,0],[278,31,1,1],[279,31,1,1],[280,44,1,0],[281,4,1,0],[282,21,1,0],[283,4,1,0],[284,28,1,0],[285,41,1,0],[286,43,1,1],[287,1,1,1],[288,19,1,0],[289,29,1,0],[290,31,1,1],[291,41,1,0],[292,34,1,0],[293,9,1,1],[294,40,1,0],[295,43,1,1],[296,44,1,0],[297,28,1,0],[298,25,1,0],[299,46,1,0],[300,1,1,1],[301,0,1,1],[302,3,1,1],[303,43,1,1],[304,43,1,1],[305,35,1,0],[306,46,1,0],[307,38,1,1],[308,39,1,0],[309,1,1,0],[310,44,1,0],[311,37,1,1],[312,37,1,1],[313,13,1,0],[314,29,1,1],[315,43,1,1],[316,9,1,0],[317,2,1,0],[318,1,1,0],[319,31,1,0],[320,29,1,0],[321,32,1,0],[322,14,1,0],[323,27,1,0],[324,44,1,1],[325,40,1,0],[326,29,1,1],[327,40,1,0],[328,43,1,0],[329,43,1,0],[330,0,1,1],[331,13,1,1],[332,8,1,0],[333,32,1,0],[334,31,1,0],[335,21,1,0],[336,7,1,1],[337,5,1,1],[338,35,1,0],[339,12,1,0],[340,22,1,0],[341,7,1,0],[342,34,1,0],[343,9,1,0],[344,28,1,0],[345,30,1,0],[346,27,1,0],[347,35,1,0],[348,4,1,0],[349,30,1,0],[350,47,1,1],[833,23,0,0],[352,29,1,0],[353,16,1,0],[354,28,1,0],[355,30,1,0],[356,43,1,1],[357,44,1,0],[358,3,1,0],[359,28,1,0],[360,18,1,0],[361,11,1,0],[362,19,1,0],[363,26,1,0],[364,24,1,0],[365,30,1,0],[366,11,1,0],[367,12,1,0],[368,35,1,0],[369,25,1,0],[370,19,1,0],[371,40,1,0],[372,43,1,0],[373,40,1,0],[374,30,1,0],[375,40,1,0],[376,42,1,0],[377,38,1,1],[378,37,1,1],[379,29,1,0],[380,40,1,0],[381,39,1,0],[382,44,1,0],[383,30,1,0],[384,44,1,0],[385,29,1,0],[386,8,1,0],[387,11,1,0],[388,30,1,0],[389,30,1,0],[390,38,1,0],[391,8,1,0],[392,11,1,0],[393,44,1,0],[394,47,1,1],[395,43,1,1],[396,11,1,0],[397,35,1,0],[398,16,1,0],[399,29,1,0],[400,27,1,0],[401,43,1,1],[402,43,1,1],[403,30,1,1],[404,43,1,0],[405,10,1,0],[406,43,1,0],[407,6,1,0],[408,46,1,1],[409,21,1,0],[410,46,1,1],[411,36,1,0],[412,41,1,0],[413,7,1,0],[414,43,1,0],[415,46,1,0],[416,47,1,1],[417,14,1,0],[418,28,1,0],[419,46,1,1],[420,5,1,0],[421,24,1,0],[422,8,1,0],[423,34,1,0],[424,44,1,0],[425,29,1,1],[426,32,1,1],[427,33,1,1],[428,21,1,1],[429,36,1,1],[430,7,1,0],[431,38,1,1],[432,31,1,0],[433,29,1,0],[434,21,1,0],[435,46,1,1],[436,25,1,0],[437,32,1,0],[438,14,1,0],[439,32,1,0],[440,13,1,0],[441,32,1,0],[442,9,1,1],[443,7,1,1],[444,29,1,1],[445,42,1,1],[446,29,1,0],[447,17,1,0],[448,40,1,0],[449,8,1,0],[450,17,1,0],[451,20,1,0],[452,29,1,0],[453,11,1,0],[454,0,1,0],[455,40,1,0],[456,21,1,0],[457,42,1,0],[458,8,1,0],[459,31,1,0],[460,42,1,1],[461,43,1,1],[462,20,1,0],[463,44,1,0],[464,29,1,1],[465,21,1,0],[466,40,1,0],[467,44,1,0],[468,44,1,0],[469,40,1,0],[470,16,1,0],[471,29,1,0],[472,0,1,1],[473,37,1,1],[474,43,1,1],[475,5,1,1],[476,19,1,0],[477,29,1,1],[859,23,0,0],[479,7,1,0],[480,25,1,0],[481,34,1,0],[482,33,1,0],[483,1,1,0],[484,13,1,0],[485,47,1,1],[486,34,1,0],[487,24,1,0],[488,43,1,1],[489,39,1,0],[490,40,1,0],[491,34,1,0],[492,22,1,0],[493,6,1,0],[494,35,1,0],[495,29,1,0],[496,11,1,1],[497,35,1,0],[498,18,1,0],[499,18,1,1],[500,29,1,0],[501,18,1,1],[502,12,1,1],[503,31,1,0],[504,46,1,0],[505,40,1,0],[506,13,1,0],[507,44,1,0],[508,27,1,0],[509,42,1,1],[510,30,1,0],[511,11,1,0],[512,14,1,0],[513,27,1,0],[514,44,1,0],[515,11,1,0],[516,46,1,0],[517,47,1,0],[518,22,1,0],[519,28,1,0],[520,11,1,0],[521,13,1,0],[522,40,1,0],[523,4,1,0],[524,27,1,0],[525,12,1,0],[526,37,1,1],[527,31,1,0],[528,43,1,1],[529,20,1,0],[530,13,1,0],[531,17,1,0],[532,19,1,0],[533,21,1,0],[534,26,1,1],[535,10,1,0],[536,48,1,0],[537,29,1,0],[538,31,1,0],[539,46,1,1],[540,3,1,1],[541,36,1,0],[542,7,1,0],[543,16,1,0],[544,32,1,0],[545,12,1,0],[546,2,1,0],[547,13,1,0],[548,29,1,0],[549,13,1,0],[550,40,1,0],[551,19,1,0],[552,41,1,0],[553,2,1,0],[554,9,1,0],[555,2,1,0],[556,39,1,0],[557,31,1,1],[558,40,1,0],[559,11,1,1],[560,45,1,0],[561,9,1,0],[562,21,1,0],[563,47,1,1],[564,29,1,0],[565,21,1,0],[566,33,1,0],[567,44,1,0],[568,44,1,0],[569,39,1,0],[570,29,1,0],[571,1,1,0],[572,22,1,0],[573,8,1,0],[574,5,1,0],[575,12,1,0],[576,31,1,0],[577,42,1,0],[578,34,1,1],[579,16,1,0],[580,1,1,1],[581,5,1,1],[582,11,1,1],[583,7,1,0],[584,43,1,0],[585,42,1,0],[586,46,1,1],[587,46,1,0],[588,40,1,0],[589,26,1,0],[590,43,1,1],[591,46,1,0],[592,18,1,0],[593,39,1,0],[594,41,1,1],[595,46,1,1],[596,45,1,0],[597,37,1,1],[598,25,1,0],[599,44,1,0],[600,29,1,0],[601,44,1,0],[602,25,1,0],[603,10,1,1],[604,6,1,0],[605,26,1,1],[606,43,1,1],[607,1,1,0],[608,21,1,0],[609,1,1,1],[610,0,1,1],[611,41,1,0],[612,19,1,0],[613,44,1,0],[614,46,1,1],[615,41,1,0],[616,7,1,0],[617,38,1,0],[618,28,1,1],[619,45,1,0],[620,20,1,0],[621,35,1,0],[622,33,1,0],[623,25,1,0],[624,29,1,0],[625,5,1,0],[626,1,1,1],[627,32,1,0],[628,18,1,1],[629,45,1,0],[630,4,1,0],[631,25,1,0],[632,45,1,0],[633,45,1,0],[634,8,1,0],[635,16,1,0],[636,29,1,0],[637,34,1,0],[638,40,1,0],[639,11,1,0],[640,0,1,0],[641,44,1,0],[642,22,1,0],[643,11,1,0],[644,44,1,0],[645,10,1,0],[646,10,1,1],[647,31,1,0],[884,23,0,0],[649,24,1,0],[650,29,1,1],[651,33,1,1],[652,1,1,0],[653,1,1,1],[654,43,1,1],[655,34,1,0],[656,21,1,1],[657,11,1,0],[658,16,1,0],[659,30,1,0],[942,23,0,0],[661,46,1,0],[662,19,1,0],[663,27,1,1],[664,7,1,0],[665,39,1,0],[666,39,1,0],[667,30,1,0],[668,46,1,1],[669,31,1,1],[670,40,1,0],[671,1,1,1],[672,19,1,0],[673,15,1,1],[674,16,1,0],[675,12,1,1],[676,29,1,0],[677,19,1,0],[678,16,1,0],[679,22,1,0],[680,21,1,1],[681,39,1,0],[682,28,1,0],[683,31,1,0],[684,35,1,0],[685,40,1,0],[686,29,1,1],[687,32,1,1],[688,0,1,1],[689,27,1,0],[690,9,1,0],[691,43,1,1],[692,43,1,1],[693,21,1,0],[694,46,1,1],[695,25,1,0],[696,8,1,0],[697,40,1,0],[698,10,1,0],[699,28,1,0],[700,37,1,1],[701,1,1,1],[702,24,1,0],[703,40,1,0],[704,29,1,0],[705,47,1,1],[706,7,1,1],[707,28,1,0],[708,25,1,0],[709,24,1,0],[710,31,1,0],[711,26,1,0],[712,1,1,0],[713,3,1,1],[714,34,1,0],[715,29,1,1],[716,40,1,0],[717,45,1,0],[718,20,1,0],[719,26,1,0],[720,32,1,0],[721,46,1,1],[722,29,1,1],[723,33,1,1],[948,23,0,0],[725,19,1,0],[726,46,1,0],[727,11,1,1],[728,17,1,0],[729,21,1,0],[730,19,1,0],[731,11,1,0],[732,1,1,0],[733,5,1,0],[734,30,1,0],[735,20,1,0],[736,29,1,1],[737,40,1,0],[738,21,1,0],[739,33,1,0],[740,29,1,0],[741,11,1,1],[742,27,1,0],[743,12,1,0],[744,29,1,1],[745,25,1,0],[746,44,1,0],[747,27,1,1],[748,46,1,1],[749,43,1,1],[750,43,1,1],[751,46,1,0],[752,4,1,0],[753,21,1,0],[754,12,1,0],[755,40,1,0],[756,20,1,0],[757,16,1,0],[758,45,1,0],[759,4,1,0],[760,3,1,0],[1057,23,0,0],[762,25,1,0],[763,14,1,0],[764,6,1,0],[765,11,1,0],[766,22,1,0],[767,38,1,0],[768,44,1,0],[769,2,1,0],[770,22,1,0],[771,8,1,0],[772,44,1,0],[773,38,1,0],[774,7,1,0],[775,28,1,0],[776,37,1,1],[777,14,1,0],[778,10,1,1],[779,46,1,0],[780,29,1,0],[781,3,1,1],[782,11,1,0],[783,43,1,1],[784,11,1,0],[785,38,1,0],[786,43,1,1],[787,40,1,0],[788,34,1,0],[789,7,1,1],[790,11,1,0],[791,46,1,1],[792,43,1,1],[793,24,1,0],[78,23,1,0],[795,36,1,0],[796,24,1,0],[797,42,1,1],[798,12,1,0],[799,40,1,0],[800,3,1,0],[801,4,1,0],[802,18,1,1],[803,3,1,0],[804,21,1,0],[805,8,1,0],[806,31,1,0],[807,17,1,0],[808,36,1,0],[809,42,1,1],[810,35,1,0],[811,44,1,0],[163,23,1,0],[813,28,1,0],[814,29,1,0],[815,45,1,0],[816,4,1,0],[817,43,1,0],[818,32,1,0],[819,31,1,0],[820,8,1,0],[821,24,1,0],[822,29,1,0],[823,15,1,0],[824,46,1,1],[825,40,1,0],[826,11,1,0],[827,44,1,0],[828,46,1,1],[829,26,1,0],[830,24,1,0],[831,1,1,1],[832,46,1,1],[212,23,1,0],[834,43,1,1],[835,10,1,0],[836,2,1,0],[837,3,1,0],[838,43,1,1],[839,39,1,0],[840,43,1,1],[841,22,1,0],[842,11,1,1],[843,28,1,0],[844,37,1,1],[845,13,1,0],[225,23,1,0],[847,47,1,0],[848,31,1,0],[849,26,1,0],[850,44,1,0],[851,5,1,0],[852,31,1,0],[853,44,1,0],[854,32,1,0],[855,33,1,1],[856,12,1,0],[857,44,1,0],[858,8,1,0],[238,23,1,0],[860,43,1,1],[861,46,1,1],[862,40,1,0],[863,0,1,1],[864,11,1,0],[865,44,1,0],[866,40,1,0],[867,29,1,0],[868,38,1,0],[869,40,1,0],[870,35,1,0],[871,46,1,1],[872,34,1,1],[873,43,1,1],[874,30,1,1],[875,11,1,0],[876,44,1,0],[877,31,1,0],[878,41,1,0],[879,40,1,0],[880,47,1,1],[881,44,1,0],[882,12,1,0],[883,24,1,0],[351,23,1,0],[885,35,1,0],[886,31,1,1],[887,30,1,0],[888,1,1,0],[889,39,1,0],[890,18,1,0],[891,43,1,1],[892,46,1,0],[893,11,1,0],[894,46,1,1],[895,21,1,0],[896,11,1,0],[897,9,1,1],[898,22,1,1],[899,34,1,0],[900,0,1,1],[901,43,1,1],[902,0,1,0],[903,22,1,0],[904,31,1,0],[905,31,1,0],[906,2,1,0],[907,19,1,0],[908,46,1,0],[909,41,1,0],[910,8,1,0],[911,42,1,0],[912,13,1,0],[913,0,1,0],[914,2,1,0],[915,41,1,0],[916,42,1,0],[917,12,1,0],[918,44,1,0],[919,22,1,0],[920,47,1,1],[921,22,1,0],[922,42,1,0],[923,42,1,1],[924,43,1,1],[925,27,1,0],[926,46,1,1],[927,25,1,0],[928,44,1,0],[929,40,1,0],[930,24,1,0],[931,13,1,0],[932,37,1,0],[933,47,1,1],[934,46,1,0],[935,19,1,0],[936,31,1,0],[937,11,1,0],[938,3,1,1],[939,29,1,1],[940,0,1,0],[941,29,1,0],[478,23,1,0],[943,15,1,1],[944,33,1,1],[945,34,1,0],[946,39,1,0],[947,36,1,0],[648,23,1,0],[949,5,1,0],[950,33,1,0],[951,29,1,1],[952,19,1,0],[953,9,1,0],[954,40,1,0],[955,44,1,0],[956,6,1,0],[957,35,1,0],[958,43,1,0],[959,29,1,0],[960,43,1,0],[961,29,1,1],[962,46,1,1],[963,44,1,0],[964,10,1,0],[965,9,1,1],[966,31,1,0],[967,41,1,1],[968,22,1,0],[969,12,1,0],[970,24,1,0],[971,44,1,0],[972,29,1,1],[973,43,1,1],[974,6,1,0],[975,19,1,0],[976,14,1,0],[977,35,1,0],[978,12,1,0],[979,27,1,1],[980,13,1,0],[981,25,1,0],[982,34,1,0],[983,36,1,1],[984,34,1,0],[985,41,1,1],[986,9,1,0],[987,37,1,1],[988,9,1,0],[989,47,1,0],[990,13,1,0],[991,38,1,1],[992,43,1,1],[993,29,1,0],[994,11,1,0],[995,15,1,1],[996,44,1,0],[997,21,1,0],[998,38,1,0],[999,21,1,0],[1000,29,1,0],[1001,40,1,0],[1002,0,1,0],[1003,33,1,0],[1004,43,1,1],[1005,21,1,0],[1006,46,1,1],[1007,11,1,0],[1008,38,1,1],[1009,11,1,0],[1010,21,1,0],[1011,25,1,0],[1012,43,1,1],[1013,46,1,0],[1014,9,1,0],[1015,2,1,0],[1016,11,1,1],[1017,31,1,0],[1018,40,1,0],[1019,10,1,0],[1020,43,1,1],[1021,30,1,0],[1022,6,1,0],[1023,33,1,0],[1024,1,1,0],[1025,29,1,0],[1026,26,1,0],[1027,24,1,0],[1028,37,1,1],[1029,44,1,0],[1030,21,1,0],[1031,0,1,1],[1032,25,1,0],[1033,0,1,1],[1034,29,1,0],[1035,8,1,0],[1036,1,1,0],[1037,39,1,0],[1038,19,1,0],[1039,24,1,0],[1040,29,1,0],[1041,31,1,1],[1042,34,1,0],[1043,21,1,0],[1044,21,1,0],[1045,11,1,0],[1046,19,1,0],[1047,45,1,0],[1048,21,1,0],[1049,27,1,0],[1050,40,1,0],[1051,7,1,0],[1052,46,1,1],[1053,2,1,0],[1054,40,1,0],[1055,26,1,0],[1056,46,1,0],[660,23,1,0],[1058,37,1,1],[1059,21,1,0],[1060,41,1,0],[1061,1,1,1],[1062,12,1,1],[1063,34,1,0],[1064,10,1,0],[1065,27,1,0],[1066,28,1,0],[1067,11,1,1],[1068,1,1,1],[1069,45,1,1],[1070,46,1,1],[0,43,2,0],[1,34,2,0],[2,35,2,0],[3,43,2,0],[4,46,2,1],[5,11,2,0],[6,31,2,0],[7,21,2,0],[8,7,2,0],[9,31,2,0],[10,41,2,0],[11,43,2,0],[12,44,2,0],[13,43,2,1],[14,20,2,0],[15,40,2,0],[16,22,2,0],[17,46,2,0],[18,27,2,0],[19,40,2,0],[20,38,2,1],[21,31,2,1],[22,44,2,0],[23,5,2,0],[24,38,2,0],[25,18,2,0],[26,47,2,0],[27,30,2,0],[28,19,2,0],[29,46,2,1],[30,27,2,0],[31,1,2,0],[32,40,2,0],[33,24,2,0],[34,44,2,0],[35,17,2,1],[36,35,2,0],[37,44,2,0],[38,10,2,0],[39,36,2,0],[40,17,2,0],[41,29,2,0],[42,14,2,0],[43,47,2,0],[44,15,2,1],[45,24,2,0],[46,47,2,1],[47,19,2,0],[48,29,2,1],[49,44,2,0],[50,17,2,0],[51,46,2,0],[52,14,2,0],[53,24,2,0],[54,29,2,1],[55,1,2,0],[56,44,2,0],[57,30,2,0],[58,27,2,0],[59,45,2,0],[60,36,2,0],[61,10,2,0],[62,40,2,0],[63,44,2,0],[64,26,2,0],[65,40,2,0],[66,35,2,0],[67,36,2,0],[68,37,2,1],[69,28,2,0],[70,9,2,0],[71,15,2,0],[72,46,2,0],[73,21,2,0],[74,39,2,0],[75,43,2,1],[76,15,2,0],[77,29,2,0],[724,23,1,0],[79,21,2,0],[80,31,2,0],[81,34,2,0],[82,11,2,1],[83,44,2,0],[84,37,2,1],[85,11,2,1],[86,15,2,1],[87,43,2,1],[88,38,2,0],[89,33,2,0],[90,14,2,0],[91,41,2,0],[92,11,2,1],[93,13,2,0],[94,8,2,0],[95,21,2,0],[96,47,2,1],[97,14,2,0],[98,46,2,1],[99,38,2,0],[100,39,2,0],[101,1,2,1],[102,11,2,1],[103,20,2,0],[104,44,2,0],[105,47,2,1],[106,33,2,0],[107,10,2,0],[108,30,2,0],[109,20,2,1],[110,12,2,1],[111,38,2,0],[112,14,2,0],[113,25,2,0],[114,24,2,0],[115,26,2,0],[116,2,2,0],[117,11,2,0],[118,47,2,0],[119,28,2,0],[120,24,2,0],[121,29,2,0],[122,40,2,0],[123,35,2,0],[124,46,2,1],[125,26,2,0],[126,11,2,1],[127,44,2,0],[128,21,2,0],[129,14,2,0],[130,8,2,0],[131,11,2,0],[132,36,2,1],[133,20,2,0],[134,24,2,0],[135,47,2,1],[136,21,2,0],[137,21,2,0],[138,34,2,0],[139,46,2,0],[140,17,2,0],[141,45,2,0],[142,31,2,0],[143,29,2,0],[144,46,2,1],[145,46,2,1],[146,35,2,0],[147,34,2,0],[148,43,2,1],[149,44,2,0],[150,44,2,0],[151,11,2,1],[152,6,2,0],[153,9,2,1],[154,36,2,0],[155,46,2,0],[156,11,2,0],[157,20,2,1],[158,31,2,1],[159,27,2,0],[160,29,2,1],[161,43,2,1],[162,6,2,0],[761,23,1,0],[164,32,2,0],[165,15,2,0],[166,35,2,0],[167,21,2,0],[168,4,2,0],[169,19,2,0],[170,43,2,1],[171,12,2,0],[172,4,2,0],[173,15,2,1],[174,43,2,1],[175,18,2,1],[176,31,2,0],[177,29,2,0],[178,46,2,1],[179,27,2,0],[180,33,2,0],[181,13,2,0],[182,27,2,0],[183,17,2,0],[184,46,2,0],[185,29,2,0],[186,33,2,1],[187,32,2,1],[188,18,2,0],[189,15,2,1],[190,40,2,0],[191,43,2,0],[192,14,2,0],[193,36,2,1],[194,24,2,0],[195,20,2,1],[196,46,2,0],[197,46,2,0],[198,6,2,0],[199,24,2,0],[200,24,2,0],[201,36,2,0],[202,15,2,1],[203,1,2,1],[204,20,2,0],[205,31,2,1],[206,6,2,0],[207,49,2,0],[208,46,2,0],[209,11,2,1],[210,42,2,0],[211,21,2,0],[812,23,1,0],[213,24,2,0],[214,12,2,0],[215,10,2,0],[216,3,2,0],[217,28,2,0],[218,40,2,0],[219,46,2,0],[220,44,2,0],[221,43,2,0],[222,26,2,0],[223,15,2,1],[224,43,2,0],[833,23,1,0],[226,3,2,0],[227,44,2,0],[228,7,2,0],[229,22,2,0],[230,10,2,0],[231,21,2,0],[232,8,2,0],[233,29,2,0],[234,7,2,1],[235,14,2,0],[236,0,2,0],[237,35,2,0],[859,23,1,0],[239,1,2,1],[240,29,2,0],[241,46,2,1],[242,29,2,0],[243,44,2,0],[244,46,2,1],[245,40,2,0],[246,35,2,0],[247,26,2,0],[248,35,2,0],[249,12,2,1],[250,33,2,1],[251,14,2,0],[252,14,2,0],[253,47,2,0],[254,46,2,1],[255,32,2,0],[256,26,2,1],[257,32,2,0],[258,43,2,0],[259,21,2,0],[260,7,2,0],[261,47,2,1],[262,34,2,0],[263,29,2,0],[264,43,2,1],[265,15,2,1],[266,3,2,1],[267,12,2,1],[268,46,2,1],[269,37,2,1],[270,3,2,1],[271,1,2,0],[272,12,2,1],[273,41,2,0],[274,17,2,0],[275,32,2,1],[276,39,2,0],[277,40,2,0],[278,31,2,1],[279,31,2,1],[280,44,2,0],[281,4,2,0],[282,21,2,0],[283,4,2,0],[284,28,2,0],[285,41,2,0],[286,43,2,1],[287,1,2,1],[288,19,2,0],[289,29,2,0],[290,31,2,1],[291,41,2,0],[292,34,2,0],[293,9,2,1],[294,40,2,0],[295,43,2,1],[296,44,2,0],[297,28,2,0],[298,25,2,0],[299,46,2,0],[300,1,2,1],[301,0,2,1],[302,3,2,1],[303,43,2,1],[304,43,2,1],[305,35,2,0],[306,46,2,0],[307,38,2,1],[308,39,2,0],[309,1,2,0],[310,44,2,0],[311,37,2,1],[312,37,2,1],[313,13,2,0],[314,29,2,1],[315,43,2,1],[316,9,2,0],[317,2,2,0],[318,1,2,0],[319,31,2,0],[320,29,2,0],[321,32,2,0],[322,14,2,0],[323,27,2,0],[324,44,2,0],[325,40,2,0],[326,29,2,1],[327,40,2,0],[328,43,2,0],[329,43,2,0],[330,0,2,0],[331,13,2,0],[332,8,2,0],[333,32,2,0],[334,31,2,0],[335,21,2,0],[336,7,2,0],[337,5,2,1],[338,35,2,0],[339,12,2,0],[340,22,2,0],[341,7,2,0],[342,34,2,0],[343,9,2,0],[344,28,2,0],[345,30,2,0],[346,27,2,0],[347,35,2,0],[348,4,2,0],[349,30,2,0],[350,47,2,1],[884,23,1,0],[352,29,2,0],[353,16,2,0],[354,28,2,0],[355,30,2,0],[356,43,2,1],[357,44,2,0],[358,3,2,0],[359,28,2,0],[360,18,2,0],[361,11,2,0],[362,19,2,0],[363,26,2,0],[364,24,2,0],[365,30,2,0],[366,11,2,0],[367,12,2,0],[368,35,2,0],[369,25,2,0],[370,19,2,0],[371,40,2,0],[372,43,2,0],[373,40,2,0],[374,30,2,0],[375,40,2,0],[376,42,2,0],[377,38,2,0],[378,37,2,1],[379,29,2,0],[380,40,2,0],[381,39,2,0],[382,44,2,0],[383,30,2,0],[384,44,2,0],[385,29,2,0],[386,8,2,0],[387,11,2,0],[388,30,2,0],[389,30,2,0],[390,38,2,0],[391,8,2,0],[392,11,2,0],[393,44,2,0],[394,47,2,1],[395,43,2,1],[396,11,2,0],[397,35,2,0],[398,16,2,0],[399,29,2,0],[400,27,2,0],[401,43,2,1],[402,43,2,1],[403,30,2,0],[404,43,2,0],[405,10,2,0],[406,43,2,0],[407,6,2,0],[408,46,2,1],[409,21,2,0],[410,46,2,1],[411,36,2,0],[412,41,2,0],[413,7,2,0],[414,43,2,0],[415,46,2,0],[416,47,2,1],[417,14,2,0],[418,28,2,0],[419,46,2,1],[420,5,2,0],[421,24,2,0],[422,8,2,0],[423,34,2,0],[424,44,2,0],[425,29,2,1],[426,32,2,1],[427,33,2,1],[428,21,2,1],[429,36,2,1],[430,7,2,0],[431,38,2,1],[432,31,2,0],[433,29,2,0],[434,21,2,0],[435,46,2,1],[436,25,2,0],[437,32,2,0],[438,14,2,0],[439,32,2,0],[440,13,2,0],[441,32,2,0],[442,9,2,1],[443,7,2,1],[444,29,2,1],[445,42,2,1],[446,29,2,0],[447,17,2,0],[448,40,2,0],[449,8,2,0],[450,17,2,0],[451,20,2,0],[452,29,2,0],[453,11,2,0],[454,0,2,0],[455,40,2,0],[456,21,2,0],[457,42,2,0],[458,8,2,0],[459,31,2,0],[460,42,2,1],[461,43,2,1],[462,20,2,0],[463,44,2,0],[464,29,2,1],[465,21,2,0],[466,40,2,0],[467,44,2,0],[468,44,2,0],[469,40,2,0],[470,16,2,0],[471,29,2,0],[472,0,2,1],[473,37,2,1],[474,43,2,1],[475,5,2,0],[476,19,2,0],[477,29,2,1],[942,23,1,0],[479,7,2,0],[480,25,2,0],[481,34,2,0],[482,33,2,0],[483,1,2,0],[484,13,2,0],[485,47,2,0],[486,34,2,0],[487,24,2,0],[488,43,2,1],[489,39,2,0],[490,40,2,0],[491,34,2,0],[492,22,2,0],[493,6,2,0],[494,35,2,0],[495,29,2,0],[496,11,2,1],[497,35,2,0],[498,18,2,0],[499,18,2,1],[500,29,2,0],[501,18,2,1],[502,12,2,1],[503,31,2,0],[504,46,2,0],[505,40,2,0],[506,13,2,0],[507,44,2,0],[508,27,2,0],[509,42,2,1],[510,30,2,0],[511,11,2,0],[512,14,2,0],[513,27,2,0],[514,44,2,0],[515,11,2,0],[516,46,2,0],[517,47,2,0],[518,22,2,0],[519,28,2,0],[520,11,2,0],[521,13,2,0],[522,40,2,0],[523,4,2,0],[524,27,2,0],[525,12,2,0],[526,37,2,1],[527,31,2,0],[528,43,2,1],[529,20,2,0],[530,13,2,0],[531,17,2,0],[532,19,2,0],[533,21,2,0],[534,26,2,1],[535,10,2,0],[536,48,2,0],[537,29,2,0],[538,31,2,0],[539,46,2,1],[540,3,2,1],[541,36,2,0],[542,7,2,0],[543,16,2,0],[544,32,2,0],[545,12,2,0],[546,2,2,0],[547,13,2,0],[548,29,2,0],[549,13,2,0],[550,40,2,0],[551,19,2,0],[552,41,2,0],[553,2,2,0],[554,9,2,0],[555,2,2,0],[556,39,2,0],[557,31,2,1],[558,40,2,0],[559,11,2,1],[560,45,2,0],[561,9,2,0],[562,21,2,0],[563,47,2,1],[564,29,2,0],[565,21,2,0],[566,33,2,0],[567,44,2,0],[568,44,2,0],[569,39,2,0],[570,29,2,0],[571,1,2,0],[572,22,2,0],[573,8,2,0],[574,5,2,0],[575,12,2,0],[576,31,2,0],[577,42,2,0],[578,34,2,0],[579,16,2,0],[580,1,2,1],[581,5,2,1],[582,11,2,1],[583,7,2,0],[584,43,2,0],[585,42,2,0],[586,46,2,1],[587,46,2,0],[588,40,2,0],[589,26,2,0],[590,43,2,1],[591,46,2,0],[592,18,2,0],[593,39,2,0],[594,41,2,1],[595,46,2,1],[596,45,2,0],[597,37,2,1],[598,25,2,0],[599,44,2,0],[600,29,2,0],[601,44,2,0],[602,25,2,0],[603,10,2,1],[604,6,2,0],[605,26,2,1],[606,43,2,1],[607,1,2,0],[608,21,2,0],[609,1,2,1],[610,0,2,1],[611,41,2,0],[612,19,2,0],[613,44,2,0],[614,46,2,1],[615,41,2,0],[616,7,2,0],[617,38,2,1],[618,28,2,1],[619,45,2,0],[620,20,2,1],[621,35,2,0],[622,33,2,1],[623,25,2,0],[624,29,2,1],[625,5,2,0],[626,1,2,1],[627,32,2,0],[628,18,2,1],[629,45,2,0],[630,4,2,0],[631,25,2,0],[632,45,2,0],[633,45,2,0],[634,8,2,0],[635,16,2,0],[636,29,2,0],[637,34,2,1],[638,40,2,0],[639,11,2,0],[640,0,2,0],[641,44,2,0],[642,22,2,0],[643,11,2,0],[644,44,2,0],[645,10,2,0],[646,10,2,1],[647,31,2,0],[948,23,1,0],[649,24,2,0],[650,29,2,1],[651,33,2,1],[652,1,2,0],[653,1,2,1],[654,43,2,1],[655,34,2,0],[656,21,2,1],[657,11,2,0],[658,16,2,0],[659,30,2,0],[1057,23,1,0],[661,46,2,0],[662,19,2,0],[663,27,2,1],[664,7,2,0],[665,39,2,0],[666,39,2,0],[667,30,2,0],[668,46,2,1],[669,31,2,1],[670,40,2,0],[671,1,2,1],[672,19,2,0],[673,15,2,1],[674,16,2,0],[675,12,2,1],[676,29,2,0],[677,19,2,0],[678,16,2,0],[679,22,2,0],[680,21,2,1],[681,39,2,0],[682,28,2,0],[683,31,2,0],[684,35,2,0],[685,40,2,0],[686,29,2,1],[687,32,2,1],[688,0,2,1],[689,27,2,0],[690,9,2,0],[691,43,2,1],[692,43,2,1],[693,21,2,0],[694,46,2,1],[695,25,2,0],[696,8,2,0],[697,40,2,0],[698,10,2,0],[699,28,2,0],[700,37,2,1],[701,1,2,1],[702,24,2,0],[703,40,2,0],[704,29,2,0],[705,47,2,1],[706,7,2,0],[707,28,2,0],[708,25,2,0],[709,24,2,0],[710,31,2,0],[711,26,2,0],[712,1,2,0],[713,3,2,1],[714,34,2,0],[715,29,2,1],[716,40,2,0],[717,45,2,0],[718,20,2,0],[719,26,2,0],[720,32,2,0],[721,46,2,1],[722,29,2,1],[723,33,2,1],[78,23,2,0],[725,19,2,0],[726,46,2,0],[727,11,2,1],[728,17,2,0],[729,21,2,0],[730,19,2,0],[731,11,2,0],[732,1,2,0],[733,5,2,1],[734,30,2,0],[735,20,2,0],[736,29,2,1],[737,40,2,0],[738,21,2,0],[739,33,2,0],[740,29,2,0],[741,11,2,1],[742,27,2,0],[743,12,2,0],[744,29,2,1],[745,25,2,0],[746,44,2,0],[747,27,2,1],[748,46,2,1],[749,43,2,1],[750,43,2,1],[751,46,2,0],[752,4,2,0],[753,21,2,0],[754,12,2,0],[755,40,2,0],[756,20,2,0],[757,16,2,0],[758,45,2,0],[759,4,2,0],[760,3,2,0],[163,23,2,0],[762,25,2,0],[763,14,2,0],[764,6,2,0],[765,11,2,0],[766,22,2,0],[767,38,2,0],[768,44,2,0],[769,2,2,0],[770,22,2,0],[771,8,2,0],[772,44,2,0],[773,38,2,0],[774,7,2,0],[775,28,2,0],[776,37,2,1],[777,14,2,0],[778,10,2,1],[779,46,2,0],[780,29,2,0],[781,3,2,1],[782,11,2,0],[783,43,2,1],[784,11,2,0],[785,38,2,0],[786,43,2,1],[787,40,2,0],[788,34,2,0],[789,7,2,1],[790,11,2,0],[791,46,2,1],[792,43,2,1],[793,24,2,0],[212,23,2,0],[795,36,2,0],[796,24,2,0],[797,42,2,1],[798,12,2,0],[799,40,2,0],[800,3,2,0],[801,4,2,0],[802,18,2,1],[803,3,2,1],[804,21,2,0],[805,8,2,0],[806,31,2,0],[807,17,2,0],[808,36,2,0],[809,42,2,1],[810,35,2,0],[811,44,2,0],[225,23,2,0],[813,28,2,1],[814,29,2,0],[815,45,2,0],[816,4,2,0],[817,43,2,0],[818,32,2,0],[819,31,2,0],[820,8,2,0],[821,24,2,0],[822,29,2,0],[823,15,2,0],[824,46,2,0],[825,40,2,0],[826,11,2,0],[827,44,2,0],[828,46,2,1],[829,26,2,0],[830,24,2,0],[831,1,2,1],[832,46,2,1],[238,23,2,0],[834,43,2,1],[835,10,2,0],[836,2,2,0],[837,3,2,0],[838,43,2,1],[839,39,2,0],[840,43,2,0],[841,22,2,0],[842,11,2,1],[843,28,2,0],[844,37,2,1],[845,13,2,0],[351,23,2,0],[847,47,2,0],[848,31,2,0],[849,26,2,0],[850,44,2,0],[851,5,2,0],[852,31,2,0],[853,44,2,0],[854,32,2,0],[855,33,2,1],[856,12,2,1],[857,44,2,0],[858,8,2,0],[478,23,2,0],[860,43,2,1],[861,46,2,1],[862,40,2,0],[863,0,2,1],[864,11,2,0],[865,44,2,0],[866,40,2,0],[867,29,2,0],[868,38,2,0],[869,40,2,0],[870,35,2,0],[871,46,2,1],[872,34,2,1],[873,43,2,1],[874,30,2,1],[875,11,2,0],[876,44,2,0],[877,31,2,1],[878,41,2,0],[879,40,2,0],[880,47,2,1],[881,44,2,0],[882,12,2,0],[883,24,2,0],[648,23,2,0],[885,35,2,0],[886,31,2,1],[887,30,2,0],[888,1,2,0],[889,39,2,0],[890,18,2,0],[891,43,2,1],[892,46,2,0],[893,11,2,0],[894,46,2,1],[895,21,2,0],[896,11,2,0],[897,9,2,1],[898,22,2,0],[899,34,2,0],[900,0,2,1],[901,43,2,1],[902,0,2,0],[903,22,2,0],[904,31,2,0],[905,31,2,0],[906,2,2,0],[907,19,2,0],[908,46,2,0],[909,41,2,0],[910,8,2,0],[911,42,2,0],[912,13,2,0],[913,0,2,0],[914,2,2,0],[915,41,2,0],[916,42,2,0],[917,12,2,0],[918,44,2,0],[919,22,2,0],[920,47,2,0],[921,22,2,0],[922,42,2,0],[923,42,2,1],[924,43,2,1],[925,27,2,0],[926,46,2,0],[927,25,2,0],[928,44,2,0],[929,40,2,0],[930,24,2,0],[931,13,2,0],[932,37,2,0],[933,47,2,1],[934,46,2,0],[935,19,2,0],[936,31,2,0],[937,11,2,0],[938,3,2,1],[939,29,2,1],[940,0,2,0],[941,29,2,1],[660,23,2,0],[943,15,2,1],[944,33,2,1],[945,34,2,0],[946,39,2,0],[947,36,2,0],[724,23,2,0],[949,5,2,0],[950,33,2,0],[951,29,2,1],[952,19,2,0],[953,9,2,0],[954,40,2,0],[955,44,2,0],[956,6,2,0],[957,35,2,0],[958,43,2,0],[959,29,2,0],[960,43,2,0],[961,29,2,1],[962,46,2,1],[963,44,2,0],[964,10,2,0],[965,9,2,1],[966,31,2,0],[967,41,2,1],[968,22,2,0],[969,12,2,0],[970,24,2,0],[971,44,2,0],[972,29,2,1],[973,43,2,1],[974,6,2,0],[975,19,2,0],[976,14,2,0],[977,35,2,0],[978,12,2,0],[979,27,2,1],[980,13,2,0],[981,25,2,0],[982,34,2,0],[983,36,2,1],[984,34,2,0],[985,41,2,1],[986,9,2,0],[987,37,2,1],[988,9,2,0],[989,47,2,0],[990,13,2,0],[991,38,2,1],[992,43,2,1],[993,29,2,0],[994,11,2,0],[995,15,2,1],[996,44,2,0],[997,21,2,0],[998,38,2,0],[999,21,2,0],[1000,29,2,0],[1001,40,2,0],[1002,0,2,0],[1003,33,2,0],[1004,43,2,1],[1005,21,2,0],[1006,46,2,1],[1007,11,2,0],[1008,38,2,1],[1009,11,2,0],[1010,21,2,0],[1011,25,2,0],[1012,43,2,1],[1013,46,2,0],[1014,9,2,0],[1015,2,2,0],[1016,11,2,1],[1017,31,2,0],[1018,40,2,0],[1019,10,2,0],[1020,43,2,1],[1021,30,2,0],[1022,6,2,0],[1023,33,2,0],[1024,1,2,0],[1025,29,2,0],[1026,26,2,0],[1027,24,2,0],[1028,37,2,1],[1029,44,2,0],[1030,21,2,0],[1031,0,2,1],[1032,25,2,0],[1033,0,2,1],[1034,29,2,0],[1035,8,2,0],[1036,1,2,0],[1037,39,2,0],[1038,19,2,0],[1039,24,2,0],[1040,29,2,0],[1041,31,2,1],[1042,34,2,0],[1043,21,2,0],[1044,21,2,0],[1045,11,2,0],[1046,19,2,0],[1047,45,2,0],[1048,21,2,0],[1049,27,2,0],[1050,40,2,0],[1051,7,2,0],[1052,46,2,1],[1053,2,2,0],[1054,40,2,0],[1055,26,2,0],[1056,46,2,0],[761,23,2,0],[1058,37,2,1],[1059,21,2,0],[1060,41,2,0],[1061,1,2,1],[1062,12,2,1],[1063,34,2,0],[1064,10,2,0],[1065,27,2,0],[1066,28,2,0],[1067,11,2,1],[1068,1,2,1],[1069,45,2,1],[1070,46,2,1],[0,43,3,0],[1,34,3,0],[2,35,3,0],[3,43,3,0],[4,46,3,1],[5,11,3,0],[6,31,3,0],[7,21,3,0],[8,7,3,0],[9,31,3,0],[10,41,3,0],[11,43,3,0],[12,44,3,0],[13,43,3,1],[14,20,3,0],[15,40,3,0],[16,22,3,0],[17,46,3,0],[18,27,3,0],[19,40,3,0],[20,38,3,0],[21,31,3,1],[22,44,3,0],[23,5,3,0],[24,38,3,0],[25,18,3,0],[26,47,3,0],[27,30,3,0],[28,19,3,0],[29,46,3,1],[30,27,3,0],[31,1,3,0],[32,40,3,0],[33,24,3,0],[34,44,3,0],[35,17,3,1],[36,35,3,0],[37,44,3,0],[38,10,3,0],[39,36,3,0],[40,17,3,0],[41,29,3,0],[42,14,3,0],[43,47,3,0],[44,15,3,1],[45,24,3,0],[46,47,3,1],[47,19,3,0],[48,29,3,1],[49,44,3,0],[50,17,3,0],[51,46,3,0],[52,14,3,0],[53,24,3,0],[54,29,3,1],[55,1,3,0],[56,44,3,0],[57,30,3,0],[58,27,3,0],[59,45,3,0],[60,36,3,0],[61,10,3,0],[62,40,3,0],[63,44,3,0],[64,26,3,0],[65,40,3,0],[66,35,3,0],[67,36,3,0],[68,37,3,1],[69,28,3,0],[70,9,3,0],[71,15,3,0],[72,46,3,0],[73,21,3,0],[74,39,3,0],[75,43,3,1],[76,15,3,0],[77,29,3,0],[812,23,2,0],[79,21,3,0],[80,31,3,0],[81,34,3,0],[82,11,3,1],[83,44,3,0],[84,37,3,1],[85,11,3,1],[86,15,3,1],[87,43,3,1],[88,38,3,0],[89,33,3,0],[90,14,3,0],[91,41,3,0],[92,11,3,1],[93,13,3,0],[94,8,3,0],[95,21,3,0],[96,47,3,1],[97,14,3,0],[98,46,3,1],[99,38,3,0],[100,39,3,0],[101,1,3,1],[102,11,3,1],[103,20,3,0],[104,44,3,0],[105,47,3,1],[106,33,3,0],[107,10,3,0],[108,30,3,0],[109,20,3,1],[110,12,3,1],[111,38,3,0],[112,14,3,0],[113,25,3,0],[114,24,3,0],[115,26,3,0],[116,2,3,0],[117,11,3,0],[118,47,3,0],[119,28,3,0],[120,24,3,0],[121,29,3,0],[122,40,3,0],[123,35,3,0],[124,46,3,1],[125,26,3,0],[126,11,3,1],[127,44,3,0],[128,21,3,0],[129,14,3,0],[130,8,3,0],[131,11,3,0],[132,36,3,1],[133,20,3,0],[134,24,3,0],[135,47,3,1],[136,21,3,0],[137,21,3,0],[138,34,3,0],[139,46,3,0],[140,17,3,0],[141,45,3,0],[142,31,3,0],[143,29,3,0],[144,46,3,1],[145,46,3,0],[146,35,3,0],[147,34,3,0],[148,43,3,1],[149,44,3,0],[150,44,3,0],[151,11,3,1],[152,6,3,0],[153,9,3,0],[154,36,3,0],[155,46,3,0],[156,11,3,0],[157,20,3,0],[158,31,3,1],[159,27,3,0],[160,29,3,1],[161,43,3,1],[162,6,3,0],[833,23,2,0],[164,32,3,0],[165,15,3,0],[166,35,3,0],[167,21,3,0],[168,4,3,0],[169,19,3,0],[170,43,3,1],[171,12,3,0],[172,4,3,0],[173,15,3,1],[174,43,3,1],[175,18,3,0],[176,31,3,0],[177,29,3,0],[178,46,3,1],[179,27,3,0],[180,33,3,0],[181,13,3,0],[182,27,3,0],[183,17,3,0],[184,46,3,0],[185,29,3,0],[186,33,3,1],[187,32,3,1],[188,18,3,0],[189,15,3,1],[190,40,3,0],[191,43,3,0],[192,14,3,0],[193,36,3,1],[194,24,3,0],[195,20,3,0],[196,46,3,0],[197,46,3,0],[198,6,3,0],[199,24,3,0],[200,24,3,0],[201,36,3,0],[202,15,3,1],[203,1,3,1],[204,20,3,0],[205,31,3,1],[206,6,3,0],[207,49,3,0],[208,46,3,0],[209,11,3,1],[210,42,3,0],[211,21,3,0],[859,23,2,0],[213,24,3,0],[214,12,3,0],[215,10,3,0],[216,3,3,0],[217,28,3,0],[218,40,3,0],[219,46,3,0],[220,44,3,0],[221,43,3,0],[222,26,3,0],[223,15,3,0],[224,43,3,0],[884,23,2,0],[226,3,3,0],[227,44,3,0],[228,7,3,0],[229,22,3,0],[230,10,3,0],[231,21,3,0],[232,8,3,0],[233,29,3,0],[234,7,3,1],[235,14,3,0],[236,0,3,0],[237,35,3,0],[942,23,2,0],[239,1,3,1],[240,29,3,0],[241,46,3,1],[242,29,3,0],[243,44,3,0],[244,46,3,1],[245,40,3,0],[246,35,3,0],[247,26,3,0],[248,35,3,0],[249,12,3,1],[250,33,3,1],[251,14,3,0],[252,14,3,0],[253,47,3,0],[254,46,3,1],[255,32,3,0],[256,26,3,1],[257,32,3,0],[258,43,3,0],[259,21,3,0],[260,7,3,0],[261,47,3,1],[262,34,3,0],[263,29,3,0],[264,43,3,1],[265,15,3,1],[266,3,3,1],[267,12,3,1],[268,46,3,1],[269,37,3,1],[270,3,3,1],[271,1,3,0],[272,12,3,1],[273,41,3,0],[274,17,3,0],[275,32,3,0],[276,39,3,0],[277,40,3,0],[278,31,3,0],[279,31,3,1],[280,44,3,0],[281,4,3,0],[282,21,3,0],[283,4,3,0],[284,28,3,0],[285,41,3,0],[286,43,3,1],[287,1,3,1],[288,19,3,0],[289,29,3,0],[290,31,3,1],[291,41,3,0],[292,34,3,0],[293,9,3,1],[294,40,3,0],[295,43,3,1],[296,44,3,0],[297,28,3,0],[298,25,3,0],[299,46,3,0],[300,1,3,0],[301,0,3,0],[302,3,3,1],[303,43,3,1],[304,43,3,1],[305,35,3,0],[306,46,3,0],[307,38,3,1],[308,39,3,0],[309,1,3,0],[310,44,3,0],[311,37,3,1],[312,37,3,1],[313,13,3,0],[314,29,3,1],[315,43,3,1],[316,9,3,0],[317,2,3,0],[318,1,3,0],[319,31,3,0],[320,29,3,0],[321,32,3,0],[322,14,3,0],[323,27,3,0],[324,44,3,0],[325,40,3,0],[326,29,3,1],[327,40,3,0],[328,43,3,0],[329,43,3,0],[330,0,3,0],[331,13,3,0],[332,8,3,0],[333,32,3,0],[334,31,3,0],[335,21,3,0],[336,7,3,0],[337,5,3,1],[338,35,3,0],[339,12,3,0],[340,22,3,0],[341,7,3,0],[342,34,3,0],[343,9,3,0],[344,28,3,0],[345,30,3,0],[346,27,3,0],[347,35,3,0],[348,4,3,0],[349,30,3,0],[350,47,3,1],[948,23,2,0],[352,29,3,0],[353,16,3,0],[354,28,3,0],[355,30,3,0],[356,43,3,1],[357,44,3,0],[358,3,3,0],[359,28,3,0],[360,18,3,0],[361,11,3,0],[362,19,3,0],[363,26,3,0],[364,24,3,0],[365,30,3,0],[366,11,3,0],[367,12,3,0],[368,35,3,0],[369,25,3,0],[370,19,3,0],[371,40,3,0],[372,43,3,0],[373,40,3,0],[374,30,3,0],[375,40,3,0],[376,42,3,0],[377,38,3,0],[378,37,3,1],[379,29,3,0],[380,40,3,0],[381,39,3,0],[382,44,3,0],[383,30,3,0],[384,44,3,0],[385,29,3,0],[386,8,3,0],[387,11,3,0],[388,30,3,0],[389,30,3,0],[390,38,3,0],[391,8,3,0],[392,11,3,0],[393,44,3,0],[394,47,3,1],[395,43,3,1],[396,11,3,0],[397,35,3,0],[398,16,3,0],[399,29,3,0],[400,27,3,0],[401,43,3,1],[402,43,3,1],[403,30,3,0],[404,43,3,0],[405,10,3,0],[406,43,3,0],[407,6,3,0],[408,46,3,1],[409,21,3,0],[410,46,3,1],[411,36,3,0],[412,41,3,0],[413,7,3,0],[414,43,3,0],[415,46,3,0],[416,47,3,1],[417,14,3,0],[418,28,3,0],[419,46,3,1],[420,5,3,0],[421,24,3,0],[422,8,3,0],[423,34,3,0],[424,44,3,0],[425,29,3,1],[426,32,3,1],[427,33,3,1],[428,21,3,1],[429,36,3,1],[430,7,3,0],[431,38,3,1],[432,31,3,0],[433,29,3,0],[434,21,3,0],[435,46,3,1],[436,25,3,0],[437,32,3,0],[438,14,3,0],[439,32,3,0],[440,13,3,0],[441,32,3,0],[442,9,3,1],[443,7,3,1],[444,29,3,1],[445,42,3,1],[446,29,3,0],[447,17,3,0],[448,40,3,0],[449,8,3,0],[450,17,3,0],[451,20,3,0],[452,29,3,0],[453,11,3,0],[454,0,3,0],[455,40,3,0],[456,21,3,0],[457,42,3,0],[458,8,3,0],[459,31,3,0],[460,42,3,1],[461,43,3,1],[462,20,3,0],[463,44,3,0],[464,29,3,1],[465,21,3,0],[466,40,3,0],[467,44,3,0],[468,44,3,0],[469,40,3,0],[470,16,3,0],[471,29,3,0],[472,0,3,1],[473,37,3,1],[474,43,3,1],[475,5,3,0],[476,19,3,0],[477,29,3,1],[1057,23,2,0],[479,7,3,0],[480,25,3,0],[481,34,3,0],[482,33,3,0],[483,1,3,0],[484,13,3,0],[485,47,3,0],[486,34,3,0],[487,24,3,0],[488,43,3,1],[489,39,3,0],[490,40,3,0],[491,34,3,0],[492,22,3,0],[493,6,3,0],[494,35,3,0],[495,29,3,0],[496,11,3,1],[497,35,3,0],[498,18,3,0],[499,18,3,0],[500,29,3,0],[501,18,3,1],[502,12,3,1],[503,31,3,0],[504,46,3,0],[505,40,3,0],[506,13,3,0],[507,44,3,0],[508,27,3,0],[509,42,3,1],[510,30,3,0],[511,11,3,0],[512,14,3,0],[513,27,3,0],[514,44,3,0],[515,11,3,0],[516,46,3,0],[517,47,3,0],[518,22,3,0],[519,28,3,0],[520,11,3,0],[521,13,3,0],[522,40,3,0],[523,4,3,0],[524,27,3,0],[525,12,3,0],[526,37,3,1],[527,31,3,0],[528,43,3,1],[529,20,3,0],[530,13,3,0],[531,17,3,0],[532,19,3,0],[533,21,3,0],[534,26,3,1],[535,10,3,0],[536,48,3,0],[537,29,3,0],[538,31,3,0],[539,46,3,1],[540,3,3,1],[541,36,3,0],[542,7,3,0],[543,16,3,0],[544,32,3,0],[545,12,3,0],[546,2,3,0],[547,13,3,0],[548,29,3,0],[549,13,3,0],[550,40,3,0],[551,19,3,0],[552,41,3,0],[553,2,3,0],[554,9,3,0],[555,2,3,0],[556,39,3,0],[557,31,3,1],[558,40,3,0],[559,11,3,1],[560,45,3,0],[561,9,3,0],[562,21,3,0],[563,47,3,1],[564,29,3,0],[565,21,3,0],[566,33,3,0],[567,44,3,0],[568,44,3,0],[569,39,3,0],[570,29,3,0],[571,1,3,0],[572,22,3,0],[573,8,3,0],[574,5,3,0],[575,12,3,0],[576,31,3,0],[577,42,3,0],[578,34,3,0],[579,16,3,0],[580,1,3,0],[581,5,3,0],[582,11,3,1],[583,7,3,0],[584,43,3,0],[585,42,3,0],[586,46,3,1],[587,46,3,0],[588,40,3,0],[589,26,3,0],[590,43,3,1],[591,46,3,0],[592,18,3,0],[593,39,3,0],[594,41,3,1],[595,46,3,1],[596,45,3,0],[597,37,3,0],[598,25,3,0],[599,44,3,0],[600,29,3,0],[601,44,3,0],[602,25,3,0],[603,10,3,1],[604,6,3,0],[605,26,3,1],[606,43,3,1],[607,1,3,0],[608,21,3,0],[609,1,3,1],[610,0,3,1],[611,41,3,0],[612,19,3,0],[613,44,3,0],[614,46,3,1],[615,41,3,0],[616,7,3,0],[617,38,3,0],[618,28,3,1],[619,45,3,0],[620,20,3,1],[621,35,3,0],[622,33,3,0],[623,25,3,0],[624,29,3,0],[625,5,3,0],[626,1,3,1],[627,32,3,0],[628,18,3,1],[629,45,3,0],[630,4,3,0],[631,25,3,0],[632,45,3,0],[633,45,3,0],[634,8,3,0],[635,16,3,0],[636,29,3,0],[637,34,3,0],[638,40,3,0],[639,11,3,0],[640,0,3,0],[641,44,3,0],[642,22,3,0],[643,11,3,0],[644,44,3,0],[645,10,3,0],[646,10,3,1],[647,31,3,0],[78,23,3,0],[649,24,3,0],[650,29,3,1],[651,33,3,1],[652,1,3,0],[653,1,3,1],[654,43,3,1],[655,34,3,0],[656,21,3,1],[657,11,3,0],[658,16,3,0],[659,30,3,0],[163,23,3,0],[661,46,3,0],[662,19,3,0],[663,27,3,1],[664,7,3,0],[665,39,3,0],[666,39,3,0],[667,30,3,0],[668,46,3,0],[669,31,3,1],[670,40,3,0],[671,1,3,1],[672,19,3,0],[673,15,3,0],[674,16,3,0],[675,12,3,1],[676,29,3,0],[677,19,3,0],[678,16,3,0],[679,22,3,0],[680,21,3,1],[681,39,3,0],[682,28,3,0],[683,31,3,0],[684,35,3,0],[685,40,3,0],[686,29,3,1],[687,32,3,1],[688,0,3,1],[689,27,3,0],[690,9,3,0],[691,43,3,1],[692,43,3,1],[693,21,3,0],[694,46,3,1],[695,25,3,0],[696,8,3,0],[697,40,3,0],[698,10,3,0],[699,28,3,0],[700,37,3,1],[701,1,3,0],[702,24,3,0],[703,40,3,0],[704,29,3,0],[705,47,3,1],[706,7,3,0],[707,28,3,0],[708,25,3,0],[709,24,3,0],[710,31,3,0],[711,26,3,0],[712,1,3,0],[713,3,3,1],[714,34,3,0],[715,29,3,1],[716,40,3,0],[717,45,3,0],[718,20,3,0],[719,26,3,0],[720,32,3,0],[721,46,3,1],[722,29,3,1],[723,33,3,1],[212,23,3,0],[725,19,3,0],[726,46,3,0],[727,11,3,1],[728,17,3,0],[729,21,3,0],[730,19,3,0],[731,11,3,0],[732,1,3,0],[733,5,3,0],[734,30,3,0],[735,20,3,0],[736,29,3,1],[737,40,3,0],[738,21,3,0],[739,33,3,0],[740,29,3,0],[741,11,3,1],[742,27,3,0],[743,12,3,0],[744,29,3,1],[745,25,3,0],[746,44,3,0],[747,27,3,1],[748,46,3,1],[749,43,3,1],[750,43,3,1],[751,46,3,0],[752,4,3,0],[753,21,3,0],[754,12,3,0],[755,40,3,0],[756,20,3,0],[757,16,3,0],[758,45,3,0],[759,4,3,0],[760,3,3,0],[225,23,3,0],[762,25,3,0],[763,14,3,0],[764,6,3,0],[765,11,3,0],[766,22,3,0],[767,38,3,0],[768,44,3,0],[769,2,3,0],[770,22,3,0],[771,8,3,0],[772,44,3,0],[773,38,3,0],[774,7,3,0],[775,28,3,0],[776,37,3,1],[777,14,3,0],[778,10,3,1],[779,46,3,0],[780,29,3,0],[781,3,3,1],[782,11,3,0],[783,43,3,1],[784,11,3,0],[785,38,3,0],[786,43,3,1],[787,40,3,0],[788,34,3,0],[789,7,3,1],[790,11,3,0],[791,46,3,1],[792,43,3,1],[793,24,3,0],[238,23,3,0],[795,36,3,0],[796,24,3,0],[797,42,3,1],[798,12,3,0],[799,40,3,0],[800,3,3,0],[801,4,3,0],[802,18,3,1],[803,3,3,1],[804,21,3,0],[805,8,3,0],[806,31,3,0],[807,17,3,0],[808,36,3,0],[809,42,3,1],[810,35,3,0],[811,44,3,0],[351,23,3,0],[813,28,3,0],[814,29,3,0],[815,45,3,0],[816,4,3,0],[817,43,3,0],[818,32,3,0],[819,31,3,0],[820,8,3,0],[821,24,3,0],[822,29,3,0],[823,15,3,0],[824,46,3,0],[825,40,3,0],[826,11,3,0],[827,44,3,0],[828,46,3,1],[829,26,3,0],[830,24,3,0],[831,1,3,1],[832,46,3,1],[478,23,3,0],[834,43,3,1],[835,10,3,0],[836,2,3,0],[837,3,3,0],[838,43,3,1],[839,39,3,0],[840,43,3,0],[841,22,3,0],[842,11,3,1],[843,28,3,0],[844,37,3,1],[845,13,3,0],[648,23,3,0],[847,47,3,0],[848,31,3,0],[849,26,3,0],[850,44,3,0],[851,5,3,0],[852,31,3,0],[853,44,3,0],[854,32,3,0],[855,33,3,0],[856,12,3,0],[857,44,3,0],[858,8,3,0],[660,23,3,0],[860,43,3,1],[861,46,3,1],[862,40,3,0],[863,0,3,1],[864,11,3,0],[865,44,3,0],[866,40,3,0],[867,29,3,0],[868,38,3,0],[869,40,3,0],[870,35,3,0],[871,46,3,1],[872,34,3,0],[873,43,3,1],[874,30,3,1],[875,11,3,0],[876,44,3,0],[877,31,3,0],[878,41,3,0],[879,40,3,0],[880,47,3,1],[881,44,3,0],[882,12,3,0],[883,24,3,0],[724,23,3,0],[885,35,3,0],[886,31,3,1],[887,30,3,0],[888,1,3,0],[889,39,3,0],[890,18,3,0],[891,43,3,1],[892,46,3,0],[893,11,3,0],[894,46,3,1],[895,21,3,0],[896,11,3,0],[897,9,3,1],[898,22,3,0],[899,34,3,0],[900,0,3,1],[901,43,3,1],[902,0,3,0],[903,22,3,0],[904,31,3,0],[905,31,3,0],[906,2,3,0],[907,19,3,0],[908,46,3,0],[909,41,3,0],[910,8,3,0],[911,42,3,0],[912,13,3,0],[913,0,3,0],[914,2,3,0],[915,41,3,0],[916,42,3,0],[917,12,3,0],[918,44,3,0],[919,22,3,0],[920,47,3,0],[921,22,3,0],[922,42,3,0],[923,42,3,1],[924,43,3,1],[925,27,3,0],[926,46,3,0],[927,25,3,0],[928,44,3,0],[929,40,3,0],[930,24,3,0],[931,13,3,0],[932,37,3,0],[933,47,3,1],[934,46,3,0],[935,19,3,0],[936,31,3,0],[937,11,3,0],[938,3,3,1],[939,29,3,1],[940,0,3,0],[941,29,3,0],[761,23,3,0],[943,15,3,1],[944,33,3,0],[945,34,3,0],[946,39,3,0],[947,36,3,0],[812,23,3,0],[949,5,3,0],[950,33,3,0],[951,29,3,1],[952,19,3,0],[953,9,3,0],[954,40,3,0],[955,44,3,0],[956,6,3,0],[957,35,3,0],[958,43,3,0],[959,29,3,0],[960,43,3,0],[961,29,3,1],[962,46,3,1],[963,44,3,0],[964,10,3,0],[965,9,3,1],[966,31,3,0],[967,41,3,1],[968,22,3,0],[969,12,3,0],[970,24,3,0],[971,44,3,0],[972,29,3,1],[973,43,3,0],[974,6,3,0],[975,19,3,0],[976,14,3,0],[977,35,3,0],[978,12,3,0],[979,27,3,1],[980,13,3,0],[981,25,3,0],[982,34,3,0],[983,36,3,1],[984,34,3,0],[985,41,3,1],[986,9,3,0],[987,37,3,1],[988,9,3,0],[989,47,3,0],[990,13,3,0],[991,38,3,0],[992,43,3,1],[993,29,3,0],[994,11,3,0],[995,15,3,1],[996,44,3,0],[997,21,3,0],[998,38,3,0],[999,21,3,0],[1000,29,3,0],[1001,40,3,0],[1002,0,3,0],[1003,33,3,0],[1004,43,3,1],[1005,21,3,0],[1006,46,3,1],[1007,11,3,0],[1008,38,3,1],[1009,11,3,0],[1010,21,3,0],[1011,25,3,0],[1012,43,3,1],[1013,46,3,0],[1014,9,3,0],[1015,2,3,0],[1016,11,3,1],[1017,31,3,0],[1018,40,3,0],[1019,10,3,0],[1020,43,3,1],[1021,30,3,0],[1022,6,3,0],[1023,33,3,0],[1024,1,3,0],[1025,29,3,0],[1026,26,3,0],[1027,24,3,0],[1028,37,3,1],[1029,44,3,0],[1030,21,3,0],[1031,0,3,1],[1032,25,3,0],[1033,0,3,1],[1034,29,3,0],[1035,8,3,0],[1036,1,3,0],[1037,39,3,0],[1038,19,3,0],[1039,24,3,0],[1040,29,3,0],[1041,31,3,1],[1042,34,3,0],[1043,21,3,0],[1044,21,3,0],[1045,11,3,0],[1046,19,3,0],[1047,45,3,0],[1048,21,3,0],[1049,27,3,0],[1050,40,3,0],[1051,7,3,0],[1052,46,3,1],[1053,2,3,0],[1054,40,3,0],[1055,26,3,0],[1056,46,3,0],[833,23,3,0],[1058,37,3,1],[1059,21,3,0],[1060,41,3,0],[1061,1,3,1],[1062,12,3,1],[1063,34,3,0],[1064,10,3,0],[1065,27,3,0],[1066,28,3,0],[1067,11,3,1],[1068,1,3,1],[1069,45,3,1],[1070,46,3,1],[0,43,4,0],[1,34,4,0],[2,35,4,0],[3,43,4,0],[4,46,4,1],[5,11,4,0],[6,31,4,0],[7,21,4,0],[8,7,4,0],[9,31,4,0],[10,41,4,0],[11,43,4,0],[12,44,4,0],[13,43,4,1],[14,20,4,0],[15,40,4,0],[16,22,4,0],[17,46,4,0],[18,27,4,0],[19,40,4,0],[20,38,4,0],[21,31,4,0],[22,44,4,0],[23,5,4,0],[24,38,4,0],[25,18,4,0],[26,47,4,0],[27,30,4,0],[28,19,4,0],[29,46,4,1],[30,27,4,0],[31,1,4,0],[32,40,4,0],[33,24,4,0],[34,44,4,0],[35,17,4,1],[36,35,4,0],[37,44,4,0],[38,10,4,0],[39,36,4,0],[40,17,4,0],[41,29,4,0],[42,14,4,0],[43,47,4,0],[44,15,4,1],[45,24,4,0],[46,47,4,1],[47,19,4,0],[48,29,4,1],[49,44,4,0],[50,17,4,0],[51,46,4,0],[52,14,4,0],[53,24,4,0],[54,29,4,1],[55,1,4,0],[56,44,4,0],[57,30,4,0],[58,27,4,0],[59,45,4,0],[60,36,4,0],[61,10,4,0],[62,40,4,0],[63,44,4,0],[64,26,4,0],[65,40,4,0],[66,35,4,0],[67,36,4,0],[68,37,4,1],[69,28,4,0],[70,9,4,0],[71,15,4,0],[72,46,4,0],[73,21,4,0],[74,39,4,0],[75,43,4,1],[76,15,4,0],[77,29,4,0],[859,23,3,0],[79,21,4,0],[80,31,4,0],[81,34,4,0],[82,11,4,0],[83,44,4,0],[84,37,4,1],[85,11,4,1],[86,15,4,1],[87,43,4,1],[88,38,4,0],[89,33,4,0],[90,14,4,0],[91,41,4,0],[92,11,4,1],[93,13,4,0],[94,8,4,0],[95,21,4,0],[96,47,4,1],[97,14,4,0],[98,46,4,1],[99,38,4,0],[100,39,4,0],[101,1,4,1],[102,11,4,1],[103,20,4,0],[104,44,4,0],[105,47,4,1],[106,33,4,0],[107,10,4,0],[108,30,4,0],[109,20,4,1],[110,12,4,1],[111,38,4,0],[112,14,4,0],[113,25,4,0],[114,24,4,0],[115,26,4,0],[116,2,4,0],[117,11,4,0],[118,47,4,0],[119,28,4,0],[120,24,4,0],[121,29,4,0],[122,40,4,0],[123,35,4,0],[124,46,4,1],[125,26,4,0],[126,11,4,1],[127,44,4,0],[128,21,4,0],[129,14,4,0],[130,8,4,0],[131,11,4,0],[132,36,4,1],[133,20,4,0],[134,24,4,0],[135,47,4,1],[136,21,4,0],[137,21,4,0],[138,34,4,0],[139,46,4,0],[140,17,4,0],[141,45,4,0],[142,31,4,0],[143,29,4,0],[144,46,4,1],[145,46,4,0],[146,35,4,0],[147,34,4,0],[148,43,4,1],[149,44,4,0],[150,44,4,0],[151,11,4,1],[152,6,4,0],[153,9,4,0],[154,36,4,0],[155,46,4,0],[156,11,4,0],[157,20,4,0],[158,31,4,1],[159,27,4,0],[160,29,4,1],[161,43,4,1],[162,6,4,0],[884,23,3,0],[164,32,4,0],[165,15,4,0],[166,35,4,0],[167,21,4,0],[168,4,4,0],[169,19,4,0],[170,43,4,1],[171,12,4,0],[172,4,4,0],[173,15,4,1],[174,43,4,1],[175,18,4,0],[176,31,4,0],[177,29,4,0],[178,46,4,1],[179,27,4,0],[180,33,4,0],[181,13,4,0],[182,27,4,0],[183,17,4,0],[184,46,4,0],[185,29,4,0],[186,33,4,1],[187,32,4,1],[188,18,4,0],[189,15,4,1],[190,40,4,0],[191,43,4,0],[192,14,4,0],[193,36,4,1],[194,24,4,0],[195,20,4,0],[196,46,4,0],[197,46,4,0],[198,6,4,0],[199,24,4,0],[200,24,4,0],[201,36,4,0],[202,15,4,1],[203,1,4,1],[204,20,4,0],[205,31,4,1],[206,6,4,0],[207,49,4,0],[208,46,4,0],[209,11,4,1],[210,42,4,0],[211,21,4,0],[942,23,3,0],[213,24,4,0],[214,12,4,0],[215,10,4,0],[216,3,4,0],[217,28,4,0],[218,40,4,0],[219,46,4,0],[220,44,4,0],[221,43,4,0],[222,26,4,0],[223,15,4,0],[224,43,4,0],[948,23,3,0],[226,3,4,0],[227,44,4,0],[228,7,4,0],[229,22,4,0],[230,10,4,0],[231,21,4,0],[232,8,4,0],[233,29,4,0],[234,7,4,1],[235,14,4,0],[236,0,4,0],[237,35,4,0],[1057,23,3,0],[239,1,4,1],[240,29,4,0],[241,46,4,1],[242,29,4,0],[243,44,4,0],[244,46,4,1],[245,40,4,0],[246,35,4,0],[247,26,4,0],[248,35,4,0],[249,12,4,1],[250,33,4,1],[251,14,4,0],[252,14,4,0],[253,47,4,0],[254,46,4,1],[255,32,4,0],[256,26,4,1],[257,32,4,0],[258,43,4,0],[259,21,4,0],[260,7,4,0],[261,47,4,1],[262,34,4,0],[263,29,4,0],[264,43,4,1],[265,15,4,1],[266,3,4,1],[267,12,4,1],[268,46,4,1],[269,37,4,1],[270,3,4,1],[271,1,4,0],[272,12,4,1],[273,41,4,0],[274,17,4,0],[275,32,4,0],[276,39,4,0],[277,40,4,0],[278,31,4,0],[279,31,4,1],[280,44,4,0],[281,4,4,0],[282,21,4,0],[283,4,4,0],[284,28,4,0],[285,41,4,0],[286,43,4,1],[287,1,4,1],[288,19,4,0],[289,29,4,0],[290,31,4,1],[291,41,4,0],[292,34,4,0],[293,9,4,1],[294,40,4,0],[295,43,4,1],[296,44,4,0],[297,28,4,0],[298,25,4,0],[299,46,4,0],[300,1,4,0],[301,0,4,0],[302,3,4,1],[303,43,4,1],[304,43,4,1],[305,35,4,0],[306,46,4,0],[307,38,4,1],[308,39,4,0],[309,1,4,0],[310,44,4,0],[311,37,4,1],[312,37,4,1],[313,13,4,0],[314,29,4,1],[315,43,4,1],[316,9,4,0],[317,2,4,0],[318,1,4,0],[319,31,4,0],[320,29,4,0],[321,32,4,0],[322,14,4,0],[323,27,4,0],[324,44,4,0],[325,40,4,0],[326,29,4,1],[327,40,4,0],[328,43,4,0],[329,43,4,0],[330,0,4,0],[331,13,4,0],[332,8,4,0],[333,32,4,0],[334,31,4,0],[335,21,4,0],[336,7,4,0],[337,5,4,1],[338,35,4,0],[339,12,4,0],[340,22,4,0],[341,7,4,0],[342,34,4,0],[343,9,4,0],[344,28,4,0],[345,30,4,0],[346,27,4,0],[347,35,4,0],[348,4,4,0],[349,30,4,0],[350,47,4,1],[78,23,4,0],[352,29,4,0],[353,16,4,0],[354,28,4,0],[355,30,4,0],[356,43,4,1],[357,44,4,0],[358,3,4,0],[359,28,4,0],[360,18,4,0],[361,11,4,0],[362,19,4,0],[363,26,4,0],[364,24,4,0],[365,30,4,0],[366,11,4,0],[367,12,4,0],[368,35,4,0],[369,25,4,0],[370,19,4,0],[371,40,4,0],[372,43,4,0],[373,40,4,0],[374,30,4,0],[375,40,4,0],[376,42,4,0],[377,38,4,0],[378,37,4,1],[379,29,4,0],[380,40,4,0],[381,39,4,0],[382,44,4,0],[383,30,4,0],[384,44,4,0],[385,29,4,0],[386,8,4,0],[387,11,4,0],[388,30,4,0],[389,30,4,0],[390,38,4,0],[391,8,4,0],[392,11,4,0],[393,44,4,0],[394,47,4,1],[395,43,4,1],[396,11,4,0],[397,35,4,0],[398,16,4,0],[399,29,4,0],[400,27,4,0],[401,43,4,1],[402,43,4,1],[403,30,4,0],[404,43,4,0],[405,10,4,0],[406,43,4,0],[407,6,4,0],[408,46,4,1],[409,21,4,0],[410,46,4,1],[411,36,4,0],[412,41,4,0],[413,7,4,0],[414,43,4,0],[415,46,4,0],[416,47,4,1],[417,14,4,0],[418,28,4,0],[419,46,4,1],[420,5,4,0],[421,24,4,0],[422,8,4,0],[423,34,4,0],[424,44,4,0],[425,29,4,1],[426,32,4,1],[427,33,4,1],[428,21,4,1],[429,36,4,1],[430,7,4,0],[431,38,4,1],[432,31,4,0],[433,29,4,0],[434,21,4,0],[435,46,4,1],[436,25,4,0],[437,32,4,0],[438,14,4,0],[439,32,4,0],[440,13,4,0],[441,32,4,0],[442,9,4,0],[443,7,4,1],[444,29,4,1],[445,42,4,1],[446,29,4,0],[447,17,4,0],[448,40,4,0],[449,8,4,0],[450,17,4,0],[451,20,4,0],[452,29,4,0],[453,11,4,0],[454,0,4,0],[455,40,4,0],[456,21,4,0],[457,42,4,0],[458,8,4,0],[459,31,4,0],[460,42,4,1],[461,43,4,1],[462,20,4,0],[463,44,4,0],[464,29,4,1],[465,21,4,0],[466,40,4,0],[467,44,4,0],[468,44,4,0],[469,40,4,0],[470,16,4,0],[471,29,4,0],[472,0,4,1],[473,37,4,1],[474,43,4,1],[475,5,4,0],[476,19,4,0],[477,29,4,1],[163,23,4,0],[479,7,4,0],[480,25,4,0],[481,34,4,0],[482,33,4,0],[483,1,4,0],[484,13,4,0],[485,47,4,0],[486,34,4,0],[487,24,4,0],[488,43,4,1],[489,39,4,0],[490,40,4,0],[491,34,4,0],[492,22,4,0],[493,6,4,0],[494,35,4,0],[495,29,4,0],[496,11,4,1],[497,35,4,0],[498,18,4,0],[499,18,4,0],[500,29,4,0],[501,18,4,1],[502,12,4,1],[503,31,4,0],[504,46,4,0],[505,40,4,0],[506,13,4,0],[507,44,4,0],[508,27,4,0],[509,42,4,1],[510,30,4,0],[511,11,4,0],[512,14,4,0],[513,27,4,0],[514,44,4,0],[515,11,4,0],[516,46,4,0],[517,47,4,0],[518,22,4,0],[519,28,4,0],[520,11,4,0],[521,13,4,0],[522,40,4,0],[523,4,4,0],[524,27,4,0],[525,12,4,0],[526,37,4,1],[527,31,4,0],[528,43,4,1],[529,20,4,0],[530,13,4,0],[531,17,4,0],[532,19,4,0],[533,21,4,0],[534,26,4,1],[535,10,4,0],[536,48,4,0],[537,29,4,0],[538,31,4,0],[539,46,4,1],[540,3,4,1],[541,36,4,0],[542,7,4,0],[543,16,4,0],[544,32,4,0],[545,12,4,0],[546,2,4,0],[547,13,4,0],[548,29,4,0],[549,13,4,0],[550,40,4,0],[551,19,4,0],[552,41,4,0],[553,2,4,0],[554,9,4,0],[555,2,4,0],[556,39,4,0],[557,31,4,1],[558,40,4,0],[559,11,4,1],[560,45,4,0],[561,9,4,0],[562,21,4,0],[563,47,4,1],[564,29,4,0],[565,21,4,0],[566,33,4,0],[567,44,4,0],[568,44,4,0],[569,39,4,0],[570,29,4,0],[571,1,4,0],[572,22,4,0],[573,8,4,0],[574,5,4,0],[575,12,4,0],[576,31,4,0],[577,42,4,0],[578,34,4,0],[579,16,4,0],[580,1,4,0],[581,5,4,0],[582,11,4,1],[583,7,4,0],[584,43,4,0],[585,42,4,0],[586,46,4,1],[587,46,4,0],[588,40,4,0],[589,26,4,0],[590,43,4,1],[591,46,4,0],[592,18,4,0],[593,39,4,0],[594,41,4,1],[595,46,4,1],[596,45,4,0],[597,37,4,0],[598,25,4,0],[599,44,4,0],[600,29,4,0],[601,44,4,0],[602,25,4,0],[603,10,4,1],[604,6,4,0],[605,26,4,1],[606,43,4,1],[607,1,4,0],[608,21,4,0],[609,1,4,1],[610,0,4,1],[611,41,4,0],[612,19,4,0],[613,44,4,0],[614,46,4,1],[615,41,4,0],[616,7,4,0],[617,38,4,0],[618,28,4,1],[619,45,4,0],[620,20,4,0],[621,35,4,0],[622,33,4,0],[623,25,4,0],[624,29,4,0],[625,5,4,0],[626,1,4,1],[627,32,4,0],[628,18,4,1],[629,45,4,0],[630,4,4,0],[631,25,4,0],[632,45,4,0],[633,45,4,0],[634,8,4,0],[635,16,4,0],[636,29,4,0],[637,34,4,0],[638,40,4,0],[639,11,4,0],[640,0,4,0],[641,44,4,0],[642,22,4,0],[643,11,4,0],[644,44,4,0],[645,10,4,0],[646,10,4,1],[647,31,4,0],[212,23,4,0],[649,24,4,0],[650,29,4,1],[651,33,4,1],[652,1,4,0],[653,1,4,1],[654,43,4,1],[655,34,4,0],[656,21,4,1],[657,11,4,0],[658,16,4,0],[659,30,4,0],[225,23,4,0],[661,46,4,0],[662,19,4,0],[663,27,4,0],[664,7,4,0],[665,39,4,0],[666,39,4,0],[667,30,4,0],[668,46,4,0],[669,31,4,1],[670,40,4,0],[671,1,4,1],[672,19,4,0],[673,15,4,0],[674,16,4,0],[675,12,4,1],[676,29,4,0],[677,19,4,0],[678,16,4,0],[679,22,4,0],[680,21,4,1],[681,39,4,0],[682,28,4,0],[683,31,4,0],[684,35,4,0],[685,40,4,0],[686,29,4,1],[687,32,4,1],[688,0,4,1],[689,27,4,0],[690,9,4,0],[691,43,4,1],[692,43,4,1],[693,21,4,0],[694,46,4,1],[695,25,4,0],[696,8,4,0],[697,40,4,0],[698,10,4,0],[699,28,4,0],[700,37,4,1],[701,1,4,0],[702,24,4,0],[703,40,4,0],[704,29,4,0],[705,47,4,1],[706,7,4,0],[707,28,4,0],[708,25,4,0],[709,24,4,0],[710,31,4,0],[711,26,4,0],[712,1,4,0],[713,3,4,1],[714,34,4,0],[715,29,4,1],[716,40,4,0],[717,45,4,0],[718,20,4,0],[719,26,4,0],[720,32,4,0],[721,46,4,1],[722,29,4,1],[723,33,4,1],[238,23,4,0],[725,19,4,0],[726,46,4,0],[727,11,4,1],[728,17,4,0],[729,21,4,0],[730,19,4,0],[731,11,4,0],[732,1,4,0],[733,5,4,0],[734,30,4,0],[735,20,4,0],[736,29,4,1],[737,40,4,0],[738,21,4,0],[739,33,4,0],[740,29,4,0],[741,11,4,1],[742,27,4,0],[743,12,4,0],[744,29,4,1],[745,25,4,0],[746,44,4,0],[747,27,4,1],[748,46,4,1],[749,43,4,1],[750,43,4,1],[751,46,4,0],[752,4,4,0],[753,21,4,0],[754,12,4,0],[755,40,4,0],[756,20,4,0],[757,16,4,0],[758,45,4,0],[759,4,4,0],[760,3,4,0],[351,23,4,0],[762,25,4,0],[763,14,4,0],[764,6,4,0],[765,11,4,0],[766,22,4,0],[767,38,4,0],[768,44,4,0],[769,2,4,0],[770,22,4,0],[771,8,4,0],[772,44,4,0],[773,38,4,0],[774,7,4,0],[775,28,4,0],[776,37,4,1],[777,14,4,0],[778,10,4,1],[779,46,4,0],[780,29,4,0],[781,3,4,0],[782,11,4,0],[783,43,4,1],[784,11,4,0],[785,38,4,0],[786,43,4,1],[787,40,4,0],[788,34,4,0],[789,7,4,1],[790,11,4,0],[791,46,4,1],[792,43,4,1],[793,24,4,0],[478,23,4,0],[795,36,4,0],[796,24,4,0],[797,42,4,1],[798,12,4,0],[799,40,4,0],[800,3,4,0],[801,4,4,0],[802,18,4,1],[803,3,4,0],[804,21,4,0],[805,8,4,0],[806,31,4,0],[807,17,4,0],[808,36,4,0],[809,42,4,1],[810,35,4,0],[811,44,4,0],[648,23,4,0],[813,28,4,0],[814,29,4,0],[815,45,4,0],[816,4,4,0],[817,43,4,0],[818,32,4,0],[819,31,4,0],[820,8,4,0],[821,24,4,0],[822,29,4,0],[823,15,4,0],[824,46,4,0],[825,40,4,0],[826,11,4,0],[827,44,4,0],[828,46,4,1],[829,26,4,0],[830,24,4,0],[831,1,4,1],[832,46,4,1],[660,23,4,0],[834,43,4,1],[835,10,4,0],[836,2,4,0],[837,3,4,0],[838,43,4,1],[839,39,4,0],[840,43,4,0],[841,22,4,0],[842,11,4,1],[843,28,4,0],[844,37,4,1],[845,13,4,0],[724,23,4,0],[847,47,4,0],[848,31,4,0],[849,26,4,0],[850,44,4,0],[851,5,4,0],[852,31,4,0],[853,44,4,0],[854,32,4,0],[855,33,4,0],[856,12,4,0],[857,44,4,0],[858,8,4,0],[761,23,4,0],[860,43,4,1],[861,46,4,1],[862,40,4,0],[863,0,4,1],[864,11,4,0],[865,44,4,0],[866,40,4,0],[867,29,4,0],[868,38,4,0],[869,40,4,0],[870,35,4,0],[871,46,4,1],[872,34,4,0],[873,43,4,1],[874,30,4,1],[875,11,4,0],[876,44,4,0],[877,31,4,0],[878,41,4,0],[879,40,4,0],[880,47,4,1],[881,44,4,0],[882,12,4,0],[883,24,4,0],[812,23,4,0],[885,35,4,0],[886,31,4,1],[887,30,4,0],[888,1,4,0],[889,39,4,0],[890,18,4,0],[891,43,4,1],[892,46,4,0],[893,11,4,0],[894,46,4,1],[895,21,4,0],[896,11,4,0],[897,9,4,1],[898,22,4,0],[899,34,4,0],[900,0,4,1],[901,43,4,1],[902,0,4,0],[903,22,4,0],[904,31,4,0],[905,31,4,0],[906,2,4,0],[907,19,4,0],[908,46,4,0],[909,41,4,0],[910,8,4,0],[911,42,4,0],[912,13,4,0],[913,0,4,0],[914,2,4,0],[915,41,4,0],[916,42,4,0],[917,12,4,0],[918,44,4,0],[919,22,4,0],[920,47,4,0],[921,22,4,0],[922,42,4,0],[923,42,4,1],[924,43,4,1],[925,27,4,0],[926,46,4,0],[927,25,4,0],[928,44,4,0],[929,40,4,0],[930,24,4,0],[931,13,4,0],[932,37,4,0],[933,47,4,1],[934,46,4,0],[935,19,4,0],[936,31,4,0],[937,11,4,0],[938,3,4,1],[939,29,4,1],[940,0,4,0],[941,29,4,0],[833,23,4,0],[943,15,4,1],[944,33,4,0],[945,34,4,0],[946,39,4,0],[947,36,4,0],[859,23,4,0],[949,5,4,0],[950,33,4,0],[951,29,4,1],[952,19,4,0],[953,9,4,0],[954,40,4,0],[955,44,4,0],[956,6,4,0],[957,35,4,0],[958,43,4,0],[959,29,4,0],[960,43,4,0],[961,29,4,1],[962,46,4,1],[963,44,4,0],[964,10,4,0],[965,9,4,1],[966,31,4,0],[967,41,4,1],[968,22,4,0],[969,12,4,0],[970,24,4,0],[971,44,4,0],[972,29,4,0],[973,43,4,0],[974,6,4,0],[975,19,4,0],[976,14,4,0],[977,35,4,0],[978,12,4,0],[979,27,4,1],[980,13,4,0],[981,25,4,0],[982,34,4,0],[983,36,4,1],[984,34,4,0],[985,41,4,1],[986,9,4,0],[987,37,4,1],[988,9,4,0],[989,47,4,0],[990,13,4,0],[991,38,4,0],[992,43,4,1],[993,29,4,0],[994,11,4,0],[995,15,4,1],[996,44,4,0],[997,21,4,0],[998,38,4,0],[999,21,4,0],[1000,29,4,0],[1001,40,4,0],[1002,0,4,0],[1003,33,4,0],[1004,43,4,1],[1005,21,4,0],[1006,46,4,1],[1007,11,4,0],[1008,38,4,1],[1009,11,4,0],[1010,21,4,0],[1011,25,4,0],[1012,43,4,1],[1013,46,4,0],[1014,9,4,0],[1015,2,4,0],[1016,11,4,1],[1017,31,4,0],[1018,40,4,0],[1019,10,4,0],[1020,43,4,1],[1021,30,4,0],[1022,6,4,0],[1023,33,4,0],[1024,1,4,0],[1025,29,4,0],[1026,26,4,0],[1027,24,4,0],[1028,37,4,1],[1029,44,4,0],[1030,21,4,0],[1031,0,4,1],[1032,25,4,0],[1033,0,4,1],[1034,29,4,0],[1035,8,4,0],[1036,1,4,0],[1037,39,4,0],[1038,19,4,0],[1039,24,4,0],[1040,29,4,0],[1041,31,4,1],[1042,34,4,0],[1043,21,4,0],[1044,21,4,0],[1045,11,4,0],[1046,19,4,0],[1047,45,4,0],[1048,21,4,0],[1049,27,4,0],[1050,40,4,0],[1051,7,4,0],[1052,46,4,1],[1053,2,4,0],[1054,40,4,0],[1055,26,4,0],[1056,46,4,0],[884,23,4,0],[1058,37,4,1],[1059,21,4,0],[1060,41,4,0],[1061,1,4,0],[1062,12,4,1],[1063,34,4,0],[1064,10,4,0],[1065,27,4,0],[1066,28,4,0],[1067,11,4,1],[1068,1,4,1],[1069,45,4,1],[1070,46,4,1],[0,43,5,0],[1,34,5,0],[2,35,5,0],[3,43,5,0],[4,46,5,1],[5,11,5,0],[6,31,5,0],[7,21,5,0],[8,7,5,0],[9,31,5,0],[10,41,5,0],[11,43,5,0],[12,44,5,0],[13,43,5,1],[14,20,5,0],[15,40,5,0],[16,22,5,0],[17,46,5,0],[18,27,5,0],[19,40,5,0],[20,38,5,0],[21,31,5,0],[22,44,5,0],[23,5,5,0],[24,38,5,0],[25,18,5,0],[26,47,5,0],[27,30,5,0],[28,19,5,0],[29,46,5,0],[30,27,5,0],[31,1,5,0],[32,40,5,0],[33,24,5,0],[34,44,5,0],[35,17,5,1],[36,35,5,0],[37,44,5,0],[38,10,5,0],[39,36,5,0],[40,17,5,0],[41,29,5,0],[42,14,5,0],[43,47,5,0],[44,15,5,1],[45,24,5,0],[46,47,5,1],[47,19,5,0],[48,29,5,1],[49,44,5,0],[50,17,5,0],[51,46,5,0],[52,14,5,0],[53,24,5,0],[54,29,5,1],[55,1,5,0],[56,44,5,0],[57,30,5,0],[58,27,5,0],[59,45,5,0],[60,36,5,0],[61,10,5,0],[62,40,5,0],[63,44,5,0],[64,26,5,0],[65,40,5,0],[66,35,5,0],[67,36,5,0],[68,37,5,1],[69,28,5,0],[70,9,5,0],[71,15,5,0],[72,46,5,0],[73,21,5,0],[74,39,5,0],[75,43,5,1],[76,15,5,0],[77,29,5,0],[942,23,4,0],[79,21,5,0],[80,31,5,0],[81,34,5,0],[82,11,5,0],[83,44,5,0],[84,37,5,1],[85,11,5,1],[86,15,5,1],[87,43,5,1],[88,38,5,0],[89,33,5,0],[90,14,5,0],[91,41,5,0],[92,11,5,1],[93,13,5,0],[94,8,5,0],[95,21,5,0],[96,47,5,1],[97,14,5,0],[98,46,5,1],[99,38,5,0],[100,39,5,0],[101,1,5,1],[102,11,5,1],[103,20,5,0],[104,44,5,0],[105,47,5,1],[106,33,5,0],[107,10,5,0],[108,30,5,0],[109,20,5,1],[110,12,5,1],[111,38,5,0],[112,14,5,0],[113,25,5,0],[114,24,5,0],[115,26,5,0],[116,2,5,0],[117,11,5,0],[118,47,5,0],[119,28,5,0],[120,24,5,0],[121,29,5,0],[122,40,5,0],[123,35,5,0],[124,46,5,1],[125,26,5,0],[126,11,5,1],[127,44,5,0],[128,21,5,0],[129,14,5,0],[130,8,5,0],[131,11,5,0],[132,36,5,1],[133,20,5,0],[134,24,5,0],[135,47,5,1],[136,21,5,0],[137,21,5,0],[138,34,5,0],[139,46,5,0],[140,17,5,0],[141,45,5,0],[142,31,5,0],[143,29,5,0],[144,46,5,1],[145,46,5,0],[146,35,5,0],[147,34,5,0],[148,43,5,1],[149,44,5,0],[150,44,5,0],[151,11,5,1],[152,6,5,0],[153,9,5,0],[154,36,5,0],[155,46,5,0],[156,11,5,0],[157,20,5,0],[158,31,5,1],[159,27,5,0],[160,29,5,1],[161,43,5,1],[162,6,5,0],[948,23,4,0],[164,32,5,0],[165,15,5,0],[166,35,5,0],[167,21,5,0],[168,4,5,0],[169,19,5,0],[170,43,5,1],[171,12,5,0],[172,4,5,0],[173,15,5,1],[174,43,5,1],[175,18,5,0],[176,31,5,0],[177,29,5,0],[178,46,5,1],[179,27,5,0],[180,33,5,0],[181,13,5,0],[182,27,5,0],[183,17,5,0],[184,46,5,0],[185,29,5,0],[186,33,5,1],[187,32,5,1],[188,18,5,0],[189,15,5,1],[190,40,5,0],[191,43,5,0],[192,14,5,0],[193,36,5,1],[194,24,5,0],[195,20,5,0],[196,46,5,0],[197,46,5,0],[198,6,5,0],[199,24,5,0],[200,24,5,0],[201,36,5,0],[202,15,5,1],[203,1,5,1],[204,20,5,0],[205,31,5,1],[206,6,5,0],[207,49,5,0],[208,46,5,0],[209,11,5,1],[210,42,5,0],[211,21,5,0],[1057,23,4,0],[213,24,5,0],[214,12,5,0],[215,10,5,0],[216,3,5,0],[217,28,5,0],[218,40,5,0],[219,46,5,0],[220,44,5,0],[221,43,5,0],[222,26,5,0],[223,15,5,0],[224,43,5,0],[78,23,5,0],[226,3,5,0],[227,44,5,0],[228,7,5,0],[229,22,5,0],[230,10,5,0],[231,21,5,0],[232,8,5,0],[233,29,5,0],[234,7,5,1],[235,14,5,0],[236,0,5,0],[237,35,5,0],[163,23,5,0],[239,1,5,1],[240,29,5,0],[241,46,5,1],[242,29,5,0],[243,44,5,0],[244,46,5,1],[245,40,5,0],[246,35,5,0],[247,26,5,0],[248,35,5,0],[249,12,5,1],[250,33,5,1],[251,14,5,0],[252,14,5,0],[253,47,5,0],[254,46,5,1],[255,32,5,0],[256,26,5,1],[257,32,5,0],[258,43,5,0],[259,21,5,0],[260,7,5,0],[261,47,5,1],[262,34,5,0],[263,29,5,0],[264,43,5,1],[265,15,5,1],[266,3,5,1],[267,12,5,1],[268,46,5,1],[269,37,5,1],[270,3,5,1],[271,1,5,0],[272,12,5,1],[273,41,5,0],[274,17,5,0],[275,32,5,0],[276,39,5,0],[277,40,5,0],[278,31,5,0],[279,31,5,1],[280,44,5,0],[281,4,5,0],[282,21,5,0],[283,4,5,0],[284,28,5,0],[285,41,5,0],[286,43,5,1],[287,1,5,1],[288,19,5,0],[289,29,5,0],[290,31,5,1],[291,41,5,0],[292,34,5,0],[293,9,5,1],[294,40,5,0],[295,43,5,1],[296,44,5,0],[297,28,5,0],[298,25,5,0],[299,46,5,0],[300,1,5,0],[301,0,5,0],[302,3,5,1],[303,43,5,1],[304,43,5,1],[305,35,5,0],[306,46,5,0],[307,38,5,1],[308,39,5,0],[309,1,5,0],[310,44,5,0],[311,37,5,1],[312,37,5,1],[313,13,5,0],[314,29,5,1],[315,43,5,1],[316,9,5,0],[317,2,5,0],[318,1,5,0],[319,31,5,0],[320,29,5,0],[321,32,5,0],[322,14,5,0],[323,27,5,0],[324,44,5,0],[325,40,5,0],[326,29,5,1],[327,40,5,0],[328,43,5,0],[329,43,5,0],[330,0,5,0],[331,13,5,0],[332,8,5,0],[333,32,5,0],[334,31,5,0],[335,21,5,0],[336,7,5,0],[337,5,5,1],[338,35,5,0],[339,12,5,0],[340,22,5,0],[341,7,5,0],[342,34,5,0],[343,9,5,0],[344,28,5,0],[345,30,5,0],[346,27,5,0],[347,35,5,0],[348,4,5,0],[349,30,5,0],[350,47,5,1],[212,23,5,0],[352,29,5,0],[353,16,5,0],[354,28,5,0],[355,30,5,0],[356,43,5,1],[357,44,5,0],[358,3,5,0],[359,28,5,0],[360,18,5,0],[361,11,5,0],[362,19,5,0],[363,26,5,0],[364,24,5,0],[365,30,5,0],[366,11,5,0],[367,12,5,0],[368,35,5,0],[369,25,5,0],[370,19,5,0],[371,40,5,0],[372,43,5,0],[373,40,5,0],[374,30,5,0],[375,40,5,0],[376,42,5,0],[377,38,5,0],[378,37,5,1],[379,29,5,0],[380,40,5,0],[381,39,5,0],[382,44,5,0],[383,30,5,0],[384,44,5,0],[385,29,5,0],[386,8,5,0],[387,11,5,0],[388,30,5,0],[389,30,5,0],[390,38,5,0],[391,8,5,0],[392,11,5,0],[393,44,5,0],[394,47,5,1],[395,43,5,1],[396,11,5,0],[397,35,5,0],[398,16,5,0],[399,29,5,0],[400,27,5,0],[401,43,5,1],[402,43,5,1],[403,30,5,0],[404,43,5,0],[405,10,5,0],[406,43,5,0],[407,6,5,0],[408,46,5,1],[409,21,5,0],[410,46,5,1],[411,36,5,0],[412,41,5,0],[413,7,5,0],[414,43,5,0],[415,46,5,0],[416,47,5,1],[417,14,5,0],[418,28,5,0],[419,46,5,1],[420,5,5,0],[421,24,5,0],[422,8,5,0],[423,34,5,0],[424,44,5,0],[425,29,5,1],[426,32,5,1],[427,33,5,1],[428,21,5,1],[429,36,5,1],[430,7,5,0],[431,38,5,1],[432,31,5,0],[433,29,5,0],[434,21,5,0],[435,46,5,1],[436,25,5,0],[437,32,5,0],[438,14,5,0],[439,32,5,0],[440,13,5,0],[441,32,5,0],[442,9,5,0],[443,7,5,1],[444,29,5,1],[445,42,5,1],[446,29,5,0],[447,17,5,0],[448,40,5,0],[449,8,5,0],[450,17,5,0],[451,20,5,0],[452,29,5,0],[453,11,5,0],[454,0,5,0],[455,40,5,0],[456,21,5,0],[457,42,5,0],[458,8,5,0],[459,31,5,0],[460,42,5,1],[461,43,5,1],[462,20,5,0],[463,44,5,0],[464,29,5,1],[465,21,5,0],[466,40,5,0],[467,44,5,0],[468,44,5,0],[469,40,5,0],[470,16,5,0],[471,29,5,0],[472,0,5,1],[473,37,5,1],[474,43,5,1],[475,5,5,0],[476,19,5,0],[477,29,5,1],[225,23,5,0],[479,7,5,0],[480,25,5,0],[481,34,5,0],[482,33,5,0],[483,1,5,0],[484,13,5,0],[485,47,5,0],[486,34,5,0],[487,24,5,0],[488,43,5,1],[489,39,5,0],[490,40,5,0],[491,34,5,0],[492,22,5,0],[493,6,5,0],[494,35,5,0],[495,29,5,0],[496,11,5,1],[497,35,5,0],[498,18,5,0],[499,18,5,0],[500,29,5,0],[501,18,5,0],[502,12,5,1],[503,31,5,0],[504,46,5,0],[505,40,5,0],[506,13,5,0],[507,44,5,0],[508,27,5,0],[509,42,5,0],[510,30,5,0],[511,11,5,0],[512,14,5,0],[513,27,5,0],[514,44,5,0],[515,11,5,0],[516,46,5,0],[517,47,5,0],[518,22,5,0],[519,28,5,0],[520,11,5,0],[521,13,5,0],[522,40,5,0],[523,4,5,0],[524,27,5,0],[525,12,5,0],[526,37,5,1],[527,31,5,0],[528,43,5,1],[529,20,5,0],[530,13,5,0],[531,17,5,0],[532,19,5,0],[533,21,5,0],[534,26,5,1],[535,10,5,0],[536,48,5,0],[537,29,5,0],[538,31,5,0],[539,46,5,1],[540,3,5,1],[541,36,5,0],[542,7,5,0],[543,16,5,0],[544,32,5,0],[545,12,5,0],[546,2,5,0],[547,13,5,0],[548,29,5,0],[549,13,5,0],[550,40,5,0],[551,19,5,0],[552,41,5,0],[553,2,5,0],[554,9,5,0],[555,2,5,0],[556,39,5,0],[557,31,5,1],[558,40,5,0],[559,11,5,1],[560,45,5,0],[561,9,5,0],[562,21,5,0],[563,47,5,1],[564,29,5,0],[565,21,5,0],[566,33,5,0],[567,44,5,0],[568,44,5,0],[569,39,5,0],[570,29,5,0],[571,1,5,0],[572,22,5,0],[573,8,5,0],[574,5,5,0],[575,12,5,0],[576,31,5,0],[577,42,5,0],[578,34,5,0],[579,16,5,0],[580,1,5,0],[581,5,5,0],[582,11,5,1],[583,7,5,0],[584,43,5,0],[585,42,5,0],[586,46,5,1],[587,46,5,0],[588,40,5,0],[589,26,5,0],[590,43,5,1],[591,46,5,0],[592,18,5,0],[593,39,5,0],[594,41,5,1],[595,46,5,1],[596,45,5,0],[597,37,5,0],[598,25,5,0],[599,44,5,0],[600,29,5,0],[601,44,5,0],[602,25,5,0],[603,10,5,1],[604,6,5,0],[605,26,5,1],[606,43,5,1],[607,1,5,0],[608,21,5,0],[609,1,5,1],[610,0,5,1],[611,41,5,0],[612,19,5,0],[613,44,5,0],[614,46,5,1],[615,41,5,0],[616,7,5,0],[617,38,5,0],[618,28,5,1],[619,45,5,0],[620,20,5,0],[621,35,5,0],[622,33,5,0],[623,25,5,0],[624,29,5,0],[625,5,5,0],[626,1,5,1],[627,32,5,0],[628,18,5,1],[629,45,5,0],[630,4,5,0],[631,25,5,0],[632,45,5,0],[633,45,5,0],[634,8,5,0],[635,16,5,0],[636,29,5,0],[637,34,5,0],[638,40,5,0],[639,11,5,0],[640,0,5,0],[641,44,5,0],[642,22,5,0],[643,11,5,0],[644,44,5,0],[645,10,5,0],[646,10,5,1],[647,31,5,0],[238,23,5,0],[649,24,5,0],[650,29,5,1],[651,33,5,1],[652,1,5,0],[653,1,5,1],[654,43,5,1],[655,34,5,0],[656,21,5,1],[657,11,5,0],[658,16,5,0],[659,30,5,0],[351,23,5,0],[661,46,5,0],[662,19,5,0],[663,27,5,0],[664,7,5,0],[665,39,5,0],[666,39,5,0],[667,30,5,0],[668,46,5,0],[669,31,5,1],[670,40,5,0],[671,1,5,1],[672,19,5,0],[673,15,5,0],[674,16,5,0],[675,12,5,1],[676,29,5,0],[677,19,5,0],[678,16,5,0],[679,22,5,0],[680,21,5,1],[681,39,5,0],[682,28,5,0],[683,31,5,0],[684,35,5,0],[685,40,5,0],[686,29,5,1],[687,32,5,1],[688,0,5,1],[689,27,5,0],[690,9,5,0],[691,43,5,1],[692,43,5,1],[693,21,5,0],[694,46,5,1],[695,25,5,0],[696,8,5,0],[697,40,5,0],[698,10,5,0],[699,28,5,0],[700,37,5,1],[701,1,5,0],[702,24,5,0],[703,40,5,0],[704,29,5,0],[705,47,5,1],[706,7,5,0],[707,28,5,0],[708,25,5,0],[709,24,5,0],[710,31,5,0],[711,26,5,0],[712,1,5,0],[713,3,5,1],[714,34,5,0],[715,29,5,1],[716,40,5,0],[717,45,5,0],[718,20,5,0],[719,26,5,0],[720,32,5,0],[721,46,5,1],[722,29,5,1],[723,33,5,1],[478,23,5,0],[725,19,5,0],[726,46,5,0],[727,11,5,1],[728,17,5,0],[729,21,5,0],[730,19,5,0],[731,11,5,0],[732,1,5,0],[733,5,5,0],[734,30,5,0],[735,20,5,0],[736,29,5,1],[737,40,5,0],[738,21,5,0],[739,33,5,0],[740,29,5,0],[741,11,5,1],[742,27,5,0],[743,12,5,0],[744,29,5,1],[745,25,5,0],[746,44,5,0],[747,27,5,1],[748,46,5,1],[749,43,5,1],[750,43,5,1],[751,46,5,0],[752,4,5,0],[753,21,5,0],[754,12,5,0],[755,40,5,0],[756,20,5,0],[757,16,5,0],[758,45,5,0],[759,4,5,0],[760,3,5,0],[648,23,5,0],[762,25,5,0],[763,14,5,0],[764,6,5,0],[765,11,5,0],[766,22,5,0],[767,38,5,0],[768,44,5,0],[769,2,5,0],[770,22,5,0],[771,8,5,0],[772,44,5,0],[773,38,5,0],[774,7,5,0],[775,28,5,0],[776,37,5,1],[777,14,5,0],[778,10,5,1],[779,46,5,0],[780,29,5,0],[781,3,5,0],[782,11,5,0],[783,43,5,0],[784,11,5,0],[785,38,5,0],[786,43,5,1],[787,40,5,0],[788,34,5,0],[789,7,5,1],[790,11,5,0],[791,46,5,1],[792,43,5,1],[793,24,5,0],[660,23,5,0],[795,36,5,0],[796,24,5,0],[797,42,5,1],[798,12,5,0],[799,40,5,0],[800,3,5,0],[801,4,5,0],[802,18,5,0],[803,3,5,0],[804,21,5,0],[805,8,5,0],[806,31,5,0],[807,17,5,0],[808,36,5,0],[809,42,5,1],[810,35,5,0],[811,44,5,0],[724,23,5,0],[813,28,5,0],[814,29,5,0],[815,45,5,0],[816,4,5,0],[817,43,5,0],[818,32,5,0],[819,31,5,0],[820,8,5,0],[821,24,5,0],[822,29,5,0],[823,15,5,0],[824,46,5,0],[825,40,5,0],[826,11,5,0],[827,44,5,0],[828,46,5,1],[829,26,5,0],[830,24,5,0],[831,1,5,1],[832,46,5,1],[761,23,5,0],[834,43,5,1],[835,10,5,0],[836,2,5,0],[837,3,5,0],[838,43,5,1],[839,39,5,0],[840,43,5,0],[841,22,5,0],[842,11,5,1],[843,28,5,0],[844,37,5,1],[845,13,5,0],[812,23,5,0],[847,47,5,0],[848,31,5,0],[849,26,5,0],[850,44,5,0],[851,5,5,0],[852,31,5,0],[853,44,5,0],[854,32,5,0],[855,33,5,0],[856,12,5,0],[857,44,5,0],[858,8,5,0],[833,23,5,0],[860,43,5,1],[861,46,5,1],[862,40,5,0],[863,0,5,1],[864,11,5,0],[865,44,5,0],[866,40,5,0],[867,29,5,0],[868,38,5,0],[869,40,5,0],[870,35,5,0],[871,46,5,1],[872,34,5,0],[873,43,5,1],[874,30,5,1],[875,11,5,0],[876,44,5,0],[877,31,5,0],[878,41,5,0],[879,40,5,0],[880,47,5,1],[881,44,5,0],[882,12,5,0],[883,24,5,0],[859,23,5,0],[885,35,5,0],[886,31,5,1],[887,30,5,0],[888,1,5,0],[889,39,5,0],[890,18,5,0],[891,43,5,1],[892,46,5,0],[893,11,5,0],[894,46,5,1],[895,21,5,0],[896,11,5,0],[897,9,5,1],[898,22,5,0],[899,34,5,0],[900,0,5,1],[901,43,5,1],[902,0,5,0],[903,22,5,0],[904,31,5,0],[905,31,5,0],[906,2,5,0],[907,19,5,0],[908,46,5,0],[909,41,5,0],[910,8,5,0],[911,42,5,0],[912,13,5,0],[913,0,5,0],[914,2,5,0],[915,41,5,0],[916,42,5,0],[917,12,5,0],[918,44,5,0],[919,22,5,0],[920,47,5,0],[921,22,5,0],[922,42,5,0],[923,42,5,1],[924,43,5,1],[925,27,5,0],[926,46,5,0],[927,25,5,0],[928,44,5,0],[929,40,5,0],[930,24,5,0],[931,13,5,0],[932,37,5,0],[933,47,5,1],[934,46,5,0],[935,19,5,0],[936,31,5,0],[937,11,5,0],[938,3,5,1],[939,29,5,1],[940,0,5,0],[941,29,5,0],[884,23,5,0],[943,15,5,1],[944,33,5,0],[945,34,5,0],[946,39,5,0],[947,36,5,0],[942,23,5,0],[949,5,5,0],[950,33,5,0],[951,29,5,1],[952,19,5,0],[953,9,5,0],[954,40,5,0],[955,44,5,0],[956,6,5,0],[957,35,5,0],[958,43,5,0],[959,29,5,0],[960,43,5,0],[961,29,5,1],[962,46,5,1],[963,44,5,0],[964,10,5,0],[965,9,5,1],[966,31,5,0],[967,41,5,1],[968,22,5,0],[969,12,5,0],[970,24,5,0],[971,44,5,0],[972,29,5,0],[973,43,5,0],[974,6,5,0],[975,19,5,0],[976,14,5,0],[977,35,5,0],[978,12,5,0],[979,27,5,1],[980,13,5,0],[981,25,5,0],[982,34,5,0],[983,36,5,1],[984,34,5,0],[985,41,5,1],[986,9,5,0],[987,37,5,1],[988,9,5,0],[989,47,5,0],[990,13,5,0],[991,38,5,0],[992,43,5,1],[993,29,5,0],[994,11,5,0],[995,15,5,1],[996,44,5,0],[997,21,5,0],[998,38,5,0],[999,21,5,0],[1000,29,5,0],[1001,40,5,0],[1002,0,5,0],[1003,33,5,0],[1004,43,5,1],[1005,21,5,0],[1006,46,5,1],[1007,11,5,0],[1008,38,5,1],[1009,11,5,0],[1010,21,5,0],[1011,25,5,0],[1012,43,5,1],[1013,46,5,0],[1014,9,5,0],[1015,2,5,0],[1016,11,5,1],[1017,31,5,0],[1018,40,5,0],[1019,10,5,0],[1020,43,5,1],[1021,30,5,0],[1022,6,5,0],[1023,33,5,0],[1024,1,5,0],[1025,29,5,0],[1026,26,5,0],[1027,24,5,0],[1028,37,5,1],[1029,44,5,0],[1030,21,5,0],[1031,0,5,1],[1032,25,5,0],[1033,0,5,1],[1034,29,5,0],[1035,8,5,0],[1036,1,5,0],[1037,39,5,0],[1038,19,5,0],[1039,24,5,0],[1040,29,5,0],[1041,31,5,1],[1042,34,5,0],[1043,21,5,0],[1044,21,5,0],[1045,11,5,0],[1046,19,5,0],[1047,45,5,0],[1048,21,5,0],[1049,27,5,0],[1050,40,5,0],[1051,7,5,0],[1052,46,5,1],[1053,2,5,0],[1054,40,5,0],[1055,26,5,0],[1056,46,5,0],[948,23,5,0],[1058,37,5,0],[1059,21,5,0],[1060,41,5,0],[1061,1,5,0],[1062,12,5,1],[1063,34,5,0],[1064,10,5,0],[1065,27,5,0],[1066,28,5,0],[1067,11,5,1],[1068,1,5,1],[1069,45,5,1],[1070,46,5,1],[0,43,8,0],[3,43,8,0],[4,46,8,1],[5,11,8,0],[7,21,8,0],[8,7,8,0],[10,41,8,0],[11,43,8,0],[13,43,8,1],[14,20,8,0],[19,40,8,0],[21,31,8,0],[22,44,8,0],[25,18,8,0],[30,27,8,0],[34,44,8,0],[36,35,8,0],[38,10,8,0],[39,36,8,0],[49,44,8,0],[52,14,8,0],[53,24,8,0],[58,27,8,0],[59,45,8,0],[62,40,8,0],[64,26,8,0],[66,35,8,0],[68,37,8,1],[71,15,8,0],[72,46,8,0],[73,21,8,0],[77,29,8,0],[1057,23,5,0],[79,21,8,0],[81,34,8,0],[84,37,8,1],[91,41,8,0],[92,11,8,1],[93,13,8,0],[94,8,8,0],[95,21,8,0],[97,14,8,0],[98,46,8,1],[101,1,8,1],[102,11,8,1],[106,33,8,0],[107,10,8,0],[109,20,8,1],[110,12,8,1],[111,38,8,0],[112,14,8,0],[113,25,8,0],[114,24,8,0],[115,26,8,0],[118,47,8,0],[119,28,8,0],[125,26,8,0],[127,44,8,0],[129,14,8,0],[132,36,8,1],[133,20,8,0],[135,47,8,1],[136,21,8,0],[137,21,8,0],[140,17,8,0],[141,45,8,0],[143,29,8,0],[147,34,8,0],[150,44,8,0],[151,11,8,1],[156,11,8,0],[158,31,8,1],[161,43,8,1],[168,4,8,0],[171,12,8,0],[173,15,8,1],[177,29,8,0],[179,27,8,0],[180,33,8,0],[185,29,8,0],[191,43,8,0],[195,20,8,0],[197,46,8,0],[198,6,8,0],[200,24,8,0],[202,15,8,1],[203,1,8,1],[204,20,8,0],[206,6,8,0],[208,46,8,0],[210,42,8,0],[211,21,8,0],[78,23,8,0],[213,24,8,0],[214,12,8,0],[215,10,8,0],[217,28,8,0],[220,44,8,0],[212,23,8,0],[226,3,8,0],[227,44,8,0],[228,7,8,0],[229,22,8,0],[231,21,8,0],[237,35,8,0],[225,23,8,0],[240,29,8,0],[241,46,8,1],[242,29,8,0],[244,46,8,1],[246,35,8,0],[247,26,8,0],[248,35,8,0],[250,33,8,1],[251,14,8,0],[254,46,8,1],[255,32,8,0],[258,43,8,0],[260,7,8,0],[262,34,8,0],[263,29,8,0],[266,3,8,1],[267,12,8,1],[272,12,8,1],[274,17,8,0],[280,44,8,0],[281,4,8,0],[283,4,8,0],[285,41,8,0],[287,1,8,0],[289,29,8,0],[293,9,8,0],[294,40,8,0],[296,44,8,0],[297,28,8,0],[298,25,8,0],[300,1,8,0],[302,3,8,1],[303,43,8,1],[305,35,8,0],[306,46,8,0],[307,38,8,1],[311,37,8,1],[312,37,8,0],[317,2,8,0],[321,32,8,0],[322,14,8,0],[323,27,8,0],[325,40,8,0],[326,29,8,1],[329,43,8,0],[332,8,8,0],[335,21,8,0],[336,7,8,0],[339,12,8,0],[340,22,8,0],[342,34,8,0],[344,28,8,0],[345,30,8,0],[346,27,8,0],[348,4,8,0],[350,47,8,1],[352,29,8,0],[353,16,8,0],[354,28,8,0],[355,30,8,0],[358,3,8,0],[361,11,8,0],[362,19,8,0],[364,24,8,0],[366,11,8,0],[367,12,8,0],[370,19,8,0],[372,43,8,0],[373,40,8,0],[374,30,8,0],[377,38,8,0],[378,37,8,1],[382,44,8,0],[383,30,8,0],[385,29,8,0],[386,8,8,0],[390,38,8,0],[392,11,8,0],[394,47,8,1],[396,11,8,0],[397,35,8,0],[399,29,8,0],[404,43,8,0],[406,43,8,0],[407,6,8,0],[408,46,8,1],[409,21,8,0],[411,36,8,0],[412,41,8,0],[414,43,8,0],[420,5,8,0],[421,24,8,0],[422,8,8,0],[425,29,8,1],[426,32,8,1],[430,7,8,0],[432,31,8,0],[433,29,8,0],[437,32,8,0],[440,13,8,0],[442,9,8,0],[446,29,8,0],[447,17,8,0],[449,8,8,0],[452,29,8,0],[455,40,8,0],[456,21,8,0],[457,42,8,0],[458,8,8,0],[462,20,8,0],[464,29,8,1],[465,21,8,0],[470,16,8,0],[471,29,8,0],[472,0,8,1],[473,37,8,1],[474,43,8,1],[475,5,8,0],[476,19,8,0],[238,23,8,0],[480,25,8,0],[481,34,8,0],[485,47,8,0],[493,6,8,0],[494,35,8,0],[498,18,8,0],[499,18,8,0],[501,18,8,0],[503,31,8,0],[504,46,8,0],[505,40,8,0],[506,13,8,0],[513,27,8,0],[518,22,8,0],[522,40,8,0],[525,12,8,0],[528,43,8,1],[530,13,8,0],[531,17,8,0],[533,21,8,0],[534,26,8,1],[535,10,8,0],[538,31,8,0],[541,36,8,0],[542,7,8,0],[544,32,8,0],[547,13,8,0],[548,29,8,0],[550,40,8,0],[552,41,8,0],[553,2,8,0],[558,40,8,0],[559,11,8,1],[560,45,8,0],[561,9,8,0],[562,21,8,0],[564,29,8,0],[565,21,8,0],[567,44,8,0],[568,44,8,0],[570,29,8,0],[571,1,8,0],[572,22,8,0],[573,8,8,0],[574,5,8,0],[575,12,8,0],[577,42,8,0],[578,34,8,0],[580,1,8,0],[581,5,8,0],[582,11,8,1],[583,7,8,0],[584,43,8,0],[586,46,8,1],[587,46,8,0],[588,40,8,0],[589,26,8,0],[591,46,8,0],[594,41,8,0],[596,45,8,0],[600,29,8,0],[601,44,8,0],[602,25,8,0],[603,10,8,1],[604,6,8,0],[605,26,8,1],[607,1,8,0],[611,41,8,0],[612,19,8,0],[613,44,8,0],[615,41,8,0],[616,7,8,0],[618,28,8,0],[627,32,8,0],[628,18,8,1],[631,25,8,0],[632,45,8,0],[635,16,8,0],[638,40,8,0],[641,44,8,0],[642,22,8,0],[644,44,8,0],[645,10,8,0],[649,24,8,0],[650,29,8,1],[653,1,8,1],[656,21,8,1],[664,7,8,0],[669,31,8,1],[671,1,8,0],[674,16,8,0],[675,12,8,1],[678,16,8,0],[679,22,8,0],[682,28,8,0],[684,35,8,0],[687,32,8,1],[688,0,8,1],[689,27,8,0],[690,9,8,0],[691,43,8,1],[692,43,8,1],[695,25,8,0],[696,8,8,0],[699,28,8,0],[702,24,8,0],[706,7,8,0],[707,28,8,0],[710,31,8,0],[711,26,8,0],[716,40,8,0],[717,45,8,0],[719,26,8,0],[720,32,8,0],[722,29,8,1],[723,33,8,1],[478,23,8,0],[732,1,8,0],[734,30,8,0],[735,20,8,0],[736,29,8,1],[738,21,8,0],[740,29,8,0],[741,11,8,1],[746,44,8,0],[750,43,8,1],[751,46,8,0],[758,45,8,0],[762,25,8,0],[763,14,8,0],[764,6,8,0],[765,11,8,0],[767,38,8,0],[779,46,8,0],[780,29,8,0],[795,36,8,0],[796,24,8,0],[798,12,8,0],[799,40,8,0],[804,21,8,0],[724,23,8,0],[814,29,8,0],[815,45,8,0],[817,43,8,0],[821,24,8,0],[822,29,8,0],[823,15,8,0],[824,46,8,0],[825,40,8,0],[827,44,8,0],[830,24,8,0],[831,1,8,1],[834,43,8,1],[835,10,8,0],[836,2,8,0],[837,3,8,0],[841,22,8,0],[855,33,8,0],[857,44,8,0],[864,11,8,0],[865,44,8,0],[867,29,8,0],[868,38,8,0],[871,46,8,1],[872,34,8,0],[873,43,8,1],[874,30,8,1],[876,44,8,0],[883,24,8,0],[887,30,8,0],[888,1,8,0],[892,46,8,0],[894,46,8,1],[896,11,8,0],[897,9,8,1],[898,22,8,0],[902,0,8,0],[903,22,8,0],[906,2,8,0],[911,42,8,0],[912,13,8,0],[914,2,8,0],[915,41,8,0],[916,42,8,0],[919,22,8,0],[922,42,8,0],[923,42,8,1],[925,27,8,0],[926,46,8,0],[927,25,8,0],[928,44,8,0],[930,24,8,0],[931,13,8,0],[932,37,8,0],[934,46,8,0],[936,31,8,0],[937,11,8,0],[939,29,8,1],[940,0,8,0],[943,15,8,1],[944,33,8,0],[947,36,8,0],[949,5,8,0],[950,33,8,0],[956,6,8,0],[959,29,8,0],[966,31,8,0],[967,41,8,1],[968,22,8,0],[969,12,8,0],[971,44,8,0],[974,6,8,0],[975,19,8,0],[977,35,8,0],[980,13,8,0],[981,25,8,0],[982,34,8,0],[983,36,8,1],[984,34,8,0],[989,47,8,0],[991,38,8,0],[992,43,8,1],[993,29,8,0],[998,38,8,0],[999,21,8,0],[1000,29,8,0],[1003,33,8,0],[1007,11,8,0],[1009,11,8,0],[1011,25,8,0],[1014,9,8,0],[1017,31,8,0],[1021,30,8,0],[1022,6,8,0],[1023,33,8,0],[1024,1,8,0],[1025,29,8,0],[1026,26,8,0],[1028,37,8,0],[1029,44,8,0],[1030,21,8,0],[1033,0,8,1],[1035,8,8,0],[1036,1,8,0],[1038,19,8,0],[1042,34,8,0],[1043,21,8,0],[1044,21,8,0],[1046,19,8,0],[1047,45,8,0],[1049,27,8,0],[1051,7,8,0],[812,23,8,0],[1058,37,8,0],[1059,21,8,0],[1060,41,8,0],[1062,12,8,1],[1065,27,8,0],[1066,28,8,0],[1069,45,8,1],[1,34,6,0],[2,35,6,0],[20,38,6,0],[28,19,6,0],[31,1,6,0],[33,24,6,0],[35,17,6,1],[42,14,6,0],[43,47,6,0],[47,19,6,0],[48,29,6,1],[50,17,6,0],[61,10,6,0],[67,36,6,0],[70,9,6,0],[72,46,6,0],[76,15,6,0],[83,44,6,0],[85,11,6,1],[86,15,6,1],[96,47,6,0],[108,30,6,0],[116,2,6,0],[124,46,6,1],[128,21,6,0],[130,8,6,0],[134,24,6,0],[145,46,6,0],[153,9,6,0],[159,27,6,0],[160,29,6,1],[164,32,6,0],[167,21,6,0],[172,4,6,0],[175,18,6,0],[178,46,6,1],[181,13,6,0],[186,33,6,1],[187,32,6,1],[189,15,6,1],[193,36,6,1],[194,24,6,0],[205,31,6,1],[216,3,6,0],[218,40,6,0],[222,26,6,0],[239,1,6,1],[249,12,6,1],[256,26,6,1],[259,21,6,0],[271,1,6,0],[277,40,6,0],[284,28,6,0],[288,19,6,0],[291,41,6,0],[292,34,6,0],[295,43,6,1],[310,44,6,0],[312,37,6,0],[314,29,6,0],[318,1,6,0],[319,31,6,0],[341,7,6,0],[347,35,6,0],[356,43,6,1],[360,18,6,0],[365,30,6,0],[368,35,6,0],[388,30,6,0],[391,8,6,0],[398,16,6,0],[405,10,6,0],[415,46,6,0],[416,47,6,1],[417,14,6,0],[418,28,6,0],[419,46,6,1],[428,21,6,1],[429,36,6,0],[434,21,6,0],[435,46,6,1],[436,25,6,0],[439,32,6,0],[441,32,6,0],[443,7,6,1],[445,42,6,1],[448,40,6,0],[453,11,6,0],[454,0,6,0],[460,42,6,1],[466,40,6,0],[477,29,6,0],[479,7,6,0],[484,13,6,0],[486,34,6,0],[487,24,6,0],[488,43,6,1],[492,22,6,0],[495,29,6,0],[496,11,6,1],[502,12,6,1],[508,27,6,0],[510,30,6,0],[512,14,6,0],[515,11,6,0],[517,47,6,0],[519,28,6,0],[520,11,6,0],[521,13,6,0],[529,20,6,0],[537,29,6,0],[546,2,6,0],[551,19,6,0],[554,9,6,0],[555,2,6,0],[563,47,6,1],[566,33,6,0],[576,31,6,0],[617,38,6,0],[619,45,6,0],[620,20,6,0],[621,35,6,0],[622,33,6,0],[623,25,6,0],[624,29,6,0],[630,4,6,0],[634,8,6,0],[636,29,6,0],[637,34,6,0],[639,11,6,0],[640,0,6,0],[643,11,6,0],[646,10,6,1],[651,33,6,1],[652,1,6,0],[654,43,6,1],[657,11,6,0],[658,16,6,0],[1057,23,8,0],[663,27,6,0],[667,30,6,0],[672,19,6,0],[676,29,6,0],[677,19,6,0],[680,21,6,1],[686,29,6,1],[708,25,6,0],[709,24,6,0],[712,1,6,0],[713,3,6,1],[714,34,6,0],[715,29,6,1],[718,20,6,0],[728,17,6,0],[730,19,6,0],[731,11,6,0],[733,5,6,0],[739,33,6,0],[747,27,6,1],[752,4,6,0],[756,20,6,0],[757,16,6,0],[769,2,6,0],[773,38,6,0],[774,7,6,0],[776,37,6,1],[778,10,6,1],[781,3,6,0],[784,11,6,0],[788,34,6,0],[790,11,6,0],[793,24,6,0],[797,42,6,1],[800,3,6,0],[801,4,6,0],[802,18,6,0],[803,3,6,0],[805,8,6,0],[807,17,6,0],[808,36,6,0],[809,42,6,1],[813,28,6,0],[816,4,6,0],[820,8,6,0],[832,46,6,1],[660,23,6,0],[843,28,6,0],[844,37,6,1],[845,13,6,0],[833,23,6,0],[849,26,6,0],[851,5,6,0],[854,32,6,0],[856,12,6,0],[863,0,6,1],[875,11,6,0],[877,31,6,0],[879,40,6,0],[880,47,6,1],[884,23,6,0],[886,31,6,1],[893,11,6,0],[895,21,6,0],[900,0,6,1],[909,41,6,0],[918,44,6,0],[933,47,6,1],[935,19,6,0],[941,29,6,0],[942,23,6,0],[945,34,6,0],[952,19,6,0],[960,43,6,0],[961,29,6,1],[965,9,6,1],[972,29,6,0],[976,14,6,0],[978,12,6,0],[985,41,6,1],[986,9,6,0],[995,15,6,1],[996,44,6,0],[1005,21,6,0],[1008,38,6,1],[1018,40,6,0],[1019,10,6,0],[1020,43,6,1],[1031,0,6,1],[1040,29,6,0],[1050,40,6,0],[1056,46,6,0],[1063,34,6,0],[6,31,7,0],[24,38,7,0],[37,44,7,0],[80,31,7,0],[99,38,7,0],[103,20,7,0],[131,11,7,0],[138,34,7,0],[154,36,7,0],[162,6,7,0],[183,17,7,0],[188,18,7,0],[199,24,7,0],[219,46,7,0],[223,15,7,0],[230,10,7,0],[232,8,7,0],[234,7,7,1],[235,14,7,0],[236,0,7,0],[257,32,7,0],[261,47,7,1],[265,15,7,1],[269,37,7,1],[270,3,7,1],[301,0,7,0],[320,29,7,0],[331,13,7,0],[337,5,7,0],[343,9,7,0],[357,44,7,0],[359,28,7,0],[423,34,7,0],[427,33,7,1],[450,17,7,0],[482,33,7,0],[500,29,7,0],[507,44,7,0],[509,42,7,0],[524,27,7,0],[526,37,7,1],[532,19,7,0],[543,16,7,0],[557,31,7,1],[585,42,7,0],[610,0,7,0],[625,5,7,0],[633,45,7,0],[668,46,7,0],[693,21,7,0],[698,10,7,0],[701,1,7,0],[703,40,7,0],[704,29,7,0],[726,46,7,0],[727,11,7,1],[737,40,7,0],[749,43,7,1],[761,23,7,0],[770,22,7,0],[771,8,7,0],[818,32,7,0],[826,11,7,0],[862,40,7,0],[878,41,7,0],[882,12,7,0],[901,43,7,1],[913,0,7,0],[924,43,7,0],[938,3,7,0],[948,23,7,0],[951,29,7,1],[957,35,7,0],[987,37,7,1],[988,9,7,0],[990,13,7,0],[997,21,7,0],[1015,2,7,0],[1016,11,7,1],[1027,24,7,0],[1034,29,7,0],[1048,21,7,0],[1055,26,7,0],[1061,1,7,0]],"depara":{"CASA BRANCA":[0,"CASA BRANCA"],"ALAGOAS 101":[1,"ALAGOAS 101"],"BALANCA":[2,"BALANÇA"],"ANEL VIARIO":[3,"ANEL VIARIO"],"CHEROKEE":[0,"CHEROKEE"],"BENDEGO":[1,"BENDEGO"],"CAMPOS ALTOS":[2,"CAMPOS ALTOS"],"BARREIRAS":[3,"BARREIRAS"],"FALCAO":[0,"FALÇÃO"],"CARAVELAS":[1,"CARAVELAS"],"CENTENARIO":[2,"CENTENARIO"],"CANDIDO SALES":[3,"CANDIDO SALES"],"FERRARI":[0,"FERRARI"],"COLONIAL 101":[1,"COLONIAL 101"],"FLASH":[2,"FLASH"],"GRANDE VALE":[3,"GRANDE VALE"],"ILHA BRAVA":[0,"ILHA BRAVA"],"FEIRA 101":[1,"FEIRA 101"],"MINAS GERAIS":[2,"MINAS GERAIS"],"GRAO DE OURO":[3,"GRAO DE OURO"],"JR":[0,"JR"],"ITABUNA":[1,"ITABUNA"],"MOC":[2,"MOC"],"MARACANA":[3,"MARACANA"],"LAJINHA":[0,"LAJINHA"],"LINHARES":[1,"LINHARES"],"MOC 135":[2,"MOC 135"],"NOVO PONTO":[3,"NOVO PONTO"],"PAPA LEGUAS 1":[0,"PAPA LEGUAS 1"],"PARCEIRO":[1,"PARCEIRO"],"NORTE DE MINAS":[2,"NORTE DE MINAS"],"PAPA LEGUAS III":[3,"PAPA LEGUAS III"],"PERIQUITO":[0,"PERIQUITO"],"SALVADOR":[1,"SALVADOR"],"QUILOMETRAGEM":[2,"QUILOMETRAGEM"],"PQ DOS COQUEIROS":[3,"PQ DOS COQUEIROS"],"PINHEIROS":[0,"PINHEIROS"],"SANTO ANTONIO":[1,"SANTO ANTONIO"],"TURMALINA III":[2,"TURMALINA III"],"SAO MARCOS":[3,"SÃO MARCOS"],"PISCINA":[0,"PISCINA"],"TALISMA":[3,"TALISMA"],"PLANALTO II":[0,"PLANALTO II"],"UIRAPURU":[3,"UIRAPURU"],"RAVENA":[0,"RAVENA"],"ULTRA":[3,"ULTRA"],"GURUPI":[3,"GURUPI"],"PAPA LEGUAS I":[0,"PAPA LEGUAS 1"],"PQ COQUEIROS":[3,"PQ DOS COQUEIROS"],"PLANALTO":[0,"PLANALTO II"],"EUCALIPTOS":[2,"EUCALIPTOS"],"MATRIZ":[4,"MATRIZ"],"TECNO ARLA MATRIZ":[4,"TECNO ARLA MATRIZ"],"TECNO ARLA MARACANA":[4,"TECNO ARLA MARACANA"]},"ordem":["SEGURANCA DO TRABALHO","EPI","BENZENO","NR 20","PLANO DE MANUTENCAO","CODIGO DE ETICA","APERFEICOE FRENTISTA CAIXA","APERFEICOE FRENTISTACAIXA","GESTAO AUDITORIA"],"origem":"RELATORIO_DIA_03-09.xlsx","atualizado":"2026-09-04"}</script>
<script id="js-painel">
(function(){
  "use strict";
  var D = JSON.parse(document.getElementById('dados').textContent);
  var REG = D.regionais, FIL = D.filiais, CUR = D.cursos, PART = D.participantes, F = D.fatos;
  var DEPARA = D.depara || {}, ORDEM = D.ordem || [];
  var CORP = REG.length - 1;

  var st = { reg:-1, fil:-1, cur:-1, q:'', limit:150 };
  var novaBase = null;

  /* ---- base salva no navegador -------------------------------------------
     A base embutida no arquivo publicado nao muda sozinha. Quando o usuario
     sobe uma planilha nova, guardamos o resultado aqui para que ele continue
     valendo depois de fechar a aba. Se o arquivo publicado for atualizado
     (data diferente da que estava no momento do save), a copia local e
     descartada, porque o publicado passa a ser a versao boa. */
  var EMB_DATA = D.atualizado || '';
  var EMB_ORIGEM = D.origem || '—';
  var LSK = 'painel-hg:base';
  var localInfo = null;

  function lerLocal(){
    try {
      var raw = localStorage.getItem(LSK);
      if (!raw) return null;
      var o = JSON.parse(raw);
      if (!o || !o.dados || !o.dados.fatos || !o.dados.fatos.length) return null;
      if (o.baseEmbutida !== EMB_DATA){ localStorage.removeItem(LSK); return null; }
      return o;
    } catch(e){ return null; }
  }
  function salvarLocal(d){
    try {
      localStorage.setItem(LSK, JSON.stringify({
        salvoEm: new Date().toISOString(), baseEmbutida: EMB_DATA, dados: d
      }));
      localInfo = lerLocal();
      return !!localInfo;
    } catch(e){ return false; }
  }
  function marcarPublicado(){
    try {
      var raw = localStorage.getItem(LSK);
      if (!raw) return;
      var o = JSON.parse(raw);
      o.publicado = true;
      localStorage.setItem(LSK, JSON.stringify(o));
      localInfo = lerLocal();
    } catch(e){}
  }
  function apagarLocal(){
    try { localStorage.removeItem(LSK); } catch(e){}
    localInfo = null;
  }

  function pct(a,b){ return b ? (100*a/b) : 0; }
  function fmt(n){ return n.toLocaleString('pt-BR'); }
  function fp(v){ return v.toFixed(1).replace('.',',') + '%'; }
  function esc(s){ return String(s).replace(/[&<>"]/g, function(c){
    return {'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]; }); }
  function norm(s){
    s = String(s == null ? '' : s).normalize('NFD').replace(/[\u0300-\u036f]/g,'').toUpperCase();
    s = s.replace('REDE HG POSTO',' ').replace('REDE HG',' ');
    return s.replace(/[^A-Z0-9]+/g,' ').trim();
  }
  function rank(c){
    var k = norm(c), i = ORDEM.indexOf(k);
    if (i >= 0) return i;
    for (var j=0;j<ORDEM.length;j++){ if (k.indexOf(ORDEM[j]) === 0) return j; }
    return 900;
  }

  function filtra(){
    var out = [];
    for (var i=0;i<F.length;i++){
      var f = F[i];
      if (st.reg >= 0 && FIL[f[1]].r !== st.reg) continue;
      if (st.fil >= 0 && f[1] !== st.fil) continue;
      if (st.cur >= 0 && f[2] !== st.cur) continue;
      out.push(f);
    }
    return out;
  }

  var segReg = document.getElementById('segReg');
  function drawSeg(){
    var html = '<button type="button" data-r="-1">Rede inteira</button>';
    for (var i=0;i<REG.length;i++){
      html += '<button type="button" data-r="'+i+'">'+esc(REG[i].replace(' - ',' · '))+'</button>';
    }
    segReg.innerHTML = html;
    Array.prototype.forEach.call(segReg.children, function(b){
      b.setAttribute('aria-pressed', String(+b.dataset.r === st.reg));
      b.onclick = function(){ st.reg = +b.dataset.r; st.fil = -1; st.limit = 150; render(); };
    });
  }
  var selFil = document.getElementById('selFil'), selCur = document.getElementById('selCur');
  function drawSelects(){
    var opts = '<option value="-1">Todas as filiais</option>';
    FIL.forEach(function(f,i){
      if (st.reg >= 0 && f.r !== st.reg) return;
      opts += '<option value="'+i+'"'+(st.fil===i?' selected':'')+'>'+esc(f.n)+'</option>';
    });
    selFil.innerHTML = opts;
    var oc = '<option value="-1">Todos os cursos</option>';
    CUR.forEach(function(c,i){ oc += '<option value="'+i+'"'+(st.cur===i?' selected':'')+'>'+(i+1)+'. '+esc(c)+'</option>'; });
    selCur.innerHTML = oc;
  }
  selFil.onchange = function(){ st.fil = +this.value; st.limit=150; render(); };
  selCur.onchange = function(){ st.cur = +this.value; st.limit=150; render(); };
  function normTxt(s){
    s = (s == null ? '' : String(s)).toUpperCase();
    try { s = s.normalize('NFD').replace(new RegExp('[\\u0300-\\u036f]', 'g'), ''); } catch(e){}
    return s;
  }
  document.getElementById('busca').oninput = function(){ st.q = normTxt(this.value.trim()); st.limit=150; renderPend(); };

  var panes = {vg:'p-vg', mx:'p-mx', pd:'p-pd', up:'p-up'};
  function abrir(p){
    Array.prototype.forEach.call(document.querySelectorAll('.tabs button'), function(x){
      x.setAttribute('aria-selected', String(x.dataset.p === p));
      document.getElementById(panes[x.dataset.p]).hidden = (x.dataset.p !== p);
    });
  }
  Array.prototype.forEach.call(document.querySelectorAll('.tabs button'), function(b){
    b.onclick = function(){ abrir(b.dataset.p); };
  });

  document.getElementById('btnReset').onclick = function(){
    st.reg = -1; st.fil = -1; st.cur = -1; st.q = ''; st.limit = 150;
    document.getElementById('busca').value = ''; render();
  };

  function barras(el, itens){
    if (!itens.length){ el.innerHTML = '<p class="empty">Sem dados para este filtro.</p>'; return; }
    var html = '';
    itens.forEach(function(it){
      var p = pct(it.ok, it.tot);
      html += '<div class="row'+(it.ok===0?' zero':'')+'" title="'+esc(it.nome)+': '+fmt(it.ok)+' de '+fmt(it.tot)+' concluídos">'
        + '<div class="barwrap">'
        +   '<div class="rname"><span>'+(it.ord?'<span class="ord">'+it.ord+'</span>':'')+esc(it.nome)+'</span><em>'+fmt(it.ok)+'/'+fmt(it.tot)+'</em></div>'
        +   '<div class="track"><i style="width:'+Math.max(p,0).toFixed(2)+'%"></i></div>'
        + '</div>'
        + '<div class="rpct">'+p.toFixed(0)+'%</div>'
        + '</div>';
    });
    el.innerHTML = html;
  }

  var RAMP = ['--s100','--s200','--s300','--s450','--s550','--s650'];
  function cellStyle(p){
    if (p === null) return 'background:var(--surface-2);color:var(--muted)';
    var i = p < 5 ? 0 : p < 15 ? 1 : p < 30 ? 2 : p < 55 ? 3 : p < 80 ? 4 : 5;
    if (p <= 0) return 'background:var(--surface-3);color:var(--muted)';
    return 'background:var('+RAMP[i]+');color:'+(i >= 3 ? '#fff' : 'var(--ink)');
  }

  function render(){
    drawSeg(); drawSelects();
    document.getElementById('btnReset').hidden = (st.reg < 0 && st.fil < 0 && st.cur < 0);
    var dados = filtra();

    var tot = dados.length, ok = 0, pset = {}, pend = {};
    for (var i=0;i<dados.length;i++){
      var d = dados[i]; pset[d[0]] = 1;
      if (d[3]) ok++; else pend[d[0]] = 1;
    }
    var nPart = Object.keys(pset).length, nPend = Object.keys(pend).length;
    var nEmDia = nPart - nPend, nFil = {};
    dados.forEach(function(d){ nFil[d[1]] = 1; });
    var qf = Object.keys(nFil).length;

    var escopo = st.reg < 0 ? 'Rede inteira' : REG[st.reg];
    if (st.fil >= 0) escopo += ' › ' + FIL[st.fil].n;
    if (st.cur >= 0) escopo += ' › ' + CUR[st.cur];
    document.getElementById('meta').innerHTML =
      'Escopo: ' + esc(escopo.replace(' - ',' · ')) + '<br>'
      + fmt(qf) + (qf===1?' filial':' filiais') + ' &middot; ' + fmt(nPart)
      + (nPart===1?' colaborador':' colaboradores') + ' &middot; ' + fmt(tot) + ' matrículas';

    var p = pct(ok,tot);
    document.getElementById('kpis').innerHTML =
      card('Andamento do escopo', fp(p), fmt(ok)+' de '+fmt(tot)+' matrículas concluídas', p) +
      card('Colaboradores', fmt(nPart), qf + (qf===1?' filial no escopo':' filiais no escopo'), null) +
      card('Treinamentos pendentes', fmt(tot-ok), 'somando todos os cursos exigidos', null) +
      card('Colaboradores 100% em dia', fmt(nEmDia), fp(pct(nEmDia,nPart))+' do efetivo do escopo', pct(nEmDia,nPart));

    var accF = {};
    dados.forEach(function(d){ var a = accF[d[1]] || (accF[d[1]]={ok:0,tot:0}); a.tot++; if(d[3]) a.ok++; });
    barras(document.getElementById('barFil'),
      Object.keys(accF).map(function(k){ return {nome:FIL[k].n, ok:accF[k].ok, tot:accF[k].tot}; })
        .sort(function(a,b){ return pct(a.ok,a.tot) - pct(b.ok,b.tot) || b.tot - a.tot; }));

    var accC = {};
    dados.forEach(function(d){ var a = accC[d[2]] || (accC[d[2]]={ok:0,tot:0}); a.tot++; if(d[3]) a.ok++; });
    barras(document.getElementById('barCur'),
      Object.keys(accC).map(Number).sort(function(a,b){ return a - b; })
        .map(function(k){ return {nome:CUR[k], ord:(k+1)+'.', ok:accC[k].ok, tot:accC[k].tot}; }));

    var accR = {};
    F.forEach(function(d){
      if (st.cur >= 0 && d[2] !== st.cur) return;
      var r = FIL[d[1]].r, a = accR[r] || (accR[r]={ok:0,tot:0}); a.tot++; if(d[3]) a.ok++;
    });
    barras(document.getElementById('barReg'),
      Object.keys(accR).map(function(k){ return {nome:REG[k].replace(' - ',' · '), ok:accR[k].ok, tot:accR[k].tot}; })
        .sort(function(a,b){ return pct(b.ok,b.tot) - pct(a.ok,a.tot); }));

    renderMatriz(dados);
    renderPend();
    document.getElementById('foot').innerHTML =
      'Base: ' + esc(D.origem || 'exportação da plataforma') + ' &middot; atualizada em ' + esc(D.atualizado || '—')
      + ' &middot; ' + fmt(F.length) + ' matrículas, ' + fmt(PART.length) + ' colaboradores ativos, '
      + fmt(FIL.length) + ' filiais, ' + CUR.length + ' cursos. '
      + 'Concluído = "Aprovado" na exportação; pendente = "Não aprovado".';
  }

  function card(label, val, foot, meter){
    return '<div class="card kpi"><div class="klabel">'+esc(label)+'</div>'
      + '<div class="kval">'+val+'</div>'
      + '<div class="kfoot">'+esc(foot)+'</div>'
      + (meter===null?'':'<div class="meter"><span style="width:'+Math.min(meter,100).toFixed(2)+'%"></span></div>')
      + '</div>';
  }

  function renderMatriz(dados){
    var cursosVis = st.cur >= 0 ? [st.cur] : CUR.map(function(_,i){ return i; });
    var m = {}, filSet = {};
    dados.forEach(function(d){
      filSet[d[1]] = 1;
      var k = d[1]+'|'+d[2], a = m[k] || (m[k]={ok:0,tot:0});
      a.tot++; if (d[3]) a.ok++;
    });
    var totFil = {};
    Object.keys(filSet).map(Number).forEach(function(f){
      var o=0,t=0;
      cursosVis.forEach(function(c){ var a=m[f+'|'+c]; if(a){ o+=a.ok; t+=a.tot; } });
      totFil[f] = t ? o/t : -1;
    });
    var fils = Object.keys(filSet).map(Number).sort(function(a,b){
      if (st.reg < 0 && FIL[a].r !== FIL[b].r) return FIL[a].r - FIL[b].r;
      return totFil[b] - totFil[a] || FIL[a].n.localeCompare(FIL[b].n,'pt-BR');
    });
    var h = '<thead><tr><th>Filial</th>';
    cursosVis.forEach(function(c){ h += '<th scope="col"><span class="ord">'+(c+1)+'</span>'+esc(CUR[c])+'</th>'; });
    h += '<th scope="col">Total filial</th></tr></thead><tbody>';
    var ncols = cursosVis.length + 2, ultima = -9;
    fils.forEach(function(f){
      if (st.reg < 0 && FIL[f].r !== ultima){
        ultima = FIL[f].r;
        h += '<tr class="grouprow"><th scope="row" colspan="'+ncols+'">'+esc(REG[ultima].replace(' - ',' · '))+'</th></tr>';
      }
      h += '<tr class="filrow" data-f="'+f+'" tabindex="0" title="Ver os nomes pendentes de '+esc(FIL[f].n)+'"><th scope="row">'+esc(FIL[f].n)+'</th>';
      var to=0, tt=0;
      cursosVis.forEach(function(c){
        var a = m[f+'|'+c];
        if (!a){ h += '<td style="'+cellStyle(null)+'">–</td>'; return; }
        to += a.ok; tt += a.tot;
        var p = pct(a.ok,a.tot);
        h += '<td style="'+cellStyle(p)+'" title="'+esc(FIL[f].n+' · '+CUR[c])+': '+a.ok+'/'+a.tot+'">'+p.toFixed(0)+'%</td>';
      });
      h += '<td style="'+cellStyle(pct(to,tt))+'" title="'+to+'/'+tt+'">'+pct(to,tt).toFixed(0)+'%</td></tr>';
    });
    h += '<tr class="totrow"><th scope="row">Total do escopo</th>';
    var gto=0, gtt=0;
    cursosVis.forEach(function(c){
      var o=0,t=0;
      fils.forEach(function(f){ var a=m[f+'|'+c]; if(a){o+=a.ok;t+=a.tot;} });
      gto+=o; gtt+=t;
      h += '<td style="'+cellStyle(t?pct(o,t):null)+'">'+(t?pct(o,t).toFixed(0)+'%':'–')+'</td>';
    });
    h += '<td style="'+cellStyle(pct(gto,gtt))+'">'+pct(gto,gtt).toFixed(0)+'%</td></tr></tbody>';
    document.getElementById('mx').innerHTML = h;

    Array.prototype.forEach.call(document.querySelectorAll('tr.filrow'), function(tr){
      var ir = function(){ st.fil = +tr.dataset.f; st.limit = 150; render(); abrir('pd'); };
      tr.onclick = ir;
      tr.onkeydown = function(e){ if (e.key === 'Enter' || e.key === ' '){ e.preventDefault(); ir(); } };
    });

    var chips = '';
    ['--surface-3','--s200','--s300','--s450','--s550','--s650'].forEach(function(v){
      chips += '<b style="background:var('+v+')"></b>';
    });
    document.getElementById('legChips').innerHTML = chips;
  }

  var pendCache = [];
  function renderPend(){
    var dados = filtra(), byP = {};
    dados.forEach(function(d){
      if (d[3]) return;
      var a = byP[d[0]] || (byP[d[0]]={fil:d[1], cur:[]});
      a.cur.push(d[2]);
    });
    var lista = Object.keys(byP).map(function(k){ return {nome:PART[k], fil:byP[k].fil, cur:byP[k].cur}; })
      .filter(function(x){ return !st.q || normTxt(FIL[x.fil].n).indexOf(st.q) >= 0; })
      .sort(function(a,b){ return b.cur.length - a.cur.length || a.nome.localeCompare(b.nome,'pt-BR'); });
    pendCache = lista;

    document.getElementById('cnt').textContent = fmt(lista.length) + (lista.length===1?' colaborador':' colaboradores');
    var tb = document.getElementById('tbody');
    if (!lista.length){
      tb.innerHTML = '<tr><td colspan="5" class="empty">Ninguém pendente com este filtro.</td></tr>';
      document.getElementById('more').hidden = true; return;
    }
    var h = '';
    lista.slice(0, st.limit).forEach(function(x){
      var pills = x.cur.slice().sort(function(a,b){ return a-b; }).map(function(c){
        return '<span class="pill">'+(c+1)+'. '+esc(CUR[c])+'</span>';
      }).join('');
      h += '<tr><td class="nm">'+esc(x.nome)+'</td>'
        + '<td>'+esc(FIL[x.fil].n)+'</td>'
        + '<td>'+esc(REG[FIL[x.fil].r].replace(' - ',' · '))+'</td>'
        + '<td class="mono" style="text-align:center">'+x.cur.length+'</td>'
        + '<td>'+pills+'</td></tr>';
    });
    tb.innerHTML = h;
    var more = document.getElementById('more');
    if (lista.length > st.limit){
      more.hidden = false;
      more.innerHTML = 'Mostrando '+fmt(st.limit)+' de '+fmt(lista.length)
        + '. <button class="btn" type="button" id="btnMore" style="margin-left:8px">Mostrar mais 150</button>';
      document.getElementById('btnMore').onclick = function(){ st.limit += 150; renderPend(); };
    } else { more.hidden = true; }
  }

  document.getElementById('btnCopy').onclick = function(){
    var b = this;
    if (!pendCache.length){
      b.textContent = 'Nada para baixar';
      setTimeout(function(){ b.textContent = 'Baixar lista filtrada'; }, 1800);
      return;
    }
    function cel(v){ return '"' + String(v == null ? '' : v).replace(/"/g, '""') + '"'; }
    var linhas = [['Colaborador','Empresa (filial)','Regional','Pendentes','Cursos pendentes'].map(cel).join(';')];
    pendCache.forEach(function(x){
      linhas.push([
        x.nome,
        FIL[x.fil].n,
        REG[FIL[x.fil].r],
        x.cur.length,
        x.cur.slice().sort(function(a,b){ return a-b; }).map(function(c){ return (c+1)+'. '+CUR[c]; }).join('; ')
      ].map(cel).join(';'));
    });

    function slug(s){ return normTxt(s).replace(/[^A-Z0-9]+/g,'-').replace(/^-+|-+$/g,'').toLowerCase(); }
    var partes = ['pendentes'];
    if (st.fil >= 0) partes.push(slug(FIL[st.fil].n));
    else if (st.q) partes.push(slug(st.q));
    else if (st.reg >= 0) partes.push(slug(REG[st.reg]));
    if (st.cur >= 0) partes.push(slug(CUR[st.cur]));
    var d = new Date(), p2 = function(n){ return (n<10?'0':'')+n; };
    partes.push(d.getFullYear() + p2(d.getMonth()+1) + p2(d.getDate()));

    var csv = '\uFEFF' + linhas.join('\r\n');
    try {
      var blob = new Blob([csv], {type:'text/csv;charset=utf-8;'});
      var url = URL.createObjectURL(blob);
      var a = document.createElement('a');
      a.href = url; a.download = partes.join('_') + '.csv';
      document.body.appendChild(a); a.click(); document.body.removeChild(a);
      setTimeout(function(){ URL.revokeObjectURL(url); }, 4000);
      b.textContent = 'Lista baixada';
    } catch(e){
      b.textContent = 'Não foi possível baixar';
    }
    setTimeout(function(){ b.textContent = 'Baixar lista filtrada'; }, 1800);
  };

  /* ================= atualização da base ================= */

  /* --- senhas: visualização (equipe) e administração (SESMT) --- */
  function sha256hex(str){
    var K = [
      0x428a2f98,0x71374491,0xb5c0fbcf,0xe9b5dba5,0x3956c25b,0x59f111f1,0x923f82a4,0xab1c5ed5,
      0xd807aa98,0x12835b01,0x243185be,0x550c7dc3,0x72be5d74,0x80deb1fe,0x9bdc06a7,0xc19bf174,
      0xe49b69c1,0xefbe4786,0x0fc19dc6,0x240ca1cc,0x2de92c6f,0x4a7484aa,0x5cb0a9dc,0x76f988da,
      0x983e5152,0xa831c66d,0xb00327c8,0xbf597fc7,0xc6e00bf3,0xd5a79147,0x06ca6351,0x14292967,
      0x27b70a85,0x2e1b2138,0x4d2c6dfc,0x53380d13,0x650a7354,0x766a0abb,0x81c2c92e,0x92722c85,
      0xa2bfe8a1,0xa81a664b,0xc24b8b70,0xc76c51a3,0xd192e819,0xd6990624,0xf40e3585,0x106aa070,
      0x19a4c116,0x1e376c08,0x2748774c,0x34b0bcb5,0x391c0cb3,0x4ed8aa4a,0x5b9cca4f,0x682e6ff3,
      0x748f82ee,0x78a5636f,0x84c87814,0x8cc70208,0x90befffa,0xa4506ceb,0xbef9a3f7,0xc67178f2];
    var H = [0x6a09e667,0xbb67ae85,0x3c6ef372,0xa54ff53a,0x510e527f,0x9b05688c,0x1f83d9ab,0x5be0cd19];
    // UTF-8
    var b = [], i, c;
    for (i = 0; i < str.length; i++){
      c = str.charCodeAt(i);
      if (c < 0x80) b.push(c);
      else if (c < 0x800){ b.push(0xc0 | (c >> 6), 0x80 | (c & 63)); }
      else if (c < 0xd800 || c >= 0xe000){ b.push(0xe0 | (c >> 12), 0x80 | ((c >> 6) & 63), 0x80 | (c & 63)); }
      else {
        i++;
        c = 0x10000 + (((c & 0x3ff) << 10) | (str.charCodeAt(i) & 0x3ff));
        b.push(0xf0 | (c >> 18), 0x80 | ((c >> 12) & 63), 0x80 | ((c >> 6) & 63), 0x80 | (c & 63));
      }
    }
    var bits = b.length * 8;
    b.push(0x80);
    while (b.length % 64 !== 56) b.push(0);
    var hi = Math.floor(bits / 0x100000000), lo = bits >>> 0;
    b.push((hi>>>24)&255,(hi>>>16)&255,(hi>>>8)&255,hi&255,(lo>>>24)&255,(lo>>>16)&255,(lo>>>8)&255,lo&255);

    function rr(x,n){ return (x >>> n) | (x << (32 - n)); }
    var w = new Array(64), a,bb,cc,d,e,f,g,h,t1,t2,j,o;
    for (o = 0; o < b.length; o += 64){
      for (j = 0; j < 16; j++)
        w[j] = (b[o+j*4]<<24) | (b[o+j*4+1]<<16) | (b[o+j*4+2]<<8) | b[o+j*4+3];
      for (j = 16; j < 64; j++){
        var s0 = rr(w[j-15],7) ^ rr(w[j-15],18) ^ (w[j-15] >>> 3);
        var s1 = rr(w[j-2],17) ^ rr(w[j-2],19) ^ (w[j-2] >>> 10);
        w[j] = (w[j-16] + s0 + w[j-7] + s1) | 0;
      }
      a=H[0];bb=H[1];cc=H[2];d=H[3];e=H[4];f=H[5];g=H[6];h=H[7];
      for (j = 0; j < 64; j++){
        var S1 = rr(e,6) ^ rr(e,11) ^ rr(e,25);
        var ch = (e & f) ^ (~e & g);
        t1 = (h + S1 + ch + K[j] + w[j]) | 0;
        var S0 = rr(a,2) ^ rr(a,13) ^ rr(a,22);
        var maj = (a & bb) ^ (a & cc) ^ (bb & cc);
        t2 = (S0 + maj) | 0;
        h=g; g=f; f=e; e=(d+t1)|0; d=cc; cc=bb; bb=a; a=(t1+t2)|0;
      }
      H[0]=(H[0]+a)|0; H[1]=(H[1]+bb)|0; H[2]=(H[2]+cc)|0; H[3]=(H[3]+d)|0;
      H[4]=(H[4]+e)|0; H[5]=(H[5]+f)|0; H[6]=(H[6]+g)|0; H[7]=(H[7]+h)|0;
    }
    var out = '';
    for (i = 0; i < 8; i++) out += ('00000000' + (H[i] >>> 0).toString(16)).slice(-8);
    return out;
  }

  /* O painel abre direto: nao ha mais senha de visualizacao.
     A senha abaixo continua valendo para a aba Atualizar base. */
  var HASH_ADM = 'effb4669e397505631f73caa1d8733c617fa1b42666b233ceda895690d3f4fc7';

  var lock = document.getElementById('lock'), areaUpload = document.getElementById('areaUpload');
  var erroSenha = document.getElementById('erroSenha');

  function destravar(){
    lock.hidden = true; areaUpload.hidden = false;
    try { sessionStorage.setItem('hg_admin','1'); } catch(e){}
  }

  document.getElementById('formSenha').onsubmit = function(ev){
    ev.preventDefault();
    var campo = document.getElementById('senha');
    if (sha256hex(campo.value.trim()) === HASH_ADM){ erroSenha.textContent = ''; campo.value = ''; destravar(); }
    else { erroSenha.textContent = 'Senha incorreta.'; campo.select(); }
  };

  try {
    if (sessionStorage.getItem('hg_admin') === '1') destravar();
  } catch(e){}

  var upStatus = document.getElementById('upStatus');
  function status(linhas){
    upStatus.innerHTML = linhas.map(function(l){
      return '<div class="linha"><span class="marca '+(l[0]||'')+'">'
        + (l[0]==='ok'?'✓':l[0]==='er'?'✕':l[0]==='av'?'!':'·')+'</span><div>'+l[1]+'</div></div>';
    }).join('');
  }

  var drop = document.getElementById('drop'), inp = document.getElementById('arquivo');
  ['dragenter','dragover'].forEach(function(e){
    drop.addEventListener(e, function(ev){ ev.preventDefault(); drop.classList.add('over'); });
  });
  ['dragleave','drop'].forEach(function(e){
    drop.addEventListener(e, function(ev){ ev.preventDefault(); drop.classList.remove('over'); });
  });
  drop.addEventListener('drop', function(ev){
    if (ev.dataTransfer.files && ev.dataTransfer.files[0]) processar(ev.dataTransfer.files[0]);
  });
  inp.onchange = function(){ if (this.files[0]) processar(this.files[0]); };

  /* --- leitor de xlsx (zip + xml, sem biblioteca externa) --- */
  async function lerXlsx(buf){
    var u8 = new Uint8Array(buf), dv = new DataView(buf), eocd = -1;
    for (var i = u8.length - 22; i >= 0 && i > u8.length - 66000; i--){
      if (dv.getUint32(i, true) === 0x06054b50){ eocd = i; break; }
    }
    if (eocd < 0) throw new Error('Não parece um arquivo .xlsx válido.');
    var nEnt = dv.getUint16(eocd + 10, true), p = dv.getUint32(eocd + 16, true), files = {};
    var td = new TextDecoder();
    for (var e = 0; e < nEnt; e++){
      if (dv.getUint32(p, true) !== 0x02014b50) break;
      var method = dv.getUint16(p + 10, true), csize = dv.getUint32(p + 20, true);
      var nlen = dv.getUint16(p + 28, true), elen = dv.getUint16(p + 30, true), clen = dv.getUint16(p + 32, true);
      var lho = dv.getUint32(p + 42, true);
      files[td.decode(u8.subarray(p + 46, p + 46 + nlen))] = {m:method, c:csize, o:lho};
      p += 46 + nlen + elen + clen;
    }
    async function ler(f){
      var nl = dv.getUint16(f.o + 26, true), el = dv.getUint16(f.o + 28, true);
      var data = u8.subarray(f.o + 30 + nl + el, f.o + 30 + nl + el + f.c);
      if (f.m === 0) return td.decode(data);
      if (typeof DecompressionStream === 'undefined')
        throw new Error('Este navegador não consegue abrir .xlsx aqui. Salve a planilha como .csv e tente de novo.');
      var s = new Blob([data]).stream().pipeThrough(new DecompressionStream('deflate-raw'));
      return await new Response(s).text();
    }
    var shared = [];
    if (files['xl/sharedStrings.xml']){
      var sd = new DOMParser().parseFromString(await ler(files['xl/sharedStrings.xml']), 'application/xml');
      var sis = sd.getElementsByTagName('si');
      for (var k=0;k<sis.length;k++){
        var ts = sis[k].getElementsByTagName('t'), s2 = '';
        for (var q=0;q<ts.length;q++) s2 += ts[q].textContent;
        shared.push(s2);
      }
    }
    var melhor = null;
    for (var nome in files){
      if (!/^xl\/worksheets\/sheet\d+\.xml$/.test(nome)) continue;
      var linhas = parseSheet(await ler(files[nome]), shared);
      if (!melhor || linhas.length > melhor.length) melhor = linhas;
    }
    if (!melhor) throw new Error('Nenhuma aba de dados encontrada na planilha.');
    return melhor;
  }

  function parseSheet(xml, shared){
    var doc = new DOMParser().parseFromString(xml, 'application/xml');
    var rows = doc.getElementsByTagName('row'), out = [];
    for (var i=0;i<rows.length;i++){
      var cs = rows[i].getElementsByTagName('c'), r = [];
      for (var j=0;j<cs.length;j++){
        var c = cs[j], m = /^([A-Z]+)/.exec(c.getAttribute('r') || ''), col = j;
        if (m){ col = 0; for (var k=0;k<m[1].length;k++) col = col*26 + (m[1].charCodeAt(k) - 64); col--; }
        var t = c.getAttribute('t'), v = '';
        if (t === 'inlineStr'){ var is = c.getElementsByTagName('t'); v = is.length ? is[0].textContent : ''; }
        else {
          var vn = c.getElementsByTagName('v')[0];
          v = vn ? vn.textContent : '';
          if (t === 's') v = shared[+v] || '';
        }
        r[col] = v;
      }
      out.push(r);
    }
    return out;
  }

  function lerCsv(txt){
    txt = txt.replace(/^﻿/,'');
    var prim = (txt.split(/\r?\n/)[0] || '');
    var sep = (prim.split(';').length > prim.split(',').length) ? ';' : ',';
    var out = [], linha = [], campo = '', aspas = false;
    for (var i=0;i<txt.length;i++){
      var ch = txt[i];
      if (aspas){
        if (ch === '"'){ if (txt[i+1] === '"'){ campo += '"'; i++; } else aspas = false; }
        else campo += ch;
      } else if (ch === '"') aspas = true;
      else if (ch === sep){ linha.push(campo); campo = ''; }
      else if (ch === '\n'){ linha.push(campo); out.push(linha); linha = []; campo = ''; }
      else if (ch !== '\r') campo += ch;
    }
    if (campo !== '' || linha.length){ linha.push(campo); out.push(linha); }
    return out;
  }

  var MAPA = {
    part:  ['PARTICIPANTE','NOME','COLABORADOR','FUNCIONARIO','NOME DO PARTICIPANTE','NOME COMPLETO'],
    emp:   ['EMPRESA','FILIAL','POSTO','UNIDADE','EMPRESA POSTO','LOJA'],
    curso: ['CURSO','TREINAMENTO','NOME DO CURSO'],
    aprov: ['APROVACAO','APROVACAO NO CURSO','RESULTADO','STATUS','STATUS DO CURSO','SITUACAO DO CURSO','SITUACAO CURSO','CONCLUSAO'],
    sit:   ['SITUACAO NO AMBIENTE','SITUACAO','SITUACAO DO COLABORADOR','SITUACAO COLABORADOR','STATUS COLABORADOR'],
    reg:   ['REGIONAL','REGIAO','GERENCIA REGIONAL']
  };
  function acharColunas(cab){
    var idx = {};
    cab.forEach(function(h, i){
      var n = norm(h);
      if (!n) return;
      for (var chave in MAPA){
        if (idx[chave] !== undefined) continue;
        if (MAPA[chave].indexOf(n) >= 0) idx[chave] = i;
      }
    });
    return idx;
  }

  function construir(linhas){
    var cabIdx = -1, idx = null;
    for (var i=0;i<Math.min(linhas.length, 20);i++){
      var t = acharColunas(linhas[i] || []);
      if (t.part !== undefined && t.curso !== undefined && t.aprov !== undefined){ cabIdx = i; idx = t; break; }
    }
    if (cabIdx < 0)
      throw new Error('Não encontrei as colunas PARTICIPANTE, CURSO e APROVAÇÃO no cabeçalho da planilha.');

    var registros = [], ignoradosInativos = 0, semNome = 0, novasEmpresas = {};
    for (var r = cabIdx + 1; r < linhas.length; r++){
      var L = linhas[r] || [];
      var nome = String(L[idx.part] == null ? '' : L[idx.part]).trim();
      var curso = String(L[idx.curso] == null ? '' : L[idx.curso]).trim();
      if (!nome || !curso){ if (L.join('').trim()) semNome++; continue; }
      if (idx.sit !== undefined){
        var sn = norm(L[idx.sit]);
        if (sn && sn.indexOf('ATIVO') !== 0){ ignoradosInativos++; continue; }
      }
      var emp = idx.emp !== undefined ? String(L[idx.emp] == null ? '' : L[idx.emp]).trim() : 'NÃO INFORMADO';
      var ke = norm(emp), dp = DEPARA[ke], ri, fn;
      if (dp){ ri = dp[0]; fn = dp[1]; }
      else if (idx.reg !== undefined && norm(L[idx.reg])){
        var rn = norm(L[idx.reg]); ri = CORP;
        for (var z=0;z<REG.length;z++){ if (norm(REG[z]).indexOf(rn) === 0 || rn.indexOf(norm(REG[z])) === 0){ ri = z; break; } }
        fn = emp.replace(/^REDE HG\s*/i,'').replace(/^POSTO\s*/i,'').trim() || emp;
        novasEmpresas[emp] = 1;
      } else {
        ri = CORP;
        fn = emp.replace(/^REDE HG\s*/i,'').replace(/^POSTO\s*/i,'').trim() || emp;
        novasEmpresas[emp] = 1;
      }
      var av = norm(L[idx.aprov]);
      var ok = (av.indexOf('APROVADO') === 0 || av.indexOf('CONCLUIDO') === 0 || av === 'SIM') ? 1 : 0;
      registros.push({p:nome, f:fn, r:ri, c:curso, ok:ok});
    }
    if (!registros.length) throw new Error('A planilha foi lida, mas nenhuma linha de matrícula válida foi encontrada.');

    var filR = {}, cursosSet = {}, partsSet = {};
    registros.forEach(function(x){ filR[x.f] = x.r; cursosSet[x.c] = 1; partsSet[x.p] = 1; });
    var cursos = Object.keys(cursosSet).sort(function(a,b){ return rank(a) - rank(b) || norm(a).localeCompare(norm(b)); });
    var fils = Object.keys(filR).sort(function(a,b){ return filR[a] - filR[b] || a.localeCompare(b,'pt-BR'); });
    var parts = Object.keys(partsSet).sort(function(a,b){ return a.localeCompare(b,'pt-BR'); });
    var pi = {}, fi = {}, ci = {};
    parts.forEach(function(v,i){ pi[v]=i; }); fils.forEach(function(v,i){ fi[v]=i; }); cursos.forEach(function(v,i){ ci[v]=i; });

    var novoDepara = {};
    for (var k in DEPARA) novoDepara[k] = DEPARA[k];
    fils.forEach(function(f){ if (!novoDepara[norm(f)]) novoDepara[norm(f)] = [filR[f], f]; });

    var hoje = new Date();
    var iso = hoje.getFullYear() + '-' + ('0'+(hoje.getMonth()+1)).slice(-2) + '-' + ('0'+hoje.getDate()).slice(-2);
    return {
      dados: {
        regionais: REG,
        filiais: fils.map(function(f){ return {n:f, r:filR[f]}; }),
        cursos: cursos,
        participantes: parts,
        fatos: registros.map(function(x){ return [pi[x.p], fi[x.f], ci[x.c], x.ok]; }),
        depara: novoDepara,
        ordem: ORDEM,
        origem: novaBase && novaBase.arquivo ? novaBase.arquivo : (D.origem || 'exportação da plataforma'),
        atualizado: iso
      },
      avisos: {inativos:ignoradosInativos, vazias:semNome, novas:Object.keys(novasEmpresas)}
    };
  }

  async function processar(file){
    status([['', 'Lendo <strong>'+esc(file.name)+'</strong>…']]);
    try {
      var linhas;
      if (/\.(csv|txt)$/i.test(file.name)) linhas = lerCsv(await file.text());
      else linhas = await lerXlsx(await file.arrayBuffer());

      novaBase = {arquivo: file.name};
      var res = construir(linhas);
      novaBase.dados = res.dados;

      var d = res.dados, tot = d.fatos.length, ok = 0;
      d.fatos.forEach(function(f){ if (f[3]) ok++; });
      var msgs = [
        ['ok', '<strong>'+fmt(tot)+'</strong> matrículas lidas de <strong>'+esc(file.name)+'</strong>'],
        ['ok', fmt(d.participantes.length)+' colaboradores · '+fmt(d.filiais.length)+' filiais · '+d.cursos.length+' cursos'],
        ['ok', 'Andamento da base nova: <strong>'+fp(pct(ok,tot))+'</strong> ('+fmt(ok)+' concluídas)']
      ];
      if (res.avisos.inativos) msgs.push(['av', fmt(res.avisos.inativos)+' linha(s) de colaborador não ativo foram ignoradas']);
      if (res.avisos.vazias)   msgs.push(['av', fmt(res.avisos.vazias)+' linha(s) sem participante ou curso foram ignoradas']);
      if (res.avisos.novas.length)
        msgs.push(['av', res.avisos.novas.length+' empresa(s) fora do de-para foram para "Corporativo / sem regional": '
          + esc(res.avisos.novas.slice(0,8).join(', ')) + (res.avisos.novas.length > 8 ? '…' : '')]);
      msgs.push(['', '<button class="btn primary" type="button" id="btnAplicar">Usar e salvar neste navegador</button> '
        + '<button class="btn" type="button" id="btnGh" style="margin-left:6px">Salvar para a equipe</button> '
        + '<button class="btn" type="button" id="btnPublicar" style="margin-left:6px">'
        + (dentroDoClaude ? 'Publicar para todos' : 'Baixar painel atualizado') + '</button>']);
      status(msgs);

      document.getElementById('btnAplicar').onclick = function(){
        var ok = aplicar(res.dados);
        if (ok === false) alert('O painel foi atualizado nesta sessao, mas o navegador nao deixou guardar a base (modo anonimo ou armazenamento cheio). Ao recarregar, os numeros antigos voltam.');
        abrir('vg');
      };
      document.getElementById('btnGh').onclick = function(){ salvarNoGitHub(this, res.dados); };

      /* Publicacao automatica: se ja existe token guardado e a opcao esta ligada,
         aplica a base e manda para o repositorio sem depender de um segundo clique. */
      if (ghAuto() && ghToken()){
        aplicar(res.dados);
        salvarNoGitHub(document.getElementById('btnGh'), res.dados, true);
      } else if (ghAuto() && !ghToken()){
        ghMsg('Para publicar sozinho, guarde primeiro o token do GitHub aqui embaixo. '
          + 'Enquanto isso, a base nova só vale se você clicar em um dos botões acima.', 'av');
      }
      document.getElementById('btnPublicar').onclick = function(){
        if (dentroDoClaude) publicar(this, res.dados); else baixarPainel(this, res.dados);
      };
    } catch(err){
      status([['er', esc(err && err.message ? err.message : 'Não consegui ler o arquivo.')]]);
    }
  }

  function aplicar(d, modo){
    REG = d.regionais; FIL = d.filiais; CUR = d.cursos; PART = d.participantes; F = d.fatos;
    DEPARA = d.depara || DEPARA; D.origem = d.origem; D.atualizado = d.atualizado;
    st = {reg:-1, fil:-1, cur:-1, q:'', limit:150};
    document.getElementById('busca').value = '';
    var salvou = null;
    if (modo !== 'local') salvou = salvarLocal(d);
    render();
    return salvou;
  }

  function limpar(app){
    ['kpis','barFil','barCur','barReg','mx','tbody','segReg','selFil','selCur',
     'legChips','meta','foot','cnt','upStatus'].forEach(function(id){
      var el = app.querySelector('#'+id); if (el) el.innerHTML = '';
    });
    var mo = app.querySelector('#more'); if (mo){ mo.innerHTML = ''; mo.setAttribute('hidden',''); }
    var bu = app.querySelector('#busca'); if (bu) bu.removeAttribute('value');
    var br = app.querySelector('#btnReset'); if (br) br.setAttribute('hidden','');
    var lk = app.querySelector('#lock'); if (lk) lk.removeAttribute('hidden');
    var au = app.querySelector('#areaUpload'); if (au) au.setAttribute('hidden','');
    var sn = app.querySelector('#senha'); if (sn) sn.removeAttribute('value');
    var er = app.querySelector('#erroSenha'); if (er) er.innerHTML = '';
    var gm = app.querySelector('#ghMsg'); if (gm) gm.innerHTML = '';
    var gt = app.querySelector('#ghToken'); if (gt) gt.removeAttribute('value');
    var gl = app.querySelector('#ghLembrar'); if (gl) gl.removeAttribute('checked');
    var ga = app.querySelector('#ghAuto'); if (ga) ga.setAttribute('checked','');
    Array.prototype.forEach.call(app.querySelectorAll('.tabs button'), function(b){
      b.setAttribute('aria-selected', String(b.dataset.p === 'vg'));
    });
    ['p-vg','p-mx','p-pd','p-up'].forEach(function(id){
      var el = app.querySelector('#'+id);
      if (!el) return;
      if (id === 'p-vg') el.removeAttribute('hidden'); else el.setAttribute('hidden','');
    });
  }

  function documento(d){
    var app = document.getElementById('app').cloneNode(true);
    limpar(app);
    var json = JSON.stringify(d).replace(/<\//g, '<\\/');
    return '<!doctype html>\n<html lang="pt-BR">\n<head>\n<meta charset="utf-8">\n'
      + '<meta name="viewport" content="width=device-width, initial-scale=1">\n'
      + '<title>Painel Treinamentos Rede HG</title>\n'
      + '<link rel="preconnect" href="https://fonts.googleapis.com">\n'
      + '<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>\n'
      + document.getElementById('fonts').outerHTML + '\n'
      + document.getElementById('css-painel').outerHTML + '\n</head>\n<body>\n'
      + app.outerHTML + '\n'
      + '<script id="dados" type="application/json">' + json + '<\/script>\n'
      + '<script id="js-painel">' + document.getElementById('js-painel').textContent + '<\/script>\n'
      + '</body>\n</html>';
  }

  /* Modo de operação: dentro do Claude publica a versão nova para todos;
     fora dele (arquivo próprio, intranet, hospedagem) gera o painel atualizado para download. */
  var nsArtifact = null;
  var dentroDoClaude = (typeof claude !== 'undefined' && claude && typeof claude.use === 'function');
  (async function(){
    try { if (dentroDoClaude) nsArtifact = await claude.use('artifact'); }
    catch(e){ nsArtifact = null; }
    nota();
  })();

  function nota(){
    var el = document.getElementById('notaAcesso');
    if (!el) return;
    var p3 = document.getElementById('passo3');
    if (p3) p3.innerHTML = dentroDoClaude
      ? 'Confira o resumo da leitura e clique em <strong>Publicar para todos</strong>.'
      : 'Com o token guardado e a publicação automática ligada, a planilha já sobe para a equipe sozinha. Sem token, escolha um dos botões do resumo.';
    el.innerHTML = dentroDoClaude
      ? '<b>Como a equipe enxerga:</b> quem recebe o link entra como leitor — vê os números, '
        + 'filtra e copia listas, mas não consegue publicar nem alterar a base, mesmo com esta senha. '
        + 'Quando você publica uma planilha nova, a tela de todo mundo que estiver com o painel aberto '
        + 'recarrega sozinha na versão atualizada.'
      : '<b>Como a equipe enxerga:</b> este painel é um arquivo único e fechado — quem abre navega, '
        + 'filtra e copia listas, mas não altera nada para os outros. Ao subir uma planilha nova você tem '
        + 'com o token do GitHub guardado e a opção <b>Publicar sozinho ao subir a planilha</b> marcada, '
        + 'basta escolher o arquivo: o painel lê, aplica e grava no repositório, e cerca de um minuto depois '
        + 'todo mundo passa a ver os números novos. Se preferir conferir antes, desmarque essa opção e use '
        + '<b>Usar e salvar neste navegador</b> (fica só para você), <b>Salvar para a equipe</b> ou '
        + '<b>Baixar painel atualizado</b>.';
  }

  function baixarPainel(btn, d){
    try {
      var blob = new Blob([documento(d)], {type:'text/html;charset=utf-8'});
      var url = URL.createObjectURL(blob);
      var a = document.createElement('a');
      a.href = url; a.download = 'painel-treinamentos-rede-hg.html';
      document.body.appendChild(a); a.click();
      setTimeout(function(){ URL.revokeObjectURL(url); a.remove(); }, 2000);
      btn.textContent = 'Painel baixado';
      setTimeout(function(){ btn.textContent = 'Baixar painel atualizado'; }, 2500);
    } catch(err){
      status([['er', 'Não consegui gerar o arquivo: ' + esc(err && err.message ? err.message : 'erro desconhecido')]]);
    }
  }

  async function publicar(btn, d){
    btn.disabled = true;
    var antes = btn.textContent;
    btn.textContent = 'Publicando…';
    try {
      var artifact = (typeof claude !== 'undefined' && claude && claude.use) ? await claude.use('artifact') : null;
      if (!artifact){
        btn.disabled = false; btn.textContent = antes;
        status([['av', 'Este painel está aberto em modo de leitura, então não dá para publicar a base nova daqui. '
          + 'Use <strong>Ver no painel</strong> para conferir os números nesta sessão.'],
          ['', '<button class="btn primary" type="button" id="btnAplicar">Ver no painel</button>']]);
        document.getElementById('btnAplicar').onclick = function(){ aplicar(d); abrir('vg'); };
        return;
      }
      await artifact.publish(documento(d));
      btn.textContent = 'Publicado';
    } catch(err){
      btn.disabled = false; btn.textContent = antes;
      var c = err && err.code;
      status([['er', c === 'conflict'
        ? 'Alguém publicou uma versão nova antes. Recarregue a página e suba a planilha de novo.'
        : 'Não consegui publicar: ' + esc(c || (err && err.message) || 'erro desconhecido')]]);
    }
  }

  /* ---- gravar a base no repositorio publicado ---------------------------- */
  var GH = {owner:'sesmt-hub', repo:'painel-treinamentos', path:'index.html', branch:'main'};
  var GHK = 'painel-hg:token';
  var GHA = 'painel-hg:auto';

  function ghAuto(){
    var c = document.getElementById('ghAuto');
    if (c) return c.checked;
    try { return localStorage.getItem(GHA) !== '0'; } catch(e){ return true; }
  }

  function ghMsg(txt, cls){
    var el = document.getElementById('ghMsg');
    if (el){ el.className = 'msg ' + (cls || ''); el.innerHTML = txt; }
  }
  function ghToken(){
    var campo = document.getElementById('ghToken');
    var v = campo && campo.value ? campo.value.trim() : '';
    if (v) return v;
    try { return localStorage.getItem(GHK) || ''; } catch(e){ return ''; }
  }
  function b64(str){
    var bytes = new TextEncoder().encode(str), bin = '', chunk = 0x8000;
    for (var i=0; i<bytes.length; i+=chunk)
      bin += String.fromCharCode.apply(null, bytes.subarray(i, i+chunk));
    return btoa(bin);
  }
  async function ghReq(url, method, body, token){
    var h = {'Authorization':'Bearer '+token, 'Accept':'application/vnd.github+json',
             'X-GitHub-Api-Version':'2022-11-28'};
    var o = {method: method || 'GET', headers: h};
    if (body){ h['Content-Type'] = 'application/json'; o.body = JSON.stringify(body); }
    var r = await fetch(url, o), t = await r.text(), j = null;
    try { j = JSON.parse(t); } catch(e){}
    if (!r.ok) throw new Error((j && j.message) ? j.message : ('HTTP ' + r.status));
    return j;
  }

  async function salvarNoGitHub(btn, d, automatico){
    var token = ghToken();
    if (!token){
      ghMsg('Cole o token do GitHub no campo abaixo e clique em Guardar token.', 'er');
      var c = document.getElementById('ghToken'); if (c) c.focus();
      return;
    }
    if (!btn) btn = {};
    btn.disabled = true;
    var antes = btn.textContent;
    btn.textContent = 'Salvando…';
    ghMsg('Enviando a base para o repositório…', '');
    try {
      var api = 'https://api.github.com/repos/'+GH.owner+'/'+GH.repo+'/contents/'+GH.path;
      var atual = await ghReq(api + '?ref=' + GH.branch, 'GET', null, token);
      await ghReq(api, 'PUT', {
        message: 'Atualiza a base do painel (' + (d.atualizado || '') + ')',
        content: b64(documento(d)),
        sha: atual.sha,
        branch: GH.branch
      }, token);
      marcarPublicado();
      btn.textContent = 'Salvo para a equipe';
      ghMsg((automatico ? 'Publicado automaticamente. ' : '')
        + 'Base gravada no repositório. O GitHub Pages leva cerca de um minuto para publicar; '
        + 'depois disso todo mundo que abrir o link vê os números novos.', 'ok');
      status([['ok', (automatico ? 'Planilha lida e publicada para a equipe' : 'Base publicada para a equipe')
        + ' — arquivo <strong>' + esc(d.origem || '—') + '</strong>, ' + fmt(d.fatos.length) + ' matrículas.'],
        ['', 'O site leva cerca de um minuto para atualizar. Até lá, esta janela já mostra os números novos.']]);
    } catch(err){
      btn.disabled = false; btn.textContent = antes;
      var m = (err && err.message) ? err.message : 'erro desconhecido';
      ghMsg('Não consegui salvar: ' + esc(m) + '. Confira se o token tem permissão de escrita neste repositório e se não expirou.'
        + (automatico ? ' A base nova continua salva neste navegador — quando resolver o token, clique em Salvar para a equipe.' : ''), 'er');
    }
  }

  var formGh = document.getElementById('formGh');
  if (formGh){
    formGh.onsubmit = function(ev){
      ev.preventDefault();
      var campo = document.getElementById('ghToken');
      var v = campo.value.trim();
      if (!v){ ghMsg('Cole o token antes de guardar.', 'er'); return; }
      if (document.getElementById('ghLembrar').checked){
        try { localStorage.setItem(GHK, v); ghMsg('Token guardado neste navegador.', 'ok'); }
        catch(e){ ghMsg('Não consegui guardar o token; ele vale só nesta sessão.', 'av'); }
      } else {
        try { localStorage.removeItem(GHK); } catch(e){}
        ghMsg('Token válido só nesta sessão.', 'ok');
      }
    };
    document.getElementById('ghEsquecer').onclick = function(){
      try { localStorage.removeItem(GHK); } catch(e){}
      var campo = document.getElementById('ghToken'); if (campo) campo.value = '';
      ghMsg('Token removido deste navegador.', '');
    };
    var chkAuto = document.getElementById('ghAuto');
    try { chkAuto.checked = (localStorage.getItem(GHA) !== '0'); } catch(e){}
    chkAuto.onchange = function(){
      try { localStorage.setItem(GHA, this.checked ? '1' : '0'); } catch(e){}
      ghMsg(this.checked
        ? 'A partir de agora, subir a planilha já publica para a equipe.'
        : 'Publicação automática desligada: você escolhe o que fazer a cada planilha.', '');
    };
    try {
      if (localStorage.getItem(GHK)){
        document.getElementById('ghLembrar').checked = true;
        ghMsg(chkAuto.checked
          ? 'Token guardado — ao subir a planilha, o painel publica sozinho para a equipe.'
          : 'Token guardado neste navegador — pode salvar direto.', '');
      }
    } catch(e){}
  }

  function statusInicial(){
    var linhas = [];
    if (localInfo){
      var dt = new Date(localInfo.salvoEm);
      var quando = dt.toLocaleDateString('pt-BR') + ' às '
        + dt.toLocaleTimeString('pt-BR', {hour:'2-digit', minute:'2-digit'});
      linhas.push(['ok', 'Em uso: base salva neste navegador em <strong>' + esc(quando)
        + '</strong> — arquivo <strong>' + esc(localInfo.dados.origem || '—') + '</strong>.']);
      if (localInfo.publicado){
        linhas.push(['', 'Essa base já foi enviada para o repositório. Se a equipe ainda vir números antigos, '
          + 'espere cerca de um minuto e recarregue a página. '
          + '<button class="btn" type="button" id="btnLimparLocal" style="margin-left:6px">Voltar para a base publicada</button>']);
      } else {
        linhas.push(['av', 'Para a equipe, a base publicada ainda é <strong>' + esc(EMB_ORIGEM)
          + '</strong> (' + esc(EMB_DATA || '—') + '). '
          + '<button class="btn" type="button" id="btnLimparLocal" style="margin-left:6px">Voltar para a base publicada</button>']);
      }
    } else {
      linhas.push(['', 'Nenhuma planilha carregada nesta sessão. A base em uso é <strong>'
        + esc(EMB_ORIGEM) + '</strong>, atualizada em <strong>' + esc(EMB_DATA || '—') + '</strong>.']);
    }
    status(linhas);
    var b = document.getElementById('btnLimparLocal');
    if (b) b.onclick = function(){ apagarLocal(); location.reload(); };
  }

  nota();
  localInfo = lerLocal();
  if (localInfo) aplicar(localInfo.dados, 'local'); else render();
  statusInicial();
})();
</script>
</body>
</html>
