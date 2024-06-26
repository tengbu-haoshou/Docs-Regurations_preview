# ウォータフォール開発工程規約

開発の品質の向上・維持を狙う。<br>

## 目次

**1\. プロセス**<br>
**2\. 開発工程**<br>

## 1. プロセス

以下の一連のプロセスを取る。<br>

* 1\) プロジェクト計画、レビュー、およびキックオフ
* 2\) 調査、およびレビュー
* 3\) 企画、およびレビュー
* 4\) 要件定義、およびレビュー
* 5\) 概要設計、およびレビュー
* 6\) 詳細設計、およびレビュー
* 7\) コーディング、およびレビュー
* 8\) 単体テストの設計、レビュー、および実施
* 9\) 結合テストの設計、レビュー、および実施
* 10\) 総合テストの設計、レビュー、および実施
* 11\) ユーザー受入れテストの実施
* 12\) リリースの設計、レビュー、およびリリース作業
* 13\)プロジェクトクロージング

上記以外にも、いろいろな呼び方（基本設計、外部設計、内部設計など）がある。どのような呼び方を採用したとしても、V 字工程のように設計工程と実装工程が対応するようにプロセスを定義すること。<br>

各プロセスにて、以下の活動を行う。<br>

* 各プロセス開始時に、作業内容およびアウトプット形式を確認する。のち、作業を実施する。
* 各レビューにて、レビューの記録を取る。レビュー指摘の傾向から品質向上対策も取る。
* 各テストにて、テスト結果の記録を取る。バグの傾向から品質向上対策も取る。
* 品質確保できたと判断できたら、次の工程に入る。

## 2. 開発工程

場合によっては前後する可能性がある。<br>
フロントローディングと呼ばれる前工程の設計に負荷を掛けることも多い。例えば、要件定義でデータベース設計やエラーメッセージ設計を行う、など。<br>

## 1) プロジェクト計画、キックオフ

各工程の作業を定義する。<br>

* 各工程の定義、各工程のフロー（作業確認、作業実施、レビュー、完了判定）
* 体制
* 開発工程（スケジュール）
* 会議体

また、本紙付録または別紙で、詳細を定義する。<br>

* ドキュメント規定、ドキュメント管理規約
* ソースコード管理規約
* コーディング規約
* スケジュール管理、課題管理

ドキュメント管理規約は、以下を含む。<br>

* フォルダー名規約、ファイル名規約
* 種類（pptx、.docx、.xlsx、.md 等）
* 形式・内容・書き方・粒度
* バージョン管理

ソースコード管理規約は、以下を含む。<br>

* フォルダー名規約、ファイル名規約
* 種類（.java、.py 等）
* ブランチ戦略

## 2) 調査

事業やシステムを実現するために必要な情報や技術を調査する工程。<br>
必要あれば、POC（概念実証：Proof Of Concept）も実施する。<br>

## 3) 企画

事業企画とシステム企画がある。“Why to do”<br>

* 目的・目標
* 背景
* 課題と対策。現状およびシステム導入後を比較した事業レベル業務フローも含む。
* 基本機能（大中項目レベル）
* 体制
* 開発工程（スケジュール）
* 効果対費用
* アウトプット定義
* 課題・リスク

## 4) 要件定義

システムに必要な要求を挙げる工程。“What to do”<br>
ユーザー要件とシステム要件からなる。<br>

* 目的・目標・背景
* 詳細機能（大中小項目）
* 担当者レベル業務フロー
* 画面一覧、画面フロー、画面機能・画面レイアウト・画面入出力項目
* システム構成（物理構成、論理構成）
* コンポーネント構成（データフローも含む）
* 運用設計
* 非機能要件、SLA（Service Level Agreement：サービス品質保証）定義
* データ移行等の特殊要件

非機能要件とは、システムに対して潜在的に期待する機能である。<br>

* Performance：性能（同時アクセスレスポンス）
* Availability：可用性（稼働時間）
* Reability：信頼性（停止時間、回数）
* Expandability：拡張性
* Security：安全性
* Maintainability：保守性
* Usability：使いやすさ

運用設計：

* 監視フロー。性能、容量。
* 監視機能
* バックアップ、リカバリ
* オペレーティングシステム・ミドルウェア・アプリケーションのアップデート、...等）。

必要あれば、本紙付録か別紙で用語辞典を作成する。<br>

## 5) 概要設計

各コンポーネントのモジュール構成とモジュール処理概要を挙げる工程。“How to do”<br>
モジュール構成の粒度を例えて言うなら、主要クラスのレベル。<br>

* モジュール間のインターフェイス設計
* 業務モジュール設計
* 共通モジュール設計（セッションクラス、ログクラス、多国語化クラス、エラークラス、...等）。
* データベース設計。テーブル一覧、テーブルレイアウト。ER 図、CRUD 図の採用可否も検討すること。
* エラーメッセージ設計

処理の設計において、UML クラス図やシーケンス図の採用を検討するとよい。<br>

## 6) 詳細設計

各モジュールの処理詳細を挙げる工程。<br>
モジュールの処理詳細の粒度を例えていうなら、処理ブロックのレベルまで。<br>
UML シーケンス図の採用を検討するとよい。<br>
モジュール一覧も作成する。<br>

## 7) コーディング

ソースコードを作成し、ビルドする。<br>

## 8) 単体テスト

各モジュールの処理のテスト項目を設計し、テストを実施する。<br>
テストの粒度を例えて言うなら、処理ブロックのレベル。<br>

テスト観点：

* 処理アルゴリズム
* 異常処理
* 最大値・最小値、異常値
* データ値組合せ
* SQL の単体性能テストも含む。

事前にテスト内容、期待動作、エビデンス有無（アプリケーションログ、ジョブログ、画面ショット）等の内容・書き方・粒度を合意しておくこと。<br>

## 9) 結合テスト

各コンポーネントの各モジュールの処理のテスト項目を設計し、テストを実施する。<br>
テストの粒度を例えて言うなら、主要クラスのレベル。<br>
モジュール間のインターフェイス・テストも含む。<br>

事前にテスト内容、期待動作、エビデンス有無（アプリケーションログ、ジョブログ、画面ショット）等の内容・書き方・粒度を合意しておくこと。<br>

## 10) 総合テスト

ユーザーの業務フローに基づいてシステム全体の動きのテスト項目を設計し、テストを実施する。<br>
必要に応じて、ペネトレーションテストなどのセキュリティテストも含む。<br>
必要に応じて、リグレッションテスト（できれば自動化したテスト）も含む。<br>

## 11) ユーザー受入れテスト

UAT（User Acceptance Testing）。<br>
ユーザー教育を実施し、ユーザーに業務フローに基づいてシステムを使用してもらい、最終評価する。<br>
必要あれば、ユーザー・マニュアルも作成する。<br>

## 12) リリース

システムのリリースに必要な作業の設計を行う。<br>
リリース作業には、インフラ構築（ネットワーク、サーバー、ディスク、...）、アプリケーションデプロイ、データ移行、システム起動、切戻し判定および切戻し作業などがある。<br>
のち、リリース作業を行い、システムをリリースする。<br>

## 13) プロジェクトクロージング

プロジェクトの振り返り。KPT（Keep/Problem/Try）による分析など。<br>


<div style="text-align: right;">- 以上 -</div>
