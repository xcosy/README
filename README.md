# README
⚠️ It's important to read these roles before commit your code to any repository.

---

## Roles List
1. [规范你的commit message](#role01)


## <span id="role01">公开身份，方便成员联系你</span>



## <span id="role01">规范你的commit message</span>

### 约定式提交规范

> 流行的方案是约定式提交规范（Conventional Commits），它受到了[Angular提交准则](https://github.com/xcosy/README/blob/master/Git%20Commit%20Message%20Conventions.pdf)的启发，并在很大程度上以其为依据。
>
>  [更多关于Commit Message规范](https://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

Commit Message 标准格式：
```shell
<type>(<scope>): <subject>

<body>

<footer>
```

它对git提交信息的表现非常直观：
* 每个commit占据一行。你只看行首，就知道某次 commit 的目的
* 可以过滤某些 commit（比如docs），便于快速查找特定信息
* 可以直接从 commit message 生成 Change log，方便使用脚本发布新版本的变更日志
```shell
* 1575c63 fix: Elasticsearch auto-configuration does not configure default converters (8f0ae46), closes #26030
* 2085bcc perf: enhancement BIOServer performance
* 8f0ae46 feat: Automatically enable h2c when HTTP/2 is enabled without SSL
* ad29ddf docs: cancel track CHANGELOG.md
* 22ed779 fix: ConfigData imports cannot override profile specific imports #25887
* 7495746 perf: improve BIOServer performance
* 2fb3343 feat: Log ApplicationAvailability state changes #23098
* a10de14 feat: Make ApplicationConversionService.getSharedInstance() unmodifiable
* bec190e feat: Configure memory leak detection for Netty #14338
* d0e913f fix: Configuration of ciphers is ignored for TCP with Reactory Netty(1adfe46), closes  #25936
```
### 使用开源工具完成规范的Commit Message
* **Step 1 &emsp;安装 commitizen & cz-conventional-changelog**

  ```shell
  npm install -g commitizen cz-conventional-changelog
  echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc
  ```
 
* **Step 2 &emsp;使用 git cz 来取代 git commit 试试看**
* **Step 3 &emsp;生成Change Log并发布新的工程版本**

  ```shell
  # 生成与上一个标签之间 commit 信息产生的 Change Log
  conventional-changelog -p angular -i CHANGELOG.md -s
  # 生成所有 commit 信息产生的 Change Log，其中 -r 表示生成 changelog 所需要使用的 release 版本数量，默认为1，全部则是0。
  conventional-changelog -p angular -i CHANGELOG.md -s -r 0
  
  # 打标签
  git tag v0.1.0
  
  git push --follow-tags origin master
  ```
* **Step 4 &emsp;将CHANGELOG.md需要的内容发布到Github Release Note**
  <img width="1060" alt="截屏2021-04-26 上午12 14 02" src="https://user-images.githubusercontent.com/26103839/116000935-ca6b5f80-a624-11eb-8ac6-07b3e4b12211.png">


