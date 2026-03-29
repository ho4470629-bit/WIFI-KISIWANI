<!DOCTYPE html>
<html lang="sw">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>NEXT LEVEL STUDIO | GOLD EDITION</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&family=Poppins:wght@300;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #ffcc00;
            --secondary: #d4af37;
            --bg-dark: #020617;
            --glass: rgba(30, 41, 59, 0.7);
        }

        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: #020617;
            overflow-x: hidden;
            color: #f8fafc;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        /* MFUMO WA VIPUTO (BUBBLES) */
        .bubble {
            position: fixed;
            bottom: -50px;
            background: rgba(255, 204, 0, 0.2);
            border-radius: 50%;
            pointer-events: none;
            animation: rise 8s infinite ease-in;
            z-index: 0;
        }

        @keyframes rise {
            0% { transform: translateY(0) scale(0); opacity: 0; }
            50% { opacity: 0.4; }
            100% { transform: translateY(-110vh) scale(1.2); opacity: 0; }
        }

        /* LOGO SEHEMU YA JUU */
        .header { text-align: center; margin-top: 30px; z-index: 10; }
        .logo-container {
            width: 80px; height: 80px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 18px;
            display: inline-flex; justify-content: center; align-items: center;
            box-shadow: 0 0 25px rgba(255, 204, 0, 0.4);
            transform: rotate(-5deg);
        }
        .logo-text { font-family: 'Orbitron', sans-serif; font-size: 30px; font-weight: 900; color: #000; }

        /* MOVIE GRID ILIYOREKEBISHWA (CENTERED) */
        .movie-section {
            width: 95%;
            max-width: 1200px;
            margin: 40px auto;
            z-index: 10;
        }

        .movie-grid {
            display: grid;
            /* Hapa ndipo marekebisho ya computer yalipo */
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
            gap: 25px;
            justify-content: center; /* Inakausha movie katikati */
            justify-items: center;
        }
        
        .movie-card {
            background: var(--glass);
            border: 1px solid rgba(255, 204, 0, 0.15);
            border-radius: 20px;
            overflow: hidden;
            transition: 0.4s;
            width: 100%;
            max-width: 220px; /* Inazuia poster kuwa kubwa sana kwenye PC */
        }

        .movie-card:hover {
            border-color: var(--primary);
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(255, 204, 0, 0.2);
        }

        .poster-img { width: 100%; height: 280px; object-fit: cover; }
        .details { padding: 15px; text-align: center; }

        /* UZIO UNAOMELEMETA KWA AJILI YA WIFI */
        .premium-border {
            position: relative;
            padding: 4px;
            border-radius: 30px;
            background: linear-gradient(90deg, var(--primary), #ffffff, var(--secondary), #ffffff);
            background-size: 300% 300%;
            animation: glowMove 5s linear infinite;
            margin: 50px 0;
            z-index: 10;
        }

        @keyframes glowMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .wifi-card {
            background: #020617;
            border-radius: 26px;
            padding: 35px;
            width: 340px;
            text-align: center;
        }

        .gold-btn {
            width: 100%; padding: 15px; background: var(--primary);
            color: #000; font-weight: 800; border: none; border-radius: 12px;
            cursor: pointer; margin-top: 15px; font-family: 'Orbitron';
        }

        input, select {
            width: 100%; padding: 12px; margin: 10px 0; border-radius: 10px;
            border: 1px solid rgba(255,204,0,0.3); background: rgba(255,255,255,0.05);
            color: white; box-sizing: border-box;
        }
    </style>
</head>
<body>

    <div class="header">
        <div class="logo-container"><span class="logo-text">NL</span></div>
        <h2 style="color:var(--primary); font-family:'Orbitron'; letter-spacing: 3px;">NEXT LEVEL STUDIO</h2>
    </div>

    <div class="movie-section">
        <div class="movie-grid" id="movieBox">
            </div>
    </div>

    <div class="premium-border">
        <div class="wifi-card">
            <h3 style="margin:0; color:var(--primary); font-family:'Orbitron';">NL WIFI PRO</h3>
            <p style="font-size:11px; color:#888;">Agiza High-Speed Internet Sasa</p>
            
            <input type="text" id="name" placeholder="Jina Kamili">
            <select id="pkg">
                <option value="1000">Siku 1 - TSH 1,000</option>
                <option value="5000">Wiki 1 - TSH 5,000</option>
                <option value="15000">Mwezi 1 - TSH 15,000</option>
            </select>
            
            <button class="gold-btn" onclick="order()">AGIZA SASA</button>
        </div>
    </div>

    <script>
        // Tengeneza viputo
        for (let i = 0; i < 20; i++) {
            let b = document.createElement('div');
            b.className = 'bubble';
            let size = Math.random() * 25 + 5 + 'px';
            b.style.width = size;
            b.style.height = size;
            b.style.left = Math.random() * 100 + 'vw';
            b.style.animationDuration = Math.random() * 4 + 6 + 's';
            b.style.animationDelay = Math.random() * 5 + 's';
            document.body.appendChild(b);
        }

        const movies = [
            { title: "Avatar: Fire and Ash", cat: "SCI-FI", price: "700", img: "https://m.media-amazon.com/images/M/MV5BZDYxY2I1OGMtN2Y4MS00ZmU1LTgyNDAtODA0MzAyYjI0N2Y2XkEyXkFqcGc@._V1_SX800.jpg" },
            { title: "War Machine", cat: "ACTION", price: "700", img: "https://m.media-amazon.com/images/M/MV5BMmM1ZTc5ZTYtOTM2My00MjBmLWE5NzktYzkyYzdlYWE3ZDAzXkEyXkFqcGc@._V1_SX800.jpg" },
            { title: "Border Hunter", cat: "ACTION", price: "500", img: "https://m.media-amazon.com/images/M/MV5BNzU0Njg5MGMtODBhZS00MDAxLWIzMGMtYmRkZDY3NzhiNjY1XkEyXkFqcGc@._V1_SX800.jpg" }
        ];

        const box = document.getElementById('movieBox');
        movies.forEach(m => {
            box.innerHTML += `
                <div class="movie-card">
                    <img src="${m.img}" class="poster-img">
                    <div class="details">
                        <div style="font-size:0.7rem; color:var(--primary); font-weight:bold;">${m.cat}</div>
                        <div style="font-size:0.95rem; font-weight:bold; margin:5px 0; height:40px; overflow:hidden;">${m.title}</div>
                        <div style="color:gold; font-weight:bold; margin-bottom:10px;">TSH ${m.price}</div>
                        <a href="https://wa.me/255768129449?text=Nahitaji Movie: ${m.title}" style="display:block; background:var(--primary); color:black; text-decoration:none; padding:8px; border-radius:8px; font-weight:bold; font-size:0.8rem">NUNUA</a>
                    </div>
                </div>`;
        });

        function order() {
            const n = document.getElementById('name').value;
            const p = document.getElementById('pkg').value;
            if(!n) return alert("Tafadhali jaza jina lako!");
            window.open(`https://wa.me/255768129449?text=Naitwa ${n}, nahitaji kifurushi cha TSH ${p}`);
        }
    </script>
</body>
</html>
