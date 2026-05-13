---
id: PRJ-018
title: 足の外科 学習ウィキ（医療従事者・患者向け教育サイト）
category: clinical
status: 進行中
created: 2026-05-12
last_updated: 2026-05-13
deadline: null
repo: https://github.com/TakaOrtho/ogawa-foot-clinic-wiki
site: https://takaortho.github.io/ogawa-foot-clinic-wiki/
local_path: projects/clinical/ogawa-foot-clinic-wiki/
structure_version: 6  # 2026-05-13: フェーズ2a（解剖図・術式図 8枚追加、SEO下地：robots.txt、OGP画像、site_description強化、keywords追加）
---

# PRJ-018 足の外科 学習ウィキ

## 依頼の経緯

看護師から「足の手術の勉強がしたい」との依頼。
看護師・理学療法士・研修医が現場で参照でき、患者にもそのまま見せられる教育サイトを GitHub Pages 上に構築・運用する。

## ゴール

- **対象疾患（4疾患）**:
    1. **足関節不安定症（外側側副靱帯損傷を含む）** — 急性捻挫から慢性 CAI までを一連の連続病態として記述
    2. 外反母趾（Hallux Valgus）
    3. 変形性足関節症（Ankle Osteoarthritis）
    4. **扁平足（Adult Acquired Flatfoot Deformity）** — Flexible/Rigid の2タイプ別戦略
- **構成（疾患ごと）**:
    - 医療従事者向け（看護師・PT・医師を統合した1系統）
        - **病態・診断** / **保存治療** / **手術治療と後療法**（3サブカテゴリ）
        - ※ 看護師の周術期管理・観察項目、PT のリハビリプロトコルは「手術治療と後療法」に統合
    - 患者さん向け（やさしい解説、疾患ごとに1ページ）
- **媒体**: GitHub Pages（MkDocs Material）、自動デプロイ

---

## アクセス情報

| 項目 | URL / 場所 |
|---|---|
| 🌐 **公開サイト** | <https://takaortho.github.io/ogawa-foot-clinic-wiki/> |
| 📦 **GitHub リポジトリ** | <https://github.com/TakaOrtho/ogawa-foot-clinic-wiki> |
| ⚙️ **GitHub Actions（デプロイ状況）** | <https://github.com/TakaOrtho/ogawa-foot-clinic-wiki/actions> |
| 📁 **ローカル作業フォルダ** | `c:\Users\takah\Dropbox\my_wiki\projects\clinical\ogawa-foot-clinic-wiki\` |
| 🔐 **認証** | gh CLI（GitHubアカウント `TakaOrtho`、認証済み・keyring保存） |

---

## 編集クイックスタート

### A. AI秘書に頼む（推奨）

セッション内で以下のように依頼するだけで、AI秘書が編集→ローカル確認→commit→pushまで実行します。

> 「足の外科ウィキの〇〇の章を◯◯に直して」
> 「PRJ-018 で **外反母趾** の医療従事者ページを完全版に拡張して」
> 「PRJ-018 にトピック『偽痛風』を追加して」

`PROJECT.md` の最初の `local_path` を見て自動でディレクトリ移動します。

### B. 自分で編集する場合（ローカルプレビュー付き）

```powershell
# 1. プロジェクトに移動
cd c:\Users\takah\Dropbox\my_wiki\projects\clinical\ogawa-foot-clinic-wiki

# 2. ローカルでプレビューサーバ起動（http://127.0.0.1:8000）
mkdocs serve

# 3. docs/ 配下の .md を編集 → 保存すると自動リロード

