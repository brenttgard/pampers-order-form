<html lang="ms">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pampers DryPants — Order Form</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700;800&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --sky: #d0eaf8;
    --sky-mid: #a8d4f0;
    --sky-deep: #5bafd6;
    --sky-dark: #2d7faa;
    --mint: #c8f0e8;
    --mint-deep: #3dbf9f;
    --blush: #fde8ef;
    --blush-deep: #f0a0c0;
    --cream: #fffdf9;
    --white: #ffffff;
    --text: #2c3e50;
    --muted: #7f8c9a;
    --border: #daeef8;
    --success: #2ecc71;
    --shadow: 0 4px 24px rgba(91,175,214,0.13);
    --shadow-hover: 0 8px 32px rgba(91,175,214,0.22);
    --radius: 18px;
    --radius-sm: 10px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Nunito', sans-serif;
    background: linear-gradient(160deg, #e8f6fd 0%, #fde8ef 60%, #e8f8f2 100%);
    min-height: 100vh;
    color: var(--text);
    padding: 0 0 60px;
  }

  /* Header */
  .header {
    background: var(--white);
    border-bottom: 2px solid var(--sky);
    padding: 20px 24px 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .header::before {
    content: '';
    position: absolute;
    top: -30px; left: -30px;
    width: 120px; height: 120px;
    background: var(--sky);
    border-radius: 50%;
    opacity: 0.4;
  }
  .header::after {
    content: '';
    position: absolute;
    bottom: -20px; right: -20px;
    width: 90px; height: 90px;
    background: var(--blush);
    border-radius: 50%;
    opacity: 0.5;
  }
  .header-inner { position: relative; z-index: 1; }
  .brand-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--sky);
    border-radius: 30px;
    padding: 6px 16px;
    font-size: 12px;
    font-weight: 700;
    color: var(--sky-dark);
    letter-spacing: 0.8px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .brand-badge .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--sky-deep);
  }
  .header h1 {
    font-family: 'Quicksand', sans-serif;
    font-size: 26px;
    font-weight: 700;
    color: var(--sky-dark);
    line-height: 1.2;
  }
  .header h1 span { color: var(--blush-deep); }
  .header p {
    font-size: 13px;
    color: var(--muted);
    margin-top: 6px;
  }
  .agent-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--mint);
    border-radius: 20px;
    padding: 5px 14px;
    font-size: 12px;
    font-weight: 700;
    color: var(--mint-deep);
    margin-top: 10px;
  }

  /* Container */
  .container {
    max-width: 480px;
    margin: 0 auto;
    padding: 20px 16px 0;
  }

  /* Section card */
  .card {
    background: var(--white);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 22px 20px;
    margin-bottom: 16px;
    border: 1.5px solid var(--border);
  }
  .card-title {
    font-family: 'Quicksand', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--sky-dark);
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 18px;
    padding-bottom: 12px;
    border-bottom: 1.5px dashed var(--sky);
  }
  .card-title .icon {
    width: 30px; height: 30px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 15px;
    flex-shrink: 0;
  }
  .icon-blue { background: var(--sky); }
  .icon-pink { background: var(--blush); }
  .icon-mint { background: var(--mint); }

  /* Product item */
  .product-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 14px;
    border: 1.5px solid var(--border);
    border-radius: var(--radius-sm);
    margin-bottom: 10px;
    transition: border-color 0.2s, box-shadow 0.2s;
    background: var(--cream);
  }
  .product-item.active {
    border-color: var(--sky-deep);
    box-shadow: 0 0 0 3px rgba(91,175,214,0.12);
    background: #f0f9ff;
  }
  .product-info { flex: 1; }
  .product-name {
    font-weight: 700;
    font-size: 14px;
    color: var(--text);
  }
  .product-size {
    display: inline-block;
    background: var(--sky);
    color: var(--sky-dark);
    font-size: 10px;
    font-weight: 800;
    padding: 2px 8px;
    border-radius: 20px;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-top: 4px;
  }
  .product-price {
    font-size: 12px;
    color: var(--muted);
    margin-top: 3px;
  }
  .qty-control {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .qty-btn {
    width: 32px; height: 32px;
    border: 2px solid var(--sky-mid);
    background: var(--white);
    border-radius: 50%;
    font-size: 18px;
    font-weight: 700;
    color: var(--sky-dark);
    cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.15s;
    line-height: 1;
    padding-bottom: 1px;
  }
  .qty-btn:hover { background: var(--sky); }
  .qty-btn:active { transform: scale(0.92); }
  .qty-input {
    width: 40px;
    text-align: center;
    font-family: 'Nunito', sans-serif;
    font-size: 16px;
    font-weight: 700;
    border: none;
    background: transparent;
    color: var(--text);
  }
  .qty-input::-webkit-inner-spin-button,
  .qty-input::-webkit-outer-spin-button { -webkit-appearance: none; }

  /* Form fields */
  .field { margin-bottom: 14px; }
  label {
    display: block;
    font-size: 13px;
    font-weight: 700;
    color: var(--sky-dark);
    margin-bottom: 6px;
  }
  label .req { color: var(--blush-deep); margin-left: 2px; }
  input[type="text"],
  input[type="tel"],
  textarea {
    width: 100%;
    padding: 12px 14px;
    border: 1.5px solid var(--border);
    border-radius: var(--radius-sm);
    font-family: 'Nunito', sans-serif;
    font-size: 14px;
    color: var(--text);
    background: var(--cream);
    transition: border-color 0.2s, box-shadow 0.2s;
    outline: none;
  }
  input[type="text"]:focus,
  input[type="tel"]:focus,
  textarea:focus {
    border-color: var(--sky-deep);
    box-shadow: 0 0 0 3px rgba(91,175,214,0.14);
    background: var(--white);
  }
  textarea { resize: vertical; min-height: 80px; }

  /* Order summary */
  .summary-empty {
    text-align: center;
    color: var(--muted);
    font-size: 13px;
    padding: 10px 0;
  }
  .summary-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 0;
    font-size: 14px;
    border-bottom: 1px solid var(--border);
  }
  .summary-row:last-child { border-bottom: none; }
  .summary-label { color: var(--muted); font-weight: 600; }
  .summary-val { font-weight: 700; color: var(--text); }
  .summary-total {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 16px;
    background: linear-gradient(90deg, var(--sky) 0%, var(--mint) 100%);
    border-radius: var(--radius-sm);
    margin-top: 12px;
  }
  .summary-total .label {
    font-weight: 800;
    font-size: 14px;
    color: var(--sky-dark);
  }
  .summary-total .amount {
    font-family: 'Quicksand', sans-serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--sky-dark);
  }

  /* Submit button */
  .btn-submit {
    width: 100%;
    padding: 16px;
    background: linear-gradient(135deg, var(--sky-deep) 0%, var(--sky-dark) 100%);
    color: var(--white);
    border: none;
    border-radius: var(--radius);
    font-family: 'Quicksand', sans-serif;
    font-size: 17px;
    font-weight: 700;
    cursor: pointer;
    transition: transform 0.15s, box-shadow 0.15s;
    box-shadow: 0 6px 20px rgba(45,127,170,0.3);
    letter-spacing: 0.3px;
    margin-top: 4px;
  }
  .btn-submit:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 28px rgba(45,127,170,0.38);
  }
  .btn-submit:active { transform: scale(0.98); }
  .btn-submit:disabled {
    opacity: 0.55;
    cursor: not-allowed;
    transform: none;
  }

  /* Config note */
  .config-note {
    background: #fff8e1;
    border: 1.5px solid #ffe082;
    border-radius: var(--radius-sm);
    padding: 12px 14px;
    font-size: 12px;
    color: #7a5c00;
    margin-bottom: 16px;
    line-height: 1.6;
  }
  .config-note strong { display: block; margin-bottom: 4px; font-size: 13px; }
  .config-note code {
    background: rgba(0,0,0,0.07);
    border-radius: 4px;
    padding: 1px 5px;
    font-family: monospace;
    font-size: 11px;
    word-break: break-all;
  }

  /* Success overlay */
  .success-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(255,255,255,0.97);
    z-index: 100;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 30px;
    text-align: center;
    animation: fadeIn 0.3s ease;
  }
  .success-overlay.show { display: flex; }
  @keyframes fadeIn { from { opacity: 0; transform: scale(0.95); } to { opacity: 1; transform: scale(1); } }
  .success-icon {
    width: 90px; height: 90px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--mint) 0%, var(--sky) 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 40px;
    margin-bottom: 22px;
    box-shadow: 0 8px 30px rgba(61,191,159,0.25);
  }
  .success-overlay h2 {
    font-family: 'Quicksand', sans-serif;
    font-size: 24px;
    font-weight: 700;
    color: var(--sky-dark);
    margin-bottom: 10px;
  }
  .success-overlay p {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.6;
    max-width: 280px;
    margin-bottom: 28px;
  }
  .btn-wa {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    width: 100%;
    max-width: 300px;
    padding: 15px;
    background: #25d366;
    color: #fff;
    border: none;
    border-radius: var(--radius);
    font-family: 'Quicksand', sans-serif;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    text-decoration: none;
    margin-bottom: 12px;
    box-shadow: 0 6px 20px rgba(37,211,102,0.3);
    transition: transform 0.15s;
  }
  .btn-wa:hover { transform: translateY(-2px); }
  .btn-wa svg { width: 22px; height: 22px; fill: #fff; }
  .btn-new {
    background: none;
    border: 1.5px solid var(--border);
    border-radius: var(--radius);
    padding: 13px;
    width: 100%;
    max-width: 300px;
    font-family: 'Nunito', sans-serif;
    font-size: 14px;
    font-weight: 700;
    color: var(--muted);
    cursor: pointer;
    transition: border-color 0.2s;
  }
  .btn-new:hover { border-color: var(--sky-mid); color: var(--sky-dark); }

  /* Spinner */
  .spinner {
    display: inline-block;
    width: 18px; height: 18px;
    border: 3px solid rgba(255,255,255,0.4);
    border-top-color: #fff;
    border-radius: 50%;
    animation: spin 0.7s linear infinite;
    vertical-align: middle;
    margin-right: 6px;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  .wa-phone-field { margin-top: 12px; display: none; }
  .wa-phone-field.show { display: block; }
  .wa-phone-label { font-size: 12px; color: var(--muted); margin-bottom: 6px; font-weight: 600; }

  @media (min-width: 520px) {
    .header { padding: 28px 32px 22px; }
    .header h1 { font-size: 30px; }
    .container { padding: 28px 20px 0; }
    .card { padding: 26px 24px; }
  }
</style>
</head>
<body>

<!-- CONFIG: Replace with your Google Apps Script URL -->
<script>
  const SHEET_URL = '(https://script.google.com/macros/s/AKfycbxqgdF_qP8zY_9dDre9KpR1F8kZ898YBvgvWjDvqOs/dev)';
  const WA_NUMBER = '60176883450'; // Replace with your WhatsApp business number (no +)
  const PRICE_PER_PACK = 100;
  const PACKS_PER_UNIT = 4; // RM100 per 4 packs
</script>

<div class="header">
  <div class="header-inner">
    <div class="brand-badge"><span class="dot"></span>Pampers Official<span class="dot"></span></div>
    <h1>DryPants <span>Order Form</span></h1>
    <p>Lengkap, mudah, dan selamat 🌟</p>
    <div id="agentBadge" class="agent-badge" style="display:none;">
      🛍️ Order melalui agent: <strong id="agentLabel"></strong>
    </div>
  </div>
</div>

<div class="container">

  <!-- Product Selection -->
  <div class="card">
    <div class="card-title">
      <div class="icon icon-blue">👶</div>
      Pilih Produk
    </div>

    <div class="product-item" id="item-M">
      <div class="product-info">
        <div class="product-name">Pampers DryPants</div>
        <div class="product-size">Size M</div>
        <div class="product-price">RM100 / 4 pek</div>
      </div>
      <div class="qty-control">
        <button class="qty-btn" onclick="changeQty('M', -1)">−</button>
        <input class="qty-input" type="number" id="qty-M" value="0" min="0" max="99" readonly>
        <button class="qty-btn" onclick="changeQty('M', 1)">+</button>
      </div>
    </div>

    <div class="product-item" id="item-L">
      <div class="product-info">
        <div class="product-name">Pampers DryPants</div>
        <div class="product-size">Size L</div>
        <div class="product-price">RM100 / 4 pek</div>
      </div>
      <div class="qty-control">
        <button class="qty-btn" onclick="changeQty('L', -1)">−</button>
        <input class="qty-input" type="number" id="qty-L" value="0" min="0" max="99" readonly>
        <button class="qty-btn" onclick="changeQty('L', 1)">+</button>
      </div>
    </div>

    <div class="product-item" id="item-XL">
      <div class="product-info">
        <div class="product-name">Pampers DryPants</div>
        <div class="product-size">Size XL</div>
        <div class="product-price">RM100 / 4 pek</div>
      </div>
      <div class="qty-control">
        <button class="qty-btn" onclick="changeQty('XL', -1)">−</button>
        <input class="qty-input" type="number" id="qty-XL" value="0" min="0" max="99" readonly>
        <button class="qty-btn" onclick="changeQty('XL', 1)">+</button>
      </div>
    </div>
  </div>

  <!-- Customer Info -->
  <div class="card">
    <div class="card-title">
      <div class="icon icon-pink">📋</div>
      Maklumat Pelanggan
    </div>
    <div class="field">
      <label>Nama Penuh <span class="req">*</span></label>
      <input type="text" id="cust-name" placeholder="cth: Ahmad bin Abu">
    </div>
    <div class="field">
      <label>Nombor WhatsApp <span class="req">*</span></label>
      <input type="tel" id="cust-phone" placeholder="cth: 0123456789">
    </div>
    <div class="field">
      <label>Alamat Penghantaran <span class="req">*</span></label>
      <textarea id="cust-address" placeholder="No. rumah, jalan, taman, poskod, negeri..."></textarea>
    </div>
    <div class="field">
      <label>Nota Tambahan</label>
      <input type="text" id="cust-notes" placeholder="cth: Hantar sebelum pukul 5 petang">
    </div>
  </div>

  <!-- Order Summary -->
  <div class="card">
    <div class="card-title">
      <div class="icon icon-mint">🧾</div>
      Ringkasan Order
    </div>
    <div id="summary-body">
      <p class="summary-empty">Tiada produk dipilih lagi.</p>
    </div>
    <div class="summary-total">
      <span class="label">Jumlah Bayaran</span>
      <span class="amount" id="summary-total">RM 0.00</span>
    </div>
  </div>

  <button class="btn-submit" id="btnSubmit" onclick="submitOrder()">
    Hantar Order Sekarang
  </button>

</div>

<!-- Success Overlay -->
<div class="success-overlay" id="successOverlay">
  <div class="success-icon">✅</div>
  <h2>Order Berjaya Dihantar!</h2>
  <p id="successMsg">Terima kasih! Kami akan menghubungi anda dalam masa terdekat untuk mengesahkan pesanan.</p>

  <a class="btn-wa" id="btnWA" href="#" target="_blank">
    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
    Hantar via WhatsApp
  </a>
  <button class="btn-new" onclick="resetForm()">+ Buat Order Baru</button>
</div>

<input type="hidden" id="agentId" value="DIRECT">

<script>
  // --- Agent tracking ---
  (function() {
    const params = new URLSearchParams(window.location.search);
    let agent = params.get('agent') || sessionStorage.getItem('agent_id') || 'DIRECT';
    agent = agent.toUpperCase().replace(/[^A-Z0-9]/g, '').slice(0, 20) || 'DIRECT';
    sessionStorage.setItem('agent_id', agent);
    document.getElementById('agentId').value = agent;
    if (agent !== 'DIRECT') {
      document.getElementById('agentLabel').textContent = agent;
      document.getElementById('agentBadge').style.display = 'inline-flex';
    }
  })();

  // --- Quantities ---
  const quantities = { M: 0, L: 0, XL: 0 };

  function changeQty(size, delta) {
    quantities[size] = Math.max(0, quantities[size] + delta);
    document.getElementById('qty-' + size).value = quantities[size];
    document.getElementById('item-' + size).classList.toggle('active', quantities[size] > 0);
    updateSummary();
  }

  // --- Pricing ---
  function calcTotal() {
    const totalPacks = (quantities.M + quantities.L + quantities.XL);
    return totalPacks * PRICE_PER_PACK;
  }

  function updateSummary() {
    const body = document.getElementById('summary-body');
    const totalEl = document.getElementById('summary-total');
    const rows = [];

    ['M', 'L', 'XL'].forEach(size => {
      if (quantities[size] > 0) {
        const subtotal = quantities[size] * PRICE_PER_PACK;
        rows.push(`
          <div class="summary-row">
            <span class="summary-label">DryPants Size ${size} × ${quantities[size]} set</span>
            <span class="summary-val">RM ${subtotal}.00</span>
          </div>`);
      }
    });

    body.innerHTML = rows.length
      ? rows.join('')
      : '<p class="summary-empty">Tiada produk dipilih lagi.</p>';

    const total = calcTotal();
    totalEl.textContent = 'RM ' + total.toFixed(2);
  }

  // --- Validation ---
  function validate() {
    const name = document.getElementById('cust-name').value.trim();
    const phone = document.getElementById('cust-phone').value.trim();
    const address = document.getElementById('cust-address').value.trim();
    const totalPacks = quantities.M + quantities.L + quantities.XL;
    if (totalPacks === 0) { alert('Sila pilih sekurang-kurangnya 1 produk.'); return false; }
    if (!name) { alert('Sila masukkan nama penuh.'); document.getElementById('cust-name').focus(); return false; }
    if (!phone) { alert('Sila masukkan nombor WhatsApp.'); document.getElementById('cust-phone').focus(); return false; }
    if (!address) { alert('Sila masukkan alamat penghantaran.'); document.getElementById('cust-address').focus(); return false; }
    return true;
  }

  // --- Submit ---
  async function submitOrder() {
    if (!validate()) return;

    const btn = document.getElementById('btnSubmit');
    btn.disabled = true;
    btn.innerHTML = '<span class="spinner"></span>Menghantar...';

    const name = document.getElementById('cust-name').value.trim();
    const phone = document.getElementById('cust-phone').value.trim();
    const address = document.getElementById('cust-address').value.trim();
    const notes = document.getElementById('cust-notes').value.trim();
    const agentId = document.getElementById('agentId').value;
    const total = calcTotal();
    const timestamp = new Date().toLocaleString('ms-MY', { timeZone: 'Asia/Kuala_Lumpur' });

    // Build product string
    const products = [];
    if (quantities.M > 0) products.push(`M×${quantities.M}`);
    if (quantities.L > 0) products.push(`L×${quantities.L}`);
    if (quantities.XL > 0) products.push(`XL×${quantities.XL}`);
    const productStr = products.join(', ');

    const payload = {
      timestamp, name, phone, address, notes,
      product: productStr,
      qty_m: quantities.M,
      qty_l: quantities.L,
      qty_xl: quantities.XL,
      total: total,
      agent_id: agentId
    };

    try {
      // POST to Google Apps Script
      await fetch(SHEET_URL, {
        method: 'POST',
        mode: 'no-cors',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(payload)
      });
    } catch (e) {
      // no-cors means we can't read response; proceed to success anyway
    }

    // Build WhatsApp message
    const waMsg = encodeURIComponent(
      `*Order Pampers DryPants* 🍼\n` +
      `──────────────────\n` +
      `Nama: ${name}\n` +
      `No. WA: ${phone}\n` +
      `Alamat: ${address}\n` +
      (notes ? `Nota: ${notes}\n` : '') +
      `──────────────────\n` +
      `Produk: ${productStr}\n` +
      `Jumlah: *RM ${total.toFixed(2)}*\n` +
      `──────────────────\n` +
      (agentId !== 'DIRECT' ? `Agent: ${agentId}\n` : '') +
      `Terima kasih! 🙏`
    );
    document.getElementById('btnWA').href = `https://wa.me/${WA_NUMBER}?text=${waMsg}`;
    document.getElementById('successMsg').textContent =
      `Terima kasih, ${name}! Kami akan menghubungi anda di ${phone} untuk mengesahkan pesanan.`;
    document.getElementById('successOverlay').classList.add('show');

    btn.disabled = false;
    btn.innerHTML = 'Hantar Order Sekarang';
  }

  function resetForm() {
    document.getElementById('successOverlay').classList.remove('show');
    ['M', 'L', 'XL'].forEach(s => {
      quantities[s] = 0;
      document.getElementById('qty-' + s).value = 0;
      document.getElementById('item-' + s).classList.remove('active');
    });
    document.getElementById('cust-name').value = '';
    document.getElementById('cust-phone').value = '';
    document.getElementById('cust-address').value = '';
    document.getElementById('cust-notes').value = '';
    updateSummary();
  }

  updateSummary();
</script>
</body>
</html>
