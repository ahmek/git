# git

##### git switch -c 创建新分支

创建一个 `feature/dev` 分支 `git switch -c feature/dev`

---

##### git rebase -i 合并本地提交
如果 `git rebase -i` 报错，则确认一下当前从哪个分支开的，如果当前分支来源于 `master`，则 `rebase -i master`;
在跳出的编辑框中从第二行开始（如果有）把 `pick` 改为 `s`;
如果有冲突，处理完冲突后执行 `git add .`;
如果合并未完成，执行 `git rebase --continue` 继续向前合并，重复第二、第三步操作直到全部完成。


##### git pull –rebase origin master 
如果远程分支有更新且当前分支在本地也有更新，`git push` 时报错，使用 `git pull –rebase origin master` 进行合并。

`git pull –rebase origin master` 意为先取消 commit 记录，并且把它们临时保存为补丁(patch)(这些补丁放到”.git/rebase”目录中)，之后同步远程库到本地，最后合并补丁到本地库之中。