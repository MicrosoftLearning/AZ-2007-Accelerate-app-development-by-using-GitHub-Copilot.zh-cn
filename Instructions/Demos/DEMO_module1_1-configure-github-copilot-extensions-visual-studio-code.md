---
demo:
  title: 演示：为 Visual Studio Code 配置 GitHub Copilot 扩展
  module: 'Module 1: Get started with GitHub Copilot'
---

# 演示：为 Visual Studio Code 配置 GitHub Copilot 扩展

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

GitHub Copilot 设置在 GitHub.com 帐户和 Visual Studio Code 环境中配置。 在 Visual Studio Code 中，请使用 GitHub Copilot 状态菜单访问 GitHub Copilot 和 GitHub Copilot Chat 的设置。

通过 Visual Studio Code 中的这些设置，你可以启用或禁用特定语言的 GitHub Copilot，配置 GitHub Copilot 对话助手的行为，并根据自己的偏好自定义 GitHub Copilot 体验。 还可以在 GitHub.com 上配置 GitHub Copilot 设置，以管理 GitHub Copilot 订阅，配置提示和建议的保留，以及允许或阻止与公共代码匹配的建议。

## 启用或禁用 GitHub Copilot

在 Visual Studio Code 中安装扩展时，默认启用 GitHub Copilot。 可以根据需要禁用 GitHub Copilot 一段时间。

若要显示 GitHub Copilot 扩展的启用和禁用选项，请执行以下步骤：

1. 在 Visual Studio Code 中，打开“扩展”视图****。

1. 在已安装的扩展列表中，向下滚动，直到找到 GitHub Copilot****。

1. 若要显示列出“启用和禁用”选项的 GitHub Copilot 扩展的下拉菜单，请选择 GitHub Copilot 旁边的齿轮图标。

如果要演示启用/禁用选项，可以选择禁用选项。 但是，在继续本演示之前，请务必重新启用 GitHub Copilot。

## 在 Visual Studio Code 中配置 GitHub Copilot 和 Copilot Chat

在 Visual Studio Code 中安装扩展时，GitHub Copilot 扩展会以默认设置进行配置。 可以根据自己的偏好自定义这些设置。

Visual Studio Code 提供了两种访问 GitHub Copilot 扩展设置的方法：

- 可以使用 `Manage` 图标打开“Visual Studio Code 设置”选项卡。在“设置”选项卡上，可以选择“扩展”，然后选择“Copilot”********。
- 可以使用 GitHub Copilot 状态图标访问 GitHub Copilot 状态菜单，然后选择“编辑设置”****。

演示如何使用 GitHub Copilot 状态菜单访问设置。 这将打开 Visual Studio Code 的“设置”选项卡，并筛选出与 GitHub Copilot 相关的设置项。 使用状态菜单是访问 GitHub Copilot 扩展设置的最快捷方法。

### 配置 GitHub Copilot 设置

若要显示 GitHub Copilot 的配置设置，请执行以下步骤：

1. 在 Visual Studio Code 窗口的底部面板中，要打开 GitHub Copilot 状态菜单，请选择 GitHub Copilot 状态图标。

    GitHub Copilot 状态图标指示 GitHub Copilot 是启用还是禁用。 启用后，图标的背景色与状态栏的颜色匹配。 禁用后，图标的背景色与状态栏的颜色形成对比。

1. 在 GitHub Copilot 状态菜单中，选择“编辑设置”****。

1. 请花一分钟查看可用设置列表。

    请注意，GitHub Copilot 和 GitHub Copilot Chat 的设置都已列出。 此外，在左侧的“扩展”标签下，两个扩展都标记为 Copilot。 第一个 Copilot 扩展针对 GitHub Copilot，第二个扩展针对 GitHub Copilot Chat。

1. 在“扩展”标签下，选择第一个 Copilot 扩展。

    请注意，设置列表现在仅针对 GitHub Copilot 进行筛选。

    GitHub Copilot 的设置包括以下选项：

    - 启用自动完成
    - 启用或禁用指定语言的 Copilot 完成

1. 花一分钟时间查看**启用或禁用指定语言的 Copilot 完成**的设置。

    请注意，该选项的设置是使用语言列表和 **true** 或 **false** 值来配置的，以便为每种语言启用或禁用 GitHub Copilot。 默认情况下，为所有语言启用 GitHub Copilot。 在第一行使用通配符 `*` 和值 **true** 指定此设置。 后续行指定为哪些语言启用或禁用 GitHub Copilot。 例如，为 C#、JavaScript 和 Python 启用了 GitHub Copilot，而为 Plaintext 和 Markdown 禁用了 GitHub Copilot********************。

1. 在“启用或禁用指定语言的 Copilot 完成”下，选择“markdown”********。

    请注意，Markdown 的值设置为“false”****。 这意味着对 Markdown 文件禁用 GitHub Copilot。

1. 要为 Markdown 文件启用 Copilot，请选择“编辑项”（铅笔图标），选择“false”，将值更改为“true”，然后选择“确定”****************。

    现在可以使用 GitHub Copilot 来协助处理使用 Markdown 文件的文档项目。

1. 在“扩展”标签下，选择第二个 Copilot 扩展。

    请注意，设置列表现在仅针对 GitHub Copilot Chat 进行筛选。

    GitHub Copilot 聊天的设置包括**预览**和**试验**选项。 设置选项包括以下选项：

    - **修复测试失败**：此选项默认启用，以便 GitHub Copilot 可以提供修复测试失败的建议。
    - **跟进**：默认情况下，此设置设置为 **firstOnly**，这意味着 GitHub Copilot 仅在第一个建议之后提供跟进建议。 其他选项为“**始终**”和“**从不**”。
    - **本地替代**：默认情况下，此选项设置为“**自动**”，这意味着 GitHub Copilot 使用 Visual Studio Code 显示语言的区域设置。
    - **范围选择**：该选项默认禁用。 启用后，当用户在 Chat 中使用 `/explain` 而没有在编辑器中选择任何内容时，系统会提示用户输入范围符号。
    - **终端聊天位置**：默认设置为 chatView，它指定聊天视图。 其他选项用于快速聊天区域和终端。
    - **使用项目模板**：该选项默认启用，这样当用户在 Chat 中使用 `/new` 时，GitHub Copilot 会使用相关的 GitHub 项目模板。
    - **启用代码操作**：该选项默认启用，以便 GitHub Copilot 在编辑器中提供代码操作。
    - **自动触发**：此选项默认启用，以便在键入时自动显示 GitHub Copilot 建议。

    我们建议在此培训期间保留默认设置。 这有助于确保你在学习本学习路径中的模块时获得预期的体验。 完成培训后，可以尝试使用这些设置来自定义自己的 GitHub Copilot 和 Copilot Chat 体验。

## 在 GitHub.com 上配置 GitHub Copilot 设置

GitHub.com 上的 GitHub 帐户设置包括用于配置 GitHub Copilot 的选项。 这些设置用于管理 GitHub Copilot 订阅，配置提示和建议的保留，以及允许或阻止与公共代码匹配的建议。

GitHub Copilot 可通过 GitHub Copilot Individual 个人帐户或 GitHub Copilot Business/Enterprise 组织帐户进行管理。

## GitHub Copilot 的键盘快捷方式

使用 GitHub Copilot 时，可以在 Visual Studio Code 中使用默认键盘快捷方式。 也可使用每个特定命令的首选键盘快捷方式在键盘快捷方式编辑器中重新绑定快捷方式。
