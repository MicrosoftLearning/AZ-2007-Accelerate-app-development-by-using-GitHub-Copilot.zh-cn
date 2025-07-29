---
demo:
  title: 演示：使用 GitHub Copilot 对话助手生成代码说明
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手生成代码说明

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

GitHub Copilot Chat 使用对话式 AI 协助和智能命令来帮助完成与编码相关的任务。 例如解释不熟悉和复杂的代码。

可以出于多种原因使用 GitHub Copilot Chat 生成说明。 例如：

- 加入现有项目时，GitHub Copilot Chat 可以解释整个工作区或特定项目文件。
- 当代码复杂或难以理解时，GitHub Copilot Chat 可以解释特定的代码行或部分。
- GitHub Copilot Chat 可以解释代码中的错误，并建议修复错误的方法。
- GitHub Copilot Chat 可以解释如何向项目添加功能，并提供演示如何实现新代码的代码片段。

### 工作区和项目文件说明

GitHub Copilot Chat 可以帮助你了解新项目或特定项目文件。 可以在“聊天”视图或“快速聊天”窗口中使用 `@workspace`、`/explain` 和 `#file` 组合来生成项目或特定项目文件的说明。

请使用以下步骤完成本演示的这一部分：

1. 在 Visual Studio Code 中打开 APL2007M2Sample1 文件夹****。

    1. 在电脑上打开 Visual Studio Code。
    1. 在 Visual Studio Code 中的“文件”菜单上，选择“打开文件夹” 。
    1. 导航到 Windows 桌面文件夹，打开 SampleApps 文件夹，找到 APL2007M2Sample1 文件夹********。
    1. 选择 APL2007M2Sample1，然后选择“选择文件夹”********。

    Visual Studio Code EXPLORER 视图应显示包含以下文件的 APL2007M2Sample1 代码项目：

    - APL2007M2Sample1.csproj
    - APL2007M2Sample1.sln
    - App.xaml
    - App.xaml.cs
    - MainWindow.xaml
    - MainWindow.xaml.cs

1. 在 Visual Studio Code 的顶部菜单栏上，选择“打开聊天”****。

    “打开聊天”按钮位于 Visual Studio Code 窗口顶部的菜单栏上，就在搜索框的右侧。 它将显示一个小的 GitHub Copilot 徽标。

1. 使用以下命令让 Copilot Chat 解释 `APL2007M2Sample1` 项目：

    ```plaintext
    @workspace Explain this project
    ```

1. 花点时间查看“聊天”视图中的回复。

    GitHub Copilot Chat 生成与以下回复类似的 APL2007M2Sample1 项目说明：

    > [!IMPORTANT]
    > GitHub Copilot Chat 使用 AI 模型生成响应。 收到的响应类似于本培训中显示的响应，但它们并不相同。

1. 在“聊天”视图底部，请注意 GitHub Copilot Chat 已建议后续问题。

    收到的响应可能包括其他后续问题。

    GitHub Copilot Chat 将生成聊天对话的历史记录。 该历史记录可帮助 GitHub Copilot Chat 了解你感兴趣的方面。 生成聊天历史记录时，AI 模型会从互动中学习，并提供更多相关的后续问题。 不建议探索“随机”后续问题。

1. 在编辑器中打开 `MainWindow.xaml.cs` 文件。

1. 使用以下命令让 Copilot 解释 `MainWindow.xaml.cs` 文件：

    ```plaintext
    @workspace /explain #file:MainWindow.xaml.cs
    ```

1. 花点时间查看“聊天”视图中的回复。

    请注意，GitHub Copilot Chat 会生成 `MainWindow.xaml.cs` 文件的详细说明。 该说明包含有关文件用途、结构和关键组成部分的信息。 你可能还会看到一个描述潜在问题和改进的部分。

    GitHub Copilot Chat 再次建议后续问题。

    > [!IMPORTANT]
    > GitHub Copilot Chat 会维护聊天对话的历史记录。 当你继续提问时，它会相应地优化其回复。 问题上下文（特别是在代码项目方面）会影响 GitHub Copilot Chat 的后续回复。 这有助于提供更准确且相关性更高的回复。 这也意味着你收到的特定问题的回复可能会因对话历史记录而有所不同。

### 所选代码说明

即使是经验丰富的开发人员也遇到难以理解的代码。 你可以让 GitHub Copilot Chat 提供说明，而不是花时间尝试理解复杂的代码。 “聊天”视图、内联聊天和智能操作都可用于生成所选代码行或节的说明。

在演示的这一部分，需要使用“解释”智能操作生成所选代码行的说明****。

1. 确保已在编辑器中打开 `MainWindow.xaml.cs` 文件。

