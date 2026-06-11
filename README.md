# zdps-translations

[ZDPS](https://github.com/Blue-Protocol-Source/BPSR-ZDPS) のテーブルデータに対する
**日本語・韓国語・中国語の名称対応表**。スタレゾ（ブループロトコル：スターレゾナンス）
ASIA クライアントから取り出した、ゲーム内の各言語テキストを ZDPS のテーブルID
（スキル/MOB等）に紐付けたもの。

ブループロトコル：スターレゾナンス バージョン `1.0.42184.0_C42184_R42184` 時点のデータ。

## 形式

ZDPS の各テーブルに対応する JSON を収録。各エントリの形式:

```json
"1101": {
  "en": "Marker 1",
  "zh": "场地标记01",
  "ja": "フィールドマーク01",
  "ko": "필드 표시01",
  "zh_fallback": false,
  "ja_fallback": false,
  "ko_fallback": false
}
```

- キーは ZDPS のテーブルID（`AppStrings` のみ職業キー）。
- `en` は ZDPS の `Name`。`zh`/`ja`/`ko` はゲームのローカライズデータから取得。
- 該当言語の訳が無い場合は `en` をフォールバックで入れ、その言語の `*_fallback` を `true` にする。

## 収録テーブル

AppStrings（職業・サブ職）, SkillTable, MonsterTable, ItemTable, BuffTable,
DungeonsTable, SceneTable, ModTable, DummyTable, FightAttrTable, TempAttrTable,
SkillFightLevelTable。

> 一致率の低いテーブル（FightAttr / Dummy / TempAttr / SkillFightLevel など）は、
> 開発用の内部名で、ゲーム本体にも訳が存在しない項目を多く含む。
> これらは `*_fallback: true` で en が入る。

## 注意

- 本リポジトリは非公式・非営利のコミュニティ向け資料であり、ゲームの開発元・運営とは
  一切関係ありません。データは現状有姿（as is）で提供され、正確性は保証しません。
- 権利者からの要請があれば速やかに削除します。
