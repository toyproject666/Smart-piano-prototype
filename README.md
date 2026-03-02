# ⬡ Smart Piano

A browser-based intelligent piano that lets you play melodies and chords together using your keyboard — no music theory knowledge required. The right hand snaps to the nearest chord tone when the left hand is held, and plays free notes when released.

---

## Getting Started

Open `smart-piano.html` in any modern browser (Chrome recommended). Click **▶ Start Audio** to initialize the sound engine. The sampled instruments will begin loading in the background — buttons show `…` while loading and `✓` when ready.

No installation, no dependencies, no backend. Everything runs in the browser.

---

## Key Mapping

### Left Hand — Chords

| Key | Chord Root |
|-----|-----------|
| C | C major |
| D | D major |
| E | E major |
| F | F major |
| G | G major |
| A | A major |
| B | B major |

Hold **S** while pressing a chord key → minor chord  
Hold **Q** while pressing a chord key → dominant 7th chord  
Press **M** → strum all notes of the current chord

### Right Hand — Melody

| Key | Note |
|-----|------|
| H | Do (C) |
| J | Re (D) |
| K | Mi (E) |
| L | Fa (F) |
| ; | So (G) |
| ' | La (A) |
| Enter | Xi (B) |
| O | High Do (C↑) |

**Black keys:** U = #Do · I = #Re · P = #Fa · [ = #So · ] = #La

### Smart Snapping

When the left hand holds a chord, right-hand notes snap to the nearest chord tone — making it nearly impossible to play a wrong note. When no chord is held, the right hand plays freely at its natural pitch.

### Function Keys

| Key | Function |
|-----|----------|
| Space | Sustain on/off |
| . | Octave up |
| , | Octave down |
| T | Drum tempo cycle: off → 80 → 100 → 120 BPM |
| R | Cycle drum pattern (3 patterns) |

---

## Instruments

All instruments use real audio samples from the **MusyngKite** soundfont (loaded from CDN on first use). Falls back to a synthesizer if the network is unavailable.

| Button | Instrument |
|--------|-----------|
| 🎹 Piano | Acoustic grand piano |
| 🎸 Guitar | Nylon string acoustic guitar |
| ⚡ Electric Guitar | Clean electric guitar |
| 🎵 Flute | Concert flute |
| 🎺 Organ | Rock organ |
| 🪘 Marimba | Marimba |
| 🎻 Strings | String ensemble |
| 🌀 Synth | Web Audio synthesis (offline fallback) |

---

## Drum Machine

Press **T** to cycle through drum tempos (off / 80 / 100 / 120 BPM).  
Press **R** to switch between 3 drum patterns:
- Pattern 1 — Standard 4/4 with crash
- Pattern 2 — Busy kick with dense hi-hat and rim shots
- Pattern 3 — Clap + tom fills

Drum sounds are synthesized entirely via Web Audio API (kick, snare, hi-hat, open hi-hat, rim, clap, crash, toms).

---

## Key Remapping

Click **⚙ Key Settings** to open the remapping panel. Click any key slot, then press a new key to reassign it. Conflicts are flagged immediately. Click **Save** to apply — settings are stored in `localStorage` and persist across sessions. Click **Reset to Default** to restore the original layout.

---

## Technical Notes

- Built with vanilla HTML/CSS/JavaScript, zero frameworks
- Audio engine: Web Audio API
- Sampled instruments: [gleitz/midi-js-soundfonts](https://github.com/gleitz/midi-js-soundfonts) via [soundfont-player](https://github.com/danigb/soundfont-player)
- Drum synthesis: multi-layer Web Audio nodes per instrument
- Frequency visualizer: canvas-based FFT display

---

---

# ⬡ Smart Piano 智能钢琴

一个运行在浏览器里的智能键盘钢琴。左手按住和弦，右手旋律自动吸附到最近的和弦音——几乎不可能弹错音。左手松开后，右手恢复自由演奏。无需乐理知识，开箱即玩。

---

## 快速开始

用现代浏览器（推荐 Chrome）打开 `smart-piano.html`，点击 **▶ 启动声音** 初始化音频引擎。采样乐器会在后台加载，按钮显示 `…` 表示加载中，`✓` 表示就绪。

无需安装，无需服务器，完全在浏览器本地运行。

---

## 键位说明

### 左手 · 和弦

| 键位 | 和弦根音 |
|------|---------|
| C | C 大和弦 |
| D | D 大和弦 |
| E | E 大和弦 |
| F | F 大和弦 |
| G | G 大和弦 |
| A | A 大和弦 |
| B | B 大和弦 |

按住 **S** 同时按和弦键 → 小和弦  
按住 **Q** 同时按和弦键 → 属七和弦  
按 **M** → 扫弦（当前和弦所有音同时发声）

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

**黑键：** U=#Do · I=#Re · P=#Fa · [=#So · ]=#La

### 智能吸附

左手按住和弦时，右手音自动吸附到最近的和弦音，弹任何键都不会跑调。左手松开后，右手恢复原音，自由演奏。

### 功能键

| 键位 | 功能 |
|------|------|
| 空格 | 延音开/关 |
| . | 升八度 |
| , | 降八度 |
| T | 鼓点速度循环：关 → 80 → 100 → 120 BPM |
| R | 切换鼓点节奏型（共3种） |

---

## 音色列表

所有乐器使用 **MusyngKite** 真实录音采样（首次使用时从 CDN 加载）。网络不可用时自动降级到合成器。

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

按 **T** 循环切换鼓点速度（关 / 80 / 100 / 120 BPM）。  
按 **R** 切换3种节奏型：
- 节奏型1 — 标准四四拍，带 crash 镲
- 节奏型2 — 加花底鼓 + 密集 hi-hat + rim shot
- 节奏型3 — 拍手声 + tom 鼓填充

所有鼓声通过 Web Audio API 合成（底鼓、军鼓、闭合/开放 hi-hat、rim shot、拍手声、碎钹、通鼓）。

---

## 键位自定义

点击 **⚙ 键位设置** 打开面板，点任意键位格子后按新键完成绑定，有冲突会即时提示。点 **保存** 写入 `localStorage`，下次打开自动恢复。点 **恢复默认** 一键重置。

---

## 技术说明

- 纯原生 HTML/CSS/JavaScript，零框架依赖
- 音频引擎：Web Audio API
- 采样来源：[gleitz/midi-js-soundfonts](https://github.com/gleitz/midi-js-soundfonts)，通过 [soundfont-player](https://github.com/danigb/soundfont-player) 加载
- 鼓声合成：每种鼓声多层 Web Audio 节点叠加
- 频谱可视化：Canvas FFT 实时显示