# 4. 反映
git add .
git commit -m "Update <変更内容>"
git push
# → GitHub Actions が約1-2分で自動デプロイ
```

### C. 自分で編集する場合（GitHub上で直接編集）

各ページ右上の **「鉛筆アイコン」**（edit_uri）から GitHub.com で直接編集可能。
コミット保存するだけで自動デプロイされる。スマホからも可。

---

## ファイル構成

```
ogawa-foot-clinic-wiki/
├── PROJECT.md                    # ← このファイル（プロジェクト管理）
├── mkdocs.yml                    # サイト設定
├── requirements.txt              # Python依存
├── README.md                     # GitHub用README
├── LICENSE                       # MIT (code) + CC BY-NC 4.0 (content)
├── .gitignore
├── .github/workflows/deploy.yml  # GitHub Actions → Pages自動デプロイ
└── docs/
    ├── index.md                  # トップページ
    ├── disclaimer.md             # 免責事項
    ├── stylesheets/extra.css     # ブランド（紺#1F3A5F アクセント）
    ├── clinical/                 # 医療従事者向け
    │   ├── index.md
    │   ├── ankle-instability/    # ★ 完全版（外側側副靱帯損傷を統合）
    │   │   ├── index.md          (概要・要点)
    │   │   ├── pathology.md      (病態・診断)
    │   │   ├── conservative.md   (保存治療)
    │   │   └── surgical.md       (手術治療と後療法)
    │   ├── hallux-valgus/              # ★ 完全版（同じ4ファイル構成）
    │   ├── ankle-osteoarthritis/       # ★ 完全版（同じ4ファイル構成）
    │   └── flatfoot/                   # ★ 完全版・新規（同じ4ファイル構成）
    └── patient/                  # 患者さん向け
        ├── index.md
        ├── ankle-instability.md       ★ 完全版（足首の捻挫含む）
        ├── hallux-valgus.md           ★ 完全版
        ├── ankle-osteoarthritis.md    ★ 完全版
        └── flatfoot.md                ★ 完全版・新規
```

---

## コンテンツ進捗チェックリスト

### 医療従事者向け（3サブカテゴリ）

| 疾患 | 病態・診断 | 保存治療 | 手術治療と後療法 |
|------|:---:|:---:|:---:|
| 足関節不安定症（外側側副靱帯損傷含む） | ✅ | ✅ | ✅ |
| 外反母趾 | ✅ | ✅ | ✅ |
| 変形性足関節症 | ✅ | ✅ | ✅ |
| 扁平足 | ✅ | ✅ | ✅ |

### 患者さん向け

| 疾患 | 状態 |
|------|:---:|
| 足関節不安定症・足首の捻挫 | ✅ 完全 |
| 外反母趾 | ✅ 完全 |
| 変形性足関節症 | ✅ 完全 |
| 扁平足 | ✅ 完全 |

凡例: ✅ 完全版 ／ 🟡 骨子（要拡張） ／ ⬜ 未着手

---

## 運用ルール

1. **個人情報・症例特定情報は絶対に含めない**（一般化されたシェーマ・編集者作成図のみ）
2. **エビデンスは可能な限り一次情報**（ガイドライン・査読論文）を出典明示
3. **患者向けページ**は中学生でも読める語彙を心がける
4. **デザイン**は `config/branding.md` の Pattern 1（紺アクセント）に準拠（CSS で実装済）
5. **mainブランチ push = 即公開**。下書きは feature ブランチ or 別 commit に分けて検証
6. **strict ビルド警告ゼロ** を維持（リンク切れ・参照漏れチェック）

## 著作権・ライセンス

- **コード**（mkdocs.yml, CSS等）: MIT License
- **コンテンツ**（docs/ 配下の .md）: CC BY-NC 4.0（教育目的の引用可、商用不可）
- 編集者: Takahisa OGAWA, M.D., MPH, Ph.D.

## 次の一歩（優先順）

1. **Google Search Console / Bing Webmaster の所有権確認**（ユーザー操作 → 認証コード共有 → 私が `docs/` に HTML ファイルを配置 → サイトマップ送信）
2. 看護師からのフィードバック収集（4疾患すべての読みやすさ・抜け・実臨床との整合）
3. 用語集・略語集ページの新設（PTT, MICA, DMMO, SMOT, TAA, MDCO, AAFD など）
4. 症例ベースの読み物追加（匿名化症例レポート）
5. アクセス解析の導入（Plausible / GA4）
6. （オプション）独自ドメイン化、英語版の整備

## Google / Bing Search Console 登録手順（ユーザー操作）

1. <https://search.google.com/search-console> にアクセス
2. URL プレフィックスで `https://takaortho.github.io/ogawa-foot-clinic-wiki/` を登録
3. 所有権確認 → 「HTML ファイル」を選択 → `google-XXXXXXXX.html` をダウンロード
4. ファイルを AI 秘書に渡す → `docs/` 直下に配置 → commit & push
5. 1-2 分で GitHub Pages にデプロイされる → Search Console で「確認」をクリック
6. サイトマップ送信: `sitemap.xml` を Search Console の「サイトマップ」から送信
7. 同様に <https://www.bing.com/webmasters> でも実施（XML サイトマップを送るだけでも可）

