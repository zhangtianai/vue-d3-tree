# tree 🌲

## 实现功能

### Tree 功能

- [x] tree orientation ：horizontal 、vertical
- [x] tree collapsible

### Node 功能

- [x] 自定义节点样式
- [x] 控制节点间距离（父子节点、兄弟节点） deepFactor / separation

### Link 功能

- [x] 可选择link连接样式 straight 直角 / diagonal 曲线 / fish 鱼钩线
- [x] 可自定义link连接样式 pathFunc

## 参数 Props

Props按功能分类：

### Tree

参数 | 说明 | 默认值 | 类型
---|---|---|---
initData | 数据初始值（必填） | `undefined` | Array
orientation | 树的方向，可选值为`horizontal`/`vertical` | `horizontal` | String
collapsible | 是否可折叠 | `true` | Boolean
zoomable | 是否可缩放 | `true` | Boolean
scaleExtent | 缩放区间，设置最大值与最小值 | `{min: 0.1,max: 1}` | Object
scale | 缩放值 | 1 | Number
translate | 位置偏移量 | `{x: 0,y: 0}` | Object
transitionDuration | 动画时间（毫秒） | 500 | Number

### Node

参数 | 说明 | 默认值 | 类型
---|---|---|---
nodeSize： | 节点大小 | `{x: 200,y: 80}` | Object
separation | 节点间距离，`siblings` 控制兄弟节点之间的距离，`nonSiblings` 控制同一父节点非兄弟节点之间的距离 | `{siblings: 1,nonSiblings: 1}` | Object
deepFactor | 节点间距离，控制父子级间的节点距离（⚠️ orientation 为 `horizontal` 时建议设置为 **1.3**，orientation 为 `vertical` 时建议设置为 **0.75**） | Number | 1.3

### Link

参数 | 说明 | 默认值 | 类型
---|---|---|---
pathFunc | 连接样式，可选值为 `straight` 直角 / `diagonal` 曲线 / `fish` 鱼钩线 | `diagonal` |  String / Function

## 使用方法

``` bash
  <Tree
    ref="treeContainer"
    :initData="data"
    :translate="translate"
  >
  <template slot-scope="scope">
      <div class="base-node">
        <p>{{scope.name}}</p>
      </div>
  </template>
</Tree>
```