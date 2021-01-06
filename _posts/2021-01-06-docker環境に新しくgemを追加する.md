Docker+railsに新規でgemを追加するときの手順
実際にslimを導入したときの手順

1. Gemfileに追加したいgemを書く

```
gem 'slim-rails'
gem ''html2slim'
```

2. ```docker-compose run [サービス名] bundle install```

3. ```docker-compose build```

4. ```docker-compose up```
