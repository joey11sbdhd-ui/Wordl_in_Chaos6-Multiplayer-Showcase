# Wordl_in_Chaos6-Multiplayer-Showcase
# 天下大乱 (World in chaos) - 6-Player Real-Time Multiplayer Engine

> **Note on Source Code:** Full game logic (`gameCore.js`) and anti-cheat validation rules are kept in a private repository due to an upcoming commercial release. Happy to walk through the architecture and core synchronization code during technical interviews!

## 🎥 Live 6-Player Gameplay Demo
👉 **[Watch 60s Real-Time Synchronization Demo on YouTube](把你的YouTube链接粘贴在这里)**

## 🏗️ System Architecture
Built with a **Node.js** authoritative server and a lightweight web client (`public/`), designed to handle real-time state synchronization across 6 concurrent players with minimal latency.

```mermaid
graph LR
    P1[Player 1 Client] <-->|Real-time Events / State| S[server.js - Node.js]
    P2[Player 2 Client] <-->|Real-time Events / State| S
    P3[Player 3-6 Clients] <-->|Real-time Events / State| S
    S <-->|Tick Loop & Validation| G[gameCore.js - Authoritative State]
