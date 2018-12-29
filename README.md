# raffle

年会抽奖程序。

用node-webkit加原生JavaScript实现的，所以可以跨平台。也就200多行代码而已，2018年用这些框架写的人都弱爆了：Vue、React、Angular、Swing、Tkinter、Qt、WPF、WinForm。

Windows的启动方法：到 https://nwjs.io/ 下载node-webkit，解压出来，把本目录拖动到nwjs.exe上。

其它操作系统按官方说明做：

```shell
cd /path/to/your/app
/path/to/nw .
```

`/path/to/nw` is the binary file of NW.js. On Windows, it’s `nw.exe`; On Linux, it’s `nw`; On Mac, it’s `nwjs.app/Contents/MacOS/nwjs`.

## 按键

- `f`：切换全屏
- `4`：下一步
- `8`：重新加载配置文件。主要用于临场增加奖项
- 空格：立刻停止名单滚动。即确定中奖人员。
- `1`：上一步，用来看看上个奖项的情况

## 核心文件说明

- `index.html`：所有代码都在这
- `steps.json`：流程配置文件，应该一看就懂。中奖后此文件会被修改，包含中奖名单。如果需要加奖项，不用退出程序，编辑完这个文件后按`8`就能重新加载配置，继续抽。
- `names.ini`：人员名单。中奖后此文件会被修改，删除已中奖的人

## TODO

- 启动的时候设置窗口大小和位置会闪动，可以做得体验好点
- 更多的可动态设置项
- 打包成独立exe