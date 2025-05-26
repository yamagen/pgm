# All Projects Overview – Updated Edition (English)

## Overview

This document outlines the structure of all ongoing linguistic research projects, centered around the Process Grammar Model (PGM), while also encompassing AEAD, classical text translation, glossing systems, utility tools, educational applications, and standardization of descriptive formats.

## AEAD: An Expression A Day

AEAD is a long-term project that records one naturally occurring Japanese expression per day based on immediate grammar principles. Over 400 entries have been documented. Each entry is stored in JSON format and includes the Japanese and English expressions, meanings, intentions, tags, and adjusted expressions.

## Nihongo Notes

"Nihongo Notes" is a reflective essay series exploring topics related to AEAD and PGM. Vol.1 (entries No.001–No.014) is scheduled for release on Zenodo in May 2025. Each entry is written in both Japanese and English, focusing on syntax, semantics, implicit meaning, and grammatical thought.

## Translation Projects: Ise Monogatari and Tosa Nikki

These classical texts are translated using a three-layered structure: strict literal translation, phrase gloss, and natural translation. Glosses follow the Leipzig Glossing Rules (LGR) along with custom Japanese extensions. Annotations are divided into "notes" and "gloss-notes" to clarify structure, word meaning, and cultural background.

## Gloss Design and Linguistic Resource Standardization

Gloss abbreviations (LGR-compliant) and nonLGR extensions (Japan-specific) are managed in JSON format. The gloss-linter supports detection of undefined or ambiguous abbreviations. Dictionary structures and gloss syntax are designed as reusable linguistic resources.

## PGM: Process Grammar Model

**Stance First Theory** is proposed as the central framework on the immediate grammar side of the Process Grammar Model. It emphasizes the primacy of stance—the psychological attitude that precedes syntax and semantics. Drawing on Du Bois's "Stance Triangle," AEAD entries are structured using a triple+extension format (category, stance, word) as a foundation for semantic description.

**Phrase Gloss Method** supports the three-layered translation model (literal → phrase gloss → natural). It structures glosses by phrase, rather than word, allowing better alignment between word order and semantic units. This enhances structural inclusivity and is being systematically applied in the Ise Monogatari and Tosa Nikki translation projects.

The Process Grammar Model as a whole is a two-axis utterance generation model consisting of Immediate Grammar and Adjustive Grammar. It incorporates phenomena like the Tasuki-gake Effect and usage-condition constraints. The theory is currently being formulated in both prose and formal notation.

## Tools: gloss-linter, k2g, gloss-rewriter

Tools such as k2g (classical Japanese morphological analyzer), gloss-rewriter (abbreviation transformation), and gloss-linter (gloss consistency checker) are developed and maintained to support JSON-based glossing. Plans include integration via GUI and CLI interfaces.

## CW: Cooccurrence Pattern Weighting

**cw** is a preprocessing tool that assigns weights to cooccurrence patterns of any two words within waka and poetic expressions. It extracts high-weight pairs for use in cooccurrence graph visualization, poetic compression, and typological analysis. It is especially used for preparing base data for 31-mora compressed waka generation, and is expected to be linked with AEAD vocabulary and expanded into semantic network modeling.

## Future Plans and Release Schedule

- June 2025: Release of Nihongo Notes Vol.1 (via Zenodo)
- During 2025: Draft publication of PGM theory / AEAD reaches No.500 / Official release of gloss-linter / Completion of Ise and Tosa translations

Moving forward, we aim to deepen the descriptive modeling of meaning—including that which remains unspoken—while advancing standardization of representational structures.