`docs/robots.txt` は配置済み。サイトマップは MkDocs が自動生成しています。

## 履歴

- **2026-05-13**: **フェーズ2a 図解充実 + SEO下地（structure v6）** — 解剖図・術式図 8枚追加（前足部ヒール靴、関節鏡視下 Broström、松葉杖+非荷重、足OA 3術式比較、DMMO、MICA chevron、PTT走行、階段昇降ルール）。患者向け4ページ・医療従事者向け4ページの該当箇所に挿入。**SEO下地整備**：`docs/robots.txt` 作成、`mkdocs.yml` の site_description 強化、OGP 画像（hero-foot-anatomy.png）と keywords 配列を追加。GitHub Search Console / Bing 認証ファイルは次セッションで配置予定。18ファイル変更、+75/-2 行
- **2026-05-13**: **フェーズ1 サイト磨き込み（structure v5）** — レビュー意見を反映：(1) `:material-foot-print-outline:` アイコン表示バグを `:material-shoe-print:` に修正、(2) AI生成シェーマ画像4枚（hero foot anatomy / hallux valgus / ankle ligaments / flatfoot）を `docs/assets/images/` に配置・各患者ページに挿入、(3) `docs/stylesheets/extra.css` にタイポグラフィ仕上げ・スマホレスポンシブ（≤480px, ≤768px）・ヒーロー/CTA カードCSS・患者intro callout を追加、(4) `docs/index.md` をヒーロー画像+患者/医療者の大きなCTAカードに改修、(5) `docs/patient/index.md` を会話調 + 症状から探す + 診察室で聞きたい質問メモ Q&A化、(6) 患者向け4ページ全文を会話調リライト（症状ベースサマリー、強い表現の緩和、危険サインに「なぜ大事か」追記、FAQ拡充）。医療従事者向けは現状のマニュアル調を維持。12ファイル変更、+751/-391行
- **2026-05-13**: **疾患リスト再編（structure v4）** — 外側側副靱帯損傷を足関節不安定症に統合（同一スペクトラム）、**扁平足を新規追加**。最終4疾患構成（足関節不安定症・外反母趾・変形性足関節症・扁平足）に。3疾患を完全版化（足関節不安定症統合版：関節鏡視下 Broström・翌日歩行・6週復帰／変形性足関節症：推奨順=骨切り→TAA→固定／扁平足：Flexible=靱帯再建、Rigid=骨切り、共通=6週非荷重+3か月サポーター）。24ファイル変更、+1529/-885行
- **2026-05-13**: **構成リファクタ（structure v3）** — 5サブカテゴリ → 3サブカテゴリへ統合。病態+診断 → `pathology.md`、手術+後療法 → `surgical.md`。患者の臨床思考フローに沿う形へ
- **2026-05-13**: **外反母趾を完全版化** — 当院臨床ノウハウ（MICA + DMMO、弾性包帯圧迫、専用サンダル6週、翌日からMTP-ROM、抜糸10–14日、シャワー可否）を全5サブカテゴリ + 患者向けに反映
- **2026-05-13**: **構成リファクタ（structure v2）** — 「看護師向け」「PT向け」の対象別ページを廃止し、医療従事者向けを **病態 / 診断 / 保存治療 / 手術治療 / 後療法** の5サブカテゴリに再編。看護師の周術期管理・観察項目、PT のリハビリプロトコルは「後療法」セクションに統合
- **2026-05-13**: GitHub リポジトリ作成・初回 push・GitHub Pages 公開（HTTP 200 確認済み）
- **2026-05-12**: MkDocs Material プロジェクト初期化、足関節不安定症 完全版作成、他3疾患の骨子作成
- **2026-05-12**: 看護師から学習サイト構築の依頼受領
