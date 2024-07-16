# Git tutorial

## Gitの基本コマンド
 - git init
 　``` カレントディレクトリ
 　git init
   - ディレクトリを指定
   git init <directory_name>
   ```
   ローカルリポジトリを新規作成する。
   コマンド実行後に指定したディレクトリが管理対象となり、「.git」ディレクトリが作成される。

 - git clone
   ```git clone <brunch_name> (もしくはURL)
   ```
   リモートリポジトリのブランチを複製してカレントディレクトリに保存する。

 - git add
```# 全ファイル
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

 - git commit
```git commit
   # コミットメッセージを付与
   git commit -m "commit_massage"
```
インデックスに登録されたファイルをリモートリポジトリにコミットする。

 - git push
```git push
   # 実行内容の確認（実行はされない）
   git push -n
```
ローカルリポジトリの変更内容をリモートリポジトリに送信し、コミットを更新する。

 - git pull
```# リモートリポジトリの全ての変更内容を取得
   git pull
   # 指定したリポジトリのブランチの変更内容を取得
   git pull リモートリポジトリ名 ブランチ名
   # デフォルトのリモートリポジトリ名はorigin
   git pull origin ブランチ名
```
リモートリポジトリの内容を取得する。

## Branchの操作
 - git branch: ブランチを表示する
 - git checkout -b <branch_name>: 新しいブランチを作成して切り替える
 - git merge <branch_name>: ブランチをマージする