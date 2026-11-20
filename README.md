[README.md](https://github.com/user-attachments/files/35131836/README.md)
<div align="center">

<img src="assets/clipear.png" width="96" alt="CLIPEAR">

# CLIPEAR

**De video largo a clips virales para YouTube Shorts, Instagram Reels y TikTok.**

Pega un link de YouTube o arrastra un video. CLIPEAR encuentra los mejores momentos, les pone
gancho y subtítulos animados, y te deja editarlos en una línea de tiempo estilo CapCut.

**100 % en tu PC · gratis · sin cuentas · sin APIs de pago · acelerado por GPU NVIDIA**

[**⬇ Descargar para Windows**](../../releases/latest) · [Cómo funciona](#cómo-funciona) · [Preguntas](#preguntas-frecuentes)

</div>

---

## ✨ Qué hace

| | |
|---|---|
| 🎯 **Encuentra los mejores momentos** | Transcribe el video palabra por palabra con IA (Whisper) y puntúa miles de tramos por gancho, energía del audio, ritmo, reacciones y el mapa de **"lo más visto"** de YouTube. |
| 🪝 **Revisa el gancho** | Puntúa los primeros segundos de cada clip en 5 propiedades (especificidad, si te habla a ti, lo que está en juego, curiosidad y brevedad) y te dice cómo mejorarlo. Incluye un probador de ganchos. |
| 📱 **Monta en vertical 9:16** | Encuadre automático: sigue la cara si alguien habla a cámara, o pone el gameplay completo sobre un fondo desenfocado. |
| 💬 **Subtítulos animados** | Palabra por palabra, resaltando la que suena. Puedes cambiar el color, el tamaño y cuántas palabras salen a la vez. |
| ✂️ **Corta lo aburrido** | Quita los silencios (pero no los momentos en los que suena el juego o la música) y puede abrir con el clímax del clip. |
| 🎵 **Música con ducking** | La música de fondo baja sola cuando alguien habla. El volumen queda normalizado a −14 LUFS. |
| 🎬 **Editor estilo CapCut** | Línea de tiempo con miniaturas y formas de onda: arrastrar, recortar, dividir, pistas de audio independientes, volumen hasta 200 %, velocidad, fundidos, textos, deshacer y rehacer, y exportar. |
| 📝 **Listo para publicar** | Cada clip trae su título, descripción y hashtags para YouTube, TikTok e Instagram, para copiar con un clic. |

## ⬇ Instalar (Windows 10/11)

1. Descarga **`CLIPEAR-Setup-2.0.0.exe`** desde [Releases](../../releases/latest).
2. Ábrelo y sigue el asistente. **No pide permisos de administrador.**
3. El instalador descarga lo necesario (unos 4 GB y algunos minutos):
   - Python privado (no toca el que ya tengas)
   - FFmpeg
   - la IA de voz
   - CUDA, solo si tienes una tarjeta NVIDIA
4. Abre **CLIPEAR** desde el escritorio.

> Si Windows SmartScreen avisa de que la app no es conocida, pulsa **Más información → Ejecutar de
> todas formas**. Pasa con todo programa nuevo que no tiene firma digital de pago.

**Requisitos:** Windows 10 o 11 de 64 bits, conexión a internet para instalar y ~4 GB libres.
Recomendado: GPU NVIDIA (transcribe 5–10× más rápido). Sin NVIDIA también funciona, usando el
procesador.

## 🚀 Uso

1. **Nuevo:** pega un link (YouTube, Twitch, Kick, TikTok…) o arrastra un `.mp4`, `.mkv` o `.mov`.
   Elige cuántos clips quieres y su duración, y pulsa **Clipear**.
2. **Proyecto:** abre cada clip para reescribir el gancho (se puntúa en vivo), mover el inicio y el
   final, cambiar el encuadre o la música, y copiar el texto para cada red.
3. **Estilo:** color de los subtítulos, tamaño, gancho, encuadre y música de todo el proyecto.
4. **Editor:** une varios clips, añade música en su propia pista y textos, y exporta.
5. Los videos quedan en `%USERPROFILE%\CLIPEAR\proyectos\<video>\salida\`.

**Atajos del editor:** `Espacio` reproducir · `S` dividir · `Supr` eliminar · `Ctrl+D` duplicar ·
`Ctrl+Z / Ctrl+Y` deshacer y rehacer · `← →` mover el cursor · `Ctrl + rueda` zoom.

### Línea de comandos (opcional)

Si marcas la opción en el instalador:

```powershell
clipear todo "https://youtube.com/watch?v=..." --clips 6
clipear renderizar ultimo --solo 1,3
clipear gancho "opción 1" "opción 2"
```

## 🧠 Cómo funciona

```
link o archivo ─▶ yt-dlp ─▶ Whisper (GPU) ─▶ análisis de momentos ─▶ FFmpeg (NVENC) ─▶ clips 9:16
                                │                    │
                       palabras con tiempo    gancho · energía · ritmo ·
                                              reacciones · "lo más visto"
```

Todo se procesa en tu equipo. Solo se usa internet para descargar el video que pegas y, la primera
vez, el modelo de voz.

| Pieza | Para qué |
|---|---|
| [faster-whisper](https://github.com/SYSTRAN/faster-whisper) | Transcripción con marcas de tiempo por palabra |
| [yt-dlp](https://github.com/yt-dlp/yt-dlp) | Descarga de videos |
| [FFmpeg](https://ffmpeg.org) | Cortes, encuadre, subtítulos, mezcla de audio y exportación |
| [OpenCV](https://opencv.org) | Detección de caras para el encuadre automático |
| [pywebview](https://pywebview.flowrl.com) + WebView2 | Ventana de la aplicación |

## ❓ Preguntas frecuentes

**¿Sube algo a YouTube o TikTok?** No. CLIPEAR prepara los clips; tú decides qué publicar.

**¿Sirve para videos sin voz?** No mucho: elige los momentos por lo que se dice. Gameplay sin
comentarios o solo música no da buenos resultados.

**¿Puedo usar música?** Sí, la que tengas derecho a usar (por ejemplo, la Biblioteca de audio de
YouTube). En TikTok y Reels, el sonido en tendencia es mejor añadirlo desde la propia app al subir.

**¿Dónde se guardan mis clips?** En `%USERPROFILE%\CLIPEAR` (se puede cambiar en Ajustes).
Desinstalar no los borra.

**Algo falló al instalar.** Abre **menú Inicio → CLIPEAR (herramientas) → Reparar CLIPEAR**. El
registro queda en `%LOCALAPPDATA%\Programs\CLIPEAR\instalacion.log`.

## ⚖️ Uso responsable

Clipea videos **tuyos** o videos para los que tengas permiso. Descargar y volver a publicar
contenido de otros creadores puede infringir sus derechos y las normas de cada plataforma.

## 🛠 Desarrollo

```
app/
  clipear.py          línea de comandos
  clipper/            motor: config, medios, transcribir, analisis, gancho, render, pipeline, edicion
  gui/main.py         ventana (pywebview) + puente Python⇄interfaz + servidor local de medios
  gui/web/            interfaz: index.html, styles.css, app.js, editor.js, editor.css
installer/
  clipear.iss         instalador (Inno Setup 6)
  setup.ps1           descarga y prepara Python, FFmpeg, librerías, CUDA y el modelo
  hacer_icono.py      genera el icono y las imágenes del instalador
build.ps1             compila dist\CLIPEAR-Setup-<versión>.exe
```

- **Compilar el instalador:** `winget install -e --id JRSoftware.InnoSetup --scope user` y luego
  `powershell -File build.ps1`.
- **Probar la interfaz en el navegador:** sirve `app/gui/web` con cualquier servidor estático; sin la
  app carga datos de ejemplo (`demo.js`).
- **Abrir la app en una vista concreta:** `CLIPEAR_INICIO="proyecto=<nombre>&clip=2"`,
  `CLIPEAR_INICIO="editor=<proyecto>|<id>"` o `CLIPEAR_INICIO=ediciones`. `CLIPEAR_DEBUG=1` abre las
  herramientas de desarrollo.

## 🙏 Créditos

- Las 21 fórmulas de gancho (`app/clipper/hooks.json`) y el método de puntuación vienen de
  [youtube-agent-skill](https://github.com/Jakeschincariol/youtube-agent-skill), de Jake
  Schincariol, bajo licencia MIT.
- Gracias a los proyectos de código abierto listados arriba.
