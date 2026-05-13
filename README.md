# 足の外科 学習ウィキ（Ogawa Foot Clinic Wiki）

[![Deploy](https://github.com/TakaOrtho/ogawa-foot-clinic-wiki/actions/workflows/deploy.yml/badge.svg)](https://github.com/TakaOrtho/ogawa-foot-clinic-wiki/actions/workflows/deploy.yml)

足関節・足部疾患の **病態・治療・看護・リハビリ・患者向け情報** をまとめた教育サイトのリポジトリです。
看護師・理学療法士・研修医・患者さんがそれぞれの目的に応じて参照できるよう、対象別ページに分けて構成しています。

公開サイト: <https://takaortho.github.io/ogawa-foot-clinic-wiki/>

---

## 取り扱う疾患

1. 足関節不安定症（Chronic Ankle Instability）
2. 外側側副靱帯損傷（Lateral Ankle Ligament Injury）
3. 外反母趾（Hallux Valgus）
4. 変形性足関節症（Ankle Osteoarthritis）

各疾患について以下の3視点でページを用意しています。

- 医療従事者向け（病態・診断・治療・術式）
- 看護師向け（周術期管理・観察・退院指導）
- 理学療法士向け（リハビリプロトコル）
- 患者さん向け（やさしい解説）

---

## ローカルでプレビュー

前提: Python 3.11 以上、git。

```bash
git clone https://github.com/TakaOrtho/ogawa-foot-clinic-wiki.git
cd ogawa-foot-clinic-wiki
pip install -r requirements.txt
mkdocs serve
```

ブラウザで <http://127.0.0.1:8000> を開く。

## ビルド

```bash
mkdocs build
```

`site/` ディレクトリに静的ファイルが生成されます。

## デプロイ

`main` ブランチに push すると GitHub Actions（`.github/workflows/deploy.yml`）が自動で GitHub Pages に公開します。

---

## ディレクトリ構成

```
ogawa-foot-clinic-wiki/
├── mkdocs.yml                    # サイト設定
├── requirements.txt              # Python依存
├── docs/                         # コンテンツ
│   ├── index.md                  # トップ
│   ├── disclaimer.md             # 免責事項
│   ├── stylesheets/extra.css     # ブランドCSS（紺アクセント）
│   ├── clinical/                 # 医療従事者向け
│   │   ├── index.md
│   │   ├── ankle-instability/    # 足関節不安定症（完全版）
│   │   ├── lateral-ligament-injury/
│   │   ├── hallux-valgus/
│   │   └── ankle-osteoarthritis/
│   └── patient/                  # 患者さん向け
│       ├── index.md
│       ├── ankle-instability.md
│       ├── lateral-ligament-injury.md
│       ├── hallux-valgus.md
│       └── ankle-osteoarthritis.md
└── .github/workflows/deploy.yml  # GitHub Pages デプロイ
```

---

## 編集ポリシー

- 医療情報の正確性を最優先
- 患者向けは平易な日本語で
- ガイドライン・査読論文を一次情報として優先
- 個人を特定できる情報・症例画像は含めない

## 免責事項

本サイトは教育目的の一般情報であり、個別診療判断に置き換わるものではありません。
詳細は [docs/disclaimer.md](docs/disclaimer.md) を参照。

## 編集者

**Takahisa OGAWA**, M.D., MPH, Ph.D. — 整形外科専門医／足の外科

## ライセンス

本文・コンテンツ: CC BY-NC 4.0（要相談で改変・再配布可、商用不可）
コード（mkdocs.yml, CSS等）: MIT
