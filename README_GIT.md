# NOTEBOOK

> NOTE FOR GIT USED

Thiết lập chứng thực cá nhân
`$ git config --global user.name "User Name"`
`$ git config --global user.email "username@gmail.com"`


Sao chép một kho chứa đã tồn tại
`$ git clone https://github.com/user/repository.git`

Để tạo mới một branch:
`$ git branch <name_branch>`
Để chuyển và tạo mới:
`$ git branch -b <name_branch>`


Chuyển nhánh
`$ git checkout <name_branch>`

Cập nhật thay đổi
`$ git add .`
`$ git commit -m "Message"`

Cập nhật lên server
`$ git push origin <name_branch>`

Git gộp nhiều commit thành 1
git log --oneline
git rebase -i HEAD~N
đổi pick thành s với những commit cần gộp
ESC
:wq xoá mô tả cũ

Xem lại lịch sử commit
`$ git log`

Xem thay đổi trước khi push
`$ git diff`

Reset brand: 
`git reset --hard @{u}`

Force
`git push --force`

Update commit without comment and don't create new commit
`git commit --amend --no-edit`
after
`git reset --hard origin/main`


Reset git branch
`git checkout mybranch`
`git reset --hard origin/mybranch`

> NOTE FOR GITHUB CLI
1. Login
`gh auth login`
2. Logout
`gh auth logout`
