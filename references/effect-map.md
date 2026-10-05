# 效果地图

按用户动作和目的检索对应族。表内术语是通用检索锚点，不是唯一实现方案。一个描述可能匹配多项，先判语义再选机制。参数轴不是必须全填的表单。

## A. 状态反馈：跟手、响应、轻微弹一下

| 用户说法 | 术语 / 可见机制 | 合适用途与边界 | 需要决定的参数轴 |
|---|---|---|---|
| 鼠标放上去有反应 | Hover feedback，悬停反馈 | 指针设备显示可操作性；触控仍须有可用操作 | 颜色/阴影/位移、幅度 |
| 按下有手感 | Press / tap feedback，按压反馈 | 按下即时改变，松开恢复；取消操作也恢复 | 按下/释放状态、缩放/颜色 |
| 键盘选中时看得见 | Focus indicator，焦点指示 | 独立于 hover 与 selected，键盘定位必需 | 可见轮廓、对比、遮挡 |
| 滑过来慢慢停住 | Easing，缓动 | 描述速度变化而不是路径；“顺滑”不等于越慢越好 | duration、timing function |
| 停下时有一点回弹 | Spring / overshoot，弹簧/越界回弹 | 小幅强调物理关联；高频控件避免持续振荡 | 阻尼、刚度、质量或等效回弹幅度 |
| 按了以后知道成功了 | State transition，状态过渡 | 从处理中到成功/失败；反馈不能只靠颜色或动画 | 状态、文本/图标、延迟与失败恢复 |
| 有进度，不要一直转圈 | Progress indicator，进度指示 | 只有真实可计算进度才能显示确定百分比，否则不定进度 | 数据来源、确定/不定、结束状态 |
| 等的时候先有个轮廓 | Skeleton loading，骨架屏 | 结构已知时减少跳动；不是伪造已加载内容 | 占位尺寸、替换方式、失败状态 |
| 操作结果轻轻提醒一下 | Toast / status message，轻通知 | 非阻塞反馈；重要动作不能只存在于短暂提示 | 消失条件、可读内容、是否需要行动 |

## B. 展开与导航：收起来、弹出来、切换连贯

| 用户说法 | 术语 / 可见机制 | 合适用途与边界 | 需要决定的参数轴 |
|---|---|---|---|
| 点开更多，再收起来 | Disclosure，信息展开/收起 | 按钮控制内容显示；不是“菜单”的同义词 | 展开状态、内容高度、触发区域 |
| 一组内容逐项展开 | Accordion，折叠组 | 多个 disclosure 的组织；是否允许多项展开由需求决定 | 单开/多开、默认项、嵌套 |
| 浮在按钮附近 | Anchored popover，锚定浮层 | 临时上下文内容；具体语义取决于内容与任务 | 锚点、碰撞避让、关闭、焦点 |
| 鼠标经过出现解释 | Tooltip，提示说明 | 补充短说明，不承载必须点击的操作；触控需替代入口 | hover/focus、时机、说明关联 |
| 弹出后先处理这件事 | Modal dialog，模态对话框 | 背景实际不可交互；有焦点管理与关闭契约 | 初始焦点、关闭路径、返还焦点 |
| 侧边滑出一块 | Drawer / side panel，侧面板 | 只是位置形态，可能模态也可能非模态 | 方向、宽度、模态性、退出 |
| 从手机底部拉起来 | Bottom sheet，底部面板 | 形态不决定模态语义；拖拽关闭是可选增强 | 高度/停靠点、拖动、按钮关闭 |
| 点标签换内容 | Tabs，标签页 | 一组关联面板；不是普通路由链接 | 激活方式、焦点键盘、面板关联 |
| 选中标记滑过去 | Active indicator，活动项指示器 | 展示当前选中项；与内容切换、焦点分别管理 | 位置/宽度、布局测量、过渡 |
| 卡片点开像原物体变大 | Shared-element transition，共享元素过渡 | 同一实体跨视图延续；页面状态与焦点仍要正确 | 元素配对、几何、内容到达时机 |
| 页面换了但位置感还在 | View transition，视图过渡 | 页面/DOM 状态间视觉衔接；API 是实现候选，不是术语的前提 | 旧/新视图、路由、滚动/焦点恢复 |

## C. 出现、滚动与直接操作：层层出现、随滚动、跟着拖

| 用户说法 | 术语 / 可见机制 | 合适用途与边界 | 需要决定的参数轴 |
|---|---|---|---|
| 慢慢显出来/淡掉 | Fade，透明度过渡 | 轻量进入/退出；不可见元素不应残留阻挡操作 | opacity、duration、移除时机 |
| 从旁边/下面进来 | Slide / translate，位移过渡 | 方向解释来源与去向；少量位移比大幅飞入更适合高频操作 | 方向、距离、opacity、时长 |
| 从一点展开 | Scale / reveal，缩放/揭示 | origin 要符合来源；大段文字缩放会影响阅读 | transform-origin、比例/裁切边界 |
| 内容一个接一个出现 | Stagger，交错进入 | 强调小组层级；长列表累计延迟不能挡住操作 | 顺序、间隔、总延迟上限 |
| 变高变宽不要跳 | Layout transition，布局过渡 | 几何状态变化；动态内容应以真实尺寸为准 | 高度/位置、测量、溢出、焦点 |
| 滚到那里才出现 | Scroll-triggered reveal，滚动触发出现 | 到达阈值后播放时间动画；不是持续绑定滚动 | 可见阈值、一次/重复、初始可读性 |
| 滚多少就变化多少 | Scroll-driven animation，滚动驱动动画 | 动画进度绑定滚动或可见范围；与触发播放分开 | scroller、区间、映射与回退 |
| 背景和前景速度不同 | Parallax，视差 | 小幅深度表现；有阅读任务或低动态偏好时简化 | 层数、速度比、最大位移 |
| 到某处标题固定住 | Sticky positioning，粘性定位 | 滚动布局规则，不必靠 JS 动画；不能盖住内容/焦点 | 容器、top/offset、结束边界 |
| 一页一页停稳 | Scroll snap，滚动吸附 | 辅助落在内容边界；不强夺用户滚动控制 | axis、snap type、内容尺寸 |
| 拖到哪就跟到哪 | Direct manipulation / drag，直接操控/拖动 | 指针位置决定状态；松手回弹是独立阶段 | 指针映射、边界、取消、替代操作 |
| 松手还滑一段再停 | Momentum / inertia，惯性 | 拖动后速度衰减；优先原生滚动，避免双重惯性 | 初速度、衰减、边界与停止 |
| 拖起来其他项让位 | Drag-and-drop reorder，拖拽排序 | 拖动、预览、提交/取消分别定义；须有非拖动替代 | 排序轴、占位、落点、键盘按钮 |

