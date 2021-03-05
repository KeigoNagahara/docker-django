# docker-django
dockerを使ってDjango mysqlでプロジェクトを作成(env環境)
# 手順
env作成  
$ python3 -m venv env  
$ source env/bin/activate

env環境でdockerインストール  
$ pip install docker-compose

必要ファイル作成  
$ touch docker-compose.yml Dockerfile requirements.txt  
書いた内容は各ファイル参照

プロジェクト作成  
$ docker-compose run web django-admin startproject docker_django .

setting.pyにDB情報追記  
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'django_docker',
        'USER': 'root',
        'HOST': ‘db’,
        'POST': 3306
    }
}  
```

参考URLになかったがSTATIC_URLが設定されてないと怒られたので  
staticフォルダをつきってsettings.pyに  
```
STATIC_URL = '/static/' 
```
を追記

docker起動  
$ docker-compose up


# 参考
https://medium.com/@hokan_dev/docker-compose%E3%81%A7django-mysql%E3%81%AE%E7%92%B0%E5%A2%83%E3%82%92%E4%BD%9C%E3%82%8B-bd99cef7df0c

http://docs.docker.jp/v1.9/compose/django.html

# 注意点
dockerを起動するにはDocker Desktop for mac (mac) が必要（ここにコンテナをたてる）

https://docs.docker.jp/docker-for-mac/install.html

pythonの識別子で-禁止（最初プロジェクト名につかってしまった)  
https://blog.aristo-solutions.net/2018/05/djangocommanderror-is-not-valid-project_22.html

# 起動
http://localhost:8000/

でアクセス
