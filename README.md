# Neural-Network-simulation

# 🧠 NEUROVIS 3D — Interactive Neural Network Visualizer

<div align="center">

![Neural Network](https://img.shields.io/badge/Deep%20Learning-Neural%20Network-7b2ff7?style=for-the-badge&logo=pytorch)
![MNIST](https://img.shields.io/badge/Dataset-MNIST-00f5d4?style=for-the-badge)
![Three.js](https://img.shields.io/badge/3D%20Engine-Three.js-f72585?style=for-the-badge&logo=threedotjs)
![Vanilla JS](https://img.shields.io/badge/Built%20With-Vanilla%20JS-ffd60a?style=for-the-badge&logo=javascript)
![No Install](https://img.shields.io/badge/No%20Install-Just%20Open%20HTML-06d6a0?style=for-the-badge)

**A fully interactive 3D neural network that learns to recognize handwritten digits — built for learners, visual thinkers, and ML explorers.**

[✨ Live Demo](#) &nbsp;·&nbsp; [📖 How It Works](#how-it-works) &nbsp;·&nbsp; [🚀 Quick Start](#quick-start) &nbsp;·&nbsp; [📚 Features](#features)

</div>

---

## ✨ What Is This?

**NEUROVIS 3D** is a browser-based, zero-dependency visualizer that brings a neural network to life in 3D. Watch neurons glow, connections pulse, and the loss curve drop in real time as the network trains on MNIST digit data — all rendered with Three.js, all running in a single HTML file.

Built specifically to make deep learning **visual and intuitive** for:
- 🎓 Students learning ML for the first time
- 👁️ Visual learners who need to *see* the math
- 🔬 Anyone curious how a neural network actually "thinks"

---

## 🎬 Features

### 🌐 3D Interactive Network
| Feature | Description |
|---|---|
| **Rotate** | Click & drag to orbit the entire network in 3D space |
| **Zoom** | Scroll to zoom in/out |
| **Click Neurons** | Click any glowing sphere to open a full info panel |
| **Live Glow** | Neurons scale and glow based on their real-time activation values |
| **Connection Colors** | Cyan lines = positive weights · Pink lines = negative weights |

### ⚡ Live Training Visualization
| What You See | What It Means |
|---|---|
| Neurons getting brighter | Higher activation — that neuron is "firing" strongly |
| Loss curve falling | The network is learning and making fewer mistakes |
| Accuracy rising | More digits correctly classified |
| Phase banner flashing | Shows whether it's a Forward Pass or Backprop step |

### 🖱️ Click Any Neuron — Full Inspector
Every neuron reveals:
- **Plain-English explanation** of what that neuron type does
- **Activation value** — how strongly it fired (0 to 1)
- **Pre-activation z** — the raw weighted sum before activation
- **Bias** — the neuron's learned offset
- **Gradient** — how much this neuron needs to change
- **Incoming weights** — color-coded positive/negative
- **Real-world analogy** for that layer

### 📚 Built-in Learning System
- **Welcome modal** — step-by-step onboarding for complete beginners
- **LEARN panel** — 3 tabs: Concepts, How It Works, Glossary (20 terms)
- **Hover tooltips** — every metric has a `?` icon with a plain-English definition
- **Beginner-first language** — no jargon without explanation

### ✍️ Draw Your Own Digit
- **Freehand drawing pad** — draw any digit 0–9 with your mouse or finger
- **Image upload** — upload a photo of a handwritten digit
- **Preprocessing pipeline** — auto-crops, resizes to 28×28, normalizes
- **Live inference** — the network immediately predicts your drawing
- **Pixel preview** — see exactly what the network "sees" after preprocessing

---

## 🚀 Quick Start

No installation. No npm. No Python. Just open the file.

```bash
# Clone the repo
git clone https://github.com/your-username/neurovis-3d.git

# Open in browser
open neural_network_3d_v2.html
```

Or simply **double-click** `neural_network_3d_v2.html` — it runs entirely in your browser.

---

## 🏗️ How It Works

### Network Architecture

```
Input Layer    Hidden Layer 1    Hidden Layer 2    Output Layer
  (16 nodes)  →   (16 nodes)   →   (12 nodes)   →  (10 nodes)
  
  Pixels          Edges &          Curves &         Digit 0–9
  0.0–1.0         Strokes          Shapes           Probabilities
```

> Note: The full MNIST input is 784 pixels (28×28). For visualization clarity, 16 representative neurons are shown in the input layer.

### The Training Loop (4 Steps)

```
1. FORWARD PASS
   Image pixels → weighted sums → ReLU → Softmax → Probabilities

2. COMPUTE LOSS
   Cross-Entropy Loss = -log( P(correct digit) )
   High loss = very wrong. Low loss = nearly correct.

3. BACKPROPAGATION
   Chain rule flows error backwards through each layer
   Computes gradient for every weight and bias

4. WEIGHT UPDATE (Gradient Descent)
   weight = weight - learning_rate × gradient
   Repeat thousands of times → network converges
```

### Key Formulas

| Concept | Formula |
|---|---|
| Neuron output | `z = Σ(wᵢ × xᵢ) + b` |
| ReLU activation | `ReLU(z) = max(0, z)` |
| Softmax (output) | `σ(zᵢ) = eᶻⁱ / Σeᶻʲ` |
| Cross-entropy loss | `L = -log(ŷ_correct)` |
| Weight update | `w = w - lr × ∂L/∂w` |

---

Everything — HTML, CSS, JavaScript, Three.js integration, the neural network simulation, the drawing pad, and the learning system — lives in a **single self-contained HTML file**. No build step, no dependencies to install, no server needed.

---

## 🧬 Tech Stack

| Technology | Purpose |
|---|---|
| **Three.js r128** | 3D rendering engine (loaded from CDN) |
| **Vanilla JavaScript** | Neural net simulation, training loop, UI logic |
| **HTML5 Canvas** | Digit drawing pad, pixel preview, loss chart |
| **CSS3** | Glassmorphism panels, animations, responsive layout |
| **Google Fonts** | Orbitron (headings), Space Mono (code), Inter (body) |

**Zero runtime dependencies** beyond Three.js (CDN). No React, no Vue, no bundler.

---

## 🎓 What You'll Learn

By exploring this tool you'll gain intuition for:

- ✅ What a **neuron** is and how it computes its output
- ✅ What **weights and biases** do and how they're learned
- ✅ Why **loss goes down** as training progresses
- ✅ What **backpropagation** actually computes
- ✅ The difference between **Forward Pass** and **Weight Update**
- ✅ What **ReLU** and **Softmax** do and why they're used
- ✅ How raw **pixel values** become digit **predictions**
- ✅ What **epoch**, **batch**, and **learning rate** mean

---

## 🗺️ Glossary (Quick Reference)

| Term | One-Line Definition |
|---|---|
| **Neuron** | Basic unit — computes weighted sum + activation |
| **Weight** | Learnable connection strength between two neurons |
| **Bias** | Learnable offset; lets a neuron activate independently |
| **Activation** | Neuron output after applying activation function |
| **ReLU** | `max(0, x)` — kills negatives, passes positives |
| **Softmax** | Converts output scores to probabilities summing to 100% |
| **Loss** | How wrong the network is — goal is to minimize it |
| **Gradient** | Direction & magnitude to nudge each weight |
| **Backprop** | Algorithm to compute gradients via chain rule |
| **Epoch** | One full pass through training data |
| **Batch** | Small subset of training samples per update step |
| **Learning Rate** | Controls the size of each weight update step |

---

## 🖥️ Browser Compatibility

| Browser | Status |
|---|---|
| Chrome 90+ | ✅ Fully supported |
| Firefox 88+ | ✅ Fully supported |
| Safari 14+ | ✅ Fully supported |
| Edge 90+ | ✅ Fully supported |
| Mobile (touch) | ✅ Drag-to-rotate supported |

WebGL must be enabled (it is by default in all modern browsers).

---

## 🔮 Potential Extensions

Want to take this further? Here are ideas to build on top of this project:

- [ ] **Real PyTorch/TensorFlow backend** — connect via WebSocket for true model weights
- [ ] **CNN Visualizer** — show convolutional filters and feature maps
- [ ] **Confusion Matrix** — display which digits are commonly confused
- [ ] **Weight Histogram** — show how weight distributions shift during training
- [ ] **Multiple architectures** — let users choose depth and width
- [ ] **Export trained weights** — save and reload network state
- [ ] **Dataset browser** — scroll through real MNIST images

---



## 🤝 Contributing

Contributions are welcome! If you'd like to improve the visualizer:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/cnn-layers`
3. Commit your changes: `git commit -m 'Add CNN layer visualization'`
4. Push to the branch: `git push origin feature/cnn-layers`
5. Open a Pull Request

---

## 📄 License

MIT License — free to use, share, and modify.

---

## 👤 Author

**Sandy** — ML student, builder, deep learning explorer.

> *"I built this because I learn best by seeing things. If a neural network is just math on paper, it's forgettable. But if you can rotate it in 3D and click on its neurons — you remember it forever."*

---

<div align="center">

**If this helped you understand neural networks, give it a ⭐ — it helps others find it too!**

Made with 🧠 + Three.js + lots of curiosity

</div>
