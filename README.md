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
            padding: 60px 20px;
            border-bottom: 1px solid var(--border-color);
            max-width: 900px;
            margin: 0 auto 40px auto;
            background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?q=80&w=1200&auto=format&fit=crop');
            background-size: cover;
            background-position: center;
            border-radius: 12px;
            color: #ffffff;
        }

        header h1 {
            font-size: 3.2rem;
            letter-spacing: 2px;
            color: #ffffff;
            font-weight: 800;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        header p {
            color: #e0e0e0;
            margin-top: 10px;
            font-size: 1.1rem;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }

        .card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.06);
        }

        .card-image {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .card-content {
            padding: 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .status-badge {
            align-self: flex-start;
            padding: 4px 10px;
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
            font-size: 1.3rem;
            font-weight: 700;
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
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--accent-color);
            margin-top: auto;
        }

        /* Payment Section */
        .payment-section {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 35px;
            margin-top: 50px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
        }

        .payment-section h3 {
            font-size: 1.6rem;
            margin-bottom: 15px;
            color: var(--accent-color);
        }

        .gopay-box {
            background-color: #f0f7ff;
            border: 1px solid #b3d7ff;
            border-radius: 8px;
            padding: 15px;
            display: inline-block;
            margin: 15px 0;
        }

        .gopay-number {
            font-size: 1.4rem;
            font-weight: bold;
            color: #0066cc;
            letter-spacing: 1px;
        }

        .btn-wa {
            display: inline-block;
            background-color: #25d366;
            color: white;
            text-decoration: none;
            padding: 12px 25px;
            border-radius: 30px;
            font-weight: bold;
            margin-top: 15px;
            transition: background-color 0.2s;
        }

        .btn-wa:hover {
            background-color: #1ebd58;
        }

        .payment-instruction {
            max-width: 550px;
            margin: 15px auto 0 auto;
            font-size: 0.9rem;
            color: #666;
        }

        footer {
            text-align: center;
            margin-top: 60px;
            padding: 25px;
            font-size: 0.85rem;
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
            <div class="card">
                <img class="card-image" src="https://images.unsplash.com/photo-1541167760496-1628856ab772?q=80&w=600&auto=format&fit=crop" alt="Kopi Titik Temu">
                <div class="card-content">
                    <div>
                        <span class="status-badge status-ready">Ready Stock</span>
                        <div class="coffee-name">Kopi Titik Temu</div>
                        <div class="coffee-original">Es Kopi Susu Gula Aren</div>
                        <p class="coffee-desc">Menu signature yang pas buat nemenin diskusi santai atau kerja kelompok bareng temen kelas.</p>
                    </div>
                    <div class="price">Rp 18.000</div>
                </div>
            </div>

            <div class="card">
                <img class="card-image" src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?q=80&w=600&auto=format&fit=crop" alt="Kopi Kejar Tayang">
                <div class="card-content">
                    <div>
                        <span class="status-badge status-ready">Ready Stock</span>
                        <div class="coffee-name">Kopi Kejar Tayang</div>
                        <div class="coffee-original">Caramel Macchiato</div>
                        <p class="coffee-desc">Perpaduan espresso dan sirup karamel yang manis, cocok buat booster fokus pas dapet tugas dadakan.</p>
                    </div>
                    <div class="price">Rp 22.000</div>
                </div>
            </div>

            <div class="card">
                <img class="card-image" src="https://images.unsplash.com/photo-1534778101976-62847782c213?q=80&w=600&auto=format&fit=crop" alt="Kopi Jam Lembur">
                <div class="card-content">
                    <div>
                        <span class="status-badge status-po">Pre-Order (H+1)</span>
                        <div class="coffee-name">Kopi Jam Lembur</div>
                        <div class="coffee-original">Cappuccino</div>
                        <p class="coffee-desc">Rasa kopi yang lebih strong dengan tekstur lembut, pas untuk nemenin kamu yang butuh kafein ekstra.</p>
                    </div>
                    <div class="price">Rp 20.000</div>
                </div>
            </div>
        </div>

        <div class="payment-section">
            <h3>Sistem Pemesanan & Pembayaran</h3>
            <p>Silakan cek status ketersediaan menu di atas terlebih dahulu. Bayar langsung melalui transfer ke nomor GoPay berikut:</p>
            
            <div class="gopay-box">
                <span style="font-size: 0.85rem; color: #555; display: block; margin-bottom: 5px; font-weight: bold;">Nomor GoPay KopiinAja:</span>
                <div class="gopay-number">0812 9254 1637</div>
            </div>

            <p class="payment-instruction">
                Setelah melakukan transfer, mohon klik tombol di bawah ini untuk mengirimkan bukti pembayaran agar pesanan kamu bisa segera diproses.
            </p>

            <a href="https://wa.me/6281292541637?text=Halo%20Admin%20KopiinAja%2C%20saya%20mau%20kirim%20bukti%20pembayaran%20kopi%20saya." class="btn-wa" target="_blank">
                📱 Kirim Bukti Transfer ke WA
            </a>
        </div>
    </div>

    <footer>
        <p>&copy; 2026 KopiinAja. Diproduksi secara higienis dalam kemasan botol praktis.</p>
    </footer>

</body>
</html>
