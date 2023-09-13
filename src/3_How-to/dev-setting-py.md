# 共通設定(setting.py)

[開発手順　pip・venv編](dev-pip-venv.md)、または[開発手順　rye編](dev-rye.md)を実行後に実施する共通手順

## 言語・タイムゾーン

``` python
LANGUAGE_CODE = 'ja'
```

```python
TIME_ZONE = 'Asia/Tokyo'
```

## テンプレートフォルダの設定

いまいち怪しいです。

`TEMPLATES = [` 以降をいじる。

＜アプリが複数ある場合＞　推奨

ファイルディレクトリ「myproject/templates/myapp/<hoge.html>」

```python
'DIRS': [os.path.join(BASE_DIR, 'templates')],
```

「myapp/template/myapp」以下のファイルを認識してくれるようになる

「myapp」が２回登場することに注意が必要


## staticフォルダの設定

「myproject/static」以下に配置するようになる。

```python
STATIC_URL = 'static/'
STATICFILES_DIRS = [BASE_DIR / "static"]
```

## デプロイを前提とした設定


