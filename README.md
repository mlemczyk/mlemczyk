These are hobby projects where software meets hardware: I play bass, do
astrophotography, and build tools, firmware and measurement rigs around both.
Much of the recent work is AI-assisted: I set the goals, the acceptance checks
and the design calls, and build with [Claude Code](https://claude.com/claude-code),
with every change verified against real data or real hardware.

## Projects

| project | what it is | built with |
|---|---|---|
| [Guitar Pro Utilities](https://github.com/mlemczyk/Guitar-Pro-Utilities) | Python tools for Guitar Pro 8 tabs: parse a tab's bass line with exact timing, align a tab to its real recording (chroma DTW, with a quality gate), embed backing tracks exactly as Guitar Pro does, export MIDI, and predict how hard a part is to play | Python, librosa, numpy/scipy, pytest, GitHub Actions |
| [Bass Guitar Equipment Analysis](https://github.com/mlemczyk/Bass-Guitar-Equipment-Analysis) | Measured frequency responses, distortion and fitted models of six bass pedals, an onboard preamp and the instrument, made by re-amping test sweeps through each one. Written as benchmark data for people and AI agents | Python, DSP (sine-sweep deconvolution, Wiener–Hammerstein and circuit models), numba |
| [Telescope PowerBox](https://github.com/mlemczyk/Telescope-Powerbox) | An ASCOM-compatible power meter and two-channel dew-heater controller for a telescope: firmware that meters the rails and drives the heaters from the dew point, a web page, and a Windows ASCOM driver | C++ (Arduino UNO R4 WiFi, PlatformIO), C# (.NET, ASCOM) |
| [Recording Footswitch](https://github.com/mlemczyk/Recording-Footswitch) | A four-button USB footswitch that drives hands-free recording while playing bass, through AutoHotkey | Arduino (C++), AutoHotkey |

## How I work

- **Verify, don't assume.** Moving or rewriting code means proving the output
  didn't change: the Guitar Pro tools were checked tab by tab against a
  1,551-tab library, and the backing-track injector against 272 files Guitar
  Pro itself wrote.
- **Measure the equipment, not just the result.** The pedal dataset measures
  the re-amp loop's own distortion and drift, because that once masqueraded as
  a pedal's behaviour.
- **Leave documentation agents and people can use.** Each repo has a README for
  people and a `CLAUDE.md` with the rules an AI agent needs to work on it
  safely.
