# FAQ・トラブルシューティング
こちらは、[N予備校プログラミングコース FAQ・トラブルシューティング](https://nnn-training.github.io/faq)の GitHub リポジトリです。


## ライセンス

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />この サイト は <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">クリエイティブ・コモンズ 表示 - 継承 4.0 国際 ライセンス</a>の下に提供されています。

## ざっくり概要

**`/MARKDOWN/` フォルダ配下のマークダウンファイルを編集するだけで、自動的にページと目次が作成されます。**

このリポジトリは、どなたでもプルリクエストを提出することができます。 
リポジトリをフォークして、マークダウンファイルを編集したのち、プルリクエストを送ってください。

## プルリクエストの出し方

### マークダウンで編集するだけ
このサイトのページは、**マークダウン**と呼ばれる形式で、簡潔に編集することができます。 
マークダウンで編集し、`main` ブランチにマージするだけで、**自動的に**ページと目次が作成されるようになっています。 
このサイトそのものの機能を改修するとき以外は、`/MARKDOWN/` フォルダ以外のファイルを編集する必要はありません。

### マークダウン形式の書き方
マークダウン形式のファイル拡張子は `.md` です。 マークダウン形式では、例えば

```
# 見出し大
## 見出し中
### 見出し小
- 箇条書き a
- 箇条書き b
**太字** 
```

などのように書くことで、簡潔に構造化された文書を記述することができます。 
詳しい書き方は、検索サイトで調べてみてください。

### メタ情報の書き方
このサイトでは、マークダウン形式のファイルの冒頭に

```
---
title: サンプルタイトル
---
# サンプルタイトル

（後略）
```

のように書くことで、ファイルのメタ情報を記述できます。 
**この `title`は、目次のタイトルになりますので、必ず記述してください。**

## このサイトの構成
このサイトは Next.js + TypeScript で実装されています。 
サイトそのものの機能を改修するとき以外、Next.js や TypeScript の知識は必要ありません。

## デプロイの仕組み
このリポジトリの `main` ブランチに変更がマージされると、GitHub Actions によって自動的に Next.js アプリのビルドが開始されます。 
ビルド時に、マークダウンファイルは HTML 形式に変換されます。さらに、マークダウンのフォルダ構成から、自動的に目次が作成されます。 
ビルド後は、GitHub Pages で表示可能な形にアプリケーションが export され、最終的に `gh-pages` ブランチに格納されることで、GitHub Pages にデプロイされます。

## ローカル環境でこのサイトを表示するには
マークダウンの編集結果をお手元の環境で確認することができます。 
この作業は、プルリクエストに必須ではありません（ただし、サイトそのものの機能を改修するときは必ず確認してください）。 
2 つの方法があります。

1. Docker を利用する方法
2. ローカルの Node.js 環境を利用する方法

### 1. Docker を利用する方法
お使いの PC（Windows または Mac）に Docker Desktop がインストールされている必要があります。 
このリポジトリをフォークして、クローンします。

```bash
$ cd 作業ディレクトリ
$ git clone git@github.com:nnn-training/faq.git
$ cd faq
```

`docker-compose` を利用してコンテナを起動します。

```bash
$ docker-compose up -d
$ docker-compose exec app bash
```

コンテナのコンソールで Next.js アプリを起動します。

```bash
$ cd /app
$ yarn install
$ yarn dev
```

### 2. ローカルの Node.js を利用する方法
お使いの PC に、Node.js および Yarn がインストールされている必要があります。 
このリポジトリをフォークして、クローンします。

```bash
$ cd 作業ディレクトリ
$ git clone git@github.com:nnn-training/faq.git
$ cd faq
```

Next.js アプリを起動します。

```bash
$ yarn install
$ yarn dev
```
