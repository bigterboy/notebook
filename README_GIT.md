### NOTEBOOK

> NOTE FOR GIT USED

Thiết lập chứng thực cá nhân

```bash
git config --global user.name "User Name"
git config --global user.email "username@gmail.com"
```

```bash
# Sao chép một kho chứa đã tồn tại
git clone https://github.com/user/repository.git
```

```bash
# Để tạo mới một branch:
git branch <name_branch>

# Để chuyển và tạo mới:
git branch -b <name_branch>
```

```bash
# Chuyển nhánh
git checkout <name_branch>
```

```bash
# Cập nhật thay đổi
git add .
git commit -m "Message"
```

```bash
# Cập nhật lên server
git push origin <name_branch>
```

```bash
# Git gộp nhiều commit thành 1
git log --oneline
git rebase -i HEAD~N # N số lượng git commit muốn gọp

# đổi pick thành s với những commit cần gộp

# Press ESC
:wq # xoá mô tả cũ
```

```bash
# Xem lại lịch sử commit
$ git log
```

```bash
# Xem thay đổi trước khi push
git diff
```

```bash
# Force
git push --force
```

```bash
# Update commit without comment and don't create new commit
git commit --amend --no-edit
```

```bash
```


```bash
```

after
`git reset --hard origin/main`
example
`git reset --hard c14809fa`


Reset brand: 
`git reset --hard @{u}`

Rebase
`git rebase master`

Reset git branch
`git checkout mybranch`
`git reset --hard origin/mybranch`

Revert a commit
`git revert 4945db2`

**# Submodule**
Add submodule
`git submodule add https://github.com/bigterboy/core-generic`


`https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule`

In modern git (I'm writing this in 2022, with an updated git installation), this has become quite a bit simpler:

Run git rm <path-to-submodule>, and commit.
This removes the filetree at <path-to-submodule>, and the submodule's entry in the .gitmodules file. I.e. all traces of the submodule in your repository proper are removed.

As the docs note however, the .git dir of the submodule is kept around (in the modules/ directory of the main project's .git dir), "to make it possible to checkout past commits without requiring fetching from another repository".
If you nonetheless want to remove this info, manually delete the submodule's directory in .git/modules/, and remove the submodule's entry in the file .git/config. These steps can be automated using the commands

rm -rf .git/modules/<path-to-submodule>, and
git config --remove-section submodule.<path-to-submodule>.

Older community wiki instructions:

Via the page Git Submodule Tutorial:

To remove a submodule you need to:

Delete the relevant section from the .gitmodules file.
Stage the .gitmodules changes:
git add .gitmodules
Delete the relevant section from .git/config.
Remove the submodule files from the working tree and index:
git rm --cached path_to_submodule (no trailing slash).
Remove the submodule's .git directory:
rm -rf .git/modules/path_to_submodule
Commit the changes:
git commit -m "Removed submodule <name>"
Delete the now untracked submodule files:
rm -rf path_to_submodule






> NOTE FOR GITHUB CLI
1. Login
`gh auth login`
2. Logout
`gh auth logout`


Error
error: Couldn't set ORIG_HEAD
fatal: Cannot update the ref 'ORIG_HEAD'.

```sh
$ git gc --prune=now
```