---
dependencies: []
disable_edit: true
kind: documentation
title: 本番コードで assert を使用しない
---
## メタデータ
**ID:** `python-best-practices/no-assert`

**言語:** Python

**重大度:** エラー

**カテゴリー:** ベストプラクティス

## 説明
コード中に `assert` ステートメントを記述することは避けてください。このルールは `_test.py` で終わるようなテストファイルには適用されません。

## 非準拠コードの例
```python
def foo(bar):
  assert bar  # 本番コードではアサートなし
```

## 準拠コードの例
```python
def foo(bar):
  assert bar  # テストコードではアサート OK
```