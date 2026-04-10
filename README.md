# Terraform × AWS インフラ自動構築

## 概要
Terraformを使用してAWSインフラをコードで構築しました。
VPCからEC2まで一括でプロビジョニングできます。

## アーキテクチャ
![構成図](terraform-vpc-ec2.png)

## 使用サービス
- Terraform（IaC）
- Amazon VPC
- パブリックサブネット
- Internet Gateway
- ルートテーブル
- セキュリティグループ
- Amazon EC2（Ubuntu + nginx）

## 構成のポイント
- VPC・サブネット・IGW・ルートテーブルをコードで一括構築
- EC2起動時にnginxを自動インストール（user_data）
- terraform applyで全リソースを一括作成
- terraform destroyで全リソースを一括削除

## 実行手順
```bash
terraform init
terraform plan
terraform apply
```

## ファイル構成
- `main.tf` - メインの構成ファイル
