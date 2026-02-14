# Para-mi-novia-vivi
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Mi Niña ✨</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            /* Usamos la imagen de Gumball como fondo con desenfoque */
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('gumball.jpg') center/cover;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: white;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        /* Cuadrícula de Apps */
        .grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            padding: 50px 20px;
        }

        .app {
            text-align: center;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .app:active { transform: scale(0.9); }

        .icon {
            width: 60px;
            height: 60px;
            border-radius: 15px;
            margin: 0 auto 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(5px);
        }

        .app span { font-size: 12px; text-shadow: 1px 1px 2px black; }

        /* Modal (Ventana Sorpresa) */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.8);
            backdrop-filter: blur(15px);
            justify-content: center;
            align-items: center;
            z-index: 100;
        }

        .modal-content {
            width: 85%;
            max-width: 350px;
            background: white;
            border-radius: 30px;
            padding: 20px;
            color: #333;
            text-align: center;
            animation: zoomIn 0.3s ease;
        }

        @keyframes zoomIn { from {transform: scale(0.5);} to {transform: scale(1);} }

        .modal img { width: 100%; border-radius: 20px; margin-bottom: 15px; }
        .quote { font-style: italic; color: #555; margin-bottom: 15px; }

        /* Barra Inferior */
        .dock {
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(20px);
            margin: 20px;
            border-radius: 25px;
            padding: 15px;
            display: flex;
            justify-content: space-around;
        }
    </style>
</head>
<body>

    <div class="grid">
        <div class="app" onclick="openApp()">
            <div class="icon">❤️</div>
            <span>Abrir</span>
        </div>
        </div>

    <div id="miModal" class="modal" onclick="closeApp()">
        <div class="modal-content" onclick="event.stopPropagation()">
            <img src="anime.jpg" alt="Tú">
            <p class="quote">"¿Estás loco?, sí un poco, pero cancelaría cualquier plan por irme contigo"</p>
            
            <iframe src="https://open.spotify.com/embed/track/1" width="100%" height="80" frameBorder="0" allow="encrypted-media"></iframe>
            
            <button onclick="closeApp()" style="margin-top:15px; border:none; background:#ff4b2b; color:white; padding:10px 20px; border-radius:20px;">Cerrar</button>
        </div>
    </div>

    <div class="dock">
        <div class="icon" style="width:45px; height:45px;">📞</div>
        <div class="icon" style="width:45px; height:45px;">💬</div>
        <div class="icon" style="width:45px; height:45px;">📸</div>
    </div>

    <script>
        function openApp() { document.getElementById('miModal').style.display = 'flex'; }
        function closeApp() { document.getElementById('miModal').style.display = 'none'; }
    </script>
</body>
</html>
