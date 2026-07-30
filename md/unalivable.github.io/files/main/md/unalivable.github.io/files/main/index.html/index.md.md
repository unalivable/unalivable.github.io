# md/unalivable.github.io/files/main/index.html/index.md
File / Файл
Content / Содержание:
```
# index.html
File / Файл
Content / Содержание:
```
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>unalivable · GitHub Explorer</title>
<meta name="description" content="Browse unalivable's public GitHub repositories, filter, and explore file trees." />
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-1:#0f0c29;
    --bg-2:#24243e;
    --red:#e94560;
    --pink:#ff6b81;
    --cyan:#00d4ff;
    --text:#f3f1f9;
    --text-dim:#a6a2c4;
    --text-faint:#726e94;
    --surface:rgba(255,255,255,0.045);
    --surface-hover:rgba(255,255,255,0.08);
    --border:rgba(255,255,255,0.10);
    --border-cyan:rgba(0,212,255,0.45);
    --radius:12px;
  }
  *{ box-sizing:border-box; }
  html{ background:var(--bg-1); }
  body{
    margin:0;
    min-height:100vh;
    color:var(--text);
    font-family:"Inter", system-ui, sans-serif;
    line-height:1.55;
    -webkit-font-smoothing:antialiased;
    background:
      radial-gradient(1100px 750px at 6% -8%, rgba(233,69,96,0.22), transparent 55%),
      radial-gradient(950px 700px at 100% 2%, rgba(0,212,255,0.15), transparent 55%),
      radial-gradient(900px 850px at 45% 112%, rgba(255,107,129,0.18), transparent 55%),
      linear-gradient(160deg, var(--bg-1), var(--bg-2));
    background-attachment:fixed;
    background-size:200% 200%, 200% 200%, 200% 200%, 100% 100%;
    animation:meshDrift 28s ease-in-out infinite;
  }
  @keyframes meshDrift{
    0%,100%{ background-position:0% 0%, 100% 0%, 50% 100%, 0 0; }
    50%{ background-position:12% 14%, 88% 16%, 42% 88%, 0 0; }
  }
  ::selection{ background:var(--red); color:#fff; }
  a{ color:var(--cyan); text-decoration:none; }
  a:hover{ color:var(--pink); }
  :focus-visible{
    outline:2px solid var(--cyan);
    outline-offset:2px;
    border-radius:4px;
  }
  .wrap{
    max-width:840px;
    margin:0 auto;
    padding:0 20px 90px;
  }
  .masthead{
    text-align:center;
    padding:52px 20px 34px;
  }
  .eyebrow{
    display:inline-flex;
    align-items:center;
    gap:8px;
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    letter-spacing:0.08em;
    color:var(--text-dim);
    margin:0 0 16px;
  }
  .status-dot{
    width:7px; height:7px;
    border-radius:50%;
    background:var(--cyan);
    box-shadow:0 0 8px 1px rgba(0,212,255,0.7);
    animation:blink 2s ease-in-out infinite;
  }
  .status-dot.dot-error{
    background:var(--red);
    box-shadow:0 0 8px 1px rgba(233,69,96,0.7);
  }
  @keyframes blink{
    0%,100%{ opacity:1; }
    50%{ opacity:0.35; }
  }
  #statusIndicator.is-error{ color:var(--red); }
  h1.title{
    font-family:"Space Grotesk", sans-serif;
    font-weight:700;
    font-size:clamp(1.8rem, 5vw, 2.6rem);
    margin:0;
    letter-spacing:-0.01em;
  }
  h1.title .grad{
    background:linear-gradient(90deg, var(--cyan), var(--pink) 55%, var(--red));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
  }
  h1.title .sub{
    display:block;
    font-family:"JetBrains Mono", monospace;
    font-size:13px;
    font-weight:500;
    letter-spacing:0.06em;
    color:var(--text-faint);
    margin-top:8px;
  }
  .panel{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    backdrop-filter:blur(6px);
  }
  #profile{ margin-bottom:28px; }
  .profile-card{
    display:flex;
    gap:18px;
    align-items:flex-start;
    padding:22px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    backdrop-filter:blur(6px);
  }
  .avatar{
    border-radius:50%;
    object-fit:cover;
    flex:none;
    border:2px solid var(--border-cyan);
  }
  .profile-name{
    font-family:"Space Grotesk", sans-serif;
    font-weight:600;
    font-size:19px;
    margin:2px 0 3px;
  }
  .profile-handle{
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    color:var(--pink);
    margin:0 0 10px;
  }
  .profile-bio{ margin:0 0 12px; color:var(--text-dim); font-size:14.5px; }
  .profile-meta{
    display:flex;
    flex-wrap:wrap;
    gap:14px;
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    color:var(--text-dim);
  }
  #controls{
    padding:16px;
    margin-bottom:18px;
    display:flex;
    flex-direction:column;
    gap:12px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    backdrop-filter:blur(6px);
  }
  .console-row{ display:flex; flex-wrap:wrap; gap:10px; }
  .action-row{ align-items:center; }
  .spacer{ flex:1; }
  .input, .select{
    font-family:"Inter", sans-serif;
    font-size:13.5px;
    color:var(--text);
    background:rgba(255,255,255,0.05);
    border:1px solid var(--border);
    border-radius:8px;
    padding:9px 12px;
    outline:none;
    transition:border-color .15s ease;
  }
  .input{ flex:1; min-width:180px; }
  .input::placeholder{ color:var(--text-faint); }
  .input:focus, .select:focus{ border-color:var(--border-cyan); }
  .select{ cursor:pointer; }
  .select-sm{ flex:none; width:76px; }
  .checkbox{
    display:inline-flex;
    align-items:center;
    gap:7px;
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    color:var(--text-dim);
    cursor:pointer;
  }
  .checkbox input{ accent-color:var(--pink); width:15px; height:15px; }
  .btn{
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    color:var(--text);
    background:rgba(255,255,255,0.05);
    border:1px solid var(--border);
    border-radius:8px;
    padding:8px 14px;
    cursor:pointer;
    transition:border-color .15s ease, color .15s ease, background .15s ease;
  }
  .btn:hover{
    border-color:var(--border-cyan);
    color:var(--cyan);
    background:rgba(0,212,255,0.06);
  }
  .btn-ghost{ background:transparent; }
  .info-row{ margin:0 0 14px; padding:0 2px; }
  .repo-count{
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    color:var(--text-faint);
  }
  #repos{ display:flex; flex-direction:column; gap:12px; }
  .repo-card{
    padding:16px 18px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    transition:border-color .18s ease, transform .18s ease, box-shadow .18s ease;
  }
  .repo-card:hover{
    border-color:var(--border-cyan);
    transform:translateY(-1px);
    box-shadow:0 10px 26px -14px rgba(0,212,255,0.35);
  }
  .repo-top{ display:flex; gap:14px; align-items:flex-start; }
  .repo-main{ min-width:0; flex:1; }
  .repo-title{
    font-family:"Space Grotesk", sans-serif;
    font-size:16.5px;
    font-weight:600;
    margin:0 0 6px;
    display:flex;
    align-items:center;
    gap:8px;
  }
  .repo-link{ color:var(--text); cursor:pointer; }
  .repo-link:hover{ color:var(--cyan); }
  .fav-star{
    cursor:pointer;
    font-size:1.15em;
    color:var(--pink);
    line-height:1;
  }
  .fav-star:hover{ color:var(--red); }
  .repo-desc{ margin:0 0 10px; color:var(--text-dim); font-size:14px; }
  .repo-stats{
    display:flex;
    flex-wrap:wrap;
    gap:14px;
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    color:var(--text-faint);
  }
  .lang-dot{
    display:inline-block;
    width:8px; height:8px;
    border-radius:50%;
    background:var(--cyan);
    margin-right:6px;
    vertical-align:middle;
  }
  .repo-tags{ margin:10px 0 0; display:flex; flex-wrap:wrap; gap:6px; }
  .tag-chip{
    font-family:"JetBrains Mono", monospace;
    font-size:11px;
    color:var(--cyan);
    border:1px solid var(--border-cyan);
    background:rgba(0,212,255,0.06);
    padding:2px 9px;
    border-radius:99px;
  }
  .repo-icon{
    border-radius:9px;
    object-fit:cover;
    border:1px solid var(--border);
    flex:none;
  }
  .manifest-details{ margin-top:12px; border-top:1px solid var(--border); padding-top:10px; }
  .manifest-details summary{ font-family:"JetBrains Mono", monospace; font-size:12px; color:var(--text-dim); cursor:pointer; }
  .manifest-details summary:hover{ color:var(--cyan); }
  .manifest-pre{
    background:rgba(0,0,0,0.35);
    border:1px solid var(--border);
    border-radius:8px;
    padding:12px;
    margin-top:8px;
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    color:var(--text-dim);
    overflow-x:auto;
  }
  .status-panel{
    padding:20px;
    font-family:"JetBrains Mono", monospace;
    font-size:13px;
    color:var(--text-dim);
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
  }
  .status-panel.error{ color:var(--red); border-color:rgba(233,69,96,0.35); }
  .pagination{ display:flex; flex-wrap:wrap; gap:6px; justify-content:center; margin-top:18px; }
  .page-btn{
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    min-width:32px;
    padding:7px 9px;
    color:var(--text-dim);
    background:rgba(255,255,255,0.04);
    border:1px solid var(--border);
    border-radius:7px;
    cursor:pointer;
  }
  .page-btn:hover:not(:disabled){ border-color:var(--border-cyan); color:var(--cyan); }
  .page-btn.active{ color:var(--bg-1); background:var(--cyan); border-color:var(--cyan); font-weight:600; }
  .page-btn:disabled{ opacity:0.35; cursor:default; }
  .page-btn.ellipsis{ background:transparent; border-color:transparent; }
  #explorer{ display:flex; flex-direction:column; gap:14px; }
  .explorer-toolbar{
    display:flex;
    align-items:center;
    gap:12px;
    padding:14px 16px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    flex-wrap:wrap;
  }
  #explorerRepoName{
    font-family:"Space Grotesk", sans-serif;
    font-size:15px;
    font-weight:600;
  }
  #explorerStatus{
    font-family:"JetBrains Mono", monospace;
    font-size:12px;
    color:var(--text-faint);
    margin-left:auto;
  }
  .breadcrumbs{
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    padding:10px 16px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
  }
  .crumb{ color:var(--cyan); }
  .crumb:hover{ color:var(--pink); }
  .crumb-sep{ color:var(--text-faint); margin:0 6px; }
  #explorerContent{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:var(--radius);
    padding:6px 8px;
  }
  .explorer-item{
    display:flex;
    align-items:center;
    gap:10px;
    padding:9px 10px;
    border-radius:7px;
    cursor:pointer;
    font-size:13.5px;
  }
  .explorer-item:hover{ background:rgba(0,212,255,0.07); }
  .explorer-item:not(:last-child){ border-bottom:1px solid var(--border); }
  .item-icon{ flex:none; }
  .item-name{ flex:1; min-width:0; overflow:hidden; text-overflow:ellipsis; white-space:nowrap; }
  .item-size{ font-family:"JetBrains Mono", monospace; font-size:11.5px; color:var(--text-faint); flex:none; }
  #fileViewer{
    background:var(--surface);
    border:1px solid var(--border-cyan);
    border-radius:var(--radius);
    padding:14px 16px;
  }
  .file-viewer-head{
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom:12px;
  }
  #fileViewerName{
    font-family:"JetBrains Mono", monospace;
    font-size:13px;
    color:var(--cyan);
    flex:1;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
  }
  .file-pre{
    white-space:pre-wrap;
    max-height:420px;
    overflow:auto;
    margin:0;
    font-family:"JetBrains Mono", monospace;
    font-size:12.5px;
    color:var(--text-dim);
    background:rgba(0,0,0,0.35);
    border:1px solid var(--border);
    border-radius:8px;
    padding:12px;
  }
  .file-image{ max-width:100%; max-height:600px; border-radius:8px; display:block; }
  .file-binary-note{ color:var(--text-faint); font-family:"JetBrains Mono", monospace; font-size:12.5px; }
  footer.footer{
    text-align:center;
    margin-top:56px;
    font-family:"JetBrains Mono", monospace;
    font-size:11px;
    color:var(--text-faint);
    letter-spacing:0.04em;
  }
  hr{ border:none; }
  @media (max-width:560px){
    .profile-card{ flex-direction:column; align-items:center; text-align:center; }
    .profile-meta{ justify-content:center; }
    .select-sm{ width:auto; flex:1; }
    #explorerStatus{ margin-left:0; }
  }
  @media (prefers-reduced-motion:reduce){
    body{ animation:none; }
    .status-dot{ animation:none; }
  }
