<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KopiinAja - Kopi Botolan Mahasiswa</title>
    <style>
        :root {
            --bg-color: #fdfdfb;
            --main-text: #2d2926;
            --accent-color: #8c6239;
            --card-bg: #ffffff;
            --border-color: #eae7e1;
            --badge-green: #e2f0d9;
            --text-green: #385723;
            --badge-orange: #fff2cc;
            --text-orange: #7f6000;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--main-text);
            line-height: 1.6;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 50px 20px;
            border-bottom: 1px solid var(--border-color);
            max-width: 900px;
            margin: 0 auto 40px auto;
        }

        header h1 {
            font-size: 2.8rem;
            letter-spacing: 2px;
            color: var(--accent-color);
            font-weight: 700;
        }

        header p {
            color: #666;
            margin-top: 8px;
            font-size: 1rem;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: box-shadow 0.2s;
        }

        .card:hover {
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }

        .status-badge {
            align-self: flex-start;
            padding: 3px 10px;
            border-radius: 4px;
            font-size: 0.75rem;
            font-weight: 600;
            margin-bottom: 12px;
        }

        .status-ready {
            background-color: var(--badge-green);
            color: var(--text-green);
        }

        .status-po {
            background-color: var(--badge-orange);
            color: var(--text-orange);
        }

        .coffee-name {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 2px;
            color: #111;
        }

        .coffee-original {
            font-size: 0.8rem;
            color: #999;
            margin-bottom: 10px;
        }

        .coffee-desc {
            font-size: 0.9rem;
            color: #555;
            margin-bottom: 15px;
        }

        .price {
            font-size: 1.15rem;
            font-weight: 700;
            color: var(--accent-color);
        }

        /* Payment Section */
        .payment-section {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 30px;
            margin-top: 40px;
            text-align: center;
        }

        .payment-section h3 {
            font-size: 1.4rem;
            margin-bottom: 8px;
        }

        .qr-placeholder {
            width: 160px;
            height: 160px;
            background: #f0eee9;
            margin: 20px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 6px;
            border: 1px solid #ddd;
        }

        .payment-instruction {
            max-width: 500px;
            margin: 10px auto 0 auto;
            font-size: 0.85rem;
            color: #777;
        }

        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            font-size: 0.8rem;
            color: #999;
            border-top: 1px solid var(--border-color);
        }
    </style>
</head>
<body>

    <header>
        <h1>KopiinAja</h1>
        <p>Kopi botolan penunjang produktivitas dan fokus kuliah kamu.</p>
    </header>

    <div class="container">
        <div class="menu-grid">
            <!-- Varian 1 -->
            <div class="card">
                <div>
                    <span class="status-badge status-ready">Ready Stock</span>
                    <div class="coffee-name">Kopi Titik Temu</div>
                    <div class="coffee-original">Es Kopi Susu Gula Aren</div>
                    <p class="coffee-desc">Menu signature yang pas buat nemenin diskusi santai atau kerja kelompok bareng temen kelas.</p>
                </div>
                <div class="price">Rp 18.000</div>
            </div>

            <!-- Varian 2 -->
            <div class="card">
                <div>
                    <span class="status-badge status-ready">Ready Stock</span>
                    <div class="coffee-name">Kopi Kejar Tayang</div>
                    <div class="coffee-original">Caramel Macchiato</div>
                    <p class="coffee-desc">Perpaduan espresso dan sirup karamel yang manis, cocok buat booster fokus pas dapet tugas dadakan.</p>
                </div>
                <div class="price">Rp 22.000</div>
            </div>

            <!-- Varian 3 -->
            <div class="card">
                <div>
                    <span class="status-badge status-po">Pre-Order (H+1)</span>
                    <div class="coffee-name">Kopi Jam Lembur</div>
                    <div class="coffee-original">Cappuccino</div>
                    <p class="coffee-desc">Rasa kopi yang lebih strong dengan tekstur lembut, pas untuk nemenin kamu yang butuh kafein ekstra.</p>
                </div>
                <div class="price">Rp 20.000</div>
            </div>
        </div>

        <!-- Sistem & Fitur Pembayaran -->
        <div class="payment-section">
            <h3>Sistem Pemesanan</h3>
            <p>Silakan cek status ketersediaan menu di atas. Untuk menu <b>Ready Stock</b> akan langsung dikirim, sedangkan menu <b>Pre-Order</b> akan diproduksi dan dikirim esok hari.</p>
            
            <!-- Box QR Code -->
            <div class="qr-placeholder">
                <div style="text-align: center;">
                    <b style="font-size: 1rem; color: #2d2926;">[ QRIS ]</b><br>
                    <span style="font-size: 0.7 nrem; color: #666; display: block; margin-top: 4px;">Scan untuk Membayar</span>
                </div>
            </div>

            <p class="payment-instruction">
                *Setelah melakukan pembayaran via QRIS, harap simpan bukti transfer dan kirimkan ke WhatsApp admin untuk konfirmasi pengiriman.
            </p>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 KopiinAja. Diproduksi secara higienis dalam kemasan botol praktis.</p>
    </footer>

</body>
</html>