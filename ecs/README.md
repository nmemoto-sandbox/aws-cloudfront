# basic-network
https://dev.classmethod.jp/cloud/aws/cloudformation-beginner01/ の例にサブネットとセキュリティグループを追加して aws cli で実行する

## 基本手順
テンプレートのバリデーション
```
$ aws cloudformation validate-template --template-body file://01_create_vpc.yaml
```

スタックの作成
```
$ aws cloudformation create-stack --stack-name networkstack --template-body file://01_create_vpc.yaml
```

変更セットの作成
```
$ aws cloudformation create-change-set --stack-name networkstack --template-body file://01_create_vpc.yaml --change-set-name AddNetworkChangeSet
```

変更セットのリスト表示
```
$ aws cloudformation list-change-sets --stack-name networkstack
```

変更セットの内容確認
```
$ aws cloudformation describe-change-set --change-set-name arn:aws:cloudformation:ap-northeast-1:999999999999:changeSet/xxxxxxx/99999999-9999-9999-9999-999999999999
```

変更セットの実行
```
$ aws cloudformation execute-change-set --change-set-name arn:aws:cloudformation:ap-northeast-1:999999999999:changeSet/xxxxxxx/99999999-9999-9999-9999-999999999999
```

スタックの削除
```
$ aws cloudformation delete-stack --stack-name networkstack
```