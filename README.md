[README.md](https://github.com/user-attachments/files/25776594/README.md)
# ⬡ Smart Piano

A browser-based intelligent piano. Hold a chord with your left hand, play melody with your right — notes automatically snap to the nearest chord tone so you almost can't play a wrong note. No installation, no server, no music theory required.

---

## Quick Start

Open `smart-piano.html` in any modern browser (Chrome recommended). Click **▶ Start Audio** to initialize the sound engine. Sampled instruments load in the background — buttons show `…` while loading, `✓` when ready. Switch the interface language with the **EN / 中文** button in the top bar.

---

## Key Map

### Left Hand — Chords

| Key | Chord |
|-----|-------|
| C | C major |
| D | D major |
| E | E major |
| F | F major |
| G | G major |
| A | A major |
| B | B major |

| Modifier | Effect |
|----------|--------|
| Hold **S** + chord key | Minor chord |
| Hold **Q** + chord key | Dominant 7th |
| Hold **W** + chord key | Flat root — e.g. B+W = B♭ |
| **M** | Strum current chord |
| **N** | Arpeggio (cycle through chord tones) |

### Right Hand — Melody

| Key | Note |
|-----|------|
| H | Do (C) |
| J | Re (D) |
| K | Mi (E) |
| L | Fa (F) |
| ; | So (G) |
| ' | La (A) |
| Enter | Ti (B) |
| O | High Do (C↑) |

**Black keys:** U = ♯Do · I = ♯Re · P = ♯Fa · [ = ♯So · ] = ♯La

### Smart Snapping

When the left hand holds a chord, right-hand notes snap to the nearest chord tone — multiple equidistant tones all play at once. When no chord is held, the right hand plays freely at its natural pitch.

### Arpeggio Modes (N key)

Switch modes with **1 / 2 / 3 / 4**. Current mode shown in the status bar.

| Key | Mode | Example (C major) |
|-----|------|-------------------|
| 1 | Up | C → E → G → C↑ |
| 2 | Root Jump | C → C↑ → E → G |
| 3 | Up-Down | C → E → G → C↑ → G → E |
| 4 | Skip (root interleaved) | C → E → C → G → C → C↑ |

For roots F♯ and above (G, A, B…), the sequence starts one octave lower so it always ascends naturally — e.g. G major: low G → low B → D → G.

Dominant 7th chords use 4 tones with no added high root (C7: C → E → G → B♭).

### Function Keys

| Key | Function |
|-----|----------|
| Space | Sustain on / off |
| . | Octave up |
| , | Octave down |
| V | Transpose up 1 semitone |
| X | Transpose down 1 semitone |
| T | Drum tempo: off → 80 → 100 → 120 BPM |
| R | Cycle drum pattern (3 patterns) |

---

## Instruments

All instruments use real audio samples from the **MusyngKite** soundfont, loaded from CDN on first use. Falls back to the built-in synthesizer if the network is unavailable.

| Button | Instrument |
|--------|-----------|
| 🎹 Piano | Acoustic grand piano |
| 🎸 Guitar | Nylon string acoustic guitar |
| ⚡ E.Guitar | Clean electric guitar |
| 🎵 Flute | Concert flute |
| 🎺 Organ | Rock organ |
| 🪘 Marimba | Marimba |
| 🎻 Strings | String ensemble |
| 🌀 Synth | Web Audio synthesis (offline fallback) |

---

## Drum Machine

**T** cycles tempo: off / 80 / 100 / 120 BPM
**R** cycles 3 patterns:
- Pattern 1 — Standard 4/4 with crash on beat 1
- Pattern 2 — Syncopated kick, dense hi-hat, rim shots
- Pattern 3 — Clap layers + tom fills

All drum sounds are synthesized via Web Audio API (kick, snare, hi-hat open/closed, rim, clap, crash, toms).

---

## Key Remapping

Click **⚙ Key Map** to open the remapping panel. Click any slot, press a new key to assign it. Conflicts are flagged immediately. **Save** writes to `localStorage` and persists across sessions. **Reset Defaults** restores the original layout.

---

## Language

Click **EN** to switch to English. Click **中文** to switch back. The preference is saved in `localStorage`.

---

## Technical Notes

- Pure HTML / CSS / JavaScript — zero frameworks, zero build step
- Audio engine: Web Audio API
- Samples: [gleitz/midi-js-soundfonts](https://github.com/gleitz/midi-js-soundfonts) via [soundfont-player](https://github.com/danigb/soundfont-player)
- Drum synthesis: multi-layer Web Audio nodes per instrument
- Frequency visualizer: canvas FFT

---

---

# ⬡ Smart Piano 智能钢琴

一个运行在浏览器里的智能键盘钢琴。左手按住和弦，右手弹旋律，音符自动吸附到最近的和弦音，几乎不可能弹错。无需安装、无需服务器、无需乐理知识。

---

## 快速开始

用现代浏览器（推荐 Chrome）打开 `smart-piano.html`，点击 **▶ 启动声音** 初始化音频引擎。采样乐器在后台加载，按钮显示 `…` 为加载中，`✓` 为就绪。点击顶部的 **EN / 中文** 按钮切换界面语言。

---

## 键位说明

### 左手 · 和弦

| 键位 | 和弦 |
|------|------|
| C | C 大和弦 |
| D | D 大和弦 |
| E | E 大和弦 |
| F | F 大和弦 |
| G | G 大和弦 |
| A | A 大和弦 |
| B | B 大和弦 |

| 修饰键 | 效果 |
|--------|------|
| 按住 **S** + 和弦键 | 小和弦 |
| 按住 **Q** + 和弦键 | 属七和弦 |
| 按住 **W** + 和弦键 | 降半音根音，如 B+W = B♭ |
| **M** | 扫弦（当前和弦所有音同发） |
| **N** | 琶音（循环弹出和弦各音） |

### 右手 · 旋律

| 键位 | 音名 |
|------|------|
| H | Do (C) |
| J | Re (D) |
| K | Mi (E) |
| L | Fa (F) |
| ; | So (G) |
| ' | La (A) |
| Enter | Xi (B) |
| O | 高音 Do (C↑) |

**黑键：** U=♯Do · I=♯Re · P=♯Fa · [=♯So · ]=♯La

### 智能吸附

左手按住和弦时，右手音自动吸附到最近的和弦音（等距时多音同发）。左手松开后，右手恢复原音自由演奏。

### 琶音模式（N 键）

按 **1 / 2 / 3 / 4** 切换模式，当前模式显示在状态栏。

| 键 | 模式 | C 大和弦示例 |
|----|------|-------------|
| 1 | 上行 | C → E → G → C↑ |
| 2 | 根音跳高 | C → C↑ → E → G |
| 3 | 来回 | C → E → G → C↑ → G → E |
| 4 | 跳音（根音穿插） | C → E → C → G → C → C↑ |

F♯ 及以上根音（G、A、B…）序列从低八度开始，保持上行感。如 G 大和弦：低 G → 低 B → D → G。

属七和弦为四音循环，不加高八度根音（C7：C → E → G → B♭）。

### 功能键

| 键位 | 功能 |
|------|------|
| 空格 | 延音开/关 |
| . | 升八度 |
| , | 降八度 |
| V | 整体移调升半音 |
| X | 整体移调降半音 |
| T | 鼓点速度循环：关 → 80 → 100 → 120 BPM |
| R | 切换鼓点节奏型（共 3 种） |

---

## 音色列表

所有乐器使用 **MusyngKite** 真实录音采样，首次使用时从 CDN 加载。网络不可用时自动降级到合成器。

| 按钮 | 乐器 |
|------|------|
| 🎹 钢琴 | 三角钢琴采样 |
| 🎸 吉他 | 尼龙弦古典吉他采样 |
| ⚡ 电吉他 | 清音电吉他采样 |
| 🎵 长笛 | 音乐会长笛采样 |
| 🎺 风琴 | 摇滚风琴采样 |
| 🪘 木琴 | 马林巴木琴采样 |
| 🎻 弦乐 | 弦乐合奏采样 |
| 🌀 合成器 | Web Audio 合成（离线兜底） |

---

## 鼓机

**T** 循环切换速度：关 / 80 / 100 / 120 BPM
**R** 切换 3 种节奏型：
- 节奏型 1 — 标准四四拍，第一拍 crash 镲
- 节奏型 2 — 加花底鼓 + 密集 hi-hat + rim shot
- 节奏型 3 — 拍手声 + 通鼓填充

全部鼓声通过 Web Audio API 合成（底鼓、军鼓、开合 hi-hat、rim shot、拍手、碎镲、通鼓）。

---

## 键位自定义

点击 **⚙ 键位设置** 打开面板，点任意键位格后按新键完成绑定，有冲突即时提示。点 **保存** 写入 `localStorage`，下次打开自动恢复。点 **恢复默认** 一键重置。

---

## 语言切换

点 **EN** 切换英文界面，点 **中文** 切换回中文，偏好保存在 `localStorage`。

---

## 技术说明

- 纯原生 HTML / CSS / JavaScript，零框架，零构建
- 音频引擎：Web Audio API
- 采样来源：[gleitz/midi-js-soundfonts](https://github.com/gleitz/midi-js-soundfonts)，通过 [soundfont-player](https://github.com/danigb/soundfont-player) 加载
- 鼓声合成：每种鼓声多层 Web Audio 节点叠加
- 频谱可视化：Canvas FFT 实时显示
