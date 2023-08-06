## git

### 检查当前的git仓库的版本是否与远程仓库一致

```bash
# 查看远程仓库分支
WebUI> git remote -v
origin  https://github.com/lcclcclcc206/Hostsite.WebUI.git (fetch)
origin  https://github.com/lcclcclcc206/Hostsite.WebUI.git (push)

# 查看所有分支
WebUI> git branch -a
* main
  remotes/origin/main
  
# 同步远程库
WebUI> git fetch origin
  
# 比较本地分支与最新分支的差异
WebUI> git diff main remotes/origin/main
```

