# 発生したエラー
```bash
web_1  | => Booting Puma
web_1  | => Rails 6.0.3.4 application starting in development 
web_1  | => Run `rails server --help` for more startup options
web_1  | warning Integrity check: System parameters don't match
web_1  | error Integrity check failed
web_1  | error Found 1 errors.
web_1  | 
web_1  | 
web_1  | ========================================
web_1  |   Your Yarn packages are out of date!
web_1  |   Please run `yarn install --check-files` to update.
web_1  | ========================================
web_1  | 
web_1  | 
web_1  | To disable this check, please change `check_yarn_integrity`
web_1  | to `false` in your webpacker config file (config/webpacker.yml).
web_1  | 
web_1  | 
web_1  | yarn check v1.13.0
web_1  | info Visit https://yarnpkg.com/en/docs/cli/check for documentation about this command.
web_1  | 
web_1  | 
web_1  | Exiting
rails-postgre-sample_web_1 exited with code 1
```

# 解決した手順
1. yarn install --check-filesを実行
```bash
Your Yarn packages are out of date!
Please run `yarn install --check-files` to update.
```
とあるのでyarn install --check-filesを実行

2. yarnが入ってなかった。

3. brew install yarnでyarnをインストール

4. yarnを入れたので再度yarn install --check-filesを実行

5. 再度docker compose-upを実行

6. 同じエラーで起動が止まった。

7. エラーに従って、webpacker.ymlをチェック
```bash
To disable this check, please change `check_yarn_integrity`
to `false` in your webpacker config file (config/webpacker.yml).
```
エラーに↑とあるのでwebpacker.yml内の該当部分をtrue->falseに変更

8. 再度docker compose-upを実行

9. 無事にサーバが起動
