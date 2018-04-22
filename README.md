# alexa-sam-template

AWS Serverless Application Model template for Alexa.

## Overview

TypeScriptでAlexaスキルを作りたい人のための、
LambdaをAWS SAMでデプロイ可能な環境を構築するためのテンプレートです。

## Requirements

- node v8.10.0
- awscli
- aws-sam-local

## Usage

### Dowload

適当なディレクトリにリポジトリをクローンしてください。

```
$ git clone https://github.com/rednes/alexa-sam-template.git
$ cd alexa-sam-template
```

### Edit package.json

package.jsonの14,18行目の`YOUR_PROFILE_NAME`を、Lambdaを作成したいAWS環境のプロファイル名に変更してください。

package.jsonの18行目の`YOUR_BUCKET_NAME`をデプロイパッケージを保存したいS3バケット名に変更してください。

```
14:    "deploy": "aws cloudformation deploy --template-file package.yml --stack-name alexa-sam-template --capabilities CAPABILITY_IAM --profile YOUR_PROFILE_NAME",

18:    "package": "aws cloudformation package --template-file template.yml --s3-bucket YOUR_BUCKET_NAME --output-template-file package.yml --profile YOUR_PROFILE_NAME",
```

### ビルド&デプロイ

```
# パッケージのインストール
$ npm run reinstall

# lint check
$ npm run lint

# lint autofix
$ npm run fixlint

# トランスパイル
$ npm run build

# トランスパイル(オート)
$ npm run watch

# SAM Local実行
$ npm run invoke

# デプロイパッケージをS3にアップロード
$ npm run package

# デプロイ
$ npm run deploy
```
