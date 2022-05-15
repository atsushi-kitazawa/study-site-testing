---
title: "How to S3 Hosting Setting"
date: 2022-05-13T00:35:01+09:00
draft: true
---

# h1 S3で静的サイトをホスティングする際の設定方法

1. バケットを作成する
2. [プロパティ]から静的ホスティングを有効にする
3. [アクセス許可]で「すべてのパブリックアクセスをブロックする」のチェックを外す
4. バケットポリシーを追加する
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::Bucket-Name/*"
            ]
        }
    ]
}
```
