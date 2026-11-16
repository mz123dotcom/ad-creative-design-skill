# ad-creative-design-skill

> 广告创意设计 Agent Skill：产品图 → 15 秒商业广告分镜脚本。
> 适配豆包 Seedance 2.0 Fast，MIT License，免费商用。

这是一套用于生成商业广告分镜的固定提示规约。它**只输出脚本**，不自动调用视频生成工具——核心生产力就是提示词本身。只要提示词不变，输出格式与风格约束就稳定，可加载到任意支持自定义系统提示词的大模型。

## 能产出什么

- 从产品参考图提炼**视觉风格 + 色彩美学 + 调性**
- **旁白文案**：50–60 字，带停顿与重音节奏标记，适配 15s 配音
- **6–8 个高密度剪辑分镜**，每镜含英文画面提示词、负面提示词、中文画面描述、配音、音乐音效
- 末尾附 **Seedance 2.0 Fast 生成使用说明**

## 什么时候触发

- 产品广告分镜、商业广告脚本、广告创意设计
- 新品宣发短视频、电商产品视频
- 用户说「生成广告脚本」「按分镜模板写广告」

**不适用**：真人出镜种草口播、探店视频、剧情短剧（这类请用 ugc-seeding-video）。

## 默认参数

| 项 | 默认值 |
|---|---|
| 时长 | 15s |
| 画幅 | 16:9 横屏 |
| 分辨率 | 720p |
| 目标模型 | Seedance 2.0 Fast |
| 镜头数量 | 6–8 镜高密度剪辑 |

自定义示例：`改成10s版本，9:16竖屏，4K，复古胶片质感` / `保持15s，改成赛博朋克风格`

## 目录结构

```
ad-creative-design-skill/
├── SKILL.md                        # 入口：角色定位、强制字段、硬性约束、输出骨架
├── references/
│   ├── prompt-spec.md              # 完整系统提示规约原始版（可直接当系统提示词用）
│   ├── output-template.md          # 空白模板，手写脚本用
│   ├── demo-earbud.md              # Demo：小米半入耳耳机 15s 完整脚本
│   └── demo-silver-phone.md        # Demo：银白流体屏旗舰手机 15s 完整脚本
├── assets/
│   └── ad-creative-demo.mp4        # 配套需求演示成片
└── LICENSE                         # MIT
```

## 安装

```bash
git clone https://github.com/mz123dotcom/ad-creative-design-skill.git
cp -R ad-creative-design-skill ~/.claude/skills/
```

`SKILL.md` 通过相对路径引用 `references/`，保持同级即可。

## 快速上手（豆包 / 任意大模型）

1. 把 `references/prompt-spec.md` 全文作为系统提示词加载
2. 上传产品图片，发送指令：`生成广告脚本`
3. 拿到分镜脚本，每个分镜单独走【图生视频】
4. 剪映按时间轴拼接、配音、加音效，完成成片

## 限制

提示词针对 Seedance 2.0 Fast 特性做了轻量化处理，复杂特效容易崩坏；优先推荐干净商业产品摄影风格。

## License

[MIT](LICENSE) — 可自由使用、修改、商用，保留署名即可。
