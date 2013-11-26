---
layout: post
title: [Draft] Git and Github workflow
date: 2013-11-26 14:29:15
disqus: y
---

# 开发流程

1. 开始开发一个新feature，
   首先`git fetch`更新仓库, `git checkout origin/v3`切换到最新的`origin/v3`分支
2. 基于`origin/v3`分支创建feature分支
   `git checkout -b new-feature-branch`
3. Code and commit
4. 然后就是push啦，
   `git push origin new-feature-branch:features/lj-new-feature-branch` 或者 #TODO
5. 发起一个 Pull Request
6. 等待队友审核
7. 审核有问题，再修改
   修改最后一个commti可以`git commit --amend`
   修改任意commit可以使用`git rebase -i HEAD~5`
8. 修改完成后再push一次，
   `g push origin new-feature-branch:lj-new-feature-branch` 或者 #TODO
9. 审核没问题的话就可以Merge Pull Request了

# 审核流程

([TargetBranch]: `origin/feature/124_chord_fix-something`)

1. `git fetch origin` (origin is optional)
2. `git checkout [TargetBranch]`

注：审核队友分支时不用 pull ， 因为 pull = fetch + merge，存在更改的效果(merge时)

# 分支命名

```
[Topic]/[Trello Card ID]_[Your Name]_[Title Part1]-[Tilte Part2]
```

除了 Topic 外其它的可以根据情况省略.

例子:

1. 功能分支 feature/124_chord_add-branch-naming
2. 修复分支 hotfix/124_chord_name-is-wrong