</style>
</head>
<body>
<header class="masthead">
  <p class="eyebrow"><span class="status-dot" id="statusDot"></span><span id="statusIndicator">loading…</span></p>
  <h1 class="title"><span class="grad">unalivable</span><span class="sub">GitHub Explorer</span></h1>
</header>
<div class="wrap">
  <div id="profile">
    <div class="status-panel">Loading profile…</div>
  </div>
  <div id="controls">
    <div class="console-row">
      <input type="text" id="searchInput" class="input" placeholder="Search repos…" />
    </div>
    <div class="console-row">
      <select id="languageFilter" class="select"><option value="">All languages</option></select>
      <select id="tagFilter" class="select"><option value="">All tags</option></select>
      <select id="sortSelect" class="select">
        <option value="updated-desc">Updated (newest)</option>
        <option value="updated-asc">Updated (oldest)</option>
        <option value="stars-desc">Stars ↓</option>
        <option value="stars-asc">Stars ↑</option>
        <option value="name-asc">Name A→Z</option>
        <option value="name-desc">Name Z→A</option>
        <option value="forks-desc">Forks ↓</option>
        <option value="forks-asc">Forks ↑</option>
      </select>
      <select id="perPageSelect" class="select select-sm">
        <option value="5">5</option>
        <option value="10" selected>10</option>
        <option value="20">20</option>
        <option value="50">50</option>
      </select>
    </div>
    <div class="console-row action-row">
      <label class="checkbox"><input type="checkbox" id="favoritesOnly" /> ★ Favorites</label>
      <div class="spacer"></div>
      <button id="viewToggle" class="btn btn-ghost">Switch view</button>
      <button id="clearFilters" class="btn btn-ghost">Clear filters</button>
    </div>
  </div>

  <!-- Info -->
  <div class="info-row">
    <span id="repoCount" class="repo-count"></span>
  </div>

  <!-- Repositories list -->
  <div id="repos">
    <div class="status-panel">Loading repositories…</div>
  </div>

  <!-- Pagination -->
  <div id="pagination" class="pagination"></div>
  <div id="explorer" style="display:none;">
    <div class="explorer-toolbar">
      <button id="backToRepos" class="btn btn-ghost">← Back to repos</button>
      <strong id="explorerRepoName"></strong>
      <span id="explorerStatus"></span>
    </div>
    <div id="breadcrumbs" class="breadcrumbs"></div>
    <div id="explorerContent">Loading…</div>
    <div id="fileViewer" style="display:none;">
      <div class="file-viewer-head">
        <button id="closeFileViewer" class="btn btn-ghost">✕ Close file</button>
        <strong id="fileViewerName"></strong>
      </div>
      <div id="fileViewerContent"></div>
    </div>
  </div>
  <hr />
  <footer class="footer">github.com/unalivable</footer>
