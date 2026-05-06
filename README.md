# てちお Portfolio — TEAM TECHIO Rebrand 2026

スクロールで朝→昼→夜と一日が進む、エディトリアルマガジン風ポートフォリオ。

## 構成

```
apps/techio-portfolio/
├── index.html          # 単一HTML（全セクション含む）
├── tweaks-panel.jsx    # Tweaksパネル（Mood切替・Clock表示・タグライン）
├── assets/
│   ├── issue-03.png    # ISSUE 03 — Engineer
│   ├── issue-04.png    # ISSUE 04 — Designer
│   ├── issue-05.png    # ISSUE 05 — Writer
│   └── issue-11.png    # ISSUE 11 — Engagement (favicon / og:image / nav avatar)
└── README.md
```

## 世界観

| Section | Issue | Phase   | BG       | Accent   | Text     | Font                              |
| ------- | ----- | ------- | -------- | -------- | -------- | --------------------------------- |
| Morning | 05    | 編集長  | #F5EDE0 | #C9924E | #2A1A0E | Noto Serif JP + Cormorant Garamond |
| Noon    | 04    | デザイナー | #FAFAFA | #B29AD8 | #2A2A2A | Noto Serif JP + Cormorant Garamond |
| Night   | 03    | エンジニア | #0F0A1E | #FF7A00 | #E8E0F0 | Noto Sans JP + JetBrains Mono     |

スクロール位置に応じて `--bg` / `--text` / `--accent` / `--rule` / `--muted`
のCSS変数を smoothstep で線形補間。GSAP不使用（軽量化のため自前実装・約120行）。
左下の時計（06:24 → 23:48）と進捗バーもスクロールに連動。

## デプロイ手順（GitHub Pages）

```bash
# このフォルダごと techio-code/techio-code.github.io にコピー（apps/techio-portfolio/ 配下）
git add apps/techio-portfolio
git commit -m "feat: techio portfolio rebrand — editorial day-cycle"
git push origin main

# 公開URL
# https://techio-code.github.io/techio-portfolio/
```

## ローカル確認

```bash
# CDN（React/Babel/Google Fonts）を読みに行くので、何でもいいので静的サーバ経由で
python3 -m http.server 8000
# → http://localhost:8000/apps/techio-portfolio/
```

## Tweaks（右下パネル）

- **Phase**: `auto` / `morning` / `noon` / `night` — スクロール連動を無効化して固定可能
- **Clock**: 左下の時刻＋進捗バー表示切替
- **Paper grain**: 紙質ノイズの表示切替
- **Mission tagline**: 朝セクションの引用文を直接編集

## クレジット

- Cover illustrations: Claude Design による生成（ISSUE 03/04/05/11）
- Built with Claude Code — May 2026
