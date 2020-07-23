# FIX HERE!
![スクリーンショット 2020-07-21 22 02 00](https://user-images.githubusercontent.com/63101140/88241605-8d54f400-ccc5-11ea-9c52-cf570291554d.png)

## 概要<br>
修繕して欲しい箇所の位置、写真、修繕内容について連絡ができるサービスです。グーグルマップにマーカーを落とすことで簡単に位置を教えることができ、管理者側もカレンダー機能、グラフ機能があることでデータを簡単に整理できます。

## 使用技術<br>
- Ruby2.6.5
- Rails5.2.4.3
- Rspec
- jQuery
- Bootstrap4
- PostgreSQL
- AWS(VPC, RDS, EC2, S3, ALB, Route53, ACM)


## ER図<br>
![ポートフォリオテーブル](https://user-images.githubusercontent.com/63101140/88241842-53382200-ccc6-11ea-90de-9bae8d9b6ed5.png)

## サービス構成図<br>
![AWS構成図](https://user-images.githubusercontent.com/63101140/88241869-6814b580-ccc6-11ea-94ee-d9cb06be92a5.png)

#当サービスについて<br>
##作成動機<br>
前職において、住民から道路の修理等の要望を受け、業者の発注するという業務についていました。
問題として、
- 電話での応答なので詳しい場所が伝わりづらい
- 写真を持ってくるために、市役所までくる必要がある
- 業務自体が紙ベースなので、データの整理が大変である
などの問題が生じておりました。

この経験から住民と行政を繋ぐ際に、手軽に写真や、位置情報を伝えること、管理者側が簡単に整理することができるサービスを作りたいと思い、作成いたしました。

##ユーザー調査<br>
###インタビュー<br>
ポートフォリオを作成する前に、まずこのサービスについて、何が求められているか調査する必要があったので、ユーザーと管理者に調査を行いました。

<ユーザー側の声>
- できるだけ最低限の入力で済ませたい
- 住所がない場所を相手に伝えることができたら便利
- どの場所で工事をしているか見れたら嬉しい

<管理者側の声>
- 自動で工事完了メールを送ってほしい
- データを視覚的に整理してほしい（カレンダーなど）
- データの検索機能がほしい

###考察
インタビューより以下の点に力を入れてサービスを作成しました。

- 必要最低限の入力で簡単に投稿
- 位置情報入力のUX
- 管理者がデータを視覚的に整理しやすくする

#ポートフォリオとしての見所
- Google Maps Javascript API を用いた位置情報伝達
- カレンダーや、グラフ機能を用いることで視覚的に見やすく
- wheneverを用いたバッヂ処理
- Rspecによるテスト
- AWSを用いたデプロイ
- docker cicleciの使用（予定)

## 機能一覧
###認証周り
- ログイン、　サインアップ機能（devise)
  - email,パスワード、ユーザー名必須（ログイン時はemailとパスワードのみ）
  - ゲストログイン機能（ゲストユーザーは退会、プロフィール変更不可）
###案件機能
-CRUD機能
- いいね機能
- コメント機能
- 工事完了メール機能（wheneverによるバッヂ処理)



##
 ※メールアドレス、名前、パスワードは必須
- パスワード再設定機能
- 案件一覧表示
 - いいね数表示
 - 案件に関するグラフ２つ
 - お知らせ（タイトルのみ）
- 案件投稿機能
 - 必須事項：案件タイトル、案件内容、案件の住所 or googlemapにマッピング、緊急性、備考　
 - 追加事項：案件のファイル（複数写真など）
- 案件編集機能（新規投稿で記入した事項を編集できます）
 - 管理者事項：実施予定日、完了予定日、案件の進捗具合（管理者のみ可能）
- 案件いいね機能
 - 案件へのいいねは１つの案件に対して1人１回しかできない
 - 自身の案件にはいいねできない
- コメント投稿機能
　- コメント編集機能とコメント削除はコメントした本人のみ可能
- お知らせ掲示板機能（管理者がお知らせを書くことができます）
- コメント機能といいね機能はページ遷移なしで実行可能

## カタログ設計<br>
https://docs.google.com/spreadsheets/d/1SCTHp8nXC_ieGuNbFEBg1TDstzUigWyWO77LK7MQDDg/edit#gid=0

## 画面遷移図<br>
https://docs.google.com/spreadsheets/d/18N2iG-viN3q7usR3FhspYlFYF2ObiG7418x0PUsB9Ys/edit#gid=0

## 画面ワイヤーフレーム<br>
https://docs.google.com/spreadsheets/d/1i6w_WKBIz_PW9PrWvviHsScHt6MfP3jJl5EMSp1-7rg/edit#gid=0

## データテーブル　ER図<br>
https://docs.google.com/spreadsheets/d/1mrwzfg59_YZ_7o_6FQ5d5z4Qe7je0MNfFt-0vSVqpak/edit#gid=0


## 使用予定gem<br>
carrierwave<br>
・mini_magik<br>
・device<br>
・ransack<br>
・Geocoder<br>

## 使用予定API<br>
・Google Maps API
