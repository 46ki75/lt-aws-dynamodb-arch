---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Welcome to Slidev
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# open graph
# seoMeta:
#  ogImage: https://cover.sli.dev
---

# Welcome to Slidev

Presentation slides for developers

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# Amazon DynamoDB とは？

Amazon DynamoDB は**サーバーレス**の**フルマネージド** **NoSQL** データベースです。

- サーバレス: 自動でスケーリング
- フルマネージド: アップグレードなどのメンテナンス不要
- 低レイテンシ: RDBMS のようなデータ増加に伴うパーフォーマンスの低下がほぼない

<!--
This is _another_ note
-->

---

# API の種類

|        |                                                                                                             |
| ------ | ----------------------------------------------------------------------------------------------------------- |
| Create | <ApiChip>PutItem</ApiChip> <ApiChip>BatchWriteItem</ApiChip>                                                |
| Read   | <ApiChip>GetItem</ApiChip> <ApiChip>BatchGetItem</ApiChip> <ApiChip>Query</ApiChip> <ApiChip>Scan</ApiChip> |
| Update | <ApiChip>UpdateItem</ApiChip> <ApiChip>PutItem</ApiChip>                                                    |
| Delete | <ApiChip>DeleteItem</ApiChip> <ApiChip>BatchWriteItem</ApiChip>                                             |

---

# CU (Capacity Unit) について

**Capacity Unit** とは、Amazon DynamoDB の**データベース操作の計算コスト**を指します。これは**レイテンシ**及び**金銭的コスト**に直結します。

Capacity Unit は書き込みと読み込みのそれぞれを区別します。

- RCU (Read Capacity Unit): 読み取り操作に使用する CU
- WCU (Write Capacity Unit): 書き込み(挿入・変更・削除)操作に使用する CU

## スループットモードの違い

Amazon DynamoDB の Capacity Unit には[2つのスループットモード](https://docs.aws.amazon.com/ja_jp/amazondynamodb/latest/developerguide/capacity-mode.html)があり、課金体系が違います。

- オンデマンド: Capacity Unit の上限を指定せず、使用された Capacity Unit の分だけ課金される。[^1]
- プロビジョンド: Capacity Unit の上限を設定し、設定値に基づいて時間課金される。

[^1]: サービスクォータによって実質的な制限あり

---

# 読み取り API の種類

## `GetItem`, `BatchGetItem`

- `GetItem`: 主キー ("PK" もしくは "PK と SK の組み合わせ") によってアイテムを1件取得するAPI
- `BatchGetItem`: `GetItem` をまとめて複数回実行できる API (通信ラウンドトリップが減る)

## `Query`

## `Scan`
