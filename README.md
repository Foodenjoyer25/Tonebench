# Tonebench

A music theory workbench in a single HTML file: circle of fifths, cheat sheet, chromatic/voice/guitar tuners, virtual piano, piano chords, scales, modes, chord charts, guitar/ukulele/bass fretboards, guitar scales (44 scales including exotic and jazz scales) and chords, a scale finder, scale and chord formulas, diatonic chords, intervals, a chord transposer and a 16-step beat maker.

No build step and no dependencies. Open `index.html` in a browser. The tuners ask for microphone access; they can also analyze an audio file or run a demo signal.

## Run with Docker

```bash
docker compose up -d --build
```

Then open http://localhost:8080. Without Compose:

```bash
docker build -t tonebench .
docker run -d -p 8080:8080 --name tonebench tonebench
```

The image is nginx (unprivileged, port 8080) serving the single `index.html`, with a health check at `/healthz`.

**Microphone note:** browsers only allow microphone access on `https://` or `localhost`. If you host Tonebench on another machine, put it behind HTTPS (for example a reverse proxy such as Caddy, Traefik or nginx with a certificate) or the tuners will fall back to file analysis and the demo signal.
