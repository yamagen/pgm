# jq スニペット集と JSONL 整形レシピ

このドキュメントは、`jq` を使って `.jsonl`（JSON Lines）形式のファイルを処理するための基本的なコマンド・整形スニペットをまとめたものです。

対象データ形式は以下のようなものと想定します：

```json
{"stance": "joy", "category": "emotive", "word": "delight"}
{"stance": "joy", "category": "emotive", "word": "glad"}
{"stance": "hesitation", "category": "cognitive", "word": "hesitate"}
```

---

## 🔍 基本構文

### ファイル全体を読み込む

```bash
jq . stance-triples.jsonl
```

### 各行から `stance` フィールドだけを抽出

```bash
jq '.stance' stance-triples.jsonl
```

---

## 🎯 フィルタリング

### `category` が "emotive" の行のみ抽出

```bash
jq 'select(.category == "emotive")' stance-triples.jsonl
```

### `word` に "he" を含む行だけ抽出（部分一致）

```bash
jq 'select(.word | test("he"))' stance-triples.jsonl
```

---

## 🧵 データ構造の変換

### JSONL 全体を配列に変換（Slurp）

```bash
jq -s '.' stance-triples.jsonl
```

### JSONL 全体を配列にし、ユニークな stance 一覧を取得

```bash
jq -s '[.[][] | .stance] | unique' stance-triples.jsonl
```

---

## 🧹 整形・再出力

### 整形済みで再出力（インデントつき）

```bash
jq . stance-triples.jsonl > formatted.jsonl
```

### 条件付きフィルタ後にファイルとして保存

```bash
jq 'select(.category == "emotive")' stance-triples.jsonl > emotive.jsonl
```

### 複数フィールドでグループ化（例：stanceごとの語一覧）

```bash
jq -s 'group_by(.stance) | map({stance: .[0].stance, words: [.[] | .word]})' stance-triples.jsonl
```

---

## 🛠 よく使うパターンまとめ

| 用途               | コマンド例                                     |
| ------------------ | ---------------------------------------------- |
| 全体表示           | `jq .`                                         |
| 特定フィールド抽出 | `jq '.word'`                                   |
| 条件抽出           | `jq 'select(.category == "emotive")'`          |
| 配列に変換         | `jq -s '.'`                                    |
| 重複除去           | `jq -s 'unique_by(.stance, .category, .word)'` |
| 書き出し           | `> 出力ファイル名.jsonl`                       |

---

## 💬 備考

- `.jsonl` は「1行 = 1 JSON」なので、`jq` は行単位で処理する
- `-s`（--slurp）を使うと、全行を配列にまとめて一括処理ができる
- 複雑なネストや入れ子構造には `map`, `group_by`, `unique_by` などを組み合わせると強力

---

✅ 目的：stance と category のペア一覧を出力
🔧 JSONLファイルから重複を除いた一覧を取得：

jq -s 'map({stance, category}) | unique' stance-triples.jsonl

    -s は全行を配列にまとめる（slurp）

    map({stance, category}) は必要な2項目だけを抽出

    unique は重複行を除去

📄 出力例：

[
{ "stance": "joy", "category": "emotive" },
{ "stance": "sadness", "category": "emotive" },
{ "stance": "hesitation", "category": "cognitive" },
{ "stance": "hesitation", "category": "speech" }
]

✅ CSVにしたい場合：

jq -r '[.stance, .category] | @csv' stance-triples.jsonl | sort | uniq

    -r は raw 出力（引用符を取り除く）

    @csv は2項目をCSV形式に整形

    sort | uniq で一覧表化

🔁 並び替え例：カテゴリ→スタンス順

jq -r '[.category, .stance] | @csv' stance-triples.jsonl | sort | uniq

jq を使えば、stance と category の一覧表は即座に出力できます。
表形式・CSV・JSONなど、目的に応じて自由に切り替えが可能です。

## ✅ 参考

- jq公式: [https://stedolan.github.io/jq/manual/](https://stedolan.github.io/jq/manual/)
- JSONL仕様: [https://jsonlines.org/](https://jsonlines.org/)

---
