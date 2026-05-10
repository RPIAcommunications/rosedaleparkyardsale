<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rosedale Park 60-Block Yard Sale</title>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css">
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --green-dark: #2C4A2E;
      --green-mid: #4CAF50;
      --green-light: #C8E6C9;
      --green-pale: #E8F5E9;
      --food-color: #b45309;
      --food-bg: #fef3c7;
      --food-border: #fcd34d;
      --text: #1a1a1a;
      --text-muted: #5a6b5a;
      --border: #d4e0d4;
      --bg: #f7faf7;
      --card: #ffffff;
      --danger: #c0392b;
      --radius: 10px;
      --radius-lg: 16px;
    }
    body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }

    header {
      background: var(--green-dark); padding: 1.25rem 1.5rem;
      display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 12px;
    }
    header h1 { font-family: 'Playfair Display', serif; font-size: clamp(17px,4vw,24px); color: #C8E6C9; }
    header p  { font-size: 12px; color: #A5D6A7; margin-top: 2px; }
    .header-badges { display: flex; gap: 8px; flex-wrap: wrap; align-items: center; }
    #count-badge, #food-badge {
      font-size: 12px; font-weight: 500; padding: 5px 12px; border-radius: 20px; white-space: nowrap;
    }
    #count-badge { background: rgba(255,255,255,0.12); border: 1px solid rgba(255,255,255,0.2); color: #C8E6C9; }
    #food-badge  { background: #fef3c7; border: 1px solid #fcd34d; color: #92400e; display: none; }

    .main { max-width: 1100px; margin: 0 auto; padding: 1.25rem; }

    #open-form-btn {
      display: block; width: 100%; background: var(--green-dark); color: #C8E6C9;
      border: none; border-radius: var(--radius); font-family: 'DM Sans', sans-serif;
      font-size: 15px; font-weight: 500; padding: 13px; cursor: pointer; margin-bottom: 1rem; transition: background .15s;
    }
    #open-form-btn:hover { background: #3a5e3c; }

    #register-panel {
      display: none; background: var(--card); border: 1px solid var(--border);
      border-radius: var(--radius-lg); padding: 1.25rem; margin-bottom: 1rem;
    }
    #register-panel h2 { font-family:'Playfair Display',serif; font-size:18px; color:var(--green-dark); margin-bottom:1rem; }

    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 10px; }
    .form-grid .full { grid-column: 1/-1; }
    @media(max-width:520px){ .form-grid { grid-template-columns:1fr; } .form-grid .full { grid-column:1; } }

    label { display:block; font-size:11px; font-weight:500; color:var(--text-muted); margin-bottom:4px; text-transform:uppercase; letter-spacing:.5px; }
    input[type=text], textarea, select {
      width:100%; padding:9px 12px; font-family:'DM Sans',sans-serif; font-size:14px;
      border:1px solid var(--border); border-radius:var(--radius);
      background:var(--bg); color:var(--text); outline:none; transition:border-color .15s;
    }
    input[type=text]:focus, textarea:focus, select:focus { border-color:var(--green-mid); box-shadow:0 0 0 3px rgba(76,175,80,.15); }
    textarea { resize:vertical; }

    /* Vending type toggle */
    .vend-group { display: flex; gap: 8px; flex-wrap: wrap; }
    .vend-btn {
      flex: 1; min-width: 100px; padding: 9px 10px; border-radius: var(--radius);
      border: 1.5px solid var(--border); background: var(--bg);
      font-family: 'DM Sans', sans-serif; font-size: 13px; font-weight: 500;
      cursor: pointer; text-align: center; transition: all .15s; color: var(--text-muted);
    }
    .vend-btn.active-yard  { border-color: var(--green-mid); background: var(--green-pale); color: var(--green-dark); }
    .vend-btn.active-food  { border-color: #f59e0b; background: #fef3c7; color: #92400e; }
    .vend-btn.active-both  { border-color: #7c3aed; background: #ede9fe; color: #4c1d95; }

    .form-actions { display:flex; gap:8px; margin-top:12px; }
    .btn-primary {
      flex:1; background:var(--green-dark); color:#C8E6C9; border:none;
      border-radius:var(--radius); font-family:'DM Sans',sans-serif;
      font-size:14px; font-weight:500; padding:10px; cursor:pointer; transition:background .15s;
    }
    .btn-primary:hover { background:#3a5e3c; }
    .btn-primary:disabled { background:#aaa; cursor:not-allowed; }
    .btn-cancel {
      padding:10px 16px; background:transparent; border:1px solid var(--border);
      border-radius:var(--radius); font-family:'DM Sans',sans-serif;
      font-size:14px; color:var(--text-muted); cursor:pointer;
    }
    #reg-msg { font-size:12px; margin-top:8px; display:none; }

    #map { width:100%; height:460px; border-radius:var(--radius-lg); border:1px solid var(--border); margin-bottom:1.25rem; }
    @media(min-width:700px){ #map { height:540px; } }

    /* Legend */
    .map-legend {
      background: var(--card); border: 1px solid var(--border); border-radius: var(--radius);
      padding: 8px 12px; display: flex; gap: 14px; flex-wrap: wrap;
      font-size: 12px; color: var(--text-muted); margin-bottom: 1rem; align-items: center;
    }
    .legend-item { display: flex; align-items: center; gap: 5px; }
    .legend-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }

    #listings-header { font-size:15px; font-weight:500; color:var(--green-dark); margin-bottom:10px; display:none; }
    #listings { display:grid; grid-template-columns:repeat(auto-fill,minmax(260px,1fr)); gap:10px; }

    .listing-card {
      background:var(--card); border:1px solid var(--border); border-radius:var(--radius-lg);
      padding:1rem; transition:border-color .15s, box-shadow .15s;
    }
    .listing-card:hover { border-color:var(--green-mid); box-shadow:0 2px 12px rgba(44,74,46,.1); }
    .card-top { display:flex; justify-content:space-between; align-items:flex-start; gap:8px; margin-bottom:4px; }
    .listing-address { font-size:14px; font-weight:500; flex:1; }
    .card-actions { display:flex; gap:4px; flex-shrink:0; }
    .card-btn {
      background: none; border: 1px solid var(--border); border-radius: 6px;
      font-size: 11px; color: var(--text-muted); padding: 3px 8px; cursor: pointer;
      font-family: 'DM Sans', sans-serif; transition: all .15s;
    }
    .card-btn:hover { background: var(--bg); }
    .card-btn.delete:hover { border-color: var(--danger); color: var(--danger); }
    .listing-meta { font-size:12px; color:var(--text-muted); margin-bottom:8px; }
    .tags { display:flex; flex-wrap:wrap; gap:4px; margin-top:6px; }
    .tag { font-size:11px; background:var(--green-pale); color:var(--green-dark); border:1px solid #c3dfc5; padding:2px 9px; border-radius:20px; font-weight:500; }
    .tag-food { background:#fef3c7; color:#92400e; border-color:#fcd34d; }
    .tag-both { background:#ede9fe; color:#4c1d95; border-color:#c4b5fd; }
    .no-items { font-size:12px; color:#aaa; font-style:italic; }

    /* Vend type badge on card */
    .vend-badge {
      display: inline-block; font-size: 11px; font-weight: 500;
      padding: 2px 9px; border-radius: 20px; margin-bottom: 6px;
    }
    .vend-badge.yard { background: var(--green-pale); color: var(--green-dark); border: 1px solid #c3dfc5; }
    .vend-badge.food { background: #fef3c7; color: #92400e; border: 1px solid #fcd34d; }
    .vend-badge.both { background: #ede9fe; color: #4c1d95; border: 1px solid #c4b5fd; }

    /* Map markers */
    .yard-marker, .food-marker, .both-marker, .center-marker {
      font-size: 11px; font-weight: 500; padding: 4px 10px; border-radius: 12px;
      white-space: nowrap; box-shadow: 0 2px 6px rgba(0,0,0,.28);
      font-family: 'DM Sans', sans-serif; cursor: pointer;
    }
    .yard-marker  { background: #2C4A2E; color: #C8E6C9; border: 1.5px solid #4CAF50; }
    .food-marker  { background: #92400e; color: #fef3c7; border: 1.5px solid #f59e0b; }
    .both-marker  { background: #4c1d95; color: #ede9fe; border: 1.5px solid #8b5cf6; }
    .center-marker { background: #fff; color: #2C4A2E; border: 2px solid #2C4A2E; font-weight: 600; }

    .leaflet-popup-content-wrapper { border-radius: 12px !important; }
    .leaflet-popup-content { margin: 12px 14px !important; }
    .iw { font-family: 'DM Sans', sans-serif; font-size: 13px; max-width: 230px; }
    .iw strong { font-size: 14px; color: #2C4A2E; display: block; margin-bottom: 4px; }
    .iw .iw-meta { color: #5a6b5a; margin-bottom: 6px; font-size: 12px; }
    .iw .iw-vend { font-size: 11px; font-weight: 500; padding: 2px 8px; border-radius: 20px; display:inline-block; margin-bottom:6px; }
    .iw .iw-vend.yard { background:#E8F5E9; color:#2C4A2E; border:1px solid #c3dfc5; }
    .iw .iw-vend.food { background:#fef3c7; color:#92400e; border:1px solid #fcd34d; }
    .iw .iw-vend.both { background:#ede9fe; color:#4c1d95; border:1px solid #c4b5fd; }
    .iw .tags { display:flex; flex-wrap:wrap; gap:4px; }
    .iw .tag { font-size:11px; background:#E8F5E9; color:#2C4A2E; border:1px solid #c3dfc5; padding:2px 8px; border-radius:20px; }

    /* Edit/Delete modal */
    #modal-overlay {
      display: none; position: fixed; inset: 0; background: rgba(0,0,0,.45);
      z-index: 9999; align-items: center; justify-content: center; padding: 1rem;
    }
    #modal-box {
      background: var(--card); border-radius: var(--radius-lg); padding: 1.5rem;
      max-width: 420px; width: 100%; border: 1px solid var(--border); position: relative;
      max-height: 90vh; overflow-y: auto;
    }
    #modal-title { font-family:'Playfair Display',serif; font-size:18px; color:var(--green-dark); margin-bottom:1rem; }
    #modal-close { position:absolute; top:12px; right:14px; background:none; border:none; font-size:22px; color:var(--text-muted); cursor:pointer; }
    .modal-form-grid { display:grid; grid-template-columns:1fr 1fr; gap:10px; margin-bottom:10px; }
    .modal-form-grid .full { grid-column:1/-1; }
    @media(max-width:480px){ .modal-form-grid { grid-template-columns:1fr; } .modal-form-grid .full { grid-column:1; } }
    .modal-actions { display:flex; gap:8px; margin-top:14px; flex-wrap:wrap; }
    .btn-save { flex:1; min-width:100px; background:var(--green-dark); color:#C8E6C9; border:none; border-radius:var(--radius); font-family:'DM Sans',sans-serif; font-size:14px; font-weight:500; padding:10px; cursor:pointer; }
    .btn-save:hover { background:#3a5e3c; }
    .btn-delete-confirm { padding:10px 16px; background:transparent; border:1px solid var(--danger); border-radius:var(--radius); font-family:'DM Sans',sans-serif; font-size:14px; color:var(--danger); cursor:pointer; }
    .btn-delete-confirm:hover { background:#fff5f5; }

    /* Delete confirm panel */
    #delete-confirm { display:none; margin-top:12px; padding:12px; background:#fff5f5; border:1px solid #f5c6c6; border-radius:var(--radius); }
    #delete-confirm p { font-size:13px; color:var(--danger); margin-bottom:10px; }
    #delete-confirm .del-btns { display:flex; gap:8px; }
    .btn-yes-delete { flex:1; background:var(--danger); color:#fff; border:none; border-radius:var(--radius); font-family:'DM Sans',sans-serif; font-size:13px; font-weight:500; padding:9px; cursor:pointer; }
    .btn-no-delete { flex:1; background:transparent; border:1px solid var(--border); border-radius:var(--radius); font-family:'DM Sans',sans-serif; font-size:13px; color:var(--text-muted); padding:9px; cursor:pointer; }

    footer { text-align:center; font-size:12px; color:var(--text-muted); padding:2rem 1rem 1.5rem; }
  </style>
</head>
<body>

<header>
  <div>
    <h1>🌿 Rosedale Park 60-Block Yard Sale</h1>
    <p>Register your address &amp; list your items for sale</p>
  </div>
  <div class="header-badges">
    <div id="count-badge">0 participants</div>
    <div id="food-badge">🍽 Food available</div>
  </div>
</header>

<div class="main">

  <button id="open-form-btn" onclick="openForm()">+ Add My Address to the Map</button>

  <div id="register-panel">
    <h2>Register your yard sale</h2>
    <div class="form-grid">
      <div class="full">
        <label for="inp-address">Street address *</label>
        <input id="inp-address" type="text" placeholder="e.g. 14800 Ashton Ave, Detroit MI">
      </div>
      <div>
        <label for="inp-name">Your name (optional)</label>
        <input id="inp-name" type="text" placeholder="e.g. The Johnson Family">
      </div>
      <div>
        <label for="inp-time">Hours (optional)</label>
        <input id="inp-time" type="text" placeholder="e.g. 8am – 2pm">
      </div>
      <div class="full">
        <label>What are you selling? *</label>
        <div class="vend-group">
          <button type="button" class="vend-btn active-yard" data-type="yard" onclick="selectVendType('yard')">🏷 Yard Sale Items</button>
          <button type="button" class="vend-btn" data-type="food" onclick="selectVendType('food')">🍽 Food &amp; Drinks</button>
          <button type="button" class="vend-btn" data-type="both" onclick="selectVendType('both')">🏷🍽 Both</button>
        </div>
      </div>
      <div class="full" id="items-section">
        <label for="inp-items">Items for sale — separate with commas</label>
        <textarea id="inp-items" rows="3" placeholder="e.g. furniture, kids clothes, tools, books, electronics, plants"></textarea>
      </div>
      <div class="full" id="food-section" style="display:none;">
        <label for="inp-food">Food &amp; drinks being sold — separate with commas</label>
        <textarea id="inp-food" rows="2" placeholder="e.g. BBQ plates, lemonade, baked goods, tamales"></textarea>
      </div>
    </div>
    <div id="reg-msg"></div>
    <div class="form-actions">
      <button class="btn-primary" id="submit-btn" onclick="registerEntry()">Add to Map</button>
      <button class="btn-cancel" onclick="closeForm()">Cancel</button>
    </div>
  </div>

  <div id="map"></div>

  <div class="map-legend">
    <span style="font-weight:500; color:var(--text);">Map key:</span>
    <span class="legend-item"><span class="legend-dot" style="background:#2C4A2E;"></span> Yard sale</span>
    <span class="legend-item"><span class="legend-dot" style="background:#92400e;"></span> Food &amp; drinks</span>
    <span class="legend-item"><span class="legend-dot" style="background:#4c1d95;"></span> Yard sale + food</span>
  </div>

  <div id="listings-header">Registered Participants</div>
  <div id="listings"></div>
</div>

<!-- Edit/Delete Modal -->
<div id="modal-overlay" onclick="handleModalOverlay(event)">
  <div id="modal-box">
    <button id="modal-close" onclick="closeModal()">×</button>
    <div id="modal-title">Edit entry</div>
    <input type="hidden" id="edit-id">
    <div class="modal-form-grid">
      <div class="full">
        <label>Street address</label>
        <input id="edit-address" type="text">
      </div>
      <div>
        <label>Your name</label>
        <input id="edit-name" type="text">
      </div>
      <div>
        <label>Hours</label>
        <input id="edit-time" type="text">
      </div>
      <div class="full">
        <label>What are you selling?</label>
        <div class="vend-group" style="margin-bottom:0;">
          <button type="button" class="vend-btn" data-etype="yard" onclick="selectEditVendType('yard')">🏷 Yard Sale Items</button>
          <button type="button" class="vend-btn" data-etype="food" onclick="selectEditVendType('food')">🍽 Food &amp; Drinks</button>
          <button type="button" class="vend-btn" data-etype="both" onclick="selectEditVendType('both')">🏷🍽 Both</button>
        </div>
      </div>
      <div class="full" id="edit-items-section">
        <label>Items for sale</label>
        <textarea id="edit-items" rows="3"></textarea>
      </div>
      <div class="full" id="edit-food-section" style="display:none;">
        <label>Food &amp; drinks</label>
        <textarea id="edit-food" rows="2"></textarea>
      </div>
    </div>
    <div class="modal-actions">
      <button class="btn-save" onclick="saveEdit()">Save changes</button>
      <button class="btn-delete-confirm" onclick="showDeleteConfirm()">Delete entry</button>
    </div>
    <div id="delete-confirm">
      <p>Are you sure you want to remove this entry from the map?</p>
      <div class="del-btns">
        <button class="btn-yes-delete" onclick="confirmDelete()">Yes, remove it</button>
        <button class="btn-no-delete" onclick="hideDeleteConfirm()">Cancel</button>
      </div>
    </div>
  </div>
</div>

<footer>Rosedale Park Improvement Association &nbsp;·&nbsp; Centered on 14869 Greenview Rd, Detroit, MI 48223</footer>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
var map, entries = [], markerObjects = [];
var CX = 42.38060, CY = -83.24410;
var currentVendType = 'yard';
var editVendType = 'yard';
var editingId = null;

// ── Map init ──────────────────────────────────────────────
function initMap() {
  map = L.map('map', { center: [CX, CY], zoom: 14 });
  L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager/{z}/{x}/{y}{r}.png', {
    attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>',
    subdomains: 'abcd', maxZoom: 19
  }).addTo(map);
  L.circle([CX, CY], { radius: 3219, color: '#2C4A2E', weight: 2, fillColor: '#4CAF50', fillOpacity: 0.06, dashArray: '8,5' }).addTo(map);
  var ci = L.divIcon({ className:'', html:'<div class="center-marker">📍 14869 Greenview Rd</div>', iconAnchor:[75,10] });
  L.marker([CX, CY], { icon: ci, zIndexOffset: -1 }).addTo(map);
}

// ── Vend type selectors ───────────────────────────────────
function selectVendType(type) {
  currentVendType = type;
  document.querySelectorAll('.vend-btn[data-type]').forEach(function(b) {
    b.className = 'vend-btn' + (b.dataset.type === type ? ' active-' + type : '');
  });
  document.getElementById('items-section').style.display = (type === 'food') ? 'none' : 'block';
  document.getElementById('food-section').style.display  = (type === 'yard') ? 'none' : 'block';
}

function selectEditVendType(type) {
  editVendType = type;
  document.querySelectorAll('.vend-btn[data-etype]').forEach(function(b) {
    b.className = 'vend-btn' + (b.dataset.etype === type ? ' active-' + type : '');
  });
  document.getElementById('edit-items-section').style.display = (type === 'food') ? 'none' : 'block';
  document.getElementById('edit-food-section').style.display  = (type === 'yard') ? 'none' : 'block';
}

// ── Register form ─────────────────────────────────────────
function openForm() {
  document.getElementById('register-panel').style.display = 'block';
  document.getElementById('open-form-btn').style.display = 'none';
  document.getElementById('inp-address').focus();
}

function closeForm() {
  document.getElementById('register-panel').style.display = 'none';
  document.getElementById('open-form-btn').style.display = 'block';
  setMsg('','');
}

function setMsg(text, color) {
  var el = document.getElementById('reg-msg');
  el.textContent = text; el.style.color = color;
  el.style.display = text ? 'block' : 'none';
}

function geocodeAddress(addr, cb) {
  var url = 'https://nominatim.openstreetmap.org/search?format=json&limit=1&countrycodes=us&q=' + encodeURIComponent(addr + ', Detroit, MI');
  fetch(url, { headers: {'Accept-Language':'en'} })
    .then(function(r){ return r.json(); })
    .then(function(d){ d && d.length ? cb(null, +d[0].lat, +d[0].lon) : cb('notfound'); })
    .catch(function(){ cb('error'); });
}

function registerEntry() {
  var addr  = document.getElementById('inp-address').value.trim();
  var name  = document.getElementById('inp-name').value.trim();
  var time  = document.getElementById('inp-time').value.trim();
  var items = document.getElementById('inp-items').value.trim();
  var food  = document.getElementById('inp-food').value.trim();
  if (!addr) { setMsg('Please enter a street address.', '#c0392b'); return; }
  setMsg('','');
  var btn = document.getElementById('submit-btn');
  btn.textContent = 'Locating…'; btn.disabled = true;
  geocodeAddress(addr, function(err, lat, lng) {
    btn.textContent = 'Add to Map'; btn.disabled = false;
    var approx = false;
    if (err) {
      var angle = Math.random()*2*Math.PI, dist = 0.006+Math.random()*0.012;
      lat = CX + dist*Math.cos(angle); lng = CY + dist*Math.sin(angle)*1.3;
      approx = true;
    }
    addEntry({ addr:addr, name:name, time:time, items:items, food:food, vendType:currentVendType, lat:lat, lng:lng, id:Date.now() }, approx);
  });
}

function addEntry(entry, approx) {
  entries.push(entry);
  var marker = createMarker(entry);
  markerObjects.push({ marker:marker, entry:entry });
  updateCount();
  addCard(entry, marker);
  ['inp-address','inp-name','inp-time'].forEach(function(id){ document.getElementById(id).value=''; });
  document.getElementById('inp-items').value='';
  document.getElementById('inp-food').value='';
  if (approx) {
    setMsg('Address not found exactly — placed approximately. Try adding "Detroit, MI".','#b7770d');
    setTimeout(function(){ setMsg('',''); }, 4000);
  } else {
    setMsg('✓ Added to the map!','#2C4A2E');
    setTimeout(closeForm, 1200);
  }
  map.setView([entry.lat, entry.lng], 16);
}

// ── Marker builder ────────────────────────────────────────
function markerClass(vt) {
  return vt === 'food' ? 'food-marker' : vt === 'both' ? 'both-marker' : 'yard-marker';
}
function markerEmoji(vt) {
  return vt === 'food' ? '🍽' : vt === 'both' ? '🏷🍽' : '🏷';
}
function vendLabel(vt) {
  return vt === 'food' ? '🍽 Food & Drinks' : vt === 'both' ? '🏷🍽 Yard Sale + Food' : '🏷 Yard Sale';
}

function createMarker(entry) {
  var shortAddr = entry.addr.split(',')[0];
  var mc = markerClass(entry.vendType);
  var icon = L.divIcon({
    className:'',
    html:'<div class="'+mc+'">'+markerEmoji(entry.vendType)+' '+esc(shortAddr)+'</div>',
    iconAnchor:[0,12]
  });
  var itemList = entry.items ? entry.items.split(',').map(function(s){ return s.trim(); }).filter(Boolean) : [];
  var foodList = entry.food  ? entry.food.split(',').map(function(s){ return s.trim(); }).filter(Boolean) : [];
  var vt = entry.vendType;
  var iwHtml = '<div class="iw"><strong>'+esc(entry.addr)+'</strong>'+
    '<div class="iw-vend '+vt+'">'+vendLabel(vt)+'</div>'+
    ([entry.name, entry.time?'⏰ '+entry.time:''].filter(Boolean).length
      ? '<div class="iw-meta">'+[entry.name,entry.time?'⏰ '+entry.time:''].filter(Boolean).map(esc).join(' · ')+'</div>':'') +
    (itemList.length ? '<div style="font-size:11px;color:#5a6b5a;margin-bottom:3px;">Items:</div><div class="tags">'+itemList.slice(0,6).map(function(i){ return '<span class="tag">'+esc(i)+'</span>'; }).join('')+(itemList.length>6?'<span class="tag">+more</span>':'')+'</div>' : '') +
    (foodList.length ? '<div style="font-size:11px;color:#92400e;margin:'+(itemList.length?'6px':'0')+'px 0 3px;">Food & drinks:</div><div class="tags">'+foodList.slice(0,4).map(function(i){ return '<span class="tag" style="background:#fef3c7;color:#92400e;border-color:#fcd34d;">'+esc(i)+'</span>'; }).join('')+(foodList.length>4?'<span class="tag" style="background:#fef3c7;color:#92400e;border-color:#fcd34d;">+more</span>':'')+'</div>' : '') +
    '</div>';
  var marker = L.marker([entry.lat, entry.lng], { icon:icon }).addTo(map);
  marker.bindPopup(iwHtml, { maxWidth:260 });
  marker.on('click', function(){ marker.openPopup(); });
  return marker;
}

// ── Cards ─────────────────────────────────────────────────
function addCard(entry, marker) {
  document.getElementById('listings-header').style.display='block';
  var div = buildCard(entry, marker);
  document.getElementById('listings').prepend(div);
}

function buildCard(entry, marker) {
  var itemList = entry.items ? entry.items.split(',').map(function(s){ return s.trim(); }).filter(Boolean) : [];
  var foodList = entry.food  ? entry.food.split(',').map(function(s){ return s.trim(); }).filter(Boolean) : [];
  var meta = [entry.name, entry.time?'⏰ '+entry.time:''].filter(Boolean);
  var vt = entry.vendType;

  var div = document.createElement('div');
  div.className = 'listing-card';
  div.id = 'card-'+entry.id;

  var tagsHtml = '';
  if (vt !== 'food' && itemList.length) tagsHtml += itemList.map(function(i){ return '<span class="tag">'+esc(i)+'</span>'; }).join('');
  if (vt !== 'yard' && foodList.length) tagsHtml += foodList.map(function(i){ return '<span class="tag tag-food">🍽 '+esc(i)+'</span>'; }).join('');
  if (!tagsHtml) tagsHtml = '<span class="no-items">No items listed</span>';

  div.innerHTML =
    '<div class="card-top">'+
      '<div class="listing-address">'+esc(entry.addr)+'</div>'+
      '<div class="card-actions">'+
        '<button class="card-btn" onclick="openEdit('+entry.id+')">Edit</button>'+
        '<button class="card-btn delete" onclick="quickDelete('+entry.id+')">Delete</button>'+
      '</div>'+
    '</div>'+
    '<span class="vend-badge '+vt+'">'+vendLabel(vt)+'</span>'+
    (meta.length ? '<div class="listing-meta">'+meta.map(esc).join(' · ')+'</div>' : '')+
    '<div class="tags">'+tagsHtml+'</div>';

  div.addEventListener('click', function(e) {
    if (e.target.classList.contains('card-btn')) return;
    map.setView([entry.lat, entry.lng], 17);
    marker.openPopup();
  });
  return div;
}

// ── Edit modal ────────────────────────────────────────────
function openEdit(id) {
  var obj = findObj(id);
  if (!obj) return;
  var e = obj.entry;
  editingId = id;
  document.getElementById('edit-id').value = id;
  document.getElementById('edit-address').value = e.addr;
  document.getElementById('edit-name').value = e.name;
  document.getElementById('edit-time').value = e.time;
  document.getElementById('edit-items').value = e.items;
  document.getElementById('edit-food').value  = e.food || '';
  selectEditVendType(e.vendType || 'yard');
  document.getElementById('delete-confirm').style.display = 'none';
  document.getElementById('modal-overlay').style.display = 'flex';
}

function closeModal() {
  document.getElementById('modal-overlay').style.display = 'none';
  editingId = null;
}

function handleModalOverlay(e) {
  if (e.target === document.getElementById('modal-overlay')) closeModal();
}

function saveEdit() {
  var obj = findObj(editingId);
  if (!obj) return;
  obj.entry.addr     = document.getElementById('edit-address').value.trim() || obj.entry.addr;
  obj.entry.name     = document.getElementById('edit-name').value.trim();
  obj.entry.time     = document.getElementById('edit-time').value.trim();
  obj.entry.items    = document.getElementById('edit-items').value.trim();
  obj.entry.food     = document.getElementById('edit-food').value.trim();
  obj.entry.vendType = editVendType;

  // Rebuild marker
  map.removeLayer(obj.marker);
  obj.marker = createMarker(obj.entry);

  // Rebuild card
  var oldCard = document.getElementById('card-'+obj.entry.id);
  if (oldCard) {
    var newCard = buildCard(obj.entry, obj.marker);
    oldCard.replaceWith(newCard);
  }
  updateCount();
  closeModal();
}

// ── Delete ────────────────────────────────────────────────
function showDeleteConfirm()  { document.getElementById('delete-confirm').style.display='block'; }
function hideDeleteConfirm()  { document.getElementById('delete-confirm').style.display='none'; }

function confirmDelete() {
  deleteEntry(editingId);
  closeModal();
}

function quickDelete(id) {
  if (confirm('Remove this entry from the map?')) deleteEntry(id);
}

function deleteEntry(id) {
  var obj = findObj(id);
  if (!obj) return;
  map.removeLayer(obj.marker);
  var card = document.getElementById('card-'+id);
  if (card) card.remove();
  entries = entries.filter(function(e){ return e.id !== id; });
  markerObjects = markerObjects.filter(function(o){ return o.entry.id !== id; });
  if (document.getElementById('listings').children.length === 0)
    document.getElementById('listings-header').style.display='none';
  updateCount();
}

// ── Utilities ─────────────────────────────────────────────
function findObj(id) {
  return markerObjects.find(function(o){ return o.entry.id === id; }) || null;
}

function updateCount() {
  var n = entries.length;
  document.getElementById('count-badge').textContent = n+' participant'+(n!==1?'s':'');
  var hasFood = entries.some(function(e){ return e.vendType==='food'||e.vendType==='both'; });
  document.getElementById('food-badge').style.display = hasFood ? 'block' : 'none';
}

function esc(s) {
  return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');
}

window.addEventListener('DOMContentLoaded', initMap);
</script>
</body>
</html>
