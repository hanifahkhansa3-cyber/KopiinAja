<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KopiinAja - Kopi Botolan Mahasiswa</title>
    <style>
        :root {
            --bg-color: #ffffff;
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
            max-width: 1000px;
            margin: 0 auto 40px auto;
        }

        header h1 {
            font-size: 3rem;
            letter-spacing: 2px;
            color: var(--accent-color);
            font-weight: 800;
        }

        header p {
            color: #666;
            margin-top: 10px;
            font-size: 1.1rem;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        /* Layout Grid Utama dengan Jarak (Gap) yang Jelas Antar Menu */
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px; 
            margin-top: 20px;
            padding: 10px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-shadow: 0 4px 15px rgba(0,0,0,0.04);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 24px rgba(0,0,0,0.08);
        }

        /* Wadah Gambar dengan Background Putih Bersih */
        .card-image-container {
            width: 100%;
            height: 320px;
            background-color: #ffffff;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            padding: 15px;
            border-bottom: 1px solid var(--border-color);
        }

        .card-image {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        .card-content {
            padding: 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            background-color: #ffffff;
        }

        .status-badge {
            align-self: flex-start;
            padding: 4px 12px;
            border-radius: 6px;
            font-size: 0.75rem;
            font-weight: 600;
            margin-bottom: 14px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
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
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 4px;
            color: #111;
        }

        .coffee-original {
            font-size: 0.85rem;
            color: #888;
            margin-bottom: 12px;
        }

        .coffee-desc {
            font-size: 0.95rem;
            color: #555;
            margin-bottom: 20px;
        }

        .price {
            font-size: 1.35rem;
            font-weight: 700;
            color: var(--accent-color);
            margin-top: auto;
            background-color: #f7f5f0;
            padding: 6px 14px;
            border-radius: 8px;
            display: inline-block;
            align-self: flex-start;
        }

        /* Bagian Sistem Informasi & Pembayaran */
        .payment-section {
            background: #ffffff;
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 40px 20px;
            margin-top: 60px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.03);
        }

        .payment-section h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--accent-color);
            font-weight: 700;
        }

        .payment-section p {
            font-size: 1rem;
            color: #444;
            max-width: 600px;
            margin: 0 auto 20px auto;
        }

        .gopay-box {
            background-color: #f0f7ff;
            border: 1px solid #b3d7ff;
            border-radius: 12px;
            padding: 20px;
            display: inline-block;
            margin: 10px 0 25px 0;
        }

        .gopay-number {
            font-size: 1.6rem;
            font-weight: bold;
            color: #0066cc;
            letter-spacing: 1.5px;
        }

        .btn-wa {
            display: inline-block;
            background-color: #25d366;
            color: white;
            text-decoration: none;
            padding: 14px 35px;
            border-radius: 30px;
            font-weight: bold;
            font-size: 1.05rem;
            box-shadow: 0 4px 12px rgba(37, 211, 102, 0.3);
            transition: background-color 0.2s, transform 0.2s;
        }

        .btn-wa:hover {
            background-color: #1ebd58;
            transform: scale(1.03);
        }

        .payment-instruction {
            max-width: 600px;
            margin: 20px auto 0 auto;
            font-size: 0.9rem;
            color: #777;
            line-height: 1.5;
        }

        footer {
            text-align: center;
            margin-top: 80px;
            padding: 30px 20px;
            font-size: 0.9rem;
            color: #999;
            border-top: 1px solid var(--border-color);
        }
    </style>
</head>
<body>

    <header>
        <h1>KopiinAja</h1>
        <p>Solusi kopi botolan praktis buat nemenin produktivitas harianmu.</p>
    </header>

    <div class="container">
        <div class="menu-grid">
            
            <div class="card">
                <div class="card-image-container">
                    <img class="card-image" src="image_6.png" alt="Kopi Kelas Pagi">
                </div>
                <div class="card-content">
                    <div>
                        <span class="status-badge status-ready">Ready Stock</span>
                        <div class="coffee-name">Kopi Kelas Pagi</div>
                        <div class="coffee-original">Es Kopi Susu Mantap</div>
                        <p class="coffee-desc">Racikan es kopi susu klasik yang creamy dan pas di lidah. Sangat cocok sebagai amunisi andalan penahan kantuk sebelum masuk kelas jam pertama.</p>
                    </div>
                    <div class="price">Rp 12.000</div>
                </div>
            </div>

            <div class="card">
                <div class="card-image-container">
                    <img class="card-image" src="image_6.png" alt="Kopi Kelas Siang">
                </div>
                <div class="card-content">
                    <div>
                        <span class="status-badge status-ready">Ready Stock</span>
                        <div class="coffee-name">Kopi Kelas Siang</div>
                        <div class="coffee-original">Es Kopi Susu Manis Gula Aren</div>
                        <p class="coffee-desc">Sentuhan manis alami gula aren dipadu espresso berkualitas tinggi. Pilihan tepat untuk mengembalikan fokus yang hilang saat siang bolong.</p>
                    </div>
                    <div class="price">Rp 12.000</div>
                </div>
            </div>

            <div class="card">
                <div class="card-image-container">
                    <img class="card-image" src="image_6.png" alt="Kopi Nugas Malam">
                </div>
                <div class="card-content">
                    <div>
                        <span class="status-badge status-po">Pre-Order (H+1)</span>
                        <div class="coffee-name">Kopi Nugas Malam</div>
                        <div class="coffee-original">Es Kopi Susu Creamy Mocca</div>
                        <p class="coffee-desc">Rasa kopi susu dengan paduan cokelat mocca yang tebal dan tekstur lembut. Menemanimu begadang menyelesaikan tumpukan tugas perkuliahan.</p>
                    </div>
                    <div class="price">Rp 12.000</div>
                </div>
            </div>

        </div>

        <div class="payment-section">
            <h3>Sistem Pemesanan & Pembayaran</h3>
            <p>Silakan pastikan status ketersediaan stok produk pada badge menu di atas sebelum memesan. Transaksi pembayaran dapat langsung dikirimkan melalui transfer saldo GoPay:</p>
            
            <div class="gopay-box">
                <span style="font-size: 0.9rem; color: #555; display: block; margin-bottom: 6px; font-weight: bold;">Nomor Resmi GoPay KopiinAja:</span>
                <div class="gopay-number">0812 9254 1637</div>
            </div>

            <p class="payment-instruction">
                Setelah proses transfer berhasil diselesaikan, harap simpan screenshot bukti transaksi dan klik tombol tautan di bawah ini untuk mengirimkannya langsung via chat WhatsApp agar pesanan botolmu segera diproses.
            </p>

            <a href="https://wa.me/6281292541637?text=Halo%20Admin%20KopiinAja%2C%20saya%20ingin%20mengirimkan%20bukti%20pembayaran%20untuk%20pesanan%20kopi%20botol%20saya." class="btn-wa" target="_blank">
                📱 Kirim Bukti Transfer ke WA
            </a>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 KopiinAja. Diproduksi secara higienis dalam kemasan botol praktis tanpa menampilkan informasi data pribadi eksternal.</p>
    </footer>

</body>
</html>
