---
demo:
  title: 演示：将代码从一种编程语言转换为另一种编程语言
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# 演示：将代码从一种编程语言转换为另一种编程语言

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

GitHub Copilot 可以帮助你将代码从一种编程语言转换为另一种编程语言。 例如，可以要求 GitHub Copilot 将函数或代码片段转换为另一种编程语言。

可以使用 GitHub Copilot 完成以下类型的代码转换：

- 将整个代码文件转换为另一种编程语言。
- 将函数转换为另一种编程语言。
- 将代码片段转换为另一种编程语言。

每个聊天界面（聊天视图、快速聊天窗口和内联聊天）都可用于在编程语言之间转换代码。 选择聊天界面取决于偏好和要转换的代码的复杂性。

假设你刚刚开始 `QuarterlyIncomeReport` 项目。 你与同事讨论项目目标。 他们提到，他们有一个 Python 文件，它可以提供你要查找的一些功能。 它们指向 Python 代码的存储库。 你决定在 Visual Studio Code 中打开 Python 代码项目，并使用聊天视图将 Python 代码转换为 C#。

## 使用聊天视图在编程语言之间转换代码

1. 在 Visual Studio Code 中打开“APL2007M3Python”项目文件夹。****

    此项目包含在本模块中处理的 `QuarterlyIncomeReport` 项目的 Python 版本。 你可以让 GitHub Copilot 使用聊天视图向你解释代码，或者解释此智能操作。

1. 运行 Python 应用程序。

    请注意，Python 应用程序的输出实质上与前面创建的 C# 应用程序的输出相同。

1. 打开 `main.py` Python 文件。

    Python 文件包含生成销售数据的函数。 你想要将此 Python 代码转换为 C#。

1. 选择整个文件内容。

1. 打开“聊天”视图，然后输入以下提示：

    ```plaintext
    Convert #selection to C#
    ```

1. 花点时间查看 GitHub Copilot 的响应。

    响应应包含所选 Python 代码的 C# 版本。

1. 打开 Visual Studio Code 的第二个实例。

1. 打开“聊天”视图，输入以下提示：

    ```plaintext
    @workspace /new console application in C# NET8 named APL2007M3B. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

    如果 Copilot 使用有关“path 参数”的错误消息进行响应，请再次尝试相同的提示。

1. 选择“创建工作区”****

1. 在“打开文件夹”对话框中，选择“桌面”**** 文件夹，然后选择“选择为父文件夹”****。

    等待工作区创建完毕。

1. 创建工作区后，选择 **Program.cs** 并删除文件内容。

1. 切换到包含 Python 代码的 Visual Studio Code 实例。

1. 滚动到“聊天”视图顶部，然后单击“复制****”按钮，将生成的 C# 代码复制到剪贴板。

1. 切换到包含 C# 代码的 Visual Studio Code 实例。

1. 将 C# 代码粘贴到 Program.cs 文件中。

1. 保存 Program.cs 文件。

1. 运行 C# 应用程序。

    请注意，C# 应用程序的输出实质上与 Python 应用程序的输出相同。

    如果有时间，请花几分钟时间查看转换后的 C# 代码与上一单元中的 C# 代码之间的差异。

## 使用内联聊天在编程语言之间转换代码

1. 切换回包含前面打开的 Python 项目的 Visual Studio Code 实例。

1. 选择 main.py 文件中的代码。

1. 打开内联聊天并输入以下提示：

    ```plaintext
    Convert #selection to C#
    ```

1. 查看 GitHub Copilot 的响应，然后选择“接受”****。

    Python 文件现在应包含 C# 代码。

1. 将生成的 C# 代码复制到剪贴板。

1. 关闭 main.py 文件而不保存更改。

1. 切换到包含 C# 项目的 Visual Studio Code 实例并打开 Program.cs 文件。

1. 若要覆盖现有的 C# 代码，请将剪贴板中的 C# 代码（使用内联聊天从 Python 转换）粘贴到 Program.cs 文件的内容上。

1. 保存 Program.cs 文件。

1. 运行 C# 应用程序。

    请注意，C# 应用程序的输出实质上与 Python 应用程序的输出相同。

使用 GitHub Copilot 在编程语言之间转换代码时，请尝试使用“聊天”视图和内联聊天。 尽管这两个工具共享相同的 AI 模型，但它们的结果可能有所不同。 尝试这两种工具可以帮助你确定哪种工具最适合你的特定用例。

> [!NOTE]
> 编程语言通常具有相关的“编程风格”，并且某些语言可能具有独特的功能或代码库。 将大量代码从一种编程语言转换为另一种编程语言时，必须充分了解目标编程语言以及代码的意图。 在接受之前，必须仔细检查 GitHub Copilot 建议。

### 总结

在本演示中，你已使用 GitHub Copilot 将 Python 代码转换为 C#。 你已使用“聊天”视图和内联聊天将 Python 代码转换为 C#。 然后运行了 C# 应用程序，验证输出是否与 Python 应用程序的输出相同。 通过使用 GitHub Copilot 在各种编程语言之间转换代码，可以快速将代码从一种语言适配到另一种语言。 请记得在转换后审查代码，确保它满足你的要求，并符合目标语言的编程风格。
