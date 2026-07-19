# Tool-Academy-For-Unity6

> 一个用Unity 6边做边学的「游戏开发法学院」：把一座小城从零搭起，
> 每加一项功能，都对应一条可拆解、可回看、可复盘的学习路径。

工程基于 `_LearnUnity/Samples/SimpleBaseGame`，场景地名沿用「草坪小城」，
整条学习体系的品牌名为 **工具法学院**。

---

## 一、它是什么

不是“看教程”，而是 **做中学（Learning by Building）**：

- 顶部 `Tools / 工具法学院` 菜单把 9 个功能 step 拆成 **基础篇 / 进阶篇 / 高级篇**
  三级（甚至四级）细粒度子步骤，共 **16 个原子步骤**。
- 每点一个子步骤，都会在场景里真正**增添一段功能代码**，并自动把这次变动——
  「涉及文件 / 代码段 / 学到的新知识 / 巩固的基础技能」——写入当日学习日志。
- 游戏内置「学习方法」任务栏可手动追踪进度、写笔记、导出当日 `.md`。

## 二、目录结构

```
New Unity Project/
├─ Assets/_LearnUnity/Samples/SimpleBaseGame/
│  ├─ Editor/
│  │  ├─ SceneSetup.cs        # 场景分步构建 + 多级菜单（基础/进阶/高级）
│  │  ├─ LearningLogger.cs    # 交互式学习日志（点 step 即记录）
│  │  ├─ BuildGame.cs          # 一键生成并打包为 EXE
│  │  └─ BuildToolbar.cs       # 顶部自定义工具栏 Overlay
│  ├─ Scripts/
│  │  ├─ PlayerController.cs   # 角色控制 + 天气影响
│  │  ├─ WeatherController.cs  # 程序化天气系统
│  │  ├─ Trap.cs / Crystal.cs / Interactable.cs ...
│  │  └─ LearningTaskbar.cs    # 游戏内学习方法任务栏
│  └─ Art/Characters/Eri       # 角色换装素材
├─ LearningNotes/              # 学习日志与笔记
│  ├─ daily_YYYY-MM-DD.md      # 交互式学习日志（点 step 自动写）
│  └─ 每日学习笔记_*.md         # 学院式复盘
├─ 后续拓展计划.md              # 颗粒度拆分与未来规划
└─ Builds/ToolAcademy/工具法学院.exe
```

## 三、学习方法任务栏（游戏内）

运行 exe 后，右侧「学习方法 ▾」按钮可：
- 勾选 **6 大学习模块**（移动 / 天气 / 陷阱 / 换装 / UI / 场景生成）的完成度；
- 给每个模块 **写笔记**（持久化到本地 JSON）；
- 一键 **导出今日笔记** 为 `每日学习笔记_日期.md`。

## 四、交互式学习日志（编辑期）

在 Unity 编辑器点击 `Tools / 工具法学院 / 基础篇|进阶篇|高级篇 / …` 任意子步骤，
即把该功能代码 + 知识点写入 `LearningNotes/daily_日期.md`，Console 也会打印 `[工具法学院] 已记录 …`。

> 这是**编辑器开发期**功能，打包后的 exe 不含它——它在你用编辑器做场景/学习时记录。

## 五、运行与打包

| 方式 | 操作 |
|------|------|
| 编辑器分步学 | `Tools / 工具法学院 / 基础篇…` 逐级点击 |
| 一键生成场景 | `Tools / 工具法学院 / 完整生成（一键）` |
| 顶栏工具 | Scene 视图顶部「工具法学院工具」浮层：打包 EXE / 生成场景 |
| 命令行打包 | `Unity -batchmode -quit -executeMethod BuildGame.BuildCityPackage` |
| 双击运行 | `Builds/ToolAcademy/工具法学院.exe`（窗口 1280×720） |

**操作**：双击 exe → 选角色 + 起名 → 开始；天气 `1~5` / 工具栏；换装 `B` 键。

## 六、命名由来

「工具法学院」寓意：像法学院逐条研读判例一样，**逐条研读每一行改变场景的代码**，
把零散的 Unity API 沉淀成可复用的工程能力。详见 `后续拓展计划.md`。
