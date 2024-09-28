# Source-Code-Lirik-Lagu
source code lirik lagu menggunakan html dan js
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Just the Way You Are - Bruno Mars</title>
    <style>
        body {
            background-color: #ffe4e1; /* Warna latar belakang */
            color: #333; /* Warna teks */
            font-family: 'Arial', sans-serif; /* Font */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh; /* Tinggi tampilan */
            text-align: center; /* Rata tengah */
        }
        h1 {
            font-size: 2.5em; /* Ukuran judul */
            color: #ff1493; /* Warna judul */
            margin-bottom: 20px; /* Jarak bawah judul */
        }
        #lyrics {
            font-size: 1.5em; /* Ukuran lirik */
            margin-top: 20px; /* Jarak atas lirik */
        }
        .line {
            opacity: 0; /* Awalnya transparan */
            transform: translateY(20px); /* Posisi awal dari bawah */
            animation: slideIn 0.5s forwards; /* Animasi slide-in */
            margin: 10px 0; /* Jarak antara lirik */
        }
        @keyframes slideIn {
            from {
                opacity: 0; /* Transparan */
                transform: translateY(20px); /* Dari bawah */
            }
            to {
                opacity: 1; /* Menjadi terlihat */
                transform: translateY(0); /* Kembali ke posisi normal */
            }
        }
    </style>
</head>
<body>

    <h1>Just the Way You Are</h1>
    <div id="lyrics"></div>

    <script>
        const lyrics = [
            "When I see your face,",
            "There's not a thing that I would change,",
            "Cause you're amazing, just the way you are.",
            "",
            "And when you smile,",
            "The whole world stops and stares for a while,",
            "Cause girl, you're amazing, just the way you are."
        ];

        const lyricsContainer = document.getElementById('lyrics');

        lyrics.forEach((line, index) => {
            setTimeout(() => {
                const lineElement = document.createElement('div');
                lineElement.className = 'line'; // Menambahkan class untuk animasi
                lineElement.innerText = line; // Menambahkan lirik ke elemen
                lineElement.style.animationDelay = `${index * 3}s`; // Delay animasi berdasarkan index
                lyricsContainer.appendChild(lineElement); // Menambahkan elemen ke kontainer
            }, index * 3000); // Jeda 3 detik antara setiap lirik
        });
    </script>

</body>
</html>
