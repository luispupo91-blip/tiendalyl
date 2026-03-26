<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Mi TV Online</title>
    <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
    <style>
        body { background: #000; color: white; font-family: sans-serif; text-align: center; padding: 20px; }
        video { width: 100%; max-width: 900px; border: 2px solid #333; border-radius: 10px; background: #111; }
        h1 { color: #00ffcc; }
        .instruccion { font-size: 0.9em; color: #888; margin-bottom: 20px; }
    </style>
</head>
<body>
    <h1>Reproductor de TV Gratis</h1>
    <p class="instruccion">Cargando señal internacional...</p>
    
    <video id="video" controls autoplay></video>

    <script>
        var video = document.getElementById('video');
        // Este es un canal de ejemplo (Noticias 24h España). Puedes cambiarlo luego.
        var videoSrc = 'https://rtve-live-nogeo.akamaized.net/rtve/24h_lv3_nogeo/playlist.m3u8';

        if (Hls.isSupported()) {
            var hls = new Hls();
            hls.loadSource(videoSrc);
            hls.attachMedia(video);
        } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
            video.src = videoSrc;
        }
    </script>
</body>
</html>
