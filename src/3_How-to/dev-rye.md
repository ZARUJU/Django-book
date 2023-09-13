# 開発手順　rye編

## ＜最終的なディレクトリ構成＞

```
プロジェクト名/
├─ src/{プロジェクト名}/
│  ├─ config/
│  │ ├─ config/
│  │ ├─ myapp/
│  │ ├─ manage.py
│  ├─ __init__.py
├─ .python-version
├─ pyproject.toml
├─ README.md
├─ requirements-dev.lock
├─ requirements.lock
```

## プロジェクトフォルダの作成

ターミナルでコマンドを実行する。

```bash
rye init {プロジェクト名}
```

## 仮想環境の整備

VScodeで作成したプロジェクトフォルダを開き、以下のコマンドを実行する

```bash
rye add django && rye sync
```
実行後、プロジェクト名と同名の仮想環境が起動される。

必要に応じて以下も実施する。いずれの場合も`rye sync`を実行し、適用を忘れぬように。

```bash
rye add djangorestframework
```

## project.tomlの準備

コピペして貼り付け

```
[tool.rye.scripts]
server = "python manage.py runserver"
app = "python manage.py startapp"
db1 = "python manage.py makemigrations"
db2 = "python manage.py migrate"
```

## Djangoプロジェクトの作成

`src`以下のプロジェクトフォルダに移動する。

```bash
cd src/{プロジェクト名}
```

そして、

```bash
django-admin startproject config && cd config
```

## 各種設定

[共通設定(setting.py)](dev-setting-py.md)を参照のこと。

## 開発開始

`project.toml`にショートカットを用意してあるので以下のようにして、適宜実行する。
実行の際は、`src/{プロジェクト名}/config`にいる必要がある。

＜開発用サーバーの起動＞
```bash
rye run server
```

＜アプリの作成＞
```bash
rye run app {アプリ名}
```

＜データベースのマイグレーション＞
```bash
rye run db1 && rye run db2
```