## D. 材质与层级：玻璃、浮起、立体

| 用户说法 | 术语 / 可见机制 | 合适用途与边界 | 需要决定的参数轴 |
|---|---|---|---|
| 半透明磨砂玻璃 | Frosted glass / glassmorphism，磨砂玻璃表现 | 后方图像经过模糊并透出；文字仍需清晰；不是降低整块内容 opacity | 背景透明度、backdrop blur、边界/对比 |
| 卡片浮在上面 | Elevation，视觉抬升 | 用阴影/边界表达叠层；不同于 modal 阻断背景 | 阴影层、边界、遮挡关系 |
| 柔和的一团颜色 | Gradient / ambient glow，渐变/环境光晕 | 局部气氛与视线引导；可读区域保持对比 | 颜色、范围、静态/动态 |
| 移动鼠标像有立体倾斜 | Pointer tilt，指针驱动倾斜 | 低频展示卡片；触控静态回退，文本和点击区稳定 | 旋转范围、perspective、复位 |
| 摸起来像真实表面 | Surface texture，表面纹理 | 细微噪声或纹理减轻平面感；无需自动变成高成本动画 | 密度、对比、尺度 |
| 边缘有光、选中时发亮 | Edge highlight / glow，边缘高光/光晕 | 低频强调重点；状态还需形状/文字等其他线索 | 强度、范围、状态与对比 |

## 评价词的译码

- **高级**：先找层级、留白、节奏和一致性缺口；只有明确需要材质时才推荐玻璃/光晕。
- **丝滑**：排除跳变与卡顿，定义状态之间连续、能被打断的变化；不直接改成慢动画。
- **跟手**：操作即时映射到反馈；跟随指针的阶段与松手后的收尾分开。
- **有层次**：先分信息顺序与空间层级，再选 disclosure、stagger 或 elevation。
- **有生命力**：用一次有因果的反馈或轻弹性，优先重要节点；不是全页面循环漂浮。
- **有冲击力**：给一个主角、一个重点时刻；幅度/对比服务重点，常规操作不抢戏。
- **科技感**：先明确信息密度、秩序与反馈方式；光晕、网格或扫描只是可选外观。

## 建议起点

已有设计系统参数优先。没有参数时，可先试微反馈 100–180ms、普通进入/退出 160–260ms、较大空间过渡 240–400ms；交错间隔 30–60ms，并限制长组累计等待。小位移可从 4–12px、按压缩放从 0.98–1 开始。它们是本 Skill 的试作建议，不是规范或最终审美判断；距离、任务频率、设备与实测会改变选择。

减少动态效果时保留状态变化，移除非必要位移、回弹、视差和长交错；用即时变化或轻微透明度反馈。静态玻璃与阴影无需因为 reduced-motion 自动消失。

## 资料与知识状态

本地图是独立整理，不依赖小红书作者完整版。以下页面已在 2026-10-05 至 2026-10-06 读取；其他表项是通用设计知识，不冒充逐项官方核验。使用新 API 前仍需核对目标环境能力。

- [WAI APG Modal Dialog](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/)：背景不可交互、焦点进入/循环/返还、Escape 与命名。
- [WAI APG Tabs](https://www.w3.org/WAI/ARIA/apg/patterns/tabs/)：面板关系与激活/键盘；自动激活仅适合无可察觉延迟的面板。
- [WAI APG Disclosure](https://www.w3.org/WAI/ARIA/apg/patterns/disclosure/)：button、Enter/Space、aria-expanded；aria-controls 在该模式可选。
- [Carbon Motion](https://www.carbondesignsystem.com/building-blocks/foundations/motion/overview)：productive / expressive 与按场景选节奏；Carbon token 属 IBM 系统指引，不是通用规范。
- [Motion Animation](https://motion.dev/docs/react-animation)：进入/退出、spring、hover/tap/focus、stagger 等实现能力；不要求安装该库。
- [MDN CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Transitions/Using)：property、duration、delay、timing-function。
- [MDN backdrop-filter](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/backdrop-filter)：过滤后方图像，需透明/半透明背景，作用范围受 backdrop root 影响。
- [MDN Scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Scroll-driven_animations)：滚动时间线与 view/scroll 范围。
- [MDN View Transition API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API)：同文档 DOM 状态与跨文档视图衔接；浏览器能力、阅读位置与焦点另行验证。
