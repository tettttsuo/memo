```ruby
git checkout -b <new_branch_name>
```
新しいブランチを作ってチェックアウトする

```ruby
HEAD
```

今チェックアウトしてるコミット

```ruby
git reset --hard HEAD~1
```
HEAD\~1より後の変更を全て捨ててHEAD~1の状態に戻ってチェックアウトする
（最後のコミットはdangling commitとなる）

```ruby
git reset --mixed HEAD~1
```
"HEAD~1"より後の変更を捨てずにHEAD~1チェックアウトする
（最後のコミットはdangling commitとなる）

```ruby
git checkout -b staging --track heroku-staging/master
```
stagingブランチを作りチェックアウト。さらに、heroku-stagingリモートのmasterブランチを基本操作（git push/git pull）対象にする。config的に言うと、
```ruby
[branch "staging"]
  remote = heroku-staging
  merge = refs/heads/master
```
が設定される。