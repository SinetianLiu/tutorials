# 欢迎使用Sinetian's Tutorials

> 若访问速度过慢，可前往[镜像站](https://sinetian.rth1.xyz/README.md)。
>
> 注意：镜像站更新较慢。

<div id="poem"></div>
<script>
  fetch('https://v1.jinrishici.com/all.json')
    .then(r => r.json())
    .then(d => {
      document.getElementById('poem').textContent = d.content + ' —— ' + d.author + '《' + d.origin + '》';
    });
</script>

这是一个乱七八糟的数码教程。（上次更新于250814）

1. [Ubuntu To Go](https://sinetianliu.github.io/tutorials/utg)
2. [在Ubuntu上配置ssh](https://sinetianliu.github.io/tutorials/ssh@ubuntu)
3. [折腾记：修复UOS使用`apt update`后无法正常登陆的问题](https://sinetianliu.github.io/tutorials/fix-apt-err)
