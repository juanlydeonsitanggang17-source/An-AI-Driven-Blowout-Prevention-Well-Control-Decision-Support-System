# An-AI-Driven-Blowout-Prevention-Well-Control-Decision-Support-System
I built an end-to-end Machine Learning pipeline utilizing a Bidirectional LSTM (BiLSTM) neural network to act as a virtual Drilling Engineer. Instead of just flagging anomalies, I wanted to create an Explainable AI (XAI) that provides context and actionable recommendations.
# 🛢️ AI-Driven Blowout Prevention & Well Control Decision Support System

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00.svg?logo=tensorflow)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Project Overview
This repository contains an end-to-end Machine Learning pipeline designed to enhance drilling safety through **Automated Blowout Prevention**. By utilizing a **Bidirectional Long Short-Term Memory (BiLSTM)** neural network, this system acts as a virtual Drilling Engineer, analyzing real-time well log and drilling mechanics data to predict kicks and other subsurface anomalies before they escalate into a blowout.

The project not only detects anomalies but also features an **Expert System (Decision Support System)** that provides explainable AI (XAI) outputs: detailing the *Reasoning*, *Recommended Mechanisms*, and *Operational Impacts* for each predicted scenario.

## 🔬 Subsurface Scenarios Covered
The model is trained on synthetic multivariate time-series data representing 4 distinct operational states:
0. **Normal Drilling:** Stable hydraulic and mechanical parameters.
1. **False Alarm (Connection Gas / Wellbore Ballooning):** Temporary U-tube effects or short-term formation breathing while the mud pump is off.
2. **Lost Circulation:** Sudden drop in pit volume and flow out, indicating mud loss into fractured or highly porous formations (Preventative BOP scenario).
3. **Actual Gas Kick (Blowout Imminent):** Lethal combination of a drilling break (ROP spike, Gamma Ray drop), cumulative pit gain, flow out > 100%, and SPP drop.

## 🏗️ System Architecture & Features
1. **Synthetic Big Data Generation:** Simulates realistic LWD (Gamma Ray, Resistivity), Drilling Mechanics (ROP, SPP), and Mud Parameters (Flow Out, Pit Volume, Gas) across multiple wells.
2. **3D Sliding Window Preprocessing:** Converts 2D tabular logs into 3D tensors `(Samples, Timesteps, Features)` capturing 30 timesteps of historical context for sequence modeling.
3. **BiLSTM Neural Network:** Leverages bidirectional recurrent layers to understand temporal geophysical trends (both forward and backward) to accurately classify well behavior.
4. **Real-Time Expert System:** Translates softmax probability outputs into actionable rig-floor commands (e.g., *Hard Shut-In*, *Circulate Bottoms Up*).
5. **Automated Well Log Visualization:** Generates multi-track standard mud log visualizations to compare the "AI's Field of View" with actual subsurface events.

## ⚙️ Installation & Setup
Clone the repository and install the required dependencies:

```bash
git clone https://github.com/juanlydeonsitanggang17-source/An-AI-Driven-Blowout-Prevention-Well-Control-Decision-Support-System/edit/main/README.md
cd blowout-prevention-bilstm
pip install -r requirements.txt
