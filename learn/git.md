# Git memo
## Github
- 100MBを超えるファイルはpushできないよーん（課金が必要）
- 過去のコミットに↑が入ってるとそのコミット内容を書き換えないとだめ
  - `git rebase -i [書き換えたいコミット以前のコミット番号]`
  - vimが開くので書き換えたいコミット番号の冒頭をpick -> edit
  - 削除したい容量クソデカマンを`git rm`必要なら.gitignore追加
  - `git rebase --continue`で最新まで戻る
  - `git rebase --abort`でrebaseを取りやめられる
  - initial commitの前のコミット番号ないやんけ-> `git rebase -i --root`

## Git
- initial commitは空コミットにしとくのが、rebaseとかするときに便利だゾ
