## 目的

本ドキュメントは、キャンプ場(架空)の予約・スケジュール管理を行うシステム開発に関する要件定義書になります。

要件定義はこちらの資料を参考にしています。  
https://notepm.jp/sharing/190de8bd-5e83-40f6-ab5e-1bc2f231beb8


## 業務要件

### 現状のフロー

現状のフローは次のようになっています。

1. キャンプの利用者が管理人に直接電話をし、利用人数、日程、名前、電話番号、利用したいスペースの場所を伝え、予約を行う。
1. 管理人がExcelに記入
1. 当日、現地にて現金決済

### 構築後のフロー

システム構築後、フローは次のようになります。

利用者
1. 利用者は、予約ページから、メールアドレス、名前、メールアドレス、電話番号、日時、利用人数、利用スペース番号を入力
1. 問題がなければ予約完了
1. 当日、現地にて現金決済
1. キャンセル・変更の場合はメールに届いた予約情報URLからキャンセル申請

ログイン利用者
1. アカウント登録、ログイン
1. 予約ページから、日時、利用人数、利用スペース番号を入力
1. 問題がなければ予約完了
1. 当日、現地にて現金決済
1. キャンセル・変更の場合は自身の予約一覧からキャンセル申請

管理者
1. 与えられたメールアドレス、パスワードでログイン
1. キャンプスペース情報の編集・削除・新規登録
1. 予約情報の確認

### 利用者一覧

- キャンプ場管理人
- キャンプ場利用者

### 規模

3人月(エンジニア1人×3)の予定です。

## 機能要件
- キャンプサイト情報確認ページ
- 空き情報確認ページ
- 予約登録
- 予約変更
- 予約キャンセル
- 予約アカウント作成ページ
- マイページ
-- ログイン
-- 予約履歴
-- 退会
- 管理者画面
-- ログイン
-- 予約一覧
-- 予約検索
-- キャンプサイト登録
-- キャンプサイト情報変更
-- キャンプサイト削除


### 画面


- 画面遷移図を参照m
- https://github.com/satoshi0122/will-laravel-project/blob/main/%E7%94%BB%E9%9D%A2%E9%81%B7%E7%A7%BB%E5%9B%B3.PNG


### 権限

- スペースの追加、予約の強制消去は管理者のみ可能とします。
- 予約者の一覧、日程の閲覧は管理者のみ可能とします。
  

### 情報・データ

本システムでは以下のデータが作成されます。

- 利用者情報
- 予約情報
- キャンプスペース情報
- ３か月先までの予約データ

### 外部インタフェース

- メール
アカウント登録をしない場合、予約情報の詳細などはメールにURLが送られます。

### 二次開発
- アカウント未登録での予約登録(メールでのCRUD機能)
- 薪の販売システム
- キャンプ道具のレンタルシステム

### スケジュール

| 日付 | 内容 |
|--------|--------|
| 2023年06月まで | データベース・画面設計 |
| 2023年08月まで | バックエンド実装 |
| 2023年11月まで | インフラ構築 |

