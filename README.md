# codelabs-firestore-web
learn https://codelabs.developers.google.com/codelabs/firestore-web/

referenced repoitory readme
https://github.com/firebase/friendlyeats-web

```
# FriendlyEats (Web)

## Introduction

FriendlyEats is a restaurant recommendation app built on Cloud Firestore.
For more information about Firestore visit [the docs][firestore-docs].

[firestore-docs]: https://firebase.google.com/docs/firestore/

## Setup

Please follow the [Cloud Firestore Web Codelab](https://codelabs.developers.google.com/codelabs/firestore-web) to setup this project.

## Support

- [Firebase Support](https://firebase.google.com/support/)

## License

© Google, 2017. Licensed under an [Apache-2](../LICENSE) license.

## Build Status

[![Build Status](https://travis-ci.org/firebase/friendlyeats-web.svg?branch=master)](https://travis-ci.org/firebase/friendlyeats-web)

```

## 事前準備

Node.jsのインストール
(アプリケーションの実行とテストの要件ですが、最終的なアプリケーションはNode.jsに依存しません。)

## 学べること

- webアプリからFirestoreへのデータの読み書き
- Firestoreのデータ変更をリアルタイムに読み取る
- Firebase認証とセキュリティルールを使用してFirestoreのデータを保護する
- 複雑なFirestoreのクエリを書く

## メモ

- Firestoreのデータは、文書、コレクション、およびサブコレクションに分割
    - https://firebase.google.com/docs/firestore/data-model


> 警告: ドキュメントを削除しても、そのサブコレクションは削除されません。
> サブコレクションが関連付けられているドキュメントを削除しても、そのサブコレクションは削除されません。その後もサブコレクションには、リファレンスによるアクセスが可能です。たとえば、db.collection('coll').doc('doc') によって参照されるドキュメントは存在しなくなったにもかかわらず、db.collection('coll').doc('doc').collection('subcoll').doc('subdoc') によって参照されるドキュメントは存在する場合があります。ドキュメントを削除するときにサブコレクション内のドキュメントも削除する場合は、コレクションを削除するで説明されているように、手動で削除する必要があります

- Query.get()メソッドを使用してリアルタイム更新をリスンするのではなく、Firestoreから一度ドキュメントをフェッチすることもできます。

- サーバー上でトランザクションが失敗すると、コールバックも繰り返し実行されます。アプリケーションの状態を変更するロジックを、トランザクションコールバック内に配置しないでください。

## 良い

- ふんわりとはfirestoreの概要はつかめた

## 悪い

- コードがES5
- queryにindexが追加できなかったのでフィルターの動作確認ができなかった
    - web上でもエラー(500)
    - cliだと反応なしで死んでしまった

## 課題

- firebase indexesがよくわかっていない

## related

- https://firebase.google.com/docs/firestore/data-model
- https://firebase.google.com/docs/firestore/security/get-started
