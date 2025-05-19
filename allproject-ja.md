# All Projects Overview – Updated Edition

## 全体構想（Overview）

この文書は、現在進行中の言語研究プロジェクト全体を構造的に記述することを目的とする。即時文法（PGM）を中心としつつ、AEAD、古典テキスト翻訳、Gloss設計、ツール群、教育応用、記述標準化など、多面的な展開を含む。

## AEAD: An Expression A Day

AEAD（An Expression A Day）は、即時文法に基づいた自然発話の表現を1日1件記録する長期プロジェクトであり、すでにNo.400を超えている。各エントリは、表現（日本語・英語）、語義、意図、タグ、調整表現（adjusted-expression）を含むJSON形式で記録される。

## Nihongo Notes: 日本語のおと

「日本語のおと」は、AEADやPGMに関連する思索を、エッセイ形式で継続的に記述するシリーズである。Vol.1（No.001–No.014）は2025年5月末にZenodoにてリリース予定。すべて英日両文で記述され、構文や意味、語られなさ、文法思想に焦点を当てている。

## 翻訳プロジェクト: 伊勢物語と土佐日記

両作品は、3層構造（逐語訳・phrase gloss・自然訳）で翻訳され、glossはLeipzig Glossing Rulesと非LGR略語によって記述されている。注釈はnotesとgloss-notesに分離され、構文・語義・文化的背景を網羅する。

## Gloss記述と言語資源の標準化

glossary-abbreviations（LGR準拠）とnonLGR-abbreviations（日本語独自拡張）をJSONで管理。gloss-linter により未定義記号や曖昧略語の検出を支援。辞書構造や記述構文は再利用可能な資源として設計されている。

## PGM: プロセス文法モデル

Process Grammar Modelは、即時文法と調整文法の2軸による発話生成モデルであり、Tasuki-gake Effect や使用文脈の選択条件なども理論に含まれる。記述は文章と数式の両形式で進行中。

## スタンス先行理論

Stance First Theory（スタンス先行理論）は、プロセス文法モデルにおける即時文法側の中心的枠組みとして提唱され、語の意味や構文に先立つ心理的態度（スタンス）の表出を第一義とする。Du Bois の「スタンストライアングル」理論を踏まえ、AEADの各エントリに triple+extension（category, stance, word）形式を適用し、意味記述の構造基盤とする。

## Phrase Gloss Method

Phrase Gloss Method は、逐語訳・phrase gloss・自然訳の三層構造記述を支える技術であり、語単位ではなく句単位で gloss を構成することにより、語順と意味単位のズレを補正し、構文的意味の包摂性を高める記述法として位置づけられる。現在、伊勢物語および土佐日記の翻訳において体系的に実装されている。

## ツール群: gloss-linter, k2g, gloss-rewriter

k2g（古語形態素解析）、gloss-rewriter（略語変換）、gloss-linter（gloss整合性検証）など、JSON形式のgloss記述を支援・管理するユーティリティを自作・運用中。今後GUIや統合CLIの開発も視野に入れている。

## 今後の展望とリリース計画

- 2025年6月：Nihongo Notes Vol.1（Zenodoリリース）
- 2025年中：PGM理論草稿の公開／AEAD No.500到達／gloss-linter正式版公開／伊勢・土佐翻訳完結の見通し

記述構造の標準化と、語られなさを含む意味生成の記述的理解にむけて、今後も多層的に進行予定。
