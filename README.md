# 淵野辺 今昔マップ（Hackathon_Oct_HimariNonaka）

青山学院大学 相模原キャンパスのある **淵野辺（神奈川県相模原市）** の古地図と現在の地図を見比べられる Web マップです。
古地図ビューア **[Maplat](https://github.com/code4history/Maplat)** を使って制作しています。

- 公開ページ（GitHub Pages）: https://furuhashilab.github.io/Hackathon_Oct_HimariNonaka/

> **現在の状態:** 現在の地図（地理院地図・航空写真・OpenStreetMap）を表示する土台まで完成しています。
> 古地図は国立国会図書館デジタルコレクションから選定中で、決まり次第追加します。

## このリポジトリについて

古橋研究室「10月 FOSS4G Hiroshima / SotM Asia OSAKA 振り返りハッカソン」（2026年10月・ソロハッカソン）の成果物です。

### ハッカソンの条件と対応

| 条件 | 対応 |
|---|---|
| FOSS4G Hiroshima / SotM Asia OSAKA で紹介された、初めて使う技術を 1 つ使う | Maplat を使用（下記「使用した技術」参照） |
| ソロハッカソン | 1 人で制作 |
| AI は Claude Code のみ使用 | 使用した AI は Claude Code のみ |
| FuruhashiLab Organization 下のリポジトリで GitHub Pages として公開 | `furuhashilab/Hackathon_Oct_HimariNonaka` で公開 |
| GitHub の更新作業はなるべく Claude Code で行う | ファイルの作成・更新・コミットは Claude Code で実施 |
| ライセンスは CC BY 4.0 | [LICENSE](LICENSE) 参照（第三者の素材は除く。下記「ライセンス」参照） |

## 使用した技術: Maplat

Maplat は、古地図や絵地図を **ゆがみを直さずにそのまま** 現在の地図と対応づけて表示できるオープンソースの古地図ビューアです。

FOSS4G Hiroshima 2026 での紹介:

- 「Bringing Old Maps & Illustrated Maps to the Web: 10 Years of Maplat and Turning Misalignment into Innovation」（大塚恒平, 2026-09-02）
  - 発表ページ: https://talks.osgeo.org/foss4g-2026/talk/33TQQC/
  - スライド: https://speakerdeck.com/kochizufan/maplat-foss4g-hiroshima-2026-talk
- 「From Open Source to Real-World Impact: Building Sustainable Geospatial Solutions with Maplat」（2026-09-03）
  - 発表ページ: https://talks.osgeo.org/foss4g-2026/talk/JSFCU7/

## ファイル構成

| ファイル・フォルダ | 役割 |
|---|---|
| `index.html` | Web ページ本体。OpenLayers と Maplat UI を CDN（jsDelivr）から読み込みます |
| `apps/fuchinobe.json` | 地図アプリの設定（表示する地図の種類、最初に表示する位置・ズームなど） |
| `assets/` | Maplat UI が使う言語ファイル・アイコン画像（`@maplat/ui` 1.1.0 から複製） |
| `LICENSE` | このリポジトリの作品のライセンス（CC BY 4.0） |

## 手元で表示する方法

`index.html` をダブルクリックで開くだけでは、設定ファイルを読み込めず表示されません。
ローカルで確認する場合は、リポジトリのフォルダで次のコマンドを実行し、ブラウザで http://localhost:8000/ を開きます。

```bash
python -m http.server 8000
```

## ライセンス

このリポジトリで作成した作品（HTML・設定ファイル・文章など）は
**[クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/deed.ja)** で公開します。

© 2026 Himari Nonaka

所属: 青山学院大学 古橋研究室（Furuhashi Laboratory, Aoyama Gakuin University）

ただし、以下の第三者の素材・ソフトウェアには、それぞれのライセンス・利用条件が適用されます（CC BY 4.0 の対象外です）。

| 素材・ソフトウェア | 権利者・出典 | ライセンス・利用条件 |
|---|---|---|
| Maplat UI（`@maplat/ui` 1.1.0。CDN から読み込み、`assets/` に一部を同梱） | Kohei Otsuka, Code for History / Nayuta, Inc. | [Apache License 2.0](assets/LICENSE-Maplat.txt) |
| OpenLayers（`ol` 10.11.0。CDN から読み込み） | OpenLayers Contributors | [BSD 2-Clause License](https://github.com/openlayers/openlayers/blob/main/LICENSE.md) |
| 地理院地図（標準地図・航空写真） | 出典: 国土地理院 | [国土地理院コンテンツ利用規約](https://www.gsi.go.jp/kikakuchousei/kikakuchousei40182.html) |
| OpenStreetMap | © OpenStreetMap contributors | [ODbL](https://www.openstreetmap.org/copyright) |
| 古地図画像 | （選定後に記載） | （選定後に記載。保護期間満了のものを使用予定） |

## 制作の進み具合

- [x] ステップ1: README と LICENSE（CC BY 4.0）の作成
- [x] ステップ2: Maplat で現在の地図を表示する土台の作成
- [ ] GitHub Pages での公開確認
- [ ] ステップ3: 古地図の選定と MaplatEditor でのデータ作成
- [ ] ステップ4: 古地図の表示
- [ ] ステップ5: 仕上げ（出典表記・スマホ表示の確認）
- [ ] ステップ6: 発表準備（ブログ・グラレコ）
