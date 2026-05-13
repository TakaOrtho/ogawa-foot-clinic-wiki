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
structure_version: 3  # 2026-05-13: 3サブカテゴリ（病態・診断 / 保存治療 / 手術治療と後療法）に再編。診断は病態と統合、後療法は手術と統合
---

# PRJ-018 足の外科 学習ウィキ

## 依頼の経緯

看護師から「足の手術の勉強がしたい」との依頼。
看護師・理学療法士・研修医が現場で参照でき、患者にもそのまま見せられる教育サイトを GitHub Pages 上に構築・運用する。

## ゴール

- **対象疾患（初回4疾患）**:
    1. 足関節不安定症（Chronic Ankle Instability）
    2. 外側側副靱帯損傷（Lateral Ankle Ligament Injury）
    3. 外反母趾（Hallux Valgus）
    4. 変形性足関節症（Ankle Osteoarthritis）
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
    │   ├── ankle-instability/    # ★ 完全版
    │   │   ├── index.md          (概要・要点)
    │   │   ├── pathology.md      (病態・診断)
    │   │   ├── conservative.md   (保存治療)
    │   │   └── surgical.md       (手術治療と後療法)
    │   ├── lateral-ligament-injury/    # 骨子（同じ4ファイル構成）
    │   ├── hallux-valgus/              # ★ 完全版（同じ4ファイル構成）
    │   └── ankle-osteoarthritis/       # 骨子（同じ4ファイル構成）
    └── patient/                  # 患者さん向け
        ├── index.md
        ├── ankle-instability.md       ★ 完全版
        ├── lateral-ligament-injury.md 骨子
        ├── hallux-valgus.md           骨子
        └── ankle-osteoarthritis.md    骨子
```

---

## コンテンツ進捗チェックリスト

### 医療従事者向け（3サブカテゴリ）

| 疾患 | 病態・診断 | 保存治療 | 手術治療と後療法 |
|------|:---:|:---:|:---:|
| 足関節不安定症 | ✅ | ✅ | ✅ |
| 外側側副靱帯損傷 | 🟡 | 🟡 | 🟡 |
| 外反母趾 | ✅ | ✅ | ✅ |
| 変形性足関節症 | 🟡 | 🟡 | 🟡 |

### 患者さん向け

| 疾患 | 状態 |
|------|:---:|
| 足関節不安定症 | ✅ 完全 |
| 外側側副靱帯損傷 | 🟡 骨子 |
| 外反母趾 | ✅ 完全 |
| 変形性足関節症 | 🟡 骨子 |

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

1. 看護師から具体的なフィードバックを収集（足関節不安定症・外反母趾ページの読みやすさ・抜け）
2. **変形性足関節症** を完全版に拡張（TAA vs Arthrodesis 選択の患者説明、術後リハ細分化）
3. **外側側副靱帯損傷** 急性期版を完全版に拡張（救急外来・整形外来での初期対応）
4. 図版・シェーマの作成（footprint、解剖図、術式模式図）
5. 検索エンジンへの登録（Google Search Console、Bing Webmaster）
6. （オプション）独自ドメイン化（例: `foot.ogawa-md.jp`）

## 履歴

- **2026-05-13**: **構成リファクタ（structure v3）** — 5サブカテゴリ → 3サブカテゴリへ統合。病態+診断 → `pathology.md`、手術+後療法 → `surgical.md`。患者の臨床思考フローに沿う形へ
- **2026-05-13**: **外反母趾を完全版化** — 当院臨床ノウハウ（MICA + DMMO、弾性包帯圧迫、専用サンダル6週、翌日からMTP-ROM、抜糸10–14日、シャワー可否）を全5サブカテゴリ + 患者向けに反映
- **2026-05-13**: **構成リファクタ（structure v2）** — 「看護師向け」「PT向け」の対象別ページを廃止し、医療従事者向けを **病態 / 診断 / 保存治療 / 手術治療 / 後療法** の5サブカテゴリに再編。看護師の周術期管理・観察項目、PT のリハビリプロトコルは「後療法」セクションに統合
- **2026-05-13**: GitHub リポジトリ作成・初回 push・GitHub Pages 公開（HTTP 200 確認済み）
- **2026-05-12**: MkDocs Material プロジェクト初期化、足関節不安定症 完全版作成、他3疾患の骨子作成
- **2026-05-12**: 看護師から学習サイト構築の依頼受領
