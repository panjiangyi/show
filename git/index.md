- git diff
    > 对比工作去和暂存区的区别
    1. --cached, --staged对比暂存区和已commit的区别
    2. --check，它将会找到可能的空白错误（多余的空格，换行等）并将它们为你列出来。
    3. a...b, 列出b分支在ab公共祖先节点之后，更新了什么
    4. -b 不对比空格
- git difftool
    > 修改的摘要（50 个字符或更少）
如果必要的话，加入更详细的解释文字。在
大概 72 个字符的时候换行。在某些情形下，
第一行被当作一封电子邮件的标题，剩下的
文本作为正文。分隔摘要与正文的空行是
必须的（除非你完全省略正文）；如果你将
两者混在一起，那么类似变基等工具无法
正常工作。
空行接着更进一步的段落。
  - 句号也是可以的。
  - 项目符号可以使用典型的连字符或星号
    前面一个空格，之间用空行隔开，
    但是可以依据不同的惯例有所不同。修改的摘要（50 个字符或更少）
如果必要的话，加入更详细的解释文字。在
大概 72 个字符的时候换行。在某些情形下，
第一行被当作一封电子邮件的标题，剩下的
文本作为正文。分隔摘要与正文的空行是
必须的（除非你完全省略正文）；如果你将
两者混在一起，那么类似变基等工具无法
正常工作。
空行接着更进一步的段落。
  - 句号也是可以的。
  - 项目符号可以使用典型的连字符或星号
    前面一个空格，之间用空行隔开，
    但是可以依据不同的惯例有所不同。 diff相同，但使用编辑器来对比文件
    > 两步，把对比工具设置成vscode
    > git config --global diff.tool vscode
    > git config --global difftool.vscode.cmd 'code --wait --diff $LOCAL $REMOTE'
    1. --tool-help查看帮助
    2. --tools=&lt;tool&gt; 用指定编辑器查看
    3. --cached, --staged对比暂存区和已commit的区别
- git commit
    1. -a 跳过add进暂存区步骤，直接提交
    2. --amend 覆盖上一次提交操作
    3. commit书写规范：
    > - 修改的摘要（50 个字符或更少） 
    > - 如果必要的话，加入更详细的解释文字。在 大概 72 个字符的时候换行。在某些情形下， 第一行被当作一封电子邮件的标题，剩下的 文本作为正文。分隔摘要与正文的空行是 必须的（除非你完全省略正文）；如果你将 两者混在一起，那么类似变基等工具无法 正常工作。 空行接着更进一步的段落。
    > - 句号也是可以的。
    > - 项目符号可以使用典型的连字符或星号
    前面一个空格，之间用空行隔开，
    但是可以依据不同的惯例有所不同。
- git rm
    > 从磁盘和暂存区中删除文件
    1. -f, 如果修改过切已暂存，则必须用此强制删除命令
    2. --cached，从git仓库中删除并不再跟踪文件
- git mv
    >移动文件
    1. 重命名 git mv file_from file_to
- git log
  > 更多命令自己搜
    1. -p 显示每次提交的内容的差异
    2. -n 显示n条记录
    3. --stat 简洁信息
    4. --abbrev-commit 显示简单唯一SHA-1值，默认七个字符，如果有重复会增加长度
    5. --pretty=oneline;
    6. --pretty=short;
    7. --pretty=full;
    8. --pretty=fuller;
    9. --pretty=format:"模板";
        | 选项 | 说明                                      |
        | ---- | ----------------------------------------- |
        | %H   | commit的完整哈希字串                      |
        | %h   | commit的简短哈希字串                      |
        | %T   | 树对象的完整哈希字串                      |
        | %t   | 书对象的简短哈希字串                      |
        | %P   | 父对象的完整哈希字串                      |
        | %p   | 父对象的简短哈希字串                      |
        | %an  | 作者的名字                                |
        | %ae  | 作者的电子邮件地址                        |
        | %ad  | 作者修订日期（可以用--date=选项指定格式） |
        | %ar  | 作者修订日期，按多久以前的方式显示        |
        | %cn  | 提交者的名字                              |
        | %ce  | 提交者的电子邮件地址                      |
        | %cd  | 提交日期                                  |
        | %cr  | 提交日期，按多久以前的方式显示            |
        | %s   | 提交说明                                  |
        | %G?   | 是否签名了                                 |
        > 注：作者是写代码的人，提交者是把代码合并到项目的人
    10. --graph， 图形化显示分支，合并历史
    11. --since --after --before --until 设定起止时间
    12. --author 指定作者
    13. --committer 指定提交者
    14. --grep 指定说明关键字
    15. -S 指定代码关键字
    16. --all-match 此命令使结果必须满足多个限制条件，否则满足一个即可
    17. --no-merges  有些提交时合并而来，不显示这些节点，历史信息更清晰
    19. [branch] 显示在指定分支上HEAD的引用日志
    20.  &lt;branch A&gt;...&lt;branch b&gt;, 或branchB --not branchA 显示属于branch b 但不属于branch a的commit
- git tag
    > 列出所有标签
    1. -l
    > git tag -l 'v1.8.5' 列出名字v1.8.5开头的标签
    > -a &lt;tag name&gt; &lt;commit hash&gt; 创建附注标签
    2. git push --tags 把标签也一并上传
    3. git checkout -b &lt;branchname&gt; &lt;tagname&gt;
    4. git show [tag] 显示tag信息
- checkout
    >工作区和暂存区没提交干净时，不能切换分支。除非目标分支和当前分支处于同一节点
- branch
   1. -v 显示每个分支的最后一次提交
   2. --no-merged 查看所有还没合并的分支
- ls-remote
    > 显示远程仓库信息
- git push
    1. -u（缩写）, --set-upstream origin featureB:featureBee  把featureB分支推送到远程库的featureBee分支,并记录跟踪关系
    >  --set-upstream origin featureB 把featureB分支推送到远程库同名分支
- git rebase
   > 提交前rebase到主分支并解决冲突，这样其他人可以fast-forward
- git merge
    1. --squash 合并分支，但在丢弃被合并分支的变更集
- git format-patch
    >生成补丁文件，用来通过邮件发送本地改动
- git apply
    >应用补丁文件
    1. --check 检查补丁文件是否有效
- git pull
    1. [url] 一次性的拉去，而不会被设定成默认远程分支
- git rev-parse branchName
    > 查看分支最后一个提交的hash
- git reflog
  > 查看HEAD的引用日志
- git show
  1. HEAD@{N} 查看HEAD倒数第N次指向那个提交
  2. master@{yesterday} 查看昨天master处于哪个提交
- 祖先引用
  1. 在引用的末尾加一个^，则指向上一个引用。
  2. 在引用末尾加~n,指向第n个引用
    >0指向当前引用，1指向上一个，2指向上上个，以此类推
    >重复n次^效果相同
- git merge-base a b
    > 找到a分支和b分支的公共祖先
- git cherry-pick &lt;hash&lt;
    >把hash代表的提交应用到当前分支
- git rerere
    >一种简化冲突解决的方法。当启用 rerere 时，Git 将会维护一些成功合并之前和之后的镜像，当 Git 发现之前已经修复过类似的冲突 时，便会使用之前的修复方案，而不需要你的干预。

    >这个功能包含两个部分：一个配置选项和一个命令，可以在全局配置中开启
    >git config --global rerere.enabled true
- git shortlog
    > 快速生成一份包含从上次发布之后项目新增内容的修改日志（changelog）类文档
