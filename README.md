# hello-helm
Helmチャート動作確認用リポジトリ
- サブモジュール化

```
templates
└ hello-helm-template(submodule)
 ├ .git
 ├ deployament.yaml
 ├ 
```
.gitはマニフェストファイルではない為、.helmignoreでHelmマニフェスト対象外にする

サブモジュールは3通りの方法で定義
- gitプロトコルを利用
  ```bash
  url = git@github.com:kick0131/hello-helm-template.git
  ```
- http(PAT)プロトコルを利用
  ```bash
  url = https://<user>:<PAT>@github.com/kick0131/hello-helm-template.git
  ```


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
# テンプレート変換(動作確認)
helm template .
# カレントディレクトリでHelmアプリケーションを作成
helm install hello-helm .
# Helmから展開されたマニフェストファイルの確認
helm install test --dry-run <chart name> .
# 終了
helm delete hello-helm
```
