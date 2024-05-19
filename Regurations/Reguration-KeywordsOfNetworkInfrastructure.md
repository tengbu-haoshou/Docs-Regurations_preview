# ネットワークインフラストラクチャ技術キーワード

## OSI 参照モデル

**OSI reference model**

|<center>レイヤー</center>|<center>名称</center>|<center>説明</center>|<center>関連技術例</center>|
|:-:|:--|:--|:--|
|7|アプリケーション層|アプリケーションの各種プロトコルのインターフェースを提供する。|HTTP（Hypter Text Transfer Protocol）|
|6|プレゼンテーション層|データの変換、暗号化、圧縮などの処理を行う。|SSL（Secure Socket Layer）|
|5|セッション層|通信のセッションの確立、維持、終了の管理を行う。|socket|
|4|トランスポート層|データを受信してデータの組立てを行う。|TCP（Transmission Control Protocol）、UDP（User Datagram Protocol）|
|3|ネットワーク層|データパケットの経路の選択や転送を行う。|IP（Internet Protocol）、ルーター、L3 スイッチ|
|2|データリンク層|ビットをフレーム単位にまとめフロー制御やエラー制御を行う。|Ethernet、MACアドレス、スイッチ（スイッチングハブ）|
|1|物理層|デバイスのビットの転送を物理的に実現する。|Ethernet ケーブル、ハブ（リピータハブ、バカハブ）|

## ネットワーク構成図

ネットワークトポロジー。<br>
論理構成図は、物理構成図より抽象的に書く。外観するもの。ネットワーク全体を把握しやすいよう1枚にまとめるのが原則である。<br>
物理構成図には，ネットワークを構成するすべての機器や端末についてケーブルの接続や物理的な配置場所を書いておく。<br>

## ネットワーク回線 

ONU（光回線の終端装置）<br>

ADSL とは『Asymmetric Digital Subscriber Line（非対称デジタル加入者線）』の略称で、上りと下りの通信速度が非対称となっている。<br>
ADSL はアナログ電話回線を利用し、ADSLモデムを通してデータ通信を行うインターネットサービスである。<br>
ADSL は廃止が決定している<br>

## 広域イーサネット（閉域網）

レイヤー2<br>

## ルーター

ルーターは、MAC アドレスと IP アドレスで直接やりとり。<br>
レイヤー3<br>

## VPN（Virtual Private Network）

インターネット VPN、エントリ VPN<br>
IP-VPN（閉域網）<br>
レイヤー3<br>

## 外部 DNS

外部 DNS は、URL をグローバル IP アドレスに変換する。<br>

NAPT（Network Address Port Translation）機能を持つ。複数のローカル IP アドレスを 1つのグローバルローカルアドレスに変換する。<br>
VPN 付きルーターもある。<br>

## ファイアウォール

ルーターとイントラネットの間にファイアウォールを設置する。<br>

## 内部 DNS

内部 DNS は、内部 URL をローカル IP アドレスに変換する。<br>
レイヤー3スイッチ（L3 スイッチ）仮想的なネットワークの分離をする。VLANと呼ばれる。<br>
NAT（Network Address Translation）機能を持つ。<br>

## レイヤー2

レイヤー2（スイッチングハブ）は、MAC アドレスで相手と直接やりとりする。<br>
イーサネット = MAC

## レイヤー1

レイヤー1（リピーターハブ、バカハブ）は、自分につながっている機器の全てにデータを転送する。<br>

<div style="text-align: right;">- 以上 -</div>
