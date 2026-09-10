# Survival Engine — Unity 6.5 / URP

这是已升级至 Unity `6000.5.5f1` 与 Universal Render Pipeline `17.5.0` 的生存、建造和种植玩法素材工程。

## 兼容性改造

- 更新旧版 Unity C# API，兼容 Unity 6.5。
- 将草地、水面、Sprite、描边、UI 和 3D 文本等 9 个自定义 Shader 迁移到 URP。
- 将旧粒子与 UI 材质转换到 URP Shader。
- 将 NavMeshSurface 引用升级到 AI Navigation `2.0.14`。
- 保留原 Shader 和资源 GUID，避免 Prefab、场景与材质引用断开。
- 提供 `Survival Engine/Unity 6.5/Run Migration and Audit` 编辑器审计入口。

## 验证结果

- C# 编辑器程序集编译通过。
- 9 个自定义 Shader 编译错误为 0。
- 464 个材质无丢失 Shader。
- 5 个场景和 311 个 Prefab 无丢失脚本。
- 14 份 NavMeshData 已使用 Unity 6.5 重存。
- 自动审计结果：`Problems: 0`。

迁移细节与人工冒烟测试建议见 [UNITY6_5_MIGRATION.md](UNITY6_5_MIGRATION.md)。

## 打开工程

使用 Unity Hub 添加本仓库目录，并使用 Unity `6000.5.5f1` 打开。首次导入完成后，可从 `Assets/SurvivalEngine/Scenes/TestMap.unity` 开始检查。

不要提交 `Library`、`Temp`、`Logs`、`UserSettings` 或 IDE 生成文件；这些内容已由 `.gitignore` 排除。
