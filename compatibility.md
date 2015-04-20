# 兼容性

注意：

* __请不要使用 `IETester` 这种不靠谱的工具测试__；
* 微软[官方的说法](https://www.modern.ie/en-us/f12)，IE 开发者工具中的浏览器模式也不一定靠谱；
* 官方提供了[各种 IE 测试虚拟机](https://www.modern.ie/zh-cn/virtualization-tools#downloads)。

## 分级浏览器支持（GBS）

[GBS](https://yuilibrary.com/yui/docs/tutorials/gbs/) 是 YUI 团队提出的应对日益增长的浏览器兼容问题的思路，详情可以查看 [YUI 相关页面](https://yuilibrary.com/yui/docs/tutorials/gbs/)。

### GBS 描述

* __A 级__：最高支持级别，充分利用 H5 和 CSS3 等技术，提供最优的视觉和交互效果。
* __B 级__：有限支持，基本的样式和正常的交互，不考虑视觉、交互效果。
* __C 级__：核心支持，显示语义化的 HTML 标记渲染的内容，不考虑样式和行为。
* __X 级__：未知、零散的很少使用或已经停止开发的浏览器，可能不支持，也可能支持。

### GBS

按照国际惯例，对主流浏览器（系统）最近两个稳定版本的全面支持。结合国内实际情况，一些浏览器的支持缩减为最新正式版，IE 则对更老版本做了有限支持。

关于浏览器功能支持的更多细节请参考 [Can I use](http://caniuse.com/)。

__OS/Browser__        | __Ver__ | __Windows__ | __iOS(7.1.2+)__ | __OS X (10.9+)__ | __Android (4.1+)__ | __WP(8+)__
:-------------------- | :------ | :---------- | :-------------- | :--------------- | :----------------- | :---------
__Chrome__            | L2      | A           | A               | A                | A                  | N/A
__IE__                | 10+	    | A           | N/A             | N/A              | N/A                | A-
                      | 9       | B           | N/A             | N/A              | N/A                | N/A
                      | 8       | C+          | N/A	            | N/A              | N/A                | N/A
                      | lte7    | C           | N/A             | N/A              | N/A                | N/A
__Firefox__           | L2      | A           | N/A             | A                | X                  | N/A
__Safari__            | L2      | X           | A               | A                | N/A                | N/A
__Opera__             | L1      | X           | N/A             | N/A              | X                  | N/A
__Opera Coast__       | L1      | N/A         | A               | N/A              | N/A                | N/A
__Opera Mini__        | L1      | N/A         | X               | N/A              | X                  | X
__Stock<sup>1</sup>__ | L1      | N/A         | N/A             | N/A              | X                  | N/A
__UC 浏览器__         | L1      | X           | A               | N/A              | A                  | A-
__360浏览器__         | L1-极速 | A-          | X               | N/A              | X                  | N/A
                      | L1-IE8  | C+          | N/A             | N/A              | X                  | N/A
__搜狗浏览器__        | L1-极速 | A-          | N/A             | N/A              | N/A                | N/A
                      | L1-IE8  | C+          | N/A             | N/A              | N/A                | N/A
__FF Mobile__         | L1      | N/A         | N/A             | N/A              | X                  | N/A

注释：

* `L` 代表 `last`，`L2` - 最新的两个稳定版本；`L1` - 最新稳定版本。
* `1` 安卓系统自动浏览器，由于部分厂商对浏览器做了修改，列为 X 级。

参考链接：

* [iOS Version Stats](http://david-smith.org/iosversionstats/)

### IE 8/9

* IE 8/9 不支持 `transition`，看不到任何动画效果；
* IE 9 对 ES5 支持相对较好，IE 8 则不然。

功能            | IE 8 | IE 9
:-------------- | :--- | :---
`border-radius` | NO   | YES
`box-shadow`    | NO   | YES
`transform`     | NO   | YES（`-ms` 前缀）
`Flex Box`      | NO   | NO
`transition`    | NO   | NO
`placeholder`   | NO   | NO

### IE 8

需要支持 IE 8 的用户请使用条件注释引入相关的 polyfill。

#### HTML5 新元素

以下任意引入一个即可。

[Modernizr](https://github.com/Modernizr/Modernizr)
[HTML5 Shiv](https://github.com/aFarkas/html5shiv)

#### Media Query

[Respond.js](https://github.com/scottjehl/Respond)

#### rem

[REM unit polyfill](https://github.com/chuckcarpenter/REM-unit-polyfill)

#### `box-sizing`

IE 8 ignores `box-sizing: border-box` if min/max-width/height is used.

#### 伪元素

IE 8 只支持 CSS 2.1 规范中的单冒号语法（`:before`/`:after`），不支持 CSS3 的双冒号语法(`::before`/`::after`)。

#### 字体图标

参见 Bootstrap 中的 [issue 及里面提供的解决方法](https://github.com/twbs/bootstrap/issues/13863)。

## 关于 IE 6/7

默认不支持
