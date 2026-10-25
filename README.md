I'm a Technical Product Owner and software architect (identity and access
management, fintech). [LinkedIn](https://linkedin.com/in/michal-lemczyk)

These are hobby projects where software meets hardware: I play bass, do
astrophotography, and build tools, firmware and measurement rigs around both.
Much of the recent work is AI-assisted: I set the goals, the acceptance checks
and the design calls, and build with [Claude Code](https://claude.com/claude-code),
with every change verified against real data or real hardware.

## Projects

| project | what it is | built with |
|---|---|---|
| [Vocals Trainer](https://github.com/mlemczyk/Guitar-Pro-Vocal-Trainer) | A browser app for singing along to your own Guitar Pro tabs: the vocal line scrolls as a piano roll with its lyrics, a ball traces the pitch you sing, each note scores hit or miss, and the backing track slows down without changing pitch. [Try it live](https://mlemczyk.github.io/Guitar-Pro-Vocal-Trainer/) | TypeScript, Vite, Web Audio (AudioWorklet), alphaTab, Signalsmith Stretch, pitchy, Vitest, GitHub Pages |
| [Bass Tempo Trainer](https://github.com/mlemczyk/bass-tempo-trainer) | A Windows practice app for two-finger bass speed: a metronome that hears each pluck through one full-duplex audio stream, scores timing and evenness every few bars, and raises the tempo as you hold it | Python, numpy/scipy, sounddevice (WASAPI), PySide6, pyqtgraph, pytest |
| [Celestron CGE OnStepX Conversion](https://github.com/mlemczyk/Celestron-CGE-OnStepX-Conversion) | Rebuilding a classic Celestron CGE mount: geared steppers fitted into enlarged motor housings, OnStepX on a FYSETC E4 inside the pier, and PHD2 Predictive PEC. It guides at 0.88" RMS | Machining and wiring, OnStepX (configured), FYSETC E4 (ESP32), PHD2 |
| [Guitar Pro Utilities](https://github.com/mlemczyk/Guitar-Pro-Utilities) | Python tools for Guitar Pro 8 tabs: parse a tab's bass line with exact timing, align a tab to its real recording (chroma DTW, with a quality gate), embed backing tracks exactly as Guitar Pro does, export MIDI, and predict how hard a part is to play | Python, librosa, numpy/scipy, pytest, GitHub Actions |
| [Telescope PowerBox](https://github.com/mlemczyk/Telescope-Powerbox) | An ASCOM-compatible power meter and two-channel dew-heater controller for a telescope: firmware that meters the rails and drives the heaters from the dew point, a web page, and a Windows ASCOM driver | C++ (Arduino UNO R4 WiFi, PlatformIO), C# (.NET, ASCOM) |
| [Bass Guitar Equipment Analysis](https://github.com/mlemczyk/Bass-Guitar-Equipment-Analysis) | Measured frequency responses, distortion and fitted models of six bass pedals, an onboard preamp and the instrument, made by re-amping test sweeps through each one. Written as benchmark data for people and AI agents | Python, DSP (sine-sweep deconvolution, Wiener–Hammerstein and circuit models), numba |
| [Recording Footswitch](https://github.com/mlemczyk/Recording-Footswitch) | A four-button USB footswitch that drives hands-free recording while playing bass, through AutoHotkey | Arduino (C++), AutoHotkey |

## How I work

- **Find the real problem before fixing it.** The CGE's stock electronics used
  the motor cable shields as ground, a known cause of runaways. I didn't patch
  around it: in the conversion, each motor has its own dedicated ground.
- **Verify, don't assume.** Moving or rewriting code means proving the output
  didn't change: the Guitar Pro tools were checked tab by tab against a
  1,551-tab library, and the backing-track injector against 272 files Guitar
  Pro itself wrote.
- **Test against the real signal, not only the synthetic one.** The tempo
  trainer's pluck detector was tuned on raw bass recordings: on a four-minute
  run up to 216 BPM it cut false extra notes from 11 to 1 and kept every real
  pluck.
- **Measure the equipment, not just the result.** The pedal dataset measures
  the re-amp loop's own distortion and drift, because that once masqueraded as
  a pedal's behaviour. The tempo trainer calibrates its audio round trip with
  a loopback cable, because a played calibration hides the player's own lead
  on the click.
- **Leave documentation agents and people can use.** Most repos have a README for
  people and a `CLAUDE.md` with the rules an AI agent needs to work on it
  safely.
