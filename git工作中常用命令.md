## git工作中常用命令： ##
### 1.统计个人提交行数： ###
    git log --author="罗仁杰" --pretty=tformat: --numstat | awk '{ add += $1; subs += $2; loc += $1 - $2 } END { printf "added lines: %s, removed lines: %s, total lines: %s\n", add, subs, loc }' -
### 2.统计每个人提交行数： ###
    git log --format='%aN' | sort -u | while read name; do echo -en "$name\t"; git log --author="$name" --pretty=tformat: --numstat | awk '{ add += $1; subs += $2; loc += $1 - $2 } END { printf "added lines: %s, removed lines: %s, total lines: %s\n", add, subs, loc }' -; done
### 3.查看用户名和邮箱地址： ###
    $ git config user.name
    $ git config user.email
### 4.修改用户名和邮箱地址 ###
    $  git config --global user.name  "xxxx"
    S  git config --global user.email  "xxxx"