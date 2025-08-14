# 折腾记：修复UOS使用`apt update`后无法正常登陆的问题

## 一、问题产生

我有一台很久没有更新过的UOS电脑。有一天手贱，用`apt update && sudo apt upgrade`给它更新了。结果更新后，登陆时输入正确密码仍然反复跳回登陆界面。

## 二、折腾过程

1. 尝试重启，失败。
2. 尝试在GRUB界面进入`System Rescue`清理磁盘，失败。
3. 尝试LiveCD启动，由于硬件问题失败。
4. 尝试在GRUB界面进入`System Rescue`恢复出场设置，成功启动电脑。

其实到这儿问题就解决了，但我不死心，又作死地尝试了一遍`apt update && sudo apt upgrade`，问题完美复刻。于是又尝试一遍上述步骤。还好最后电脑开机了。

## 三、问题分析

判断是由于电脑太久未更新，直接使用了`apt update && sudo apt upgrade`导致的问题。

## 四、怎么正常更新？

1. 先试了一下

    ```bash
    aptitude safe-upgrade
    ```

    结果提示没更新（~~玩我呢~~），失败。

2. 于是执行了

```bash
sudo -s
apt update
apt dist-upgrade
```

并且更新过程中碰到提问的一律按`y`，成功开机。
