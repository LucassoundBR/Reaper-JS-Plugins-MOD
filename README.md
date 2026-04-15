# JKK Visualizer (Lucas MOD)

An advanced, highly optimized modification of the original `junkikim-sound/JKK_Visualizer`. This MOD radically improves rendering performance, UI flexibility, and adds new visual processing features while retaining the core audio analysis tools.

## ✨ MOD Exclusive Features

### 1. Dynamic Module Resizing & Toggles
- **Interactive Dividers**: Seamlessly drag the vertical dividers between modules to customize their width in real-time.
- **Active Toggles**: Completely disable or hide modules you don't need via explicit checkboxes in the Editor, freeing up UI space and processing overhead.

### 2. Advanced Theming System
- Replaced the hardcoded color palette with a robust **Theme Preset** selector directly in the Editor window.
- Includes custom presets out of the box: `Cyberpunk`, `Neon Green`, `High Contrast`, and `Default Dark Blue`.

### 3. Optimized DSP & Rendering Performance
- **Blackman-Harris Window**: Replaced standard FFT windowing with Blackman-Harris, resulting in vastly superior frequency isolation and significantly reduced side-lobe bleeding.
- **24kHz Frequency Ceiling**: The FFT loop now intelligently halts processing above 24kHz, removing immense processing waste on sub-Nyquist/ultrasonic noise.
- **Font Cache Stability**: Quantized all ImGui font scaling calls to integers, actively preventing REAPER memory/font cache overflow crashes during scroll or slider adjustments.

### 4. Enhanced Visualizer Stability
- **Scope Trigger Stabilization**: Engineered a zero-crossing trigger detection algorithm that "stills" and stabilizes the waveform display, making it much easier to read rather than constantly drifting.
- **Spectrogram History Preservation**: Completely rewrote the spectrogram rendering using an advanced dual-buffer blitting system. Unlike the original tool (which wiped all visual history completely blank whenever you resized the plugin), this MOD dynamically scales and keeps your rich spectrogram history firmly intact during both horizontal and vertical window resizing.
- **Hover Scroll-Wheel Integration**: Added targeted mouse-wheel bind support directly over modules. You can quickly adjust the specific Gain ratios or zooms of a module simply by hovering over it and scrolling.

### 5. Sample Rate Independence (Restored & Enhanced)
- The Mod inherits the original logic to ensure **Gonio trail lengths** and **Scope sweep speeds** look identical whether your project is 44.1kHz or 96kHz.
- Further optimized FFT hop sizes based on time (ms) to ensure CPU usage remains exceptionally low, even when analyzing high-resolution 192kHz audio.

## 🛠 Installation

1. Copy the `JKK Lucas MOD` folder into your REAPER `Scripts` directory (or wherever you prefer to store custom scripts).
2. Load `action_editor.txt` or `action_visualizer.txt` via REAPER's Action List (`?`).
3. Ensure the `jsfx.txt` routing effect is placed correctly on your track or monitoring FX chain.

---
*Based on the original architecture by Junki Kim.*
