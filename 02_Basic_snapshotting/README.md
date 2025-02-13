# 02 基本的なスナップショット

## `git add`

![git add](images/git_add.png)

ワーキングディレクトリのコンテンツをステージングエリアに追加するコマンドです。  
変更したファイルをコミット対象として登録するために必要な操作です。  
複数のファイルを一度に追加する場合は`git add .`を使用します。

```bash
# 特定のファイルを追加
git add file.txt

# 全てのファイルを追加
git add .

# 特定の拡張子のファイルを追加
git add *.java

# 対話形式でファイルを追加
git add -i
```

## `git status`

![git status](images/git_status.png)

現在の作業状態を確認するためのコマンドです。  
ファイルの追加、修正、削除などの変更状態を確認できます。  
`-s`オプションを使用すると、簡易的なフォーマットで結果を表示できます。

```bash
# 基本的な状態確認
git status

# 簡易表示
git status -s

# ブランチ情報も含めて表示
git status -sb
```

## `git diff`

![git diff](images/git_diff.png)

変更内容の差分を確認するためのコマンドです。  
ステージング前の変更は`git diff`、ステージング後は`git diff --staged`で確認できます。  
リモートとの差分を確認する場合は`git diff HEAD..origin/main`を使用します。

```bash
# 作業ディレクトリの変更を表示
git diff

# ステージングエリアの変更を表示
git diff --staged

# 特定のファイルの差分を表示
git diff file.txt
```

## `git commit`

![git commit](images/git_commit.png)

ステージングエリアに追加された変更をリポジトリに記録するコマンドです。  
コミットメッセージを付けて変更内容を説明することができます。  
変更履歴として後から参照することができます。

```bash
# 基本的なコミット
git commit -m "コミットメッセージ"

# 変更をステージングしてコミット
git commit -am "コミットメッセージ"

# 直前のコミットを修正
git commit --amend
```

## `git notes`

![git notes](images/git_notes.png)

コミットに対して追加のメモを付けることができるコマンドです。  
コミットメッセージとは別に補足情報を残すことができます。  
後からコミットに関する情報を追加する際に使用します。

```bash
# ノートを追加
git notes add -m "メモ内容"

# ノートを表示
git notes show

# ノートを編集
git notes edit
```

## `git restore`

![git restore](images/git_restore.png)

変更したファイルを元の状態に戻すためのコマンドです。  
誤って変更してしまったファイルを復元する際に使用します。  
特定のファイルだけを指定して復元することも可能です。

```bash
# ファイルを復元
git restore file.txt

# ステージングした変更を取り消し
git restore --staged file.txt

# 特定のコミットの状態に戻す
git restore --source=HEAD~1 file.txt
```

## `git reset`

![git reset](images/git_reset.png)

コミットを取り消すためのコマンドです。  
直前のコミットを取り消したり、特定のコミットまで戻したりできます。  
慎重に使用する必要があるコマンドです。

```bash
# 直前のコミットを取り消し（変更は保持）
git reset --soft HEAD^

# コミットとステージングを取り消し
git reset --mixed HEAD^

# 全ての変更を取り消し
git reset --hard HEAD^
```

## `git rm`

![git rm](images/git_rm.png)

Git の管理下にあるファイルを削除するコマンドです。  
ワーキングディレクトリからファイルを削除し、その変更をステージングエリアに登録します。  
`-f`オプションで強制的に削除することも可能です。

```bash
# ファイルを削除
git rm file.txt

# キャッシュのみ削除（ファイルは保持）
git rm --cached file.txt

# 強制削除
git rm -f file.txt
```
