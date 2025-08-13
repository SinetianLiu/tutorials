# 在Ubuntu环境下配置git仓库

## 一、前言

鉴于Ubuntu上没有比较好用的GitCredentialManager，我决定改用SSH连接GitHub。

## 二、环境

- Ubuntu25.04
- git2.48.1

## 三、步骤

### 生成密钥

- 生成密钥对：

```bash
ssh-keygen -t ed25519 -C "<你注册GitHub使用的邮箱>"
```

> 冷知识：上述代码中，`-C "<你注册GitHub使用的邮箱>"`其实是不必须的。

- 此时系统会询问文件保存位置：

``` text
> Enter a file in which to save the key (/home/YOU/.ssh/id_ALGORITHM):[Press enter]
```

直接回车即可。

- 接下来输入密码（两次相同密码）：

```text
> Enter passphrase (empty for no passphrase): [Type a passphrase]

> Enter same passphrase again: [Type passphrase again]
```

### 添加密钥

- 启动ssh-agent：

```bash
eval "$(ssh-agent -s)"
```

- 向ssh-agent添加密钥：

```bash
ssh-add ~/.ssh/id_ed25519
```

- 打开[密钥管理页面](https://github.com/settings/keys)。

- 点击『New SSH key』（在页面右上角）。

- 回到终端。

- 显示公钥：

```bash
cd ~/.ssh

cat id_ed25519.pub
```

- 系统输出（以我自己的公钥为例）：

```text
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJGAJjMFzGzbhyRAX+2c9hngC8pBTU90QZa9xLLcM4KI liujingyu2020@outlook.com
```

- 复制这几行（选中|右键|复制）。

- 回到浏览器。

- 在页面上的『Title』输入一个标题。

- 在『Key』粘贴你的公钥（Ctrl+V）。

- 点击绿色按钮，确认。

- 完成！

### 开始推送

