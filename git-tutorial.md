# Git tutorial


## Gitのコマンドと機能
  - init
```
   # カレントディレクトリ
 　git init
   # ディレクトリを指定
   git init <directory_name>
```
   ローカルリポジトリを新規作成する。
   コマンド実行後に指定したディレクトリが管理対象となり、「.git」ディレクトリが作成される。

 - clone
```
   git clone <brunch_name>or<URL>
```
   リモートリポジトリのブランチを複製してカレントディレクトリに保存する。

 - add
```
   # 全ファイル
   git add .
　 # 変更ファイルのみ
   git add -u
   # ファイルを指定
   git add ファイル名
   # 変更されたファイルのみステージング
   git add -n .
   git diff —name-only
```
指定したファイル名、もしくはオプションに応じたファイルをステージングする。

 - commit
```
   git commit
   # コミットメッセージを付与
   git commit -m "commit_massage"
   # コミットの修正(ファイルの内容は上書きされるが、コミット履歴を残さない。)
   git commit --amend --no-edit
```
インデックスに登録されたファイルをリモートリポジトリにコミットする。

 - push
```
   git push
   # 実行内容の確認（実行はされない）
   git push -n
```
ローカルリポジトリの変更内容をリモートリポジトリに送信し、コミットを更新する。

 - pull
```
   # リモートリポジトリの全ての変更内容を取得
   git pull
   # 指定したリポジトリのブランチの変更内容を取得
   git pull <remote_repository_name> <branch_name>
   # デフォルトのリモートリポジトリ名はorigin
   git pull origin <branch_name>
```
リモートリポジトリの内容を取得して、作業中のブランチに取り込む。

 - branch
```
   # ローカルブランチ一覧の表示
   git branch
   # リモートブランチ一覧の表示
   git branch -r
   # 現在のHEADからブランチの作成
   git branch <branch_name>
   # ブランチの削除
   git branch -d <branch_name>
   # 指定したリモートブランチを追跡する
   git branch -u <remote_branch_name>
   # リモートブランチ(origin/main)と紐づける
   git branch --set-upstream-to origin/main
```
ブランチを表示、作成、削除する。

 - checkout
```
   # ブランチの切り替え
   git checkout <branch_name>
   # コミットの切り替え（ステージングの内容はそのまま）
   git checkout <commit_value>
   # ブランチの作成
   git checkout -b <branch_name>
```
ブランチの作成や切り替えを行う。また、作業を行ったブランチを元に戻す。コミットの切り替えも可能である。

 - merge
```
   git merge <branch_name>
   # mainブランチを、マージを試行する前の状態に復元
   git merge --abort
```
ローカルブランチ内の別ブランチの全コミットを作業中のブランチにマージする。

 - config
```
   # gitへ設定
   git config --global user.name "user_name"
   git config --global user.email "mail_adress"
   
   # gitの設定を確認
   git config --list
```
gitの初期設定とその確認が出来る。

 - stash
```
   git stash
```
作業中ブランチの内容を退避する。コミットせずにブランチの切り替えを行いたいときや、作業するブランチを間違えたときに使用する。

 - diff
```
   # ステージングした内容を表示
   git diff —cached
   git diff —staged
   # 前回コミット時の内容と比較
   git diff HEAD^
   # コミット同士を比較
   git diff <before_commit_value> <after_commit_value>
   # ローカルブランチ同士を比較
   git diff <branch_name_1> <branch_name_2>
   # ローカルリポジトリとリモートリポジトリの比較
   git diff <local_branch_name> origin/<remote_branch_name>
   # ファイルの変更点の表示
   git diff - <file_path>
   git <branch_name_1> <branch_name_2> - <file_path>
   # 変更内容をゲージで表示
   git diff —stat
   # 変更されたファイルのパスのみ表示
   git diff <branch_name>|<commit_value> --name-only
   # 空白や改行コードの違いを無視
   git diff -w
   # 空行を無視
   git diff —ignore-blank-lines
   # 差分を上側に表示
   git diff -compaction-heuristic
```
コミットやローカルブランとリモートブランチの差分を表示する。

 - reset
```
   git reset <option> <commit_value>
   # 作業中の内容を全てリセットする
   git reset --hard <commit_value>
   # コミット値に指定したコミットを削除する
   git reset --soft <commit_value>
   # コミット値に指定したコミットとインデックスを削除する
   git reset --mixed <commit_value>
```
インデックスに登録されたファイル一覧を削除したり、ブランチをコミット前の状態に戻す操作を行う。
resetコマンドではリセットしたい内容に応じて主に「--soft」「--mixed」「--hard」の3つのオプションを指定する。

 - log
```
   git log <branch_name>or<file_name>
```
コミットの履歴と詳細を表示する。

 - status
```
   git status
   # 省略表示
   git status -s
```
ステージングされたファイルの一覧を表示する。
 - revert
```
   git revert <commit_value>
```
指定したコミットの変更を打ち消す。

 - rm
```
   git rm <file_name>
```
削除したファイルを指定し、ステージングする。リモートリポジトリに削除ファイルを反映するにはrmでステージングを行った後にコミットする必要がある。

 - remote
```
   # リモートリポジトリ名を表示
   git remote
   # リモートリポジトリ名とURLを表示
   git remote -v
```
リモートリポジトリの操作を行う。デフォルトのリモートリポジトリ名はorigin。
 - request-pull
```
   git request-pull
```
変更の依頼を行う。