# Ｖ Ａ Ｐ Ｏ Ｒ Ｐ Ｌ Ａ Ｙ (vaporwave-mp3-exe)

> *play your local songs in style ・ ヴェイパーウェイヴ ・ 1.25x ・ 永遠*

A zero-dependency, single-file browser music player wrapped in a nostalgic Windows 95 / Outrun vaporwave aesthetic. Point it at any local folder on your computer to instantly scan, shuffle, and stream your music locally with pitch-preserved 1.25× playback, real-time frequency visualization, and custom DSP equalization.

---

## ✨ Features

- **🌴 Pure Vaporwave Aesthetics**:
  - Classic Windows 95/98 window frame, bevels, and titlebar (`♫ AESTHETIC.EXE`).
  - Animated outrun sunset with horizontal blinds mask and an endless scrolling perspective 3D neon grid.
  - Glowing LCD display with marquee scrolling song titles and retro monospace typography (`Monoton` and `VT323`).
  - Real-time 48-band canvas spectrum visualizer with a neon cyan-purple-pink gradient.

- **⚡ 1.25× Playback with Pitch Preservation**:
  - Automatically speeds up tracks to 1.25× while preserving the original musical pitch (time-stretching instead of chipmunk pitch-shifting).

- **🎛️ Built-In DSP Smoothing EQ & Dynamics Compressor**:
  - Time-stretching algorithms can thin out low frequencies and introduce metallic, phasey upper-mid artifacts. A tuned 6-band Web Audio filter chain counteracts this:
    - **25 Hz High-pass**: Cleans up subsonic rumble.
    - **110 Hz Low-shelf (+2.5 dB)**: Restores warmth and low-end body.
    - **350 Hz Peaking (-1.0 dB)**: Clears boxiness and muddiness.
    - **2800 Hz Peaking (-2.0 dB)**: Tames stretch warble and harsh edge.
    - **5500 Hz Peaking (-1.5 dB)**: Softens digital sibilance and artifacts.
    - **11000 Hz High-shelf (+1.5 dB)**: Adds sparkle and air.
  - **Soft Dynamics Compressor** (-18 dB threshold, 2.5:1 ratio) glues the master signal together.
  - Instant **EQ bypass checkbox** to toggle DSP filtering on and off.

- **🔒 100% Private & Client-Side**:
  - Files are streamed directly from your local disk using the modern **File System Access API** (`showDirectoryPicker`) with an `<input type="file" webkitdirectory>` fallback.
  - Songs are only opened into memory on demand when played; nothing is ever uploaded to any server or cloud.

- **🔀 Recursive Scan & Infinite Shuffle**:
  - Automatically scans subfolders for all supported audio files.
  - Automatically shuffles on folder selection.
  - Loops forever: when the playlist reaches the end, it reshuffles and keeps playing.
  - Reshuffle button to randomize on demand.

- **🎵 Supported Formats**:
  - `.mp3`, `.m4a`, `.aac`, `.wav`, `.ogg`, `.oga`, `.flac`, `.opus`, `.webm`.

- **📦 Zero Dependencies & No Build Step**:
  - Self-contained inside a single file: [`vaporwave-player.html`](vaporwave-player.html).
  - No `npm install`, bundlers, or local servers required.

---

## 🚀 Getting Started

1. **Download or clone** this repository:
   ```bash
   git clone https://github.com/Ken/vaporwave-mp3-exe.git
   ```
2. **Open the player**:
   - Double-click [`vaporwave-player.html`](vaporwave-player.html) to launch it in your default web browser (Chrome, Edge, Firefox, Brave, Safari, etc.).
3. **Select your music**:
   - Click **📁 ＳＥＬＥＣＴ ＦＯＬＤＥＲ**.
   - Choose any folder on your computer containing audio files.
   - The player will scan, shuffle, and immediately start playing.

---

## 🎛️ Controls & Interface

| Element | Description |
| :--- | :--- |
| **📁 ＳＥＬＥＣＴ ＦＯＬＤＥＲ** | Pick a folder from your disk to scan and start playback |
| **⏮** | Previous track (or restarts track if played > 3 seconds) |
| **▶ / ⏸** | Play / Pause toggle |
| **⏭** | Next track in shuffled queue |
| **🔀 reshuffle** | Randomizes the entire queue and starts playing from index 0 |
| **Progress Bar** | Click anywhere on the progress bar to seek through the track |
| **VOL Slider** | Master volume control |
| **EQ Toggle** | Toggle the custom Web Audio DSP filter chain and compressor |
| **Playlist View** | Scrollable list of all discovered tracks; click any song to jump directly to it |

---

## 🌐 Browser Support

- **Chromium Browsers (Chrome, Edge, Brave, Opera)**: Full support including the File System Access API for smooth folder scanning and low memory usage.
- **Firefox & Safari**: Full support via directory input fallback.

---

## 📄 License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for details.