1. 向下滚动，找到 `SumPageSizesAsync()` 方法。

    ```csharp

    private async Task SumPageSizesAsync()
    {
        var stopwatch = Stopwatch.StartNew();
        IEnumerable<Task<int>> downloadTasksQuery =
            from url in _urlList
            select ProcessUrlAsync(url, _client);
        Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
        int[] lengths = Task.WhenAll(downloadTasks);
        int total = lengths.Sum();
        await Dispatcher.BeginInvoke(() =>
        {
            stopwatch.Stop();
    
            _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
            _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
        });
    }

    ```

1. 选择以下代码行，然后使用“解释”智能操作生成说明****。

    若要选择“解释”智能操作，请右键单击所选代码行，选择“Copilot”，然后从上下文菜单中选择“解释”************。

    ```csharp

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in _urlList
        select ProcessUrlAsync(url, _client);
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

    ```

1. 花点时间查看“聊天”视图中的回复。

1. 请注意说明中包含的详细信息级别。

    GitHub Copilot Chat 生成详细说明，其中包含有关所选代码行、用途及其运行方式的信息。 响应包括代码片段和自然语言说明，可帮助你理解代码。

### 错误说明

管理错误是软件开发的一个重要方面。 某些错误易于发现和修复，而另一些错误可能更具挑战性。 在代码中遇到难以理解的错误时，可以让 GitHub Copilot Chat 提供说明。 例如，可以让 GitHub Copilot Chat 解释为什么特定代码行导致错误。

请使用以下步骤完成本演示的这一部分：

1. 确保已在编辑器中打开 `MainWindow.xaml.cs`。

1. 在 `SumPageSizesAsync()` 方法中，找到以下代码行：

    ```csharp
    int[] lengths = Task.WhenAll(downloadTasks);
    ```

1. 将鼠标光标悬停在 `downloadTasks` 上以显示错误消息。

    错误消息不一定会说明如何解决编码问题。 当没有明显的解决方案时，可以要求 GitHub Copilot Chat 解释错误并提供解决方法方面的建议。

1. 选择包含错误的代码行，然后按 Ctrl+I**** 打开内联聊天。

1. 若要生成错误说明，请输入以下提示：

    ```plaintext
    /explain why is the selection causing an error
    ```

1. 花点时间查看“聊天”视图中的回复。

    请注意，回复包含有关错误的信息以及修复错误的建议。 在本例中，GitHub Copilot Chat 解释称 `Task.WhenAll(downloadTasks)` 行导致了错误，因为它缺少 `await` 关键字。 回复还提供了一个代码片段，演示如何通过在 `Task.WhenAll(downloadTasks)` 行之前添加 `await` 关键字来修复错误。

1. 根据 GitHub Copilot Chat 提供的说明修复代码中的错误。

    在 `Task.WhenAll(downloadTasks)` 行之前添加 `await` 关键字，如以下代码片段所示：

    ```csharp
    int[] lengths = await Task.WhenAll(downloadTasks);
    ```

    进行此更改后，应可以解决该错误。

### 新功能或功能说明

GitHub Copilot Chat 可以解释如何向项目添加新特性或功能。

以 APL2007M2Sample1 项目为例。 代码下载网页并计算已下载页面的总大小。 假设需要向应用程序添加异常处理。 在演示的这一部分，你将使用 GitHub Copilot 对话助手来说明如何在下载过程中管理异常。

请使用以下步骤完成本演示的这一部分：

1. 选择包含 `SumPageSizesAsync` 和 `ProcessUrlAsync` 方法的代码行。

1. 在“聊天”视图中，若要让 GitHub Copilot Chat 解释如何处理下载过程中引发的异常，请输入以下问题：

    ```plaintext
    @workspace /explain #MainWindow.xaml.cs How can I handle exceptions thrown during the download process?
    ```

1. 花点时间查看“聊天”视图中的回复。

    Copilot Chat 生成类似于以下说明的回复：

    回复提供了有关如何处理下载过程中引发的异常的详细说明。 还可以获取实现建议的异常处理代码的代码片段。 可以复制代码片段，或将其插入代码项目中的光标位置。

    下一步不是从“聊天”视图复制或插入代码片段，而是研究使用内联聊天来实现建议的异常处理代码。

1. 若要询问内联聊天如何实现异常处理，请选择 `ProcessUrlAsync` 方法，按 Ctrl+I****，然后输入以下提示：

    ```plaintext
    How can I handle exceptions thrown during the download process?
    ```

1. 花点时间查看内联回复。

1. 若要接受建议的错误处理代码，请选择“接受”****。

    请注意，已实现建议的 `try-catch` 块。

### 总结

在本演示中，你已使用 GitHub Copilot 对话助手生成关于代码行、错误和新功能的说明。 GitHub Copilot Chat 提供了一组强大的功能，可帮助你快速启动新项目。 通过使用内联聊天和“聊天”视图，你可以在不离开 Visual Studio Code 环境的情况下从 GitHub Copilot Chat 获取帮助。 GitHub Copilot Chat 的 AI 模型可生成准确且有用的回复，帮助你成为更迅速、更高效的开发人员。
