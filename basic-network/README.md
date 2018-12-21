# basic-network
https://dev.classmethod.jp/cloud/aws/cloudformation-beginner01/ を aws cli で実施

## 実行手順
```
$ aws cloudformation create-stack --stack-name myteststack --template-body file://./01_create_vpc.yaml
```