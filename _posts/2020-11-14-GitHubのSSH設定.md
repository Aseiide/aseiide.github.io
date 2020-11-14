# この記事に従ってやった
https://qiita.com/shizuma/items/2b2f873a0034839e47ce
ちょっと詰まったのでまとめ
# やりかた
1. 公開鍵・秘密鍵を作成する
```ssh-keygen -t rsa```
2. 公開鍵をGitHubにアップする
3. 接続を確かめる
```ssh -T git@github.com```
4. ここで詰まった
>Warning: Permanently added the RSA host key for IP address '104.192.143.1' to the list of known hosts.

5. .gitconfigに追記
```
[url "github:"]
    InsteadOf = https://github.com/
    InsteadOf = git@github.com:
```

6. もう一回接続確認
```ssh -T git@github.com```
通った！

7. SSHを使ってgit cloneやってみる
```git clone [リポジトリのssh]```

8. エラー
```
ssh: Could not resolve hostname github: nodename nor servname provided, or not known
fatal: Could not read from remote repository.
```

9. 5で設定した追記分を削除

10. もう一回git clone

11. 成功
