# docker-django
dockerを使ってDjango mysqlでプロジェクトを作成(env環境)

# コマンド
env
$ pip install docker-compose

# 参考
https://medium.com/@hokan_dev/docker-compose%E3%81%A7django-mysql%E3%81%AE%E7%92%B0%E5%A2%83%E3%82%92%E4%BD%9C%E3%82%8B-bd99cef7df0c

http://docs.docker.jp/v1.9/compose/django.html

# 注意点
dockerを起動するにはDocker Desktop for mac (mac) が必要（ここにコンテナをたてる）

https://docs.docker.jp/docker-for-mac/install.html

pythonの識別子で-禁止（最初プロジェクト名につかってしまった）
https://blog.aristo-solutions.net/2018/05/djangocommanderror-is-not-valid-project_22.html

参考URLになかったがSTATIC_URLが設定されてないと怒られたので
staticフォルダをつきってsettings.pyにSTATIC_URL = '/static/'
を追記

# 起動
http://localhost:8000/

でアクセス
