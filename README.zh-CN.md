# Retro Print Portrait · 复古印刷肖像

[English](README.md) · **简体中文**

Retro Print Portrait 是一个 Codex Skill，用于将普通人像与生活化多人合影转换成 1:1 复古编辑肖像海报，在添加孔版印刷与丝网印刷质感的同时，保留人物身份、表情、姿态、人物关系及原照片结构。

可调用的 Skill 名称是 `retro-print-portrait`。

![修图前后对比](examples/comparisons/example-01.jpg)

## 核心特点

- 保留人物身份、五官比例、表情、视线、发型、姿态、手势、服装和拍摄视角。
- 维持真实照片基础，避免把人物变成卡通或缺乏辨识度的通用插画。
- 多人合影会锁定准确人数、前后景顺序、遮挡关系、独立动作、道具和随手拍的不对称构图。
- 使用孔版印刷颗粒、丝网印刷纹理、半调网点、油墨渗色、纸张纤维和轻微套色偏移。
- 根据原照片的服装、光线与场景调整背景配色，不重复套用固定模板。
- 输出无文字、无标志、无签名、无水印的 1:1 海报。

## 效果案例

以下人物均为专门用于演示本 Skill 的 AI 虚构人物。

| 冷调钴蓝 / 珊瑚红 | 暖调珊瑚 / 粉色 | 奶油白 / 暖黄 / 钴蓝 |
| --- | --- | --- |
| ![案例 1](examples/comparisons/example-01.jpg) | ![案例 2](examples/comparisons/example-02.jpg) | ![案例 3](examples/comparisons/example-03.jpg) |

### 生活化多人合影验证

![四人生活合影验证](examples/comparisons/example-04.jpg)

案例 4 使用一张刻意保持普通感的四人手机随拍进行压力测试：人物距离不均、身体互相遮挡、表情各异，并包含杯子、剪刀手、餐桌杂物及混合室内光线。处理结果保留了全部四人、前后景关系、动作、道具、随意裁切和居家场景线索，同时应用统一的复古印刷视觉体系。

所有案例属于同一视觉家族，但会根据原照片的服装、光线和场景改变背景主色与版面分布。

## 运行要求

- Codex 或其他兼容的 Skill 运行环境。
- 用于分析输入和检查结果的图像查看能力。
- 支持图像编辑的内置图像生成能力。

生成质量和身份保真程度取决于运行环境中的图像模型。发布结果前应始终进行人工检查。

## 安装

克隆仓库，并将 Skill 复制到个人 Codex Skills 目录：

```bash
git clone https://github.com/valokxyz/retro-print-portrait-skill.git
mkdir -p ~/.codex/skills
cp -R retro-print-portrait-skill/skills/retro-print-portrait ~/.codex/skills/
```

如果 Skill 没有立即出现，请重启 Codex。

## 使用方法

上传一张人物照片并调用：

```text
$retro-print-portrait 处理这张照片。
```

你可以补充简短的美术方向，无需重新编写完整提示词：

```text
$retro-print-portrait 保留原来的俯拍角度，背景偏暖黄和奶油白，钴蓝只做小面积对比。
```

处理生活化多人合影：

```text
$retro-print-portrait 处理这张合影，保留每个人的身份、表情、动作、遮挡关系、道具和随手拍构图。
```

Skill 支持本地图像流程可识别的 JPG、PNG、HEIC 等人物照片格式。原文件不会被修改；必要时只会为 HEIC 创建非破坏性的工作副本。

## 视觉基因

配色是一套可变化的统一色彩家族，而不是固定配方：

- 主锚点：深钴蓝、群青、蓝紫色；
- 次级色面：柔粉、珊瑚粉、暖红、低饱和橙色；
- 平衡色：暖黄、奶油白；
- 鲜绿色：用于服装或克制的小面积点缀。

颜色面积与位置会响应原照片。整体保持真实摄影基础，仅进行轻度色块化和模拟印刷处理。

## 保真规则

Skill 会重点保留：

- 真实身份与人物辨识度；
- 脸型、五官、年龄、表情、视线和头部角度；
- 发型、眼镜、帽子、配饰、服装、姿态和手势；
- 准确人数以及人物左右、前后的空间关系；
- 关键道具、生活场景线索、拍摄视角和原照片骨架。

Skill 会避免美颜滤镜、换脸、统一化表情、畸形手部、人物缺失或重复、棚拍式重新站位、卡通化以及固定背景模板。

## 仓库结构

```text
skills/retro-print-portrait/   可安装的 Codex Skill
examples/before/               AI 虚构人物原始照片
examples/after/                Skill 风格处理结果
examples/comparisons/          适合 GitHub 展示的前后对比图
README.md                      默认英文说明
README.zh-CN.md                简体中文说明
```

## 隐私

人物照片可能包含敏感个人信息。请仅处理你有权使用的照片，并在公开发布前检查生成结果。本仓库中的所有案例素材均为 AI 生成的虚构人物。

## 开源许可

MIT，详见 [LICENSE](LICENSE)。