</div>
<script>
  (function() {
    "use strict";
    var userAvatar = '';
    var allRepos = [];
    var manifests = {};
    var favorites = new Set(JSON.parse(localStorage.getItem('favorites') || '[]'));
    var currentPage = 1;
    var viewMode = 'cards';
    var perPage = 10;
    var currentMode = 'list';
    var explorerRepo = null;
    var explorerPath = '';
    var viewingFile = null;
    function $(id) { return document.getElementById(id); }
    var statusIndicator = $('statusIndicator');
    var statusDot = $('statusDot');
    var profileEl = $('profile');
    var reposEl = $('repos');
    var paginationEl = $('pagination');
    var repoCountEl = $('repoCount');
    var searchInput = $('searchInput');
    var languageFilter = $('languageFilter');
    var tagFilter = $('tagFilter');
    var sortSelect = $('sortSelect');
    var perPageSelect = $('perPageSelect');
    var favoritesOnly = $('favoritesOnly');
    var viewToggle = $('viewToggle');
    var clearFiltersBtn = $('clearFilters');
    var explorerDiv = $('explorer');
    var explorerRepoName = $('explorerRepoName');
    var explorerStatus = $('explorerStatus');
    var breadcrumbs = $('breadcrumbs');
    var explorerContent = $('explorerContent');
    var fileViewer = $('fileViewer');
    var fileViewerName = $('fileViewerName');
    var fileViewerContent = $('fileViewerContent');
    var closeFileViewerBtn = $('closeFileViewer');
    var backToReposBtn = $('backToRepos');
    var controlsEl = $('controls');
    var infoEl = $('info');
    function escapeHtml(s) {
      return String(s).replace(/[&<>"']/g, function(c) {
        if (c === '&') return '&amp;';
        if (c === '<') return '&lt;';
        if (c === '>') return '&gt;';
        if (c === '"') return '&quot;';
        if (c === "'") return '&#39;';
        return c;
      });
    }
    function setStatus(msg, isError) {
      if (statusIndicator) {
        statusIndicator.textContent = msg;
        statusIndicator.classList.toggle('is-error', !!isError);
      }
      if (statusDot) {
        statusDot.classList.toggle('dot-error', !!isError);
      }
    }
    function getFileType(filename) {
      var ext = filename.split('.').pop().toLowerCase();
      var images = ['png', 'jpg', 'jpeg', 'gif', 'svg', 'webp', 'bmp', 'ico', 'tiff', 'tif'];
      var binaries = ['exe', 'dll', 'bin', 'so', 'dylib', 'dat', 'class', 'jar', 'war', 'ear', 'zip', 'rar', '7z', 'gz', 'bz2', 'xz', 'tar', 'iso', 'img', 'msi', 'deb', 'rpm', 'apk', 'appimage', 'elf'];
      if (images.indexOf(ext) !== -1) return 'image';
      if (binaries.indexOf(ext) !== -1) return 'binary';
      return 'text';
    }
    function getMimeType(filename) {
      var ext = filename.split('.').pop().toLowerCase();
      var map = {
        'png': 'image/png',
        'jpg': 'image/jpeg',
        'jpeg': 'image/jpeg',
        'gif': 'image/gif',
        'svg': 'image/svg+xml',
        'webp': 'image/webp',
        'bmp': 'image/bmp',
        'ico': 'image/x-icon',
        'tiff': 'image/tiff',
        'tif': 'image/tiff'
      };
      return map[ext] || 'application/octet-stream';
    }
    function base64ToUtf8(base64) {
      var binaryString = atob(base64);
      var bytes = new Uint8Array(binaryString.length);
      for (var i = 0; i < binaryString.length; i++) {
        bytes[i] = binaryString.charCodeAt(i);
      }
      return new TextDecoder('utf-8').decode(bytes);
    }
    async function fetchGitHub(url) {
      var res = await fetch(url);
      if (!res.ok) throw new Error('HTTP ' + res.status + ': ' + res.statusText);
      return await res.json();
    }
    async function loadProfile() {
      var data = await fetchGitHub('https://api.github.com/users/unalivable');
      userAvatar = data.avatar_url;
      return data;
    }
    async function loadRepos() {
      return await fetchGitHub('https://api.github.com/users/unalivable' + '/repos?sort=updated&per_page=100');
    }
    async function loadManifest(repo) {
      try {
        var url = 'https://raw.githubusercontent.com/unalivable' + '/' + repo + '/main/webmanifest.data';
        var res = await fetch(url);
        if (!res.ok) return null;
        var text = await res.text();
        return JSON.parse(text);
      } catch (e) {
        return null;
      }
    }
    async function loadRepoContents(repo, path) {
      path = path || '';
      var url = 'https://api.github.com/repos/unalivable' + '/' + repo + '/contents/' + path;
      return await fetchGitHub(url);
    }
    async function loadAll() {
      setStatus('Loading…');
      if (profileEl) profileEl.innerHTML = '<div class="status-panel">Loading profile…</div>';
      if (reposEl) reposEl.innerHTML = '<div class="status-panel">Loading repositories…</div>';
      if (paginationEl) paginationEl.innerHTML = '';
      try {
        var profile = await loadProfile();
        renderProfile(profile);
        var repos = await loadRepos();
        allRepos = repos;
        var chunkSize = 5;
        for (var i = 0; i < repos.length; i += chunkSize) {
          var chunk = repos.slice(i, i + chunkSize);
          await Promise.all(chunk.map(function(repo) {
            return loadManifest(repo.name).then(function(m) {
              if (m) manifests[repo.name] = m;
            });
          }));
        }
        populateFilters(repos);
        applyFiltersAndRender();
        setStatus('Ready — ' + repos.length + ' repos');
      } catch (e) {
        setStatus('Error: ' + e.message, true);
        if (profileEl) profileEl.innerHTML = '<div class="status-panel error">' + escapeHtml(e.message) + '</div>';
        if (reposEl) reposEl.innerHTML = '<div class="status-panel error">' + escapeHtml(e.message) + '</div>';
      }
    }
    function renderProfile(profile) {
      if (!profileEl) return;
      profileEl.innerHTML =
        '<div class="profile-card">' +
          '<img src="' + escapeHtml(profile.avatar_url) + '" width="72" height="72" class="avatar" alt="avatar" />' +
          '<div>' +
            '<div class="profile-name">' + escapeHtml(profile.name || profile.login) + '</div>' +
            '<div class="profile-handle">@' + escapeHtml(profile.login) + '</div>' +
            (profile.bio ? '<div class="profile-bio">' + escapeHtml(profile.bio) + '</div>' : '') +
            '<div class="profile-meta">' +
              (profile.location ? '<span>📍 ' + escapeHtml(profile.location) + '</span>' : '') +
              '<span>👥 ' + profile.followers + ' followers</span>' +
              '<a href="' + escapeHtml(profile.html_url) + '" target="_blank">' + escapeHtml(profile.html_url.replace('https://','')) + '</a>' +
            '</div>' +
          '</div>' +
        '</div>';
    }
    function populateFilters(repos) {
      if (!languageFilter || !tagFilter) return;
      var langs = {};
      var tags = {};
      repos.forEach(function(r) {
        if (r.language) langs[r.language] = true;
        var m = manifests[r.name];
        if (m && m.tags) m.tags.forEach(function(t) { tags[t] = true; });
      });
      var langKeys = Object.keys(langs).sort();
      var tagKeys = Object.keys(tags).sort();
      languageFilter.innerHTML = '<option value="">All languages</option>' +
        langKeys.map(function(l) { return '<option value="' + escapeHtml(l) + '">' + escapeHtml(l) + '</option>'; }).join('');
      tagFilter.innerHTML = '<option value="">All tags</option>' +
        tagKeys.map(function(t) { return '<option value="' + escapeHtml(t) + '">' + escapeHtml(t) + '</option>'; }).join('');
    }
    function getFilteredRepos() {
      var search = searchInput ? searchInput.value.toLowerCase().trim() : '';
      var lang = languageFilter ? languageFilter.value : '';
      var tag = tagFilter ? tagFilter.value : '';
      var onlyFav = favoritesOnly ? favoritesOnly.checked : false;
      var sortKey = sortSelect ? sortSelect.value : 'updated-desc';
      var filtered = allRepos.filter(function(repo) {
        if (search) {
          var nameMatch = repo.name.toLowerCase().indexOf(search) !== -1;
          var descMatch = (repo.description || '').toLowerCase().indexOf(search) !== -1;
          var m = manifests[repo.name];
          var mDesc = (m && m.description || '').toLowerCase().indexOf(search) !== -1;
          var mName = (m && m.displayName || '').toLowerCase().indexOf(search) !== -1;
          if (!(nameMatch || descMatch || mDesc || mName)) return false;
        }
        if (lang && repo.language !== lang) return false;
        if (tag) {
          var repoTags = (manifests[repo.name] && manifests[repo.name].tags) || [];
          if (repoTags.indexOf(tag) === -1) return false;
        }
        if (onlyFav && !favorites.has(repo.name)) return false;
        return true;
      });
      var parts = sortKey.split('-');
      var field = parts[0];
      var desc = parts[1] === 'desc';
      filtered.sort(function(a, b) {
        var va, vb;
        if (field === 'name') { va = a.name; vb = b.name; }
        else if (field === 'stars') { va = a.stargazers_count; vb = b.stargazers_count; }
        else if (field === 'forks') { va = a.forks_count; vb = b.forks_count; }
        else if (field === 'updated') { va = new Date(a.updated_at); vb = new Date(b.updated_at); }
        else return 0;
        if (va < vb) return desc ? 1 : -1;
        if (va > vb) return desc ? -1 : 1;
        return 0;
      });
      return filtered;
    }
    function renderRepos(filtered) {
      if (!reposEl) return;
      var total = filtered.length;
      var totalPages = Math.ceil(total / perPage);
      if (currentPage > totalPages) currentPage = totalPages || 1;
      var start = (currentPage - 1) * perPage;
      var end = Math.min(start + perPage, total);
      var pageItems = filtered.slice(start, end);
      var totalAll = allRepos.length;
      var label = total + ' repo' + (total !== 1 ? 's' : '');
      if (total !== totalAll) label += ' (filtered from ' + totalAll + ')';
      if (favoritesOnly && favoritesOnly.checked) label += ' ★ favorites';
      if (repoCountEl) repoCountEl.textContent = label;
      if (pageItems.length === 0) {
        reposEl.innerHTML = '<div class="status-panel">No repositories match your filters.</div>';
        if (paginationEl) paginationEl.innerHTML = '';
        return;
      }
      var html = '';
      pageItems.forEach(function(repo) {
        var manifest = manifests[repo.name] || null;
        var icon = (manifest && manifest.icon) || userAvatar;
        var displayName = (manifest && manifest.displayName) || repo.name;
        var desc = (manifest && manifest.description) || repo.description || 'No description.';
        var tags = (manifest && manifest.tags) || [];
        var isFav = favorites.has(repo.name);
        var themeColor = (manifest && manifest.themeColor) || null;
        var starBtn = '<span class="fav-star" data-repo="' + escapeHtml(repo.name) + '">' + (isFav ? '★' : '☆') + '</span>';
        var tagsHtml = tags.length ? '<div class="repo-tags">' + tags.map(function(t) { return '<span class="tag-chip">' + escapeHtml(t) + '</span>'; }).join('') + '</div>' : '';
        var manifestHtml = manifest ? '<details class="manifest-details"><summary>📦 manifest</summary><pre class="manifest-pre">' + escapeHtml(JSON.stringify(manifest, null, 2)) + '</pre></details>' : '';
        html +=
          '<div class="repo-card" style="' + (themeColor ? 'border-color:' + themeColor + ';' : '') + '">' +
            '<div class="repo-top">' +
              '<div class="repo-main">' +
                '<div class="repo-title">' +
                  '<span class="repo-link" data-repo="' + escapeHtml(repo.name) + '">' + escapeHtml(displayName) + '</span> ' +
                  starBtn +
                '</div>' +
                '<div class="repo-desc">' + escapeHtml(desc) + '</div>' +
                '<div class="repo-stats">' +
                  (repo.language ? '<span><span class="lang-dot"></span>' + escapeHtml(repo.language) + '</span>' : '') +
                  '<span>⭐ ' + repo.stargazers_count + '</span>' +
                  '<span>🍴 ' + repo.forks_count + '</span>' +
                  '<span>📅 ' + new Date(repo.updated_at).toLocaleDateString() + '</span>' +
                '</div>' +
                tagsHtml +
                manifestHtml +
              '</div>' +
              '<img src="' + escapeHtml(icon) + '" width="40" height="40" class="repo-icon" alt="" onerror="this.src=\'' + escapeHtml(userAvatar) + '\'" />' +
            '</div>' +
          '</div>';
      });
      reposEl.innerHTML = html;
      reposEl.querySelectorAll('.fav-star').forEach(function(el) {
        el.addEventListener('click', function(e) {
          e.stopPropagation();
          var repoName = this.getAttribute('data-repo');
          toggleFavorite(repoName);
        });
      });
      reposEl.querySelectorAll('.repo-link').forEach(function(el) {
        el.addEventListener('click', function() {
          var repoName = this.getAttribute('data-repo');
          openExplorer(repoName);
        });
      });
      if (!paginationEl) return;
      var pagHtml = '';
      if (totalPages > 1) {
        pagHtml += '<button class="page-btn" ' + (currentPage === 1 ? 'disabled' : '') + ' data-page="' + (currentPage-1) + '">‹</button>';
        for (var i = 1; i <= totalPages; i++) {
          if (i === currentPage) {
            pagHtml += '<button class="page-btn active" data-page="' + i + '">' + i + '</button>';
          } else if (i === 1 || i === totalPages || Math.abs(i - currentPage) <= 2) {
            pagHtml += '<button class="page-btn" data-page="' + i + '">' + i + '</button>';
          } else if (i === currentPage - 3 || i === currentPage + 3) {
            pagHtml += '<button class="page-btn ellipsis" disabled>…</button>';
          }
        }
        pagHtml += '<button class="page-btn" ' + (currentPage === totalPages ? 'disabled' : '') + ' data-page="' + (currentPage+1) + '">›</button>';
      }
      paginationEl.innerHTML = pagHtml;
      paginationEl.querySelectorAll('button.page-btn[data-page]').forEach(function(btn) {
        btn.addEventListener('click', function() {
          var page = parseInt(this.getAttribute('data-page'));
          if (!isNaN(page) && page >= 1 && page <= totalPages) {
            currentPage = page;
            applyFiltersAndRender();
          }
        });
      });
    }
    function toggleFavorite(repoName) {
      if (favorites.has(repoName)) favorites.delete(repoName);
      else favorites.add(repoName);
      localStorage.setItem('favorites', JSON.stringify([].slice.call(favorites)));
      applyFiltersAndRender();
    }
    function applyFiltersAndRender() {
      if (currentMode === 'list') {
        var filtered = getFilteredRepos();
        renderRepos(filtered);
      }
    }
    function resetFilters() {
      if (searchInput) searchInput.value = '';
      if (languageFilter) languageFilter.value = '';
      if (tagFilter) tagFilter.value = '';
      if (sortSelect) sortSelect.value = 'updated-desc';
      if (perPageSelect) perPageSelect.value = '10';
      if (favoritesOnly) favoritesOnly.checked = false;
      perPage = 10;
      currentPage = 1;
      applyFiltersAndRender();
    }
    function toggleView() {
      viewMode = viewMode === 'cards' ? 'list' : 'cards';
      applyFiltersAndRender();
    }
    function hideListElements() {
      if (controlsEl) controlsEl.style.display = 'none';
      if (infoEl) infoEl.style.display = 'none';
      if (reposEl) reposEl.style.display = 'none';
      if (paginationEl) paginationEl.style.display = 'none';
    }
    function showListElements() {
      if (controlsEl) controlsEl.style.display = '';
      if (infoEl) infoEl.style.display = '';
      if (reposEl) reposEl.style.display = '';
      if (paginationEl) paginationEl.style.display = '';
    }
    async function openExplorer(repoName) {
      currentMode = 'explorer';
      explorerRepo = repoName;
      explorerPath = '';
      viewingFile = null;
      if (fileViewer) fileViewer.style.display = 'none';
      hideListElements();
      if (explorerDiv) explorerDiv.style.display = 'block';
      if (explorerRepoName) explorerRepoName.textContent = '📁 ' + repoName;
      if (explorerStatus) explorerStatus.textContent = 'loading…';
      await renderExplorerContents(repoName, '');
    }
    async function renderExplorerContents(repo, path) {
      explorerPath = path;
      if (explorerContent) explorerContent.innerHTML = 'Loading…';
      viewingFile = null;
      if (fileViewer) fileViewer.style.display = 'none';
      try {
        var data = await loadRepoContents(repo, path);
        if (!Array.isArray(data)) {
          showFileContent(repo, data);
          return;
        }
        var items = data;
        if (explorerStatus) explorerStatus.textContent = items.length + ' items';
        if (breadcrumbs) {
          var breadHtml = '<a href="#" data-path="" class="crumb">root</a>';
          if (path) {
            var parts = path.split('/');
            var cum = '';
            parts.forEach(function(p, idx) {
              cum += (idx === 0 ? '' : '/') + p;
              breadHtml += '<span class="crumb-sep"> / </span><a href="#" data-path="' + cum + '" class="crumb">' + escapeHtml(p) + '</a>';
            });
          }
          breadcrumbs.innerHTML = breadHtml;
          breadcrumbs.querySelectorAll('a[data-path]').forEach(function(el) {
            el.addEventListener('click', function(e) {
              e.preventDefault();
              var newPath = this.getAttribute('data-path');
              renderExplorerContents(repo, newPath);
            });
          });
        }
        var listHtml = '';
        var dirs = items.filter(function(i) { return i.type === 'dir'; });
        var files = items.filter(function(i) { return i.type === 'file'; });
        [].concat(dirs, files).forEach(function(item) {
          var isDir = item.type === 'dir';
          var icon = isDir ? '📁' : '📄';
          var name = item.name;
          var size = item.size ? ' (' + (item.size/1024).toFixed(1) + ' KB)' : '';
          var dataAttr = isDir ? 'data-path="' + (path ? path + '/' : '') + name + '"' : 'data-file="' + name + '" data-sha="' + item.sha + '"';
          var type = isDir ? 'dir' : 'file';
          listHtml += '<div class="explorer-item" data-type="' + type + '" ' + dataAttr + '>' +
            '<span class="item-icon">' + icon + '</span>' +
            '<span class="item-name">' + escapeHtml(name) + '</span>' +
            '<span class="item-size">' + size + '</span>' +
          '</div>';
        });
        if (explorerContent) explorerContent.innerHTML = listHtml;
        explorerContent.querySelectorAll('.explorer-item').forEach(function(el) {
          el.addEventListener('click', function() {
            var type = this.getAttribute('data-type');
            if (type === 'dir') {
              var newPath = this.getAttribute('data-path');
              renderExplorerContents(repo, newPath);
            } else {
              var fileName = this.getAttribute('data-file');
              var sha = this.getAttribute('data-sha');
              fetchFileContent(repo, fileName, sha);
            }
          });
        });
        if (explorerStatus) explorerStatus.textContent = '📂 ' + dirs.length + ' dirs, 📄 ' + files.length + ' files';
      } catch (e) {
        if (explorerContent) explorerContent.innerHTML = '<div class="status-panel error">Error: ' + escapeHtml(e.message) + '</div>';
        if (explorerStatus) explorerStatus.textContent = '❌ error';
      }
    }
    async function fetchFileContent(repo, fileName, sha) {
      var path = explorerPath ? explorerPath + '/' : '';
      var url = 'https://api.github.com/repos/unalivable' + '/' + repo + '/contents/' + path + fileName;
      try {
        var data = await fetchGitHub(url);
        if (data.encoding !== 'base64') {
          showFileViewer(fileName, 'Unsupported encoding.', 'text');
          return;
        }
        var fileType = getFileType(fileName);
        if (fileType === 'image') {
          showFileViewer(fileName, data.content, 'image', getMimeType(fileName));
          return;
        }
        var content = base64ToUtf8(data.content);
        var sizeMB = (content.length / (1024 * 1024)).toFixed(1);
        if (content.length > 1024 * 1024) {
          if (!confirm('File "' + fileName + '" is large (' + sizeMB + ' MB). Do you want to load it?')) {
            return;
          }
        }
        if (fileType === 'binary') {
          showFileViewer(fileName, '', 'binary');
        } else {
          if (isBinaryContent(content)) {
            showFileViewer(fileName, '', 'binary');
          } else {
            showFileViewer(fileName, content, 'text');
          }
        }
      } catch (e) {
        showFileViewer(fileName, 'Error: ' + e.message, 'text');
      }
    }
    function isBinaryContent(str) {
      for (var i = 0; i < Math.min(str.length, 1000); i++) {
        var c = str.charCodeAt(i);
        if (c < 32 && c !== 9 && c !== 10 && c !== 13) return true;
      }
      return false;
    }
    function showFileViewer(name, content, type, mime) {
      viewingFile = { name, content, type, mime };
      if (fileViewerName) fileViewerName.textContent = name;
      if (fileViewerContent) {
        fileViewerContent.innerHTML = '';
        if (type === 'image') {
          var img = document.createElement('img');
          img.src = 'data:' + (mime || 'image/png') + ';base64,' + content;
          img.className = 'file-image';
          fileViewerContent.appendChild(img);
        } else if (type === 'binary') {
          fileViewerContent.innerHTML = '<div class="file-binary-note">⚠️ This is a binary file. Cannot display.</div>';
        } else {
          var pre = document.createElement('pre');
          pre.className = 'file-pre';
          pre.textContent = content;
          fileViewerContent.appendChild(pre);
        }
      }
      if (fileViewer) fileViewer.style.display = 'block';
      fileViewer.scrollIntoView({ behavior: 'smooth' });
    }
    function showFileContent(repo, data) {
      if (data.encoding === 'base64') {
        var fileType = getFileType(data.name);
        if (fileType === 'image') {
          showFileViewer(data.name, data.content, 'image', getMimeType(data.name));
          return;
        }
        var content = base64ToUtf8(data.content);
        if (fileType === 'binary') {
          showFileViewer(data.name, '', 'binary');
        } else {
          if (isBinaryContent(content)) {
            showFileViewer(data.name, '', 'binary');
          } else {
            showFileViewer(data.name, content, 'text');
          }
        }
      } else {
        showFileViewer(data.name, 'Cannot display this file.', 'text');
      }
    }
    if (closeFileViewerBtn) {
      closeFileViewerBtn.addEventListener('click', function() {
        if (fileViewer) fileViewer.style.display = 'none';
        viewingFile = null;
      });
    }
    if (backToReposBtn) {
      backToReposBtn.addEventListener('click', function() {
        currentMode = 'list';
        if (explorerDiv) explorerDiv.style.display = 'none';
        showListElements();
        applyFiltersAndRender();
      });
    }
    function init() {
      perPage = parseInt(perPageSelect ? perPageSelect.value : '10') || 10;
      loadAll();
      if (searchInput) searchInput.addEventListener('input', function() { currentPage = 1; applyFiltersAndRender(); });
      if (languageFilter) languageFilter.addEventListener('change', function() { currentPage = 1; applyFiltersAndRender(); });
      if (tagFilter) tagFilter.addEventListener('change', function() { currentPage = 1; applyFiltersAndRender(); });
      if (sortSelect) sortSelect.addEventListener('change', function() { currentPage = 1; applyFiltersAndRender(); });
      if (perPageSelect) perPageSelect.addEventListener('change', function() {
        perPage = parseInt(perPageSelect.value) || 10;
        currentPage = 1;
        applyFiltersAndRender();
      });
      if (favoritesOnly) favoritesOnly.addEventListener('change', function() { currentPage = 1; applyFiltersAndRender(); });
      if (viewToggle) viewToggle.addEventListener('click', toggleView);
      if (clearFiltersBtn) clearFiltersBtn.addEventListener('click', resetFilters);
    }
    init();
  })();
</script>
</body>
</html>
```
[Back / Назад](../)
```
[Back / Назад](../)
