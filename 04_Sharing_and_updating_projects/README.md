# 04 共有と更新

## `git fetch`

リモートリポジトリから最新の変更履歴を取得するコマンドです。  
ローカルの作業ディレクトリには影響を与えず、情報の取得のみを行います。  
取得した内容は`FETCH_HEAD`として参照することができます。

```bash
# 全てのリモートブランチの情報を取得
git fetch --all

# 特定のリモートから取得
git fetch origin

# 特定のブランチのみ取得
git fetch origin develop
```

## `git pull`

リモートリポジトリから変更を取得し、現在のブランチに統合するコマンドです。  
内部的には`git fetch`と`git merge`を連続で実行する処理です。  
`--rebase`オプションを使用すると、マージの代わりにリベースを行います。

```bash
# 基本的な使用方法
git pull origin main

# リベースを使用した取得
git pull --rebase origin main

# 特定のブランチから取得
git pull origin feature/branch
```

## `git push`

ローカルの変更をリモートリポジトリに送信するコマンドです。  
新しいブランチやタグも送信することができます。  
`-u`オプションで上流ブランチの設定も同時に行えます。

```bash
# 変更をプッシュ
git push origin main

# 新規ブランチをプッシュして追跡設定
git push -u origin feature/branch

# タグをプッシュ
git push origin --tags
```

## `git remote`

リモートリポジトリの設定を管理するコマンドです。  
リモートの追加、削除、URL 変更などの操作が可能です。  
`-v`オプションで詳細な情報を確認できます。

```bash
# リモート一覧の表示
git remote -v

# リモートの追加
git remote add origin https://github.com/user/repo.git

# リモートの削除
git remote remove origin
```

## `git submodule`

プロジェクト内で他の Git リポジトリを管理するためのコマンドです。  
外部ライブラリやプラグインを独立したリポジトリとして管理できます。  
メインプロジェクトとサブプロジェクトを別々に管理することができます。

```bash
# サブモジュールの追加
git submodule add https://github.com/user/library.git

# サブモジュールの初期化とデータの取得
git submodule update --init

# 全サブモジュールの更新
git submodule update --remote
```
