# メモ

## Data Store memo

`server/api/db/*` はmongodbスキーマ定義。`index.ts`が王様で、その下にスキーマが5つある。Apps, Users, Questions<=_likes, _logs

mongoDBとFireStoreをどうコンバートすれば良いか？FireStoreはドキュメント型NoSQLDB。スキーマっぽいのは「コレクション」にあたり、その中に「ドキュメント」がある。ドキュメントはサブコレクションを持つことができて、さらにネストまでできちゃう（100ネスト行けるとか。やべぇ）ドキュメントはJSONっぽいやつで書かれてるというかJSONだわ。詳しくは[Cloud Firestore doc](https://firebase.google.com/docs/firestore/data-model?hl=ja)を参照。

つまるところ、もとのスキーマ適宜をとりあえずFireStoreに作成すれば良いという感じになるかな。あとはAPIを経由してデータストアがどうなるかどうかを見ていけばよいか。

Cloud FirestoreのDB設計は[このスライド](https://speakerdeck.com/1amageek/firestore-database-design)が参考になる。また、先のスライドを踏まえた上で[実装例](https://medium.com/google-cloud-jp/firestore2-920ac799345c)を読むと更にいい感じに入ってきた。

たぶん`index.ts`は不要になりそうというか、DBスキーマ書いてるtsファイルすら不要になりそうな気がする。

セキュリティルールについて学習が進んでないが、ひとまずそれっぽい形作りを進めていく。

## API memo

