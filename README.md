# DevcontainerによるSpringBoot環境
SpringBootの環境構築をした際の備忘録

# 環境
- JavaはSDKMAN!によりインストール  
Dockerfile内の引数指定を変更することで、SDKを変更可
```
ARG JAVA_VERSION="17.0.6-amzn"
ARG GRADLE_VERSION="8.5"
```

- DBはMySQLを使用  
.envファイルに設定情報を記述
```
# MySQLの設定情報
# MYSQL_ROOT_PASSWORD : rootでログインする際のパスワード
# MYSQL_USER : userでログインする際のユーザー名
# MYSQL_PASSWORD : userでログインする際のパスワード
# MYSQL_DATABASE : 作成するDBの名前
```
Port = 3306 DatabaseClientから接続