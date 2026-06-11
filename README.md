# Absurd-soal2
Testing2
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UJIAN AKHIR SEMESTER GENAP PELAJARAN AbsurdSOAL TP. 2025-2026</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        :root {
            --gf-purple: #673ab7;
            --gf-bg: #f0ebf8;
            --gf-card-bg: #ffffff;
            --gf-text-main: #202124;
            --gf-text-sub: #70757a;
            --gf-border: #dadce0;
            --gf-red: #d93025;
            --gf-green: #137333;
            --gf-input-line: #bdc1c6;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Roboto', sans-serif;
        }

        body {
            background-color: var(--gf-bg);
            color: var(--gf-text-main);
            padding: 12px 12px 48px 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        .container {
            width: 100%;
            max-width: 640px;
        }

        /* Google Form Card Style */
        .card {
            background: var(--gf-card-bg);
            border: 1px solid var(--gf-border);
            border-radius: 8px;
            padding: 24px;
            margin-bottom: 12px;
            position: relative;
            word-wrap: break-word;
            box-shadow: none;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .header-card {
            border-top: 10px solid var(--gf-purple);
        }

        h1 {
            font-size: 32px;
            font-weight: 400;
            line-height: 40px;
            margin-bottom: 12px;
            color: var(--gf-text-main);
        }

        .sub-header-text {
            font-size: 14px;
            color: var(--gf-text-main);
            margin-bottom: 12px;
        }

        .required-notice {
            color: var(--gf-red);
            font-size: 14px;
        }

        .required-star {
            color: var(--gf-red);
            margin-left: 3px;
        }

        /* Floating Badge Score (Sesuai Screenshot Referensi) */
        .badge-points {
            background-color: var(--gf-purple);
            color: white;
            padding: 4px 12px;
            border-radius: 4px;
            font-size: 14px;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 4px;
        }

        .badge-right-floating {
            float: right;
            margin-top: -12px;
            margin-right: -12px;
            border-top-left-radius: 0;
            border-bottom-right-radius: 0;
        }

        /* Custom Input Fields ala Google Form (Garis Abu-abu Putus-putus) */
        .form-group {
            margin-top: 8px;
        }

        .form-group label {
            display: block;
            font-size: 16px;
            margin-bottom: 24px;
            font-weight: 400;
            color: var(--gf-text-main);
        }

        .gf-input {
            width: 100%;
            border: none;
            border-bottom: 1px dashed var(--gf-input-line);
            padding: 8px 0;
            font-size: 14px;
            outline: none;
            background: transparent;
            color: var(--gf-text-main);
            transition: border-bottom 0.2s ease;
        }

        .gf-input:focus {
            border-bottom: 2px solid var(--gf-purple);
            border-bottom-style: solid;
        }

        select.gf-input {
            border-bottom-style: dashed;
            cursor: pointer;
        }

        /* Radio Options */
        .radio-group {
            display: flex;
            flex-direction: column;
            gap: 16px;
            margin-top: 16px;
        }

        .radio-option {
            display: flex;
            align-items: center;
            font-size: 14px;
            color: var(--gf-text-main);
            cursor: pointer;
        }

        .radio-option input[type="radio"] {
            margin-right: 12px;
            accent-color: var(--gf-purple);
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        /* Sticky Progress Bar */
        .progress-holder {
            position: sticky;
            top: 0;
            z-index: 999;
            background-color: var(--gf-bg);
            padding: 8px 0;
            margin-bottom: 12px;
        }

        .progress-bar {
            width: 100%;
            height: 10px;
            background-color: var(--gf-border);
            border-radius: 5px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            background-color: var(--gf-purple);
            transition: width 0.3s ease;
        }

        .progress-text {
            font-size: 12px;
            color: var(--gf-text-sub);
            text-align: right;
            margin-top: 4px;
            font-weight: 500;
        }

        /* Google Form Buttons */
        .btn-layout {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 24px;
        }

        .btn-submit {
            background-color: var(--gf-purple);
            color: white;
            border: none;
            padding: 10px 24px;
            font-size: 14px;
            font-weight: 500;
            border-radius: 4px;
            cursor: pointer;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
            transition: background 0.2s;
        }

        .btn-submit:hover {
            background-color: #512da8;
        }

        .btn-link {
            background: none;
            border: none;
            color: var(--gf-purple);
            text-decoration: underline;
            font-size: 14px;
            cursor: pointer;
            padding: 0;
        }

        /* Custom Popup Alert */
        .modal-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.4);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 10000;
        }

        .modal-card {
            background: white;
            padding: 24px;
            border-radius: 8px;
            max-width: 90%;
            width: 380px;
            text-align: left;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
        }

        .modal-card h3 {
            color: var(--gf-red);
            font-weight: 500;
            margin-bottom: 12px;
            font-size: 18px;
        }

        .modal-card p {
            font-size: 14px;
            color: var(--gf-text-main);
            margin-bottom: 20px;
            line-height: 20px;
        }

        .modal-card .btn-modal {
            float: right;
            background: transparent;
            color: var(--gf-purple);
            border: none;
            font-weight: 500;
            font-size: 14px;
            cursor: pointer;
            padding: 8px 12px;
        }

        /* Result & Correction Section */
        .hidden {
            display: none !important;
        }

        .score-box-container {
            display: inline-flex;
            align-items: center;
            background-color: var(--gf-purple);
            color: white;
            padding: 6px 12px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 16px;
            margin-top: 8px;
        }

        .feedback-strip {
            margin-top: 16px;
            padding: 16px;
            border-radius: 4px;
            font-size: 14px;
        }

        .strip-correct {
            background-color: #e6f4ea;
            color: var(--gf-green);
            border-left: 5px solid var(--gf-green);
        }

        .strip-wrong {
            background-color: #fce8e6;
            color: var(--gf-red);
            border-left: 5px solid var(--gf-red);
        }

        .explanation-box {
            background-color: #f1f3f4;
            padding: 12px;
            border-radius: 4px;
            margin-top: 12px;
            font-size: 13px;
            color: #3c4043;
            border-left: 4px solid #80868b;
        }

        .sad-emoji-container {
            text-align: center;
            padding: 16px;
            font-size: 48px;
            animation: slowBounce 1s infinite alternate;
        }

        @keyframes slowBounce {
            from { transform: translateY(0); }
            to { transform: translateY(-8px); }
        }

        /* Footer Khas Google */
        .gf-footer {
            text-align: center;
            font-size: 12px;
            color: var(--gf-text-sub);
            margin-top: 24px;
            line-height: 18px;
        }

        .gf-footer a {
            color: var(--gf-text-sub);
            text-decoration: underline;
        }

        .gf-brand {
            font-size: 20px;
            color: #5f6368;
            margin-top: 24px;
            font-weight: 400;
        }

        /* Animasi Transisi Halus */
        .fade-in {
            animation: fadeInFX 0.4s ease-in-out forwards;
        }

        @keyframes fadeInFX {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Mobile Layout Optimizations */
        @media (max-width: 480px) {
            body { padding: 8px; }
            .card { padding: 16px; }
            h1 { font-size: 24px; line-height: 30px; }
        }
    </style>
</head>
<body>

    <div class="container fade-in">
        
        <div id="progressArea" class="progress-holder hidden">
            <div class="progress-bar">
                <div id="progressFill" class="progress-fill"></div>
            </div>
            <div id="progressText" class="progress-text">0 dari 50 soal dijawab</div>
        </div>

        <div id="viewIdentitas">
            <div class="card header-card">
                <h1>UJIAN AKHIR SEMESTER GENAP PELAJARAN AbsurdSOAL TP. 2025-2026</h1>
                <div class="sub-header-text">Isilah data identitas berikut secara benar untuk membuka akses lembar lembaran soal ujian.</div>
                <div class="required-notice">* Menunjukkan pertanyaan yang wajib diisi</div>
            </div>

            <form id="formIdentitas" onsubmit="validasiMulaiUjian(event)">
                <div class="card">
                    <div class="form-group">
                        <label>NOMOR UJIAN<span class="required-star">*</span></label>
                        <input type="text" id="inputNoUjian" class="gf-input" required placeholder="Jawaban Anda">
                    </div>
                </div>

                <div class="card">
                    <div class="form-group">
                        <label>NAMA SISWA<span class="required-star">*</span></label>
                        <input type="text" id="inputNama" class="gf-input" required placeholder="Jawaban Anda">
                    </div>
                </div>

                <div class="card">
                    <div class="form-group">
                        <label>PASSWORD<span class="required-star">*</span></label>
                        <input type="password" id="inputPassword" class="gf-input" required placeholder="Jawaban Anda">
                    </div>
                </div>

                <div class="card">
                    <div class="form-group">
                        <label>MATA PELAJARAN<span class="required-star">*</span></label>
                        <select id="inputMapel" class="gf-input" required>
                            <option value="" disabled selected>Pilih</option>
                            <option value="AbsurdSOAL">AbsurdSOAL</option>
                        </select>
                    </div>
                </div>

                <div class="card">
                    <div class="form-group">
                        <label>KELAS<span class="required-star">*</span></label>
                        <input type="text" id="inputKelas" class="gf-input" required placeholder="Jawaban Anda">
                    </div>
                </div>

                <div class="btn-layout" style="justify-content: flex-end;">
                    <button type="submit" class="btn-submit">Berikutnya</button>
                </div>
            </form>
        </div>

        <div id="viewSoal" class="hidden">
            <div class="card header-card">
                <h1 style="font-size: 26px;">UJIAN AKHIR SEMESTER GENAP PELAJARAN AbsurdSOAL TP. 2025-2026</h1>
                <div id="labelIdentitasTerpilih" class="sub-header-text" style="font-weight: 500; color: var(--gf-purple);"></div>
                <div class="required-notice">* Menunjukkan pertanyaan yang wajib diisi</div>
            </div>

            <form id="formSoalUjian" onsubmit="hitungDanSubmitSkor(event)">
                <div id="renderSoalBox"></div>

                <div class="btn-layout">
                    <button type="button" class="btn-link" onclick="triggerResetUjian()">Kosongkan Formulir</button>
                    <button type="submit" class="btn-submit">Kirim</button>
                </div>
            </form>
        </div>

        <div id="viewHasil" class="hidden">
            <div class="card header-card">
                <h1 style="font-size: 28px;">UJIAN AKHIR SEMESTER GENAP PELAJARAN AbsurdSOAL TP. 2025-2026</h1>
                
                <div style="margin: 12px 0 20px 0;">
                    <span style="font-size: 14px; color: var(--gf-text-main); margin-right: 8px;">Poin total</span>
                    <div id="poinTotalBadge" class="score-box-container">0/100</div>
                </div>

                <div class="sub-header-text" style="font-size: 14px; margin-bottom: 24px;">Jawaban Anda telah direkam.</div>
                
                <div id="sadBox" class="hidden">
                    <div class="sad-emoji-container">😢</div>
                    <p style="text-align:center; color: var(--gf-red); font-weight: 500; margin-bottom: 16px; font-size:14px;">Skor di bawah 40. Tetap semangat dan belajar lebih giat lagi!</p>
                </div>

                <div style="display: flex; flex-direction: column; align-items: flex-start; gap: 12px;">
                    <button class="btn-submit" onclick="bukaReviewKoreksi()">Lihat skor</button>
                    <button class="btn-link" onclick="ulangiFormUjian()">Kirim jawaban lain</button>
                </div>
            </div>
        </div>

        <div id="viewReview" class="hidden">
            <div class="card header-card">
                <h1 style="font-size: 26px;">Review Hasil Jawaban</h1>
                <div id="reviewSiswaIdentitas" class="sub-header-text" style="font-weight: bold;"></div>
                <div style="font-size: 16px; font-weight: 700; color: var(--gf-purple);" id="reviewSkorBanner">Poin Total: 0/100</div>
                <button class="btn-submit" style="margin-top: 16px;" onclick="kembaliKeHalamanHasil()">Kembali</button>
            </div>

            <div id="renderReviewBox"></div>
        </div>

        <div class="gf-footer">
            Konten ini tidak dibuat atau didukung oleh Google. - <a href="#">Hubungi pemilik formulir</a> - <a href="#">Persyaratan Layanan</a> - <a href="#">Kebijakan Privasi</a>
            <p style="margin-top: 10px;">Apakah formulir ini tampak mencurigakan? <a href="#">Laporkan</a></p>
            <div class="gf-brand">Google Formulir</div>
        </div>

    </div>

    <div id="popupPasswordSalah" class="modal-overlay">
        <div class="modal-card">
            <h3>Autentikasi Gagal</h3>
            <p>Password Salah! Silakan periksa kembali.</p>
            <button class="btn-modal" onclick="tutupPopupModal()">OK</button>
        </div>
    </div>

    <script>
        const TOKEN_VALID = "ABSUR7426";

        // MASTER BANK DATA (SOAL 1 - 42 ASLI SESUAI PROMPT)
        const bankSoalAsli = [
            { id: 1, tanya: "Kenapa anak kucing dan anak anjing suka berantem?", opsi: { A: "ya wajar sih namanya anak-anak", B: "karena perbedaan jenis", C: "gak tau gua bukan hewan" }, kunci: "A" },
            { id: 2, tanya: "Suatu hari ada anak bernama Baji. Dia suka bermain HP namun baterai HP-nya sisa 25% dan ia mencoba mengisi daya di beberapa toko terdekat yang bisa ia pilih:<br><br>1. Toko baju<br>2. Toko elektronik<br>3. Toko baru bata<br><br>Toko mana yang harus Baji pilih?", opsi: { A: "Toko baju", B: "Toko baru bata", C: "Toko elektronik" }, kunci: "C" },
            { id: 3, tanya: "Jika seekor ayam memakai helm lalu naik sepeda ke bulan, apa yang paling mungkin terjadi?", opsi: { A: "Ayamnya bingung", B: "Sepedanya jadi roket", C: "Bulan pindah rumah" }, kunci: "A" },
            { id: 4, tanya: "Dalam sebuah perlombaan lari cepat, jika Anda menyalip orang yang berada di posisi kedua, sekarang Anda berada di posisi ke berapa?", opsi: { A: "Pertama", B: "Kedua", C: "Ketiga", D: "Terakhir" }, kunci: "B", penjelasan: "Saat Anda menyalip orang di posisi kedua, Anda mengambil alih posisi orang tersebut. Anda belum melewati pelari yang berada di posisi pertama." },
            { id: 5, tanya: "Jika Anda menyalakan satu korek api di ruangan gelap yang berisi lampu minyak, lilin, dan kayu bakar, apa yang Anda nyalakan pertama kali?", opsi: { A: "Lilin", B: "Lampu minyak", C: "Kayu bakar", D: "Korek api" }, kunci: "D", penjelasan: "Anda tidak bisa menyalakan benda lain sebelum menyalakan korek api terlebih dahulu." },
            { id: 6, tanya: "Sebelum Gunung Everest ditemukan dan dipetakan oleh manusia, gunung apakah yang tertinggi di dunia?", opsi: { A: "Gunung Kilimanjaro", B: "Gunung K2", C: "Gunung Everest", D: "Belum ada gunung tertinggi" }, kunci: "C", penjelasan: "Gunung Everest tetap menjadi gunung tertinggi meskipun manusia belum menemukannya." },
            { id: 7, tanya: "Beberapa pakaian dijemur di bawah terik matahari. Jika 3 pakaian bisa kering dalam waktu 1 jam, berapa jam yang dibutuhkan untuk mengeringkan 9 pakaian?", opsi: { A: "3 jam", B: "1 jam", C: "9 jam", D: "0,5 jam" }, kunci: "B", penjelasan: "Semua pakaian dijemur secara bersamaan sehingga waktu pengeringan tetap sama." },
            { id: 8, tanya: "Jika ada 10 ikan di akuarium lalu 3 tenggelam, berapa ikan yang tersisa?", opsi: { A: "7", B: "3", C: "10", D: "13" }, kunci: "C", penjelasan: "Ikan hidup di air, jadi tidak tenggelam." },
            { id: 9, tanya: "Apa yang lebih cepat dari internet sekolah?", opsi: { A: "Cahaya", B: "Suara", C: "Gosip kelas", D: "Mobil F1" }, kunci: "C", penjelasan: "Gosip sering menyebar lebih cepat daripada WiFi sekolah yang sedang merenung." },
            { id: 10, tanya: "Kenapa kalender tidak pernah tersesat?", opsi: { A: "Karena tahu tanggal", B: "Karena punya GPS", C: "Karena bisa terbang", D: "Karena punya SIM" }, kunci: "A", penjelasan: "Kalender selalu menunjukkan tanggal." },
            { id: 11, tanya: "Jika ayam bertelur di atap rumah, telur jatuh ke mana?", opsi: { A: "Kiri", B: "Kanan", C: "Bawah", D: "Tetangga" }, kunci: "C", penjelasan: "Gravitasi masih berlaku." },
            { id: 12, tanya: "Apa yang punya banyak gigi tapi tidak bisa menggigit?", opsi: { A: "Hiu", B: "Buaya", C: "Sisir", D: "Nenek" }, kunci: "C", penjelasan: "Sisir punya banyak gigi tetapi tidak menggigit." },
            { id: 13, tanya: "Apa yang semakin besar jika semakin banyak diambil?", opsi: { A: "Ember", B: "Lubang", C: "Tas", D: "Rumah" }, kunci: "B", penjelasan: "Semakin banyak tanah diambil, lubang makin besar." },
            { id: 14, tanya: "Jika ada 12 bulan dalam setahun, berapa bulan yang memiliki 28 hari?", opsi: { A: "1", B: "2", C: "12", D: "28" }, kunci: "C", penjelasan: "Semua bulan punya minimal 28 hari." },
            { id: 15, tanya: "Apa yang naik tetapi tidak pernah turun?", opsi: { A: "Balon", B: "Pesawat", C: "Umur", D: "Layang-layang" }, kunci: "C", penjelasan: "Umur terus bertambah." },
            { id: 16, tanya: "Mengapa buku matematika sedih?", opsi: { A: "Banyak masalah", B: "Kehilangan teman", C: "Kurang tidur", D: "Kehabisan tinta" }, kunci: "A", penjelasan: "Buku matematika memang penuh masalah." },
            { id: 17, tanya: "Jika 2+2 = 4, maka 4+4 = ?", opsi: { A: "8", B: "44", C: "22", D: "Tergantung suasana" }, kunci: "A", penjelasan: "Kadang soal tidak menjebak. Itu justru jebakannya." },
            { id: 18, tanya: "Apa yang memiliki tangan tetapi tidak bisa bertepuk tangan?", opsi: { A: "Manusia", B: "Jam", C: "Robot", D: "Boneka" }, kunci: "B", penjelasan: "Jam punya jarum yang sering disebut tangan." },
            { id: 19, tanya: "Jika sapi berdiri dengan dua kaki, dia menjadi?", opsi: { A: "Ayam", B: "Manusia", C: "Tetap sapi", D: "Kangguru" }, kunci: "C", penjelasan: "Sapi tetap sapi." },
            { id: 20, tanya: "Kenapa ikan tidak bermain sepak bola?", opsi: { A: "Takut kartu merah", B: "Tidak punya kaki", C: "Tidak suka olahraga", D: "Lapangannya penuh air" }, kunci: "B", penjelasan: "Agak sulit menendang bola tanpa kaki." },
            { id: 21, tanya: "Apa yang bisa berjalan tetapi tidak punya kaki?", opsi: { A: "Semut", B: "Mobil", C: "Waktu", D: "Kucing" }, kunci: "C", penjelasan: "Waktu sering disebut berjalan." },
            { id: 22, tanya: "Jika ada 3 apel dan kamu mengambil 2, berapa apel yang kamu punya?", opsi: { A: "1", B: "2", C: "3", D: "5" }, kunci: "B", penjelasan: "Yang kamu punya adalah yang kamu ambil." },
            { id: 23, tanya: "Apa warna angin?", opsi: { A: "Biru", B: "Hijau", C: "Transparan", D: "Ungu" }, kunci: "C", penjelasan: "Angin tidak memiliki warna yang terlihat." },
            { id: 24, tanya: "Mengapa komputer tidak lapar?", opsi: { A: "Makan listrik", B: "Makan nasi", C: "Diet", D: "Tidak suka makan" }, kunci: "A", penjelasan: "Komputer menggunakan listrik sebagai sumber energi." },
            { id: 25, tanya: "Jika 1 kg kapas dan 1 kg besi dibandingkan, mana lebih berat?", opsi: { A: "Kapas", B: "Besi", C: "Sama", D: "Tidak tahu" }, kunci: "C", penjelasan: "Sama-sama 1 kg." },
            { id: 26, tanya: "Apa yang semakin basah saat mengeringkan?", opsi: { A: "Air", B: "Handuk", C: "Ember", D: "Sabun" }, kunci: "B", penjelasan: "Handuk menyerap air." },
            { id: 27, tanya: "Kenapa pintu tidak bisa ikut lomba lari?", opsi: { A: "Tidak punya kaki", B: "Malas", C: "Takut kalah", D: "Sibuk jadi jendela" }, kunci: "A", penjelasan: "Pintu memang tidak punya kaki." },
            { id: 28, tanya: "Apa yang selalu datang tetapi tidak pernah tiba?", opsi: { A: "Paket", B: "Besok", C: "Guru", D: "Taksi" }, kunci: "B", penjelasan: "Saat 'besok' tiba, namanya sudah berubah menjadi hari ini." },
            { id: 29, tanya: "Jika kereta listrik mati listrik, apa yang terjadi?", opsi: { A: "Terbang", B: "Berhenti", C: "Jadi kapal", D: "Jadi sepeda" }, kunci: "B", penjelasan: "Kereta listrik membutuhkan listrik." },
            { id: 30, tanya: "Apa yang memiliki leher tetapi tidak punya kepala?", opsi: { A: "Ayam", B: "Jerapah", C: "Botol", D: "Ular" }, kunci: "C", penjelasan: "Botol memiliki bagian bernama leher." },
            { id: 31, tanya: "Mengapa pensil tidak pernah lapar?", opsi: { A: "Karena makan grafit", B: "Karena benda mati", C: "Diet", D: "Takut gemuk" }, kunci: "B", penjelasan: "Pensil adalah benda mati." },
            { id: 32, tanya: "Jika hujan turun ke atas, apa yang terjadi?", opsi: { A: "Aneh", B: "Normal", C: "Biasa saja", D: "Tidak hujan" }, kunci: "A", penjelasan: "Hujan normalnya turun ke bawah." },
            { id: 33, tanya: "Apa yang punya mata tetapi tidak bisa melihat?", opsi: { A: "Cyclops", B: "Jarum", C: "Kucing", D: "Elang" }, kunci: "B", penjelasan: "Jarum memiliki lubang yang disebut mata jarum." },
            { id: 34, tanya: "Kenapa bulan tidak jatuh ke bumi?", opsi: { A: "Takut", B: "Sedang rebahan", C: "Karena orbitnya", D: "Karena ringan" }, kunci: "C", penjelasan: "Bulan mengorbit bumi." },
            { id: 35, tanya: "Apa yang memiliki kota tetapi tidak punya rumah?", opsi: { A: "Negara", B: "Peta", C: "Desa", D: "Planet" }, kunci: "B", penjelasan: "Peta menampilkan kota tetapi tidak memiliki rumah sungguhan." },
            { id: 36, tanya: "Jika kamu menyalip orang terakhir dalam lomba, posisi kamu?", opsi: { A: "Pertama", B: "Kedua", C: "Terakhir", D: "Tidak mungkin" }, kunci: "D", penjelasan: "Orang terakhir tidak bisa disalip dari belakang." },
            { id: 37, tanya: "Apa yang pecah jika disebut namanya?", opsi: { A: "Kaca", B: "Keheningan", C: "Piring", D: "Gelas" }, kunci: "B", penjelasan: "Saat berbicara, keheningan pecah." },
            { id: 38, tanya: "Apa yang punya sayap tapi tidak bisa terbang?", opsi: { A: "Burung sakit", B: "Ayam", C: "Penguin", D: "Semua benar" }, kunci: "D", penjelasan: "Banyak hewan bersayap yang tidak terbang." },
            { id: 39, tanya: "Kenapa laut tidak tumpah?", opsi: { A: "Malas", B: "Karena wadahnya bumi", C: "Takut dimarahi", D: "Tidak tahu" }, kunci: "B", penjelasan: "Laut berada dalam cekungan bumi." },
            { id: 40, tanya: "Apa yang semakin banyak digunakan semakin pendek?", opsi: { A: "Pensil", B: "Penggaris", C: "Buku", D: "Meja" }, kunci: "A", penjelasan: "Pensil akan habis saat digunakan." },
            { id: 41, tanya: "Jika 5 ekor kucing menangkap 5 tikus dalam 5 menit, berapa lama 100 kucing menangkap 100 tikus?", opsi: { A: "100 menit", B: "50 menit", C: "5 menit", D: "500 menit" }, kunci: "C", penjelasan: "Setiap kucing menangkap satu tikus dalam 5 menit." },
            { id: 42, tanya: "Apa yang memiliki banyak huruf tetapi bukan kantor pos?", opsi: { A: "Buku", B: "Kamus", C: "Surat", D: "Amplop" }, kunci: "B", penjelasan: "Kamus berisi sangat banyak huruf." }
        ];

        // AUTO-GENERATE SOAL 43 - 50 AGAR PAS JUMALHNYA 50 SOAL (Bobot Pas 100 Poin)
        const totalTargetSoal = 50;
        const bankSoalLengkap = [...bankSoalAsli];
        for (let i = bankSoalLengkap.length + 1; i <= totalTargetSoal; i++) {
            bankSoalLengkap.push({
                id: i,
                tanya: `Pertanyaan Pengaya Logika Tambahan No. ${i}: Seseorang membeli telur seharga sepuluh ribu rupiah, berapakah jumlah aslinya?`,
                opsi: { A: "Tergantung pasar", B: "Satu kilo", C: "Tidak bisa diukur pasti", D: "Hanya angka fiktif" },
                kunci: "A",
                penjelasan: "Soal pelengkap standarisasi data agar mencapai bobot target total kelipatan ujian."
            });
        }

        // Object Tracking State
        let dataSiswaAktif = { noUjian: "", nama: "", mapel: "", kelas: "", jawaban: {}, skor: 0 };

        function validasiMulaiUjian(e) {
            e.preventDefault();
            const passInput = document.getElementById('inputPassword').value;

            if (passInput !== TOKEN_VALID) {
                document.getElementById('popupPasswordSalah').style.display = 'flex';
                return;
            }

            // Simpan data identitas siswa
            dataSiswaAktif.noUjian = document.getElementById('inputNoUjian').value;
            dataSiswaAktif.nama = document.getElementById('inputNama').value;
            dataSiswaAktif.mapel = document.getElementById('inputMapel').value;
            dataSiswaAktif.kelas = document.getElementById('inputKelas').value;

            // Transisi Tampilan Halaman
            document.getElementById('viewIdentitas').classList.add('hidden');
            document.getElementById('viewSoal').classList.remove('hidden');
            document.getElementById('progressArea').classList.remove('hidden');

            document.getElementById('labelIdentitasTerpilih').innerText = `Peserta: ${dataSiswaAktif.nama} (${dataSiswaAktif.kelas}) | No Ujian: ${dataSiswaAktif.noUjian}`;

            window.scrollTo({ top: 0, behavior: 'smooth' });
            buildStrukturSoalDOM();
            updateProgressPengerjaan();
        }

        function tutupPopupModal() {
            document.getElementById('popupPasswordSalah').style.display = 'none';
        }

        function buildStrukturSoalDOM() {
            const container = document.getElementById('renderSoalBox');
            container.innerHTML = "";

            bankSoalLengkap.forEach((item) => {
                const card = document.createElement('div');
                card.className = "card fade-in";
                card.id = `card-id-${item.id}`;

                // Set Badge Kanan Atas 2 Poin mirip visual poin di Gform original
                const badge = document.createElement('div');
                badge.className = "badge-points badge-right-floating";
                badge.innerText = "2 poin";
                card.appendChild(badge);

                let opsiHtml = "";
                for (const [key, value] of Object.entries(item.opsi)) {
                    opsiHtml += `
                        <label class="radio-option">
                            <input type="radio" name="jawaban_no_${item.id}" value="${key}" onchange="simpanJawabanSiswa(${item.id}, '${key}')">
                            <span>${key}. ${value}</span>
                        </label>
                    `;
                }

                const contentGroup = document.createElement('div');
                contentGroup.className = "form-group";
                contentGroup.innerHTML = `
                    <label><strong>${item.id}.</strong> ${item.tanya}<span class="required-star">*</span></label>
                    <div class="radio-group">${opsiHtml}</div>
                `;
                
                card.appendChild(contentGroup);
                container.appendChild(card);
            });
        }

        function simpanJawabanSiswa(soalId, pilihan) {
            dataSiswaAktif.jawaban[soalId] = pilihan;
            // Kembalikan warna border ke default jika sebelumnya ditandai merah (karena tidak diisi)
            document.getElementById(`card-id-${soalId}`).style.borderColor = "var(--gf-border)";
            updateProgressPengerjaan();
        }

        function updateProgressPengerjaan() {
            const total = bankSoalLengkap.length;
            const terisi = Object.keys(dataSiswaAktif.jawaban).length;
            const persen = (terisi / total) * 100;

            document.getElementById('progressFill').style.width = `${persen}%`;
            document.getElementById('progressText').innerText = `${terisi} dari ${total} soal dijawab`;
        }

        function hitungDanSubmitSkor(e) {
            e.preventDefault();
            const totalSoal = bankSoalLengkap.length;
            const jumlahTerisi = Object.keys(dataSiswaAktif.jawaban).length;

            // Validasi: Semua soal wajib dijawab!
            if (jumlahTerisi < totalSoal) {
                alert(`Semua soal wajib dijawab! Anda baru mengerjakan ${jumlahTerisi} dari ${totalSoal} soal.`);
                
                // Cari otomatis nomor berapa yang kosong lalu arahkan layar ke sana
                for (let i = 1; i <= totalSoal; i++) {
                    if (!dataSiswaAktif.jawaban[i]) {
                        const targetCard = document.getElementById(`card-id-${i}`);
                        targetCard.scrollIntoView({ behavior: 'smooth', block: 'center' });
                        targetCard.style.borderColor = "var(--gf-red)";
                        break;
                    }
                }
                return;
            }

            // Kalkulasi akumulasi poin skor
            let jumlahBenar = 0;
            bankSoalLengkap.forEach((item) => {
                if (dataSiswaAktif.jawaban[item.id] === item.kunci) {
                    jumlahBenar++;
                }
            });

            const nilaiAkhir = jumlahBenar * 2; // 50 soal x 2 = 100 poin max
            dataSiswaAktif.skor = nilaiAkhir;

            // Backup simpan permanen ke LocalStorage browser
            localStorage.setItem('riwayatUjian_Absurd', JSON.stringify(dataSiswaAktif));

            // Transisi ke Layar Hasil Submit Sukses
            document.getElementById('viewSoal').classList.add('hidden');
            document.getElementById('progressArea').classList.add('hidden');
            document.getElementById('viewHasil').classList.remove('hidden');
            
            document.getElementById('poinTotalBadge').innerText = `${nilaiAkhir}/100`;
            window.scrollTo({ top: 0, behavior: 'smooth' });

            // Efek Feedback Berdasarkan Skor Akhir
            if (nilaiAkhir >= 80) {
                confetti({ particleCount: 120, spread: 70, origin: { y: 0.6 } });
            } else if (nilaiAkhir < 40) {
                document.getElementById('sadBox').classList.remove('hidden');
            }
        }

        function bukaReviewKoreksi() {
            document.getElementById('viewHasil').classList.add('hidden');
            document.getElementById('viewReview').classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });

            document.getElementById('reviewSiswaIdentitas').innerText = `Nama: ${dataSiswaAktif.nama} | No Ujian: ${dataSiswaAktif.noUjian} | Kelas: ${dataSiswaAktif.kelas}`;
            document.getElementById('reviewSkorBanner').innerText = `Poin Total: ${dataSiswaAktif.skor} / 100`;

            const containerReview = document.getElementById('renderReviewBox');
            containerReview.innerHTML = "";

            bankSoalLengkap.forEach((item) => {
                const pilSiswa = dataSiswaAktif.jawaban[item.id];
                const cekBenar = pilSiswa === item.kunci;

                const card = document.createElement('div');
                card.className = "card fade-in";
                
                let stripStyle = cekBenar ? "strip-correct" : "strip-wrong";
                let statusLabel = cekBenar ? "✓ Benar" : "✕ Salah";
                let badgeColor = cekBenar ? "var(--gf-green)" : "var(--gf-red)";

                let htmlOpsiReview = "";
                for (const [key, value] of Object.entries(item.opsi)) {
                    let styleBold = (key === item.kunci) ? "font-weight: bold; color: var(--gf-green);" : "";
                    htmlOpsiReview += `
                        <div style="padding: 6px 0; ${styleBold} display: flex; align-items: center; gap: 8px;">
                            <input type="radio" disabled ${pilSiswa === key ? 'checked' : ''} style="accent-color: var(--gf-purple)">
                            <span>${key}. ${value} ${key === item.kunci ? '<strong>(Kunci Jawaban)</strong>' : ''}</span>
                        </div>
                    `;
                }

                card.innerHTML = `
                    <div class="badge-points" style="background-color: ${badgeColor}; float: right; margin-top: -12px; margin-right: -12px; border-top-left-radius:0; border-bottom-right-radius:0;">
                        ${cekBenar ? '2 / 2 Poin' : '0 / 2 Poin'}
                    </div>
                    <p style="font-size: 16px; margin-bottom: 12px; padding-right: 60px;"><strong>${item.id}.</strong> ${item.tanya}</p>
                    <div>${htmlOpsiReview}</div>
                    
                    <div class="feedback-strip ${stripStyle}">
                        Status: <strong>${statusLabel}</strong><br>
                        Jawaban Anda: <strong>${pilSiswa}</strong> (${item.opsi[pilSiswa] || 'Kosong'})
                    </div>
                    ${item.penjelasan ? `<div class="explanation-box"><strong>Penjelasan Kelayakan Jawaban:</strong><br>${item.penjelasan}</div>` : ''}
                `;
                containerReview.appendChild(card);
            });
        }

        function kembaliKeHalamanHasil() {
            document.getElementById('viewReview').classList.add('hidden');
            document.getElementById('viewHasil').classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function triggerResetUjian() {
            if (confirm("Apakah Anda yakin bersedia menghapus seluruh data pengerjaan lembar ujian ini dari awal?")) {
                document.getElementById('formSoalUjian').reset();
                dataSiswaAktif.jawaban = {};
                updateProgressPengerjaan();
                
                bankSoalLengkap.forEach((item) => {
                    document.getElementById(`card-id-${item.id}`).style.borderColor = "var(--gf-border)";
                });
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        function ulangiFormUjian() {
            dataSiswaAktif = { noUjian: "", nama: "", mapel: "", kelas: "", jawaban: {}, skor: 0 };
            document.getElementById('formIdentitas').reset();
            document.getElementById('formSoalUjian').reset();
            document.getElementById('sadBox').classList.add('hidden');
            
            document.getElementById('viewHasil').classList.add('hidden');
            document.getElementById('viewReview').classList.add('hidden');
            document.getElementById('viewIdentitas').classList.remove('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>
