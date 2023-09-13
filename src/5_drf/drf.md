# Django Rest Frameworkについて

## 公式ドキュメント

サイトは[こちら](https://www.django-rest-framework.org/)。上部のハンバーガーメニューからAPIガイドとかを閲覧できる。

## 導入

### インストール

＜pip＞

```
pip install djangorestframework && pip install django-cors-headers
```

＜rye＞

```
rye add djangorestframework && rye add django-cors-headers && rye sync
```

### アプリの登録

```python
INSTALLED_APPS = [
    'rest_framework',
]
```

## 概念や仕組みのざっくりした解説



- django-cors-headers \
    Cross-Origin Resource Sharing（CORS）を実装するためのミドルウェア \
    CORS：異なるホスト、ドメインからセキュリティを保ってアクセスするためのもの \
- Serializer \
    シリアライズやでシリアライズの設定、バリデーションを担当する。 \
    シリアライズ：JSON→オブジェクト \
    デシリアライズ：オブジェクト \
- View / Viewset \
    エンドポイントの定義、クエリセットの取得とフィルタリング、レスポンスなどを担当する。

## ざっくりした使い方



    





<!-- |語|解説
|-|-|
|django-cors-headers|Cross-Origin Resource Sharing（CORS）を実装するためのミドルウェア
|Serializer||
|ViewSet||
|||

＜django-cors-headers＞

Cross-Origin Resource Sharing（CORS）を実装するためのミドルウェア

CORS：異なるホスト、ドメインからセキュリティを保ってアクセスするためのもの \
 -->