# Otimizar vídeo para web

O vídeo de **206 MB** é grande demais para a web e causa travamentos. Para uma experiência profissional, o arquivo deve ter **10–30 MB** (para 3–4 minutos).

## Opção 1: FFmpeg (recomendado)

Instale o [FFmpeg](https://ffmpeg.org/download.html) e execute no terminal:

```bash
ffmpeg -i Tech_video.mp4 -c:v libx264 -crf 23 -preset medium -movflags +faststart -vf "scale=-2:720" -c:a aac -b:a 128k Tech_video_otimizado.mp4
```

**O que faz:**
- `-crf 23` – qualidade boa
- `-vf "scale=-2:720"` – 720p (ajuste para 1080 se precisar)
- `-movflags +faststart` – permite começar a reproduzir antes de baixar tudo
- Resultado esperado: ~15–40 MB

## Opção 2: HandBrake (interface gráfica)

1. Baixe [HandBrake](https://handbrake.fr/)
2. Abra o vídeo
3. Preset: **Web** → **Gmail Medium 5 Minutes 480p30**
4. Ou use **Fast 720p30**
5. Marque **Web Optimized** (equivale ao faststart)
6. Exporte e substitua o `Tech_video.mp4`

## Opção 3: YouTube (sem hospedar)

Se o YouTube funcionar na sua rede, use o embed. Ele cuida de streaming e CDN.

---

**Depois de otimizar:** substitua o arquivo em `assets/video/Tech_video.mp4` na hospedagem.
