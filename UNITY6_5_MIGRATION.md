# Survival Engine v1.32 — Unity 6.5 / URP 迁移记录

迁移目标：Unity `6000.5.5f1`，Universal Render Pipeline `17.5.0`。

## 已完成

- 将旧 Unity API 更新为 Unity 6.5 API，包括对象查找、刚体速度和编辑器工具相关调用。
- 将 9 个自定义 Shader 重写或补充为 URP 兼容实现，并保留原 Shader GUID，避免材质引用断开。
- 将 6 个旧管线特效/UI 材质显式转换到 URP 或项目自定义 URP Shader。
- 将 `NavMesh.prefab` 的旧 `NavMeshSurface` 脚本引用更新到 AI Navigation 2.0.14。
- 使用 Unity 6.5 重存 14 份 NavMeshData 和 5 个场景。
- 增加可重复运行的迁移/审计工具：`Survival Engine > Unity 6.5 > Run Migration and Audit`。

## 自动验证结果

验证日期：2026-09-10。

- Unity 无界面迁移进程返回码：`0`
- C# 编辑器程序集编译：通过
- 自定义 Shader：9 个，编译错误 0
- 材质：464 个，丢失 Shader 0
- 场景：5 个，丢失脚本 0
- Prefab：311 个，丢失脚本 0
- NavMeshData：14 份，成功重存
- 最终审计：`Problems: 0`

## 建议的人工冒烟测试

自动审计无法替代最终画面确认。建议在 Unity 中依次打开 `TestMap`、`LargeMap` 和 `WorldGenMap`，重点查看草、水面、雨滴/波纹、描边以及 3D 文本；随后进入 Play Mode，确认 Console 没有新增运行时错误。

## 回滚

迁移前备份位于：

`C:\Users\26906\Desktop\第一批_立项与设计\_Unity65_Backups\SurvivalEngine-v1.32-before-Unity65-20260910-161456.zip`
