# hello-helm
動作確認用リポジトリ

```bash
# 作成方法
helm create hello-helm
```
こちらをベースに以下を確認

- templatesの使い方
- templatesにGitSubmoduleを使い、他のリポジトリを流用する使い方

## 前提条件
kubenertes環境が構築されている事
```bash
kubectl version
helm version
```

## 基本コマンド
```bash
# カレントディレクトリでHelmアプリケーションを作成
helm install hello-helm .
# Helmから展開されたマニフェストファイルの確認
helm install test --dry-run .
# 終了
helm delete hello-helm
```
