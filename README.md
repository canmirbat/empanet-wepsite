<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EmpaNet - Dünyayı Başkasının Gözünden Görün</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #090a0f;
            --surface: #121520;
            --surface-border: #23293e;
            --primary: #7c3aed;
            --primary-glow: rgba(124, 58, 237, 0.4);
            --accent: #06b6d4;
            --text: #f3f4f6;
            --text-muted: #9ca3af;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header & Nav */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 5%;
            border-bottom: 1px solid var(--surface-border);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
            background: rgba(9, 10, 15, 0.8);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        nav a {
            color: var(--text-muted);
            text-decoration: none;
            margin-left: 2rem;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--text);
        }

        .btn {
            background: linear-gradient(135deg, var(--primary), #4c1d95);
            color: #fff;
            padding: 0.75rem 1.5rem;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            box-shadow: 0 0 15px var(--primary-glow);
            transition: transform 0.2s, box-shadow 0.2s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 25px var(--primary-glow);
        }

        /* Hero Section */
        .hero {
            padding: 8rem 5% 5rem;
            text-align: center;
            max-width: 900px;
            margin: 0 auto;
        }

        .quote {
            color: var(--accent);
            font-size: 1.1rem;
            letter-spacing: 1px;
            margin-bottom: 1rem;
            text-transform: uppercase;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 1.5rem;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2.5rem;
        }

        /* Tech Components Grid */
        .section-title {
            text-align: center;
            font-size: 2rem;
            margin: 5rem 0 2rem;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            padding: 0 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .card {
            background-color: var(--surface);
            border: 1px solid var(--surface-border);
            padding: 2rem;
            border-radius: 12px;
            transition: border-color 0.3s;
        }

        .card:hover {
            border-color: var(--primary);
        }

        .card-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .card h3 {
            margin-bottom: 0.5rem;
        }

        .card p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* Interactive Demo Section */
        .demo-box {
            background: linear-gradient(180deg, var(--surface) 0%, var(--bg) 100%);
            border: 1px solid var(--surface-border);
            border-radius: 16px;
            margin: 5rem 5%;
            padding: 3rem;
            text-align: center;
        }

        .scenario-selector {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .scenario-btn {
            background: var(--bg);
            border: 1px solid var(--surface-border);
            color: var(--text);
            padding: 0.75rem 1.25rem;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .scenario-btn.active, .scenario-btn:hover {
            border-color: var(--accent);
            background: rgba(6, 182, 212, 0.1);
        }

        .experience-preview {
            background: #000;
            border-radius: 12px;
            padding: 3rem;
            border: 1px dashed var(--surface-border);
            margin-top: 1.5rem;
        }

        /* Table Section */
        .table-container {
            padding: 0 5%;
            max-width: 1200px;
            margin: 0 auto 5rem;
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--surface);
            border-radius: 12px;
            overflow: hidden;
        }

        th, td {
            padding: 1.2rem;
            text-align: left;
            border-bottom: 1px solid var(--surface-border);
        }

        th {
            background-color: rgba(255,255,255,0.03);
            color: var(--accent);
        }

        /* Footer */
        footer {
            border-top: 1px solid var(--surface-border);
            padding: 3rem 5%;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 2.2rem; }
            nav { display: none; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">EmpaNet</div>
        <nav>
            <a href="#teknoloji">Teknoloji</a>
            <a href="#kullanim">Kullanım Alanları</a>
            <a href="#ekonomi">İş Modeli</a>
            <a href="#etik">Etik</a>
        </nav>
        <a href="#demo" class="btn">Deneyimi Başlat</a>
    </header>

    <section class="hero">
        <div class="quote">“Dünyayı başkasının gözünden görmek, insan olmanın en ileri halidir.”</div>
        <h1>Empatiyi Sadece Anlama, Birebir Yaşa.</h1>
        <p>EmpaNet; Yapay Zekâ, Sanal Gerçeklik ve Biyolojik Duygu Analizini birleştirerek insan anlayışını yeniden inşa ediyor.</p>
        <a href="#demo" class="btn" style="font-size: 1.1rem; padding: 1rem 2rem;">10 Dakikalık Deneyimi Seç</a>
    </section>

    <h2 class="section-title" id="teknoloji">Teknolojik Mimari</h2>
    <div class="grid">
        <div class="card">
            <div class="card-icon">🧠</div>
            <h3>EmpaVR</h3>
            <p>360° görüntü, 3D uzamsal ses ve haptic feedback ile duyusal gerçekliği tam simülasyon ortamına aktarır.</p>
        </div>
        <div class="card">
            <div class="card-icon">🧬</div>
            <h3>EmpaAI</h3>
            <p>EEG verileri, biyometrik tepkiler ve NLP analizi ile gerçek duygu profillerini matematiksel his setlerine dönüştürür.</p>
        </div>
        <div class="card">
            <div class="card-icon">🌐</div>
            <h3>EmpaNet Cloud</h3>
            <p>Anonimleştirilmiş verilerle küresel empati haritası oluşturarak toplumsal analiz ve strateji desteği sağlar.</p>
        </div>
    </div>

    <section class="demo-box" id="demo">
        <h2>Simülasyon Modülünü Test Edin</h2>
        <p style="color: var(--text-muted);">Aşağıdaki senaryolardan birini seçerek EmpaAI motorunun girdi parametrelerini inceleyin.</p>
        
        <div class="scenario-selector">
            <button class="scenario-btn active" onclick="updateDemo('gorme', this)">Görme Engelli Müzisyen</button>
            <button class="scenario-btn" onclick="updateDemo('multeci', this)">Mülteci Çocuk</button>
            <button class="scenario-btn" onclick="updateDemo('yasli', this)">Yaşlı Birey</button>
        </div>

        <div class="experience-preview" id="demo-content">
            <h3 style="color: var(--accent); margin-bottom: 0.5rem;">Görme Engelli Müzisyen Senaryosu</h3>
            <p id="demo-desc">Görsel akış karartılır. 3D Ses yankı motoru (Echolocation) ve baston titreşim modülü aktif hale getirilir.</p>
            <div style="margin-top: 1.5rem; display: flex; justify-content: center; gap: 2rem; font-size: 0.9rem;">
                <span>STRES ENDEKSİ: <b>%42</b></span>
                <span>ODAKLANMA: <b>%88</b></span>
                <span>EMPATİ POTANSİYELİ: <b>Yüksek</b></span>
            </div>
        </div>
    </section>

    <h2 class="section-title" id="kullanim">Kullanım ve Toplumsal Etki</h2>
    <div class="table-container">
        <table>
            <thead>
                <tr>
                    <th>Sektör / Alan</th>
                    <th>Uygulama Şekli</th>
                    <th>Toplumsal Katkısı</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><b>Eğitim</b></td>
                    <td>Empati müfredatı entegrasyonu, kültürel değişim simülasyonları</td>
                    <td>Öğrencilerde ölçülebilir duygusal zekâ artışı</td>
                </tr>
                <tr>
                    <td><b>Kurumsal IK</b></td>
                    <td>Liderlik ve adil yönetim için psikolojik zorluk deneyimleri</td>
                    <td>Daha adil yönetim ve çalışan desteği</td>
                </tr>
                <tr>
                    <td><b>Toplum & Adalet</b></td>
                    <td>Kamu görevlileri (Polis, Hâkim, Doktor) farkındalık eğitimi</td>
                    <td>Karar süreçlerinde sistemik önyargının azalması</td>
                </tr>
                <tr>
                    <td><b>Rehabilitasyon</b></td>
                    <td>Travma sonrası duygu donması ve duygu eksikliği terapileri</td>
                    <td>Toplumsal entegrasyon ve psikolojik iyileşme</td>
                </tr>
            </tbody>
        </table>
    </div>

    <div style="background: var(--surface); padding: 4rem 5%; text-align: center;" id="etik">
        <h2 style="margin-bottom: 1rem;">Etik & Veri Güvenliği</h2>
        <p style="max-width: 700px; margin: 0 auto; color: var(--text-muted);">
            EmpaNet, duygusal verilerin hassasiyetinin bilincindedir. Tüm biyometrik çıktılar anında anonimleştirilir. Bağımsız Etik Kurulumuz, dramatik sömürüyü engellemek adına her senaryoyu düzenli olarak denetler.
        </p>
    </div>

    <footer>
        <p>&copy; 2026 EmpaNet Inc. Tüm hakları saklıdır. — "Duygu Yoluyla İnsanlık"</p>
    </footer>

    <script>
        function updateDemo(type, btn) {
            document.querySelectorAll('.scenario-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');

            const content = document.getElementById('demo-content');
            if(type === 'gorme') {
                content.innerHTML = `
                    <h3 style="color: var(--accent); margin-bottom: 0.5rem;">Görme Engelli Müzisyen Senaryosu</h3>
                    <p>Görsel akış karartılır. 3D Ses yankı motoru (Echolocation) ve baston titreşim modülü aktif hale getirilir.</p>
                    <div style="margin-top: 1.5rem; display: flex; justify-content: center; gap: 2rem; font-size: 0.9rem;">
                        <span>STRES ENDEKSİ: <b>%42</b></span>
                        <span>ODAKLANMA: <b>%88</b></span>
                        <span>EMPATİ POTANSİYELİ: <b>Yüksek</b></span>
                    </div>`;
            } else if(type === 'multeci') {
                content.innerHTML = `
                    <h3 style="color: var(--accent); margin-bottom: 0.5rem;">Mülteci Çocuk Senaryosu</h3>
                    <p>Ses frekanslarında yüksek desibel filtreleri uygulanır. Kalp ritmi sensörleri panik seviyesini simüle eder.</p>
                    <div style="margin-top: 1.5rem; display: flex; justify-content: center; gap: 2rem; font-size: 0.9rem;">
                        <span>STRES ENDEKSİ: <b>%85</b></span>
                        <span>ADRENALİN: <b>Yüksek</b></span>
                        <span>EMPATİ POTANSİYELİ: <b>Çok Yüksek</b></span>
                    </div>`;
            } else if(type === 'yasli') {
                content.innerHTML = `
                    <h3 style="color: var(--accent); margin-bottom: 0.5rem;">Yaşlı Birey Senaryosu</h3>
                    <p>VR görüntü netliği düşürülür, duyusal tepki sürelerine gecikme eklenir (motor beceri kısıtlaması).</p>
                    <div style="margin-top: 1.5rem; display: flex; justify-content: center; gap: 2rem; font-size: 0.9rem;">
                        <span>STRES ENDEKSİ: <b>%30</b></span>
                        <span>YORULMA HIZI: <b>%75</b></span>
                        <span>EMPATİ POTANSİYELİ: <b>Yüksek</b></span>
                    </div>`;
            }
        }
    </script>
</body>
</html>
