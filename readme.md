# poster-girl-l2d-2233

2233娘的 Live2D 看板娘插件(WordPress)！

支持切换人物、切换服装。

使用本项目的 Demo （因服务器~~卓越~~性能的限制，初次加载、换装时会较慢）

- [Demo: https://cxlm.work](https://cxlm.work)
- [只含有看板娘功能的 Demo](https://cxlm.work/home/live2d/demo.html) 即本项目中，src/demo.html 效果

默认的代码**通常**无法跨域使用，但同域下是可以通过配置来使用的

## 基于原项目的改动

[修改的原项目](https://github.com/xb2016/poster-girl-l2d-2233)

原项目是基于 php 的，需要后端接口配合

这里做了一些改动（将需要后台生成的配置文件全部生成出来，调整一下请求参数），使其无需后端支持，只要路径配置正确即可使用。

参考 [另一个博客](https://nocilol.me/) 返回顶部按钮的样式，魔改了本项目的开关按钮。

参考 [另一个项目](https://github.com/stevenjoezhang/live2d-widget) 自动装配的实现方案，为本项目添加了自动配置的脚本（auto_waifu.js）

## 使用方法

1. Star 本项目

2. Download ZIP，解压，通常需要修改 auto_waifu.js 指定静态资源路径。另外，auto_waifu.js 中添加了一些定制项，现在可以更加灵活地进行定制了

    - 比如下面是默认的配置

    ```javascript
    // 同时需要引入的 css
    const live2d_waifu_css = ['/home/live2d/waifu.css'];
    // 需要引入的 js 文件，无需手动添加 Jquery 因为后面会自动检测并添加
    const live2d_waifu_js = ['/home/live2d/live2d.min.js', '/home/live2d/waifu-tips.js']
    ```

    - 静态服务器的 home 目录下的文件结构

    ```text
    live2d/
    |-- 22
    |   |-- 22.v2.idle-01.mtn
    |   |-- 22.v2.idle-02.mtn
    |   |-- 22.v2.idle-03.mtn
    ...
    |   |-- closet.2016.xmas
    |   |   |-- texture_01.png
    |   |   |-- texture_02.png
    |   |   |-- texture_03_1.png
    |   |   `-- texture_03_2.png
    |   |-- closet.2017.cba-normal
    ...
    |-- 22.2020.newyear.config.json
    |-- 22.default.v2.config.json
    |-- 33
    |   |-- 33.v2.idle-01.mtn
    |   |-- 33.v2.idle-02.mtn
    ...
    |-- auto_waifu.js
    |-- demo.html
    |-- live2d.min.js
    |-- waifu-btn.png
    |-- waifu.css
    `-- waifu-tips.js
    ```

3. 上传至站点静态目录下

4. 在需要使用的页面包含 auto_waifu.js 文件即可

## 配置

此插件修改为自动检测 JQuery，无需手动添加

此插件包含果体模型，默认是不显示的，如有需要请编辑 `waifu-tips.js` 文件

此插件允许设置默认服装，如需指定也请编辑 `waifu-tips.js` 文件

更多配置请修改 `waifu-tips.js` 文件

## 感谢

感谢 [@huzikai0424](https://github.com/huzikai0424) [@SkiTiSu](https://github.com/SkiTiSu) 对 waifu-tips.js 的优化。

## 授权

由于原项目使用 GPL 2.0 协议，故本项目也采用相同的开源协议进行授权。

另，2233 版权归 bilibili 所有！

原创不易！如果喜欢本项目，请 Star 它以示对我的支持

## 使用的开源项目’

- [Live2D-Src](https://github.com/journey-ad/live2d_src)

## Author

**poster-girl-l2d-2233** © [Moedog](https://github.com/xb2016), Released under the [GPL-2.0](./LICENSE) License.

> Blog [moedog.org](https://moedog.org) · GitHub [@xb2016](https://github.com/xb2016) · Twitter [@moesdog](https://twitter.com/moesdog) · Telegram [@xb2016](https://t.me/xb2016)

## TODO

+ 已知BUG：页面局部刷新后，绑定的监听失效