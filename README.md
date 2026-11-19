
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#5146c8">
  <title>Joki ML — Order</title>
  <style>
    :root { --bg1:#17164b; --bg2:#5146c8; --accent:#7567ef; --ink:#3440a5; }
    * { box-sizing:border-box; }
    body {
      margin:0; min-height:100vh; padding:28px 16px 40px;
      font-family:Inter,system-ui,-apple-system,Segoe UI,sans-serif; color:#fff;
      background:radial-gradient(circle at 15% 5%,#7168ed 0,transparent 32%),
                 linear-gradient(145deg,var(--bg1),#302b83 55%,var(--bg2));
    }
    .wrap { width:min(760px,100%); margin:auto; }
    header { text-align:center; margin:8px 0 26px; }
    .logo { display:inline-grid; place-items:center; width:58px;height:58px;border-radius:19px;
      background:rgba(255,255,255,.16);font-size:28px;box-shadow:0 10px 30px #17164b55; }
    h1 { margin:13px 0 5px; font-size:clamp(28px,6vw,39px); letter-spacing:-1px; }
    .sub { margin:0;color:#d9d7ff;font-size:14px; }
    .panel { background:rgba(255,255,255,.09); border:1px solid rgba(255,255,255,.16);
      border-radius:24px;padding:20px;backdrop-filter:blur(12px);box-shadow:0 18px 45px #100f3b44; }
    .section-title { margin:0 0 14px;font-size:16px; }
    .ranks { display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:11px; }
    .rank {
      border:2px solid transparent;border-radius:16px;background:#fff;color:var(--ink);
      padding:15px 14px;text-align:left;cursor:pointer;transition:.18s ease;min-height:86px;
    }
    .rank:hover { transform:translateY(-2px);box-shadow:0 9px 20px #11104a30; }
    .rank.selected { border-color:#bcb5ff;background:#f1efff;box-shadow:0 0 0 3px #a69eff44; }
    .rank strong { display:block;font-size:16px;margin-bottom:7px; }
    .rank span { font-size:14px;font-weight:700;color:#5146c8; }
    .order { margin-top:18px; }
    label { display:block;font-size:14px;font-weight:650;margin:0 0 8px; }
    input {
      display:block;width:100%;height:54px;border:2px solid #c8c4ff;border-radius:14px;
      padding:0 15px;font:600 18px inherit;color:#29256f;background:#fff;outline:none;
    }
    input:focus { border-color:#a69eff;box-shadow:0 0 0 4px #a69eff33; }
    .hint { color:#d9d7ff;font-size:12px;margin:7px 2px 0; }
    .summary { display:flex;justify-content:space-between;gap:12px;align-items:center;
      background:rgba(255,255,255,.1);border-radius:14px;padding:14px 15px;margin-top:16px; }
    .summary small { color:#d9d7ff;display:block;font-size:12px;margin-bottom:3px; }
    .total { font-size:21px;font-weight:800;white-space:nowrap; }
    .send {
      width:100%;border:0;border-radius:15px;padding:16px;margin-top:14px;
      color:#30277e;background:#fff;font-size:15px;font-weight:800;cursor:pointer;
      box-shadow:0 8px 22px #14104455;transition:.18s;
    }
    .send:hover { transform:translateY(-2px);background:#f0eeff; }
    .send:disabled { opacity:.5;cursor:not-allowed;transform:none; }
    .foot { text-align:center;color:#d1ceff;font-size:12px;margin:17px 0 0;line-height:1.6; }
    @media(min-width:600px){.ranks{grid-template-columns:repeat(4,minmax(0,1fr));}.panel{padding:25px;}}
  </style>
</head>
<body>
  
  <main class="wrap">
    <header>
      <center>
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQuCl0sQ-mZGTGQGLTuD4-Vqvp7t6Bw1pXIyqP_fRfG5Q&s=10" alt="gambar"width="100">
      </center>
       <h1>kirana chan store</h1>
      <h3>store paling jago yah di kirana store</h3>
      <p class="sub">Pilih rank, masukkan jumlah bintang, lalu pesan.</p>
    </header>

    <section class="panel">
      <h2 class="section-title">Pilih harga joki</h2>
      <div class="ranks" id="ranks">
        <button class="rank" type="button" data-name="Master" data-price="1000"><strong>Master</strong><span>Rp1.000 / bintang</span></button>
        <button class="rank" type="button" data-name="GM" data-price="2000"><strong>GM</strong><span>Rp2.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Epik" data-price="3000"><strong>Epik</strong><span>Rp3.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Legend" data-price="4000"><strong>Legend</strong><span>Rp4.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Mythic" data-price="5000"><strong>Mythic</strong><span>Rp5.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Honor" data-price="7000"><strong>Honor</strong><span>Rp7.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Glory" data-price="9000"><strong>Glory</strong><span>Rp9.000 / bintang</span></button>
        <button class="rank" type="button" data-name="Immortal" data-price="11000"><strong>Immortal</strong><span>Rp11.000 / bintang</span></button>
      </div>

      <div class="order">
        <label for="stars">Mau berapa bintang?</label>
        <input id="stars" type="number" inputmode="numeric" min="1" step="1" placeholder="Masukkan angka saja" disabled>
        <p class="hint">Isi jumlah bintang dengan angka, minimal 1.</p>
        <div class="summary">
          <div><small>Pesanan</small><strong id="chosen">Belum pilih rank</strong></div>
          <div style="text-align:right"><small>Total harga</small><div class="total" id="total">Rp0</div></div>
        </div>
        <button class="send" id="send" type="button" disabled>Pesan lewat WhatsApp ↗</button>
      </div>
    </section>
    <p class="foot">Dengan menekan tombol pesan, WhatsApp akan terbuka dengan detail order yang sudah diisi.<br>Pesan belum terkirim sampai kamu menekan tombol Kirim di WhatsApp.</p>
  </main>

  <script>
    const cards = [...document.querySelectorAll('.rank')];
    const starsInput = document.getElementById('stars');
    const chosen = document.getElementById('chosen');
    const totalEl = document.getElementById('total');
    const send = document.getElementById('send');
    let selected = null;
    const rupiah = n => new Intl.NumberFormat('id-ID', {
      style:'currency',currency:'IDR',maximumFractionDigits:0
    }).format(n);

    function update() {
      const count = Number(starsInput.value);
      const valid = selected && Number.isInteger(count) && count > 0;
      chosen.textContent = selected ? `${selected.name} • ${selected.priceLabel}` : 'Belum pilih rank';
      totalEl.textContent = valid ? rupiah(count * selected.price) : 'Rp0';
      send.disabled = !valid;
    }

    cards.forEach(card => card.addEventListener('click', () => {
      cards.forEach(c => c.classList.remove('selected'));
      card.classList.add('selected');
      selected = {
        name:card.dataset.name,
        price:Number(card.dataset.price),
        priceLabel:rupiah(Number(card.dataset.price)) + ' / bintang'
      };
      starsInput.disabled = false;
      starsInput.focus();
      update();
    }));
    starsInput.addEventListener('input', update);
    starsInput.addEventListener('keydown', e => {
      if (['e','E','+','-','.'].includes(e.key)) e.preventDefault();
    });
    send.addEventListener('click', () => {
      const count = Number(starsInput.value);
      if (!selected || !Number.isInteger(count) || count < 1) return;
      const total = count * selected.price;
      const message = `Halo, saya mau order joki Mobile Legends.%0A Rank: ${selected.name}%0A Jumlah bintang: ${count}%0A Harga per bintang: ${rupiah(selected.price)}%0A Total: ${rupiah(total)}`;
      window.open('https://wa.me/6289523320105?text=' + message, '_blank', 'noopener');
    });
  </script>
</body>
</html>
