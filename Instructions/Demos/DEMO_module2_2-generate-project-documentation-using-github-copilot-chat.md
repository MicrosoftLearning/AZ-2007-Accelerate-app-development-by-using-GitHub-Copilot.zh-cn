---
demo:
  title: 演示：使用 GitHub Copilot 对话助手生成项目文档
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手生成项目文档

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

创建文档是软件开发的重要组成部分。 内联文档可以帮助开发人员理解代码库、其目的以及使用方法。 项目文档为有关各方提供了了解项目范围和目的所必需的信息。

项目文档通常包含以下部分：

- **项目概述**：项目、其目的和目标的大致摘要。
- **项目要求**：项目要求的列表，包括功能要求和非功能要求。
- **项目约束**：影响项目的任何约束，例如时间、预算或技术约束。
- **项目依赖项**：项目依赖项的列表，包括项目依赖的库、框架和其他组件。
- **项目摘要**：项目、其目的和目标的简要摘要。

在本演示中，你将使用 GitHub Copilot 对话助手为 `APL2007M2Sample1` 项目生成项目文档。

> [!IMPORTANT]
> 讲师应强调查看 GitHub Copilot 建议的文档的重要性。 开发人员需要验证准确性和完整性。 GitHub Copilot 生成的文档是一个着手点。 你可能需要添加、移除或修改内容，以满足项目的特定需求。

### 生成 APL2007M2Sample1 项目的项目文档

可以使用“聊天”视图和 `@workspace` 参与者在 Visual Studio Code 中生成项目文档。 可以包括自然语言说明以生成项目文档的特定部分，例如项目概述、要求、约束、依赖项和摘要。 还可以使用 GitHub Copilot Chat 生成特定类型的文档文件，例如 `readme.md` 文件。

1. 确保在 Visual Studio Code 中打开了 `APL2007M2Sample1` 项目。

1. 若要打开“聊天”视图，请选择“打开聊天”****。

1. 若要生成工作区的文档，请在“聊天”视图中输入以下提示：

    ```output
    @workspace document this project
    ```

1. 花一分钟时间查看为 `APL2007M2Sample1` 项目生成的项目文档。

    请注意，建议的项目文档类似于上一单元中生成的项目说明。

    通过追加“记录项目约束”或“记录项目依赖项”等提示，可以获取有关项目的详细信息。

1. 若要生成描述项目依赖项的文档，请在“聊天”视图中输入以下提示：

    ```output
    @workspace document the project dependencies
    ```

1. 花一分钟时间查看项目依赖项文档。

    Copilot 聊天生成的响应应类似于以下信息：

    GitHub Copilot 聊天可帮助记录项目的任何方面。 可以使用“聊天”视图为项目中的特定文件、类或函数生成文档。 项目的大小和复杂性有助于确定所需的详细级别。

    如果时间允许，请使用 Chat 视图为以下项目部分生成文档：

    - 项目要求
    - 项目约束
    - 项目体系结构
    - 项目设计
    - 项目测试
    - 项目部署
    - 项目摘要

    可以根据项目及其利益干系人的特定需求定制 Copilot Chat 生成的项目文档。

1. 若要为 `APL2007M2Sample1` 项目生成自述文件，请在“聊天”视图中输入以下提示：

    ```output
    @workspace generate a readme document that can be used as a repo description
    ```

1. 花一分钟时间查看为 `APL2007M2Sample1` 项目生成的自述文件。

    Copilot Chat 生成的自述文件内容提供了项目的大致概述，其中包括此类文件中经常包含的几个部分。

    可以调整提示，以指定特定的 README 部分。 还可以编写单独的提示来生成自述文件的特定部分。

    > [!NOTE]
    > 如果要将自述文件文档格式化为 markdown 文件，可以输入类似于以下提示的提示：`generate readme project documentation formatted using a raw markdown format`。 如果 GitHub Copilot 已配置为使用 Markdown 文件，你可以使用内联聊天功能将 README 文档的格式设置为 Markdown 文件。

### 总结

在本演示中，你使用了 GitHub Copilot 对话助手为 `APL2007M2Sample1` 项目生成项目文档。 通过使用“聊天”视图和 `@workspace` 参与者，你能够为项目概述、要求、约束、依赖项和摘要生成文档。 你还为 `APL2007M2Sample1` 项目生成了自述文件。 通过使用 Copilot Chat 生成项目文档，可以创建一个大致概述，帮助其他开发人员了解项目及其目标。 请记住查看 Copilot Chat 生成的文档，以确保准确性和完整性。
