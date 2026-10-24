<div align="center">

# Hi, I'm Truong Nguyen 👋

**Senior Full-Stack Engineer & Mentor** · Ho Chi Minh City, Viet Nam 🇻🇳

I build production systems with .NET, Python and React, ship them with Docker and Kubernetes —
and in my spare time I make free multiplayer browser games.

[![Website](https://img.shields.io/badge/ginjs.click-website-84cc16?style=for-the-badge&logo=googlechrome&logoColor=white)](https://www.ginjs.click)
[![Play games](https://img.shields.io/badge/16_free_games-play_now-22c55e?style=for-the-badge&logo=gamepad&logoColor=white)](https://www.ginjs.click/en/playground/)
[![Blog](https://img.shields.io/badge/blog-read-3b82f6?style=for-the-badge&logo=bookstack&logoColor=white)](https://www.ginjs.click/en/blogs/)

</div>

---

## 🧑‍💻 About me

- 🏗️ **5+ years** building production systems, **30+ projects** delivered — from microservices and backend APIs to cloud infrastructure.
- 🎓 I **mentor developers** through real-world code reviews, architecture decisions and hands-on DevOps work → [about me](https://www.ginjs.click/en/about/) · [my story](https://www.ginjs.click/en/story/)
- 🏠 My own site runs on a **home Kubernetes cluster of Raspberry Pis** — I like owning the whole stack, from the React component down to the node it runs on.
- 🌏 Everything I publish is bilingual: **English & Tiếng Việt**.

## 🛠️ Tech I work with

| Area | Stack |
|---|---|
| **Backend** | .NET / ASP.NET Core, Python (FastAPI, Django), Node.js |
| **Frontend** | React, TypeScript, Vite, Tailwind CSS |
| **Real-time** | Socket.IO, WebSockets |
| **DevOps** | Docker, Kubernetes, Helm, GitHub Actions / GitLab CI, multi-arch images (amd64 + arm64) |
| **Infra** | Traefik, Cloudflare, Keycloak (SSO), MinIO (S3) |

---

## 🎮 Free browser games I built

All playable at **[ginjs.click/playground](https://www.ginjs.click/en/playground/)** — no download, no sign-up, works on desktop and mobile.

### ♟️ Board & card games — play the computer or a friend online
| Game | What it is | Modes |
|---|---|---|
| [**Chaos Billiards**](https://www.ginjs.click/en/chaos-billiards/) | 8-ball pool where every ball you sink earns an ability: bombs, black holes, phantom cue balls, freeze, swap, giant cue ball | vs CPU · online 1v1 · same device |
| [**Caro (Gomoku)**](https://www.ginjs.click/en/caro/) | Five in a row on a 15×15 board, Vietnamese rules — a five blocked at both ends doesn't count | vs CPU · online 1v1 · same device |
| [**Tiến Lên Miền Nam**](https://www.ginjs.click/en/tien-len/) | The Vietnamese "Thirteen" card game — bombs, chopping 2s, instant wins | vs bots · 2–4 players online |
| [**Bulwark**](https://www.ginjs.click/en/bulwark/) | Race your pawn across a 9×9 board and place walls to lengthen your opponent's path | vs CPU · online 1v1 |

### 💥 Action
| Game | What it is |
|---|---|
| [**Zombie Rush**](https://www.ginjs.click/en/zombie-rush/) | Endless squad shooter — run through gates to grow your army, upgrade between runs · 🏆 leaderboard |
| [**Brick Storm**](https://www.ginjs.click/en/brick-storm/) | Brick breaker with multi-ball, fireballs, lasers and TNT — **online co-op for up to 4 paddles** · 🏆 leaderboard |
| [**Blade Toss**](https://www.ginjs.click/en/blade-toss/) | Throw knives into a spinning log, boss stages every 5th level · 🏆 leaderboard |
| [**SNES Emulator**](https://www.ginjs.click/en/snes/) | Play Super Nintendo games in the browser with a ROM you own |

### 🎉 Party games
| Game | What it is |
|---|---|
| [**Who's the Spy?**](https://www.ginjs.click/en/who-is-the-spy/) | Pass-the-phone word game for 3–10 players — find the spies holding a slightly different word |
| [**Share or Dare**](https://www.ginjs.click/en/share-or-dare/) | 155 share questions and dares, no repeats on your device |
| [**Icebreaker**](https://www.ginjs.click/en/icebreaker/) | Anonymous chat with a stranger matched by language & interests, plus would-you-rather and two truths and a lie |

### ☕ Idle & skill
| Game | What it is |
|---|---|
| [**Merge Lab**](https://www.ginjs.click/en/merge-lab/) | Drag-and-merge puzzle from "Like" to "Infinity", with offline progress and 52 achievements |
| [**IT Certificate Simulator**](https://www.ginjs.click/en/code-clicker/) | Idle clicker for developers — ship code, hire a team, earn a certificate in your career track |
| [**Gacha Draw**](https://www.ginjs.click/en/gacha-draw/) | Pachinko board + scratch cards, loot across six rarities |
| [**Battle Arena**](https://www.ginjs.click/en/battle-arena/) | Name two fighters and watch them bounce and battle until one runs out of HP |
| [**Reflex Rush**](https://www.ginjs.click/en/reflex-rush/) | WarioWare-style micro-challenges that keep speeding up · 🏆 leaderboard |

---

## ⚙️ How the games are built

Not just a weekend toy — the playground is a small real-time system:

- **Shared game engines.** Rules for each multiplayer game live in one pure TypeScript module with no DOM or Node dependency, imported by both the browser and the server — so client and server can never disagree on the rules.
- **Server-authoritative.** A Node.js + Socket.IO room server re-validates every move and never trusts the client. Card games send each seat **only its own hand** until the game ends.
- **Deterministic physics.** Chaos Billiards' simulation uses only `+ − × ÷` and `sqrt` with a seeded PRNG, so the server simulates each shot to rest and every client replays it step-by-step to the identical result.
- **Turn clocks.** Chess-style timing (30 s per move + a 5 or 10 min bank), enforced on the server.
- **Leaderboards.** Weekly + all-time boards, nickname only, no login.
- **Moderation** for the stranger chat: rate limits, skip/report, profanity masking and link stripping.
- **Static front end + one small server.** The React/Vite SPA is prerendered per route for SEO (meta tags, JSON-LD, sitemap) in both languages; the room server ships as a multi-arch Docker image to GHCR and runs on the Raspberry Pi cluster behind Traefik and Cloudflare.

---

## ✍️ Latest from the blog

- [5 Years of Full-Stack Development: Lessons Learned](https://www.ginjs.click/en/blogs/five-years-fullstack-journey/)
- [Building Scalable React Applications: A Real-World Example](https://www.ginjs.click/en/blogs/scalable-react-applications/)
- [Modern CSS Techniques: A Practical Example](https://www.ginjs.click/en/blogs/modern-css-techniques/)

## 🤝 Let's connect

- 🌐 **Website:** [ginjs.click](https://www.ginjs.click)
- 📬 **Mentorship & collaboration:** [contact page](https://www.ginjs.click/en/contact/)
- 🎮 **Found a bug in a game or have an idea?** Open the game and tell me through the contact page — feedback is very welcome.

<div align="center">

*Chơi game miễn phí bằng tiếng Việt: [ginjs.click/vi/playground](https://www.ginjs.click/vi/playground/)* 🇻🇳

</div>
