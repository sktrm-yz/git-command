# 03 ブランチとマージ

## `git branch`

ブランチを新規作成、削除、一覧表示するためのコマンドです。  
主にブランチの作成や削除、現在のブランチ状態の確認に使用します。  
-vv オプションを使用すると、上流ブランチの情報も含めて表示できます。

```bash
# ブランチの作成
git branch feature/new-branch

# ブランチ一覧の表示
git branch -vv

# リモートブランチを含む一覧表示
git branch -a
```

## `git checkout`

ブランチの切り替えやファイルの特定バージョンへの復元に使用するコマンドです。  
-b オプションを使用すると、ブランチの作成と切り替えを同時に行えます。  
特定のコミットやタグの状態に戻す際にも使用できます。

```bash
# ブランチの切り替え
git checkout develop

# 新規ブランチの作成と切り替え
git checkout -b feature/new-feature

# 特定のファイルを元に戻す
git checkout -- file.txt
```

## `git switch`

Git 2.23 以降で導入された、ブランチ切り替え専用の新しいコマンドです。  
checkout コマンドの機能を分割し、ブランチ切り替えに特化しています。  
-c オプションで新しいブランチの作成と切り替えを同時に行えます。

```bash
# ブランチの切り替え
git switch main

# 新規ブランチの作成と切り替え
git switch -c feature/new-branch

# 直前のブランチに戻る
git switch -
```

## `git merge`

現在のブランチに対して、指定したブランチの変更内容を統合するコマンドです。  
同じファイルが変更されている場合、コンフリクト（競合）が発生する可能性があります。  
--no-ff オプションで強制的にマージコミットを作成できます。

```bash
# ブランチのマージ
git merge feature-branch

# マージコミットを必ず作成
git merge --no-ff feature-branch

# マージの中止
git merge --abort
```

## `git mergetool`

マージ時のコンフリクトを解決するための外部ツールを起動するコマンドです。  
設定されたマージツール（vimdiff、p4merge など）を使用してコンフリクトを解決します。  
視覚的にコンフリクトを解決できるため、複雑な競合の解決に役立ちます。

```bash
# マージツールの起動
git mergetool

# 特定のファイルのみ解決
git mergetool file.txt

# マージツールの設定確認
git mergetool --tool-help
```

## `git log`

コミット履歴を表示するコマンドです。  
様々なオプションを組み合わせることで、必要な情報を見やすく表示できます。  
--graph オプションでブランチの分岐も視覚的に確認できます。

```bash
# 基本的な履歴表示
git log

# グラフ表示
git log --graph --oneline

# 特定ファイルの履歴
git log -p file.txt
```

## `git stash`

作業中の変更を一時的に保存し、後で復元することができるコマンドです。  
ブランチの切り替え時に、コミットしていない変更を一時的に退避させる際に使用します。  
複数の変更を個別に保存し、必要に応じて復元できます。

```bash
# 変更の一時保存
git stash save "作業メモ"

# 保存した変更の一覧
git stash list

# 最新の保存を復元
git stash pop
```

## `git tag`

特定のコミットにタグ付けを行うコマンドです。  
主にリリースバージョンの管理に使用されます。  
注釈付きタグ（-a）とライトウェイトタグの 2 種類があります。

```bash
# 注釈付きタグの作成
git tag -a v1.0.0 -m "バージョン1.0.0"

# タグ一覧の表示
git tag -l

# タグの削除
git tag -d v1.0.0
```

## `git worktree`

同じリポジトリの複数の作業ディレクトリを管理するコマンドです。  
異なるブランチを別々のディレクトリで同時に作業できます。  
大規模な機能開発や並行作業時に便利です。

```bash
# 新しい作業ツリーの作成
git worktree add ../path/to/folder branch-name

# 作業ツリー一覧の表示
git worktree list

# 作業ツリーの削除
git worktree remove ../path/to/folder
```
