<div align="center">

<img src="./banner.webp" width="100%" alt="Fahim Islam"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&pause=1200&color=00E5FF&center=true&vCenter=true&width=640&lines=Turning+ASM+charts+into+silicon;FSM+%2B+Datapath+%7C+Moore+machines;RTL+%E2%86%92+GDSII+on+sky130;Building+games%2C+radios+and+radar+on+FPGAs)](https://git.io/typing-svg)

![Profile Views](https://komarev.com/ghpvc/?username=YOUR_USERNAME&label=Profile%20Views&color=00e5ff&style=flat-square)
![EEE](https://img.shields.io/badge/EEE-AIUB-0f4c5c?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Digital%20IC%20%2F%20FPGA-00e5ff?style=flat-square)

</div>

---

## 👋 About Me

Third-year **Electrical & Electronic Engineering** student at **American International University-Bangladesh (AIUB)**, obsessed with how a few lines of RTL become real hardware.

- 🔬 Focus: **digital IC & FPGA design**
- 🧠 Strong on **RTL / SystemVerilog**, **FSM-datapath methodology** and **DSP concepts**
- 🏭 Pushing designs through the **RTL-to-GDSII** flow on **sky130**
- 🎮 Building things that are fun: games, displays, radios, radar
- 🎯 Currently exploring **capstone** directions

---

## 🧩 How I Write RTL

Clean, explicit and predictable. FSM and datapath are always separated, with no implicit defaults.

```systemverilog
// Moore FSM — three-block style, named enums from a package
typedef enum logic [1:0] {IDLE, RUN, DONE} state_t;

state_t state_r, state_n;

// 1) state register
always_ff @(posedge clk or negedge rst_n)
  if (!rst_n) state_r <= IDLE;
  else        state_r <= state_n;

// 2) next-state logic (comparator flags feed this, not inline expressions)
always_comb begin
  case (state_r)
    IDLE:    state_n = start  ? RUN  : IDLE;
    RUN:     state_n = k_last ? DONE : RUN;
    DONE:    state_n = IDLE;
    default: state_n = IDLE;
  endcase
end

// 3) Moore outputs — every output assigned in every branch
always_comb begin
  case (state_r)
    IDLE:    begin busy = 1'b0; done = 1'b0; end
    RUN:     begin busy = 1'b1; done = 1'b0; end
    DONE:    begin busy = 1'b0; done = 1'b1; end
    default: begin busy = 1'b0; done = 1'b0; end
  endcase
end
```

> Counters live in separate sequential registers, outside the FSM.

---

## 🚀 Projects

| Project | What it is | Stack |
|---|---|---|
| 🟡 **Pac-Man FPGA Clone** | From-scratch Pac-Man arcade hardware for the Sipeed TangNano9K | SystemVerilog · FPGA |
| ⭕ **Tic Tac Toe** | FPGA game with PKG / FSM / DATAPATH / TOP / TB structure | SystemVerilog |
| 🖥️ **VGA Controller** | VESA 800×600 @ 60 Hz controller (PKG / FSM / DP / TOP) | SystemVerilog |
| 🛰️ **Radar Detection Pipeline** | FMCW → FFT → CFAR aerial vehicle detection on FPGA | DSP · FPGA |
| 📡 **LoRa Receiver** | SX127x-based LoRa RX implemented on FPGA | SystemVerilog |
| 🧮 **MMA Core** | GPU-style matrix multiply-accumulate (Tensor Core-like) core | SystemVerilog |
| 🏭 **mul3x3 ASIC** | 3×3 unsigned sequential multiplier through RTL-to-GDSII | sky130 · LibreLane |
| 🎧 **Lossless Audio Codec** | Encoder + decoder as an ASIC portfolio project | RTL · ASIC |
| ✈️ **PFD Display** | Primary flight display with artificial horizon on a round GC9A01 LCD | ESP32-C3 |
| 🦯 **Blind-Assist Helmet** | Sensory-substitution helmet with haptic feedback from spatial sensing | ESP32 |
| 🎫 **DEF CON-style Badge** | Wearable conference badge with an LED matrix | XIAO ESP32-C6 |
| ❤️ **PPG Pulse Sensor** | Analog photoplethysmography front-end circuit design | Analog |

> 📌 Pin your favourites and link each project to its repo.

---

## 🛠️ Toolbox

![SystemVerilog](https://img.shields.io/badge/SystemVerilog-0f4c5c?style=for-the-badge)
![Verilog](https://img.shields.io/badge/Verilog-1f6f8b?style=for-the-badge)
![FPGA](https://img.shields.io/badge/FPGA-00b4d8?style=for-the-badge)
![sky130](https://img.shields.io/badge/SkyWater_sky130-333?style=for-the-badge)
![LibreLane](https://img.shields.io/badge/LibreLane-0d1117?style=for-the-badge)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=for-the-badge)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

**Methodology:** ASM chart → RTL · FSM/datapath separation · Moore machines · package-defined enums · testbench-driven verification

---

## 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117" />

</div>

---

## 🔭 What I'm Exploring

- 🎓 Capstone project ideas in digital IC / FPGA
- 🏭 More tape-out-style ASIC flows on open-source PDKs
- 📶 DSP-heavy FPGA pipelines (radar, radio, audio)

---

<div align="center">

[![Email](https://img.shields.io/badge/Email-0f4c5c?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_LINKEDIN)

```
  always_ff @(posedge coffee) begin
      code <= more_code;
  end
```

<img src="./footer.webp" width="100%" alt=""/>

</div>
