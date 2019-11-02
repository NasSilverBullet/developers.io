# ハイブリッド/マルチVPC環境を構成するためのAWSネットワーク完全理解

菊池修治

VPC のホップができないため
VPCで相互接続にはフルメッシュが必要

しかし

aws transit gateway

ハブ型のトポロジーが組める
ルートテーブルが編集可能

## vpc * tgw

transit gateway を中心におき
vpcとの接続のための attachment というものを作成する
transit gateway にルートテーブルを作成する

vpc ルートテーブルにtgwを設定

route設定の自動化が可能

default route table association で attachment するだけで自動でルートテーブルに追加してくれる
あとはvpcルートテーブルの作成のみ

## vpn * tgw
tgw をおく
attachment を置く
vpcルートテーブルの作成

アタッチメントごと $0 .07/時間
