# CONTEXT —— 交接文档

> 给下一个接手的 AI 助手（Codex）看。读完就能接着教翔、接着推进项目，不用重新问他「学到哪了、环境是什么、下一步干嘛」。
> 最后更新：2026-10-15

## 1. 翔是谁、要做什么

- 软件工程大三学生，想走游戏编程方向。
- 目标：6 个月内（2026-09 到 2027-03）做出一个能投游戏公司实习的 Unity 2D 作品。
- 作品方向已定：**俯视角 2D 肉鸽爬塔**（俯视角 + Roguelike + 爬塔，不是吸血鬼幸存者式割草）。
- 时间预算：每天 1-2 小时，每周约 10 小时。

## 2. 基础水平

- C#：有基础，已私下补过一轮，但掌握程度需要接手时用文末「C# 自测清单」快速核对。
- Unity：零基础起步。已学完编辑器、组件、生命周期、俯视角移动 + 鼠标瞄准。还没碰：动画、UI、音效、碰撞、存档。

## 3. 环境

- 引擎：Unity 2022.3 LTS
- 项目路径：`D:\unity\My first 2d`
- 日志仓库：`D:\Projects\unity-devlog`（GitHub 同名仓库，账号 Ra1ninG6006）
- 主线课：Unity 2D Dungeon Gunner Roguelike（B 站国语版，UP 主 JaysongShao，164 节 / 51 小时）。是中级课、不教基础，进阶段 2 前要先垫好俯视角 2D 基础和 C#。

## 4. 当前进度（快照）

### 已完成

- 阶段 0 入门：编辑器界面、组件（GameObject 是空壳，能力来自组件）、生命周期（Awake → Start → Update）。
- 阶段 1 俯视角基础，完成前两周：
  - 第 1 周移动：WASD 八方向移动，Rigidbody2D。
  - 第 2 周鼠标瞄准：ScreenToWorldPoint 转世界坐标，Atan2 + Rad2Deg 算角度，Quaternion.Euler 旋转朝向鼠标。

### 现有代码（`D:\unity\My first 2d\Assets`）

- `LifecycleDemo.cs`：验证生命周期的演示脚本。
- `Scripts\PlayerController.cs`：俯视角玩家控制器，含移动（FixedUpdate + rb.velocity）和瞄准（Update + transform.rotation）。

### 已掌握的 Unity 知识点

- 组件模型、生命周期
- Rigidbody2D 物理移动（用 rb.velocity，不动 transform.position）
- FixedUpdate（物理）与 Update（视觉）的分工
- 屏幕坐标（像素）与世界坐标（米）两套体系，要换算
- 方向向量归一化、Atan2 / Rad2Deg / Quaternion.Euler

## 5. 下一步（从这里继续）

按 PLAN.md，阶段 1 还剩：

- 第 3 周：相机跟随、Animator 动画、Collider2D 碰撞。
- 第 4 周：UI（Canvas、血条）+ 综合练手，产出「俯视角移动 + 射击 + 打靶」小 demo，提交 Git。
- 之后进阶段 2 主线课《地牢枪手》。

接手建议顺序：先核对 C# 自测清单补薄弱点，再从第 3 周相机跟随开始。

## 6. 教学方式（必须遵守）

翔明确要求：

- 两者结合：先讲原理、给思路/骨架，让他自己动手写；卡住再给提示或示范，不要一上来就甩完整代码。
- 讲代码知识：每个 API 是干嘛的、为什么这么写。
- 讲制作思路：为什么这样做、有什么取舍、对后面功能有什么影响。
- 目标是让他真正学懂、能独立写，不是机械照做。

## 7. 表达风格

- 对话用简体中文；代码、路径、标识符保持英文。
- 笔记 / 日志 / 文档要平实简洁的要点式：不过度解释、不堆术语、不加语气词。

## 8. 已踩过的坑（别重蹈）

- 新建脚本默认叫 NewBehaviourScript，复制代码没改类名，导致类重复定义、编译报错。
- ScreenToWorldPoint 不补 z 深度，换算结果不对。
- 移动写 Update 会有物理抖动，要写 FixedUpdate。
- 屏幕坐标和世界坐标是两套体系，别混用。

## 9. 工作流约定

- 每次学习后写一篇日志到 `logs/YYYY-MM-DD.md`。
- 每次改动 commit + push 到本仓库。
- 学完一个阶段，回来更新本文件第 4、5 节的「当前进度」和「下一步」——这是保持下一个 AI 能无缝衔接的关键。
- 期末（12 月底 - 1 月初）预留缓冲，寒假可加速。

## 10. 接手第一步（行动清单）

1. 读本文件。
2. 打开 `D:\unity\My first 2d` 看现有代码。
3. 用文末 C# 自测清单核对翔的 C# 水平，缺哪补哪。
4. 从第 5 节「下一步」继续。

## 附：C# 自测清单

接手时逐项让翔口头或动手确认，会的跳过，不会的先补：

- 变量与基本类型：int / float / bool / string，类型转换
- 方法：定义、参数、返回值
- 类与对象：字段、方法、new 实例化
- 访问修饰符：public / private
- 控制流：if / else、switch、for、while、foreach
- 数组 与 List<T>
- 引用类型 vs 值类型
- 命名空间与 using
