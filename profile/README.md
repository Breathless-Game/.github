<p align="center">
  <img src="https://raw.githubusercontent.com/Breathless-Game/Breathless/main/docs/showcase.gif" alt="Breathless: a fjord under the aurora, where a diver holds their breath and dives down to catch fish" width="720">
</p>

<h1 align="center">屏息 Breathless</h1>

<p align="center"><b>Hold your real breath to dive and catch fish.</b></p>

<p align="center">
  <a href="https://github.com/Breathless-Game/Breathless/releases/latest"><img src="https://img.shields.io/github/v/release/Breathless-Game/Breathless" alt="Latest release"></a>
  <img src="https://img.shields.io/badge/HackRU_2026-Maverick-0b7285" alt="HackRU 2026, Maverick track">
  <img src="https://img.shields.io/badge/Solana-devnet-9945FF?logo=solana&logoColor=white" alt="Solana devnet">
</p>

<p align="center">
  <a href="https://breathless.gotclass.xyz"><b>Play in the browser</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/Breathless-Game/Breathless/releases/latest"><b>Desktop download</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/Breathless-Game/Breathless"><b>Source</b></a>
</p>

A low-poly 2.5D diving game where your lungs are the oxygen tank. Built at **HackRU 2026** for the **Maverick** track.

## How it plays

- **Hold your breath to dive.** The diver only descends while you hold. Right now that means holding `Shift` (see the note below).
- **Greed against risk.** Deeper water holds rarer fish. Breathe underwater and you have 3.2 seconds to reach the surface, or you black out and lose every fish in your net.
- **Three maps.** Fjord, Heaven Lake and Open Ocean, each with a bottomless trench under the boat. Nights roll rarity twice; the Open Ocean has storms and sharks.
- **Bank, sell, upgrade.** Every banked fish is minted as an NFT. Sell it to the market and it is burned for PEARL, which buys gear and feeds the fish in your 3D aquarium.
- **A private health report.** Press `H` for a report on your breath holds. It is wellness reference only, not medical advice.

> **Camera mode is paused.** The design is to read your breathing through a plain webcam with the Presage SDK. Its credits ran out, so camera detection is switched off for now and the game runs in keyboard mode. The camera code is still in the repo behind two switches.

## Under the hood

| Part | What it uses |
| --- | --- |
| Game | Three.js + TypeScript, built with Vite. Art, water, weather and fish are generated in code |
| Server | Node API on Vercel, state in Upstash Redis: PEARL market, NFT metadata and images. The webcam sensor bridge (WebSocket) runs self-hosted when camera mode is on |
| Chain | **Solana devnet**: Metaplex Core fish NFTs, the PEARL SPL token, and the `player_state` Anchor program (gear, aquarium, progress) |
| Desktop | Electron app for macOS (arm64 / x64), Windows (installer + portable) and Linux (AppImage, deb) |

- **Devnet only.** PEARL and the fish NFTs have no real-money value.
- **Progress lives on chain.** Gear, PEARL, aquarium and progress are read from Solana; the server stores no player data.
- **Health data stays with you.** Breath and health data stay in your browser. They never go on chain or to the server, and one button deletes them.
- The desktop builds are unsigned, so the first launch shows a warning: [how to open it anyway](https://github.com/Breathless-Game/Breathless/blob/main/desktop/README.md#first-launch-of-an-unsigned-build).

## Team

[@Bowen1314](https://github.com/Bowen1314) · [@Deler329](https://github.com/Deler329) · [@LucasYanzy](https://github.com/LucasYanzy) · [@ISmkuI](https://github.com/ISmkuI)

---

### 中文

**屏息 Breathless**：用你真实的憋气来潜水抓鱼。憋住气才能下潜，越深鱼越稀有，在水下一换气就得马上浮上去，否则网里的鱼全丢。HackRU 2026 作品，Maverick 赛道。

- 摄像头呼吸检测（Presage）暂时关闭，现在用键盘模式：按住 `Shift` 代表憋气。
- 抓到的鱼铸造成 Solana NFT，卖给市场换 PEARL 币。全部在 **devnet** 上，不涉及真钱。
- 健康和呼吸数据只留在你的浏览器里，不上链，也不传到服务器。
- [浏览器直接玩](https://breathless.gotclass.xyz) · [下载桌面版](https://github.com/Breathless-Game/Breathless/releases/latest) · [源代码](https://github.com/Breathless-Game/Breathless) · [中文 README](https://github.com/Breathless-Game/Breathless/blob/main/README.zh-CN.md)
