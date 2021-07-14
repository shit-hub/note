---
title: "Accurev使用"
weight: 1
bookFlatSection: false
bookToc: true
bookHidden: false
bookCollapseSection: false
bookComments: false
---

<!--more-->

### 基本概念
- Workspace : 私有开发区域
- Stream : 代码流
- Depot : 服务器上的主要仓库，用于存储具体代码
- Snapshot : 代码流的某个节点的记录，不可移动，重命名或修改

### 用户管理
- 登录
```bash 
$ accurev login
```

- 更改密码
```bash 
$ axxurev chpassword
```

- 使用UI界面
Environment: X11 Server(mobaXTerm or Xmanager)
```bash
$ acgui
```

### 工作区操作
- 创建工作区
```bash
$ accurev mkws -w <workspace-name> -b <backing-stream> -l <location> -e u
```
> -w : Workspace name
> -b : Origin stream
> -l : Directory name, it will be created in `/vob`
> -e : EOF
> u : unix

- 修改工作区
```bash
accurev chws -w <workspace> <new name>
accurev chws -w <workspace> -l <new-location> -m <new-machine>
accurev chws -w <workspace> -b <new-backing-stream>
```

- 检查工作区
```bash
accurev show wspaces
accurev info
```

- 删除工作区
```bash
accurev rmws -s <workspace>
```

### 代码操作
- 拉取代码流最新代码
```bash
$ accurev update
```

- 检查代码修改状态
```bash
accurev stat -m
```
> -k : kept
> -x : external
> -p : pending
> -M : Missing
> -m : modified

- 保存修改
```bash
accurev keep <file_name> -c  "comment"
```

- 提交修改到issue
```bash
accurev cpkadd -l <issue_id> <file_name>
```

- 得到review之后提交
```bash
accurev promote -I <issue_id> -k -c "comment"
```

- 取消issue关联的修改
```bash
accurev cpkremove -l <issue_id> <file_name>
```

