---
demo:
  title: 演示：使用 GitHub Copilot 对话助手生成内联代码文档
  module: 'Module 2: Generate documentation using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手生成内联代码文档

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

生成代码文档是软件开发过程的一个重要方面。 内联文档（代码注释）可以帮助开发人员理解代码库、其目的以及使用方法。

GitHub Copilot Chat 可帮助你快速准确地记录代码。 有几个选项可用于使用 GitHub Copilot Chat 生成内联文档：

- 自行构建可用于生成特定文档的自然语言提示。
- 在内联聊天会话期间使用 `/doc` 命令为所选代码生成注释。
- 使用“生成文档”智能操作为所选代码生成注释。****

正确记录代码可创建更具可读性和可维护性的代码库，让其他开发人员更容易理解和使用。

### 使用“聊天”视图生成内联代码文档

在本演示中，你将使用 GitHub Copilot 对话助手为 `APL2007M2Sample1` 项目生成内联代码文档。

请使用以下步骤完成本演示的这一部分：

1. 确保在 Visual Studio Code 中打开了 `APL2007M2Sample1` 项目。

1. 打开 `MainWindow.xaml.cs` 文件。

1. 选择从命名空间声明开始到文件结尾的所有代码。

1. 打开“聊天”视图。

1. 若要查看 GitHub Copilot Chat 如何记录所选代码，请输入以下提示：

    ```output
    @workspace #selection generate inline code documentation for the selected code
    ```

1. 花一分钟时间查看建议的代码文档。

    生成的响应应类似于以下代码示例：

    ```csharp

    namespace ParallelAsyncExample
    {
        public partial class MainWindow : Window
        {
            // HttpClient instance with a maximum response content buffer size of 1,000,000 bytes
            private readonly HttpClient _client = new HttpClient { MaxResponseContentBufferSize = 1_000_000 };
            // List of URLs to download content from
            private readonly IEnumerable<string> _urlList = new string[]
            {
                "https://docs.microsoft.com",
                "https://docs.microsoft.com/azure",
                "https://docs.microsoft.com/powershell",
                "https://docs.microsoft.com/dotnet",
                "https://docs.microsoft.com/aspnet/core",
                "https://docs.microsoft.com/windows",
                "https://docs.microsoft.com/office",
                "https://docs.microsoft.com/enterprise-mobility-security",
                "https://docs.microsoft.com/visualstudio",
                "https://docs.microsoft.com/microsoft-365",
                "https://docs.microsoft.com/sql",
                "https://docs.microsoft.com/dynamics365",
                "https://docs.microsoft.com/surface",
                "https://docs.microsoft.com/xamarin",
                "https://docs.microsoft.com/azure/devops",
                "https://docs.microsoft.com/system-center",
                "https://docs.microsoft.com/graph",
                "https://docs.microsoft.com/education",
                "https://docs.microsoft.com/gaming"
            };
            // Event handler for the start button click event
            private void OnStartButtonClick(object sender, RoutedEventArgs e)
            {
                // Disable the start button and clear the results text box
                _startButton.IsEnabled = false;
                _resultsTextBox.Clear();
                // Start the asynchronous operation to sum page sizes
                Task.Run(() => StartSumPageSizesAsync());
            }
            // Starts the asynchronous operation to sum page sizes
            private async Task StartSumPageSizesAsync()
            {
                // Perform the main download operation
                await SumPageSizesAsync();
                // Update the UI to re-enable the start button and indicate that control has returned
                await Dispatcher.BeginInvoke(() =>
                {
                    _resultsTextBox.Text += $"\nControl returned to {nameof(OnStartButtonClick)}.";
                    _startButton.IsEnabled = true;
                });
            }
            // Asynchronously sums the sizes of the pages from the URLs
            private async Task SumPageSizesAsync()
            {
                // Start a stopwatch to measure elapsed time
                var stopwatch = Stopwatch.StartNew();
                // Create tasks to download content from each URL
                IEnumerable<Task<int>> downloadTasksQuery =
                    from url in _urlList
                    select ProcessUrlAsync(url, _client);
                // Convert the sequence of tasks into an array
                Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
                // Wait for all tasks to complete and sum the lengths of the downloaded content
                int[] lengths = await Task.WhenAll(downloadTasks);
                int total = lengths.Sum();
                // Update the UI with the total bytes and elapsed time
                await Dispatcher.BeginInvoke(() =>
                {
                    stopwatch.Stop();
                    _resultsTextBox.Text += $"\nTotal bytes returned:  {total:#,#}";
                    _resultsTextBox.Text += $"\nElapsed time:          {stopwatch.Elapsed}\n";
                });
            }
            // Asynchronously processes a URL by downloading its content and returning the length of the content
            private async Task<int> ProcessUrlAsync(string url, HttpClient client)
            {
                try
                {
                    // Download the content of the URL
                    byte[] byteArray = await client.GetByteArrayAsync(url);
                    // Update the UI with the URL and content length
                    await DisplayResultsAsync(url, byteArray);
                    // Return the length of the downloaded content
                    return byteArray.Length;
                }
                catch (HttpRequestException e)
                {
                    // Handle HTTP request exceptions by updating the UI with an error message
                    await Dispatcher.BeginInvoke(() =>
                    {
                        _resultsTextBox.Text += $"{url,-60} {"Error",-10}\n";
                        _resultsTextBox.Text += $"Exception: {e.Message}\n";
                    });
                    // Return 0 to indicate failure
                    return 0;
                }
            }
            // Updates the UI with the URL and the length of the downloaded content
            private Task DisplayResultsAsync(string url, byte[] content) =>
                Dispatcher.BeginInvoke(() =>
                    _resultsTextBox.Text += $"{url,-60} {content.Length,10:#,#}\n")
                          .Task;
            // Disposes of the HttpClient instance when the window is closed to free up resources
            protected override void OnClosed(EventArgs e) => _client.Dispose();
        }
    }

    ```

    响应包括建议的代码注释和一部分相关代码**。 为了简洁起见，可能会省略某些代码。 可以手动将代码注释移动到实际代码文件中。

    内联聊天提供了向代码添加注释的更直接的方法。

### 使用内联聊天生成内联代码文档

1. 滚动到 `MainWindow.xaml.cs` 文件的顶部。

1. 选择 `OnStartButtonClick` 方法。

1. 若要打开内联聊天，请按 Ctrl+I****。

1. 若要为 `OnStartButtonClick` 方法生成内联文档，请输入以下提示：

    ```output
    /doc
    ```

1. 花一分钟时间查看生成的代码文档。

    请注意，`OnStartButtonClick` 方法的建议文档包括两个参数的摘要和说明。 当方法包含返回值时，也会包含返回值的说明。

    > [!IMPORTANT]
    > 在接受之前，请始终查看 GitHub Copilot 建议的更新。 如果发现建议的代码更新中存在问题，可以放弃该更新，或者在接受建议的代码更新之前尝试纠正该问题。

1. 若要放弃建议的更新，请选择“放弃”****。

    在下一部分中，将一次性为所有方法生成文档。

### 使用“生成文档”智能操作生成内联代码文档****

“生成文档”智能操作是生成内联代码文档的另一种方法。**** 你可以使用此智能操作生成描述所选代码的注释。

请使用以下步骤完成本演示的这一部分：

1. 在 Visual Studio Code 编辑器中，选择 `MainWindow` 类中的所有方法**。

1. 右键单击所选代码，选择“Copilot”，然后选择“生成文档”********。

    等待文档生成。

1. 查看建议的更改。

    > [!IMPORTANT]
    > 如果在生成的文档中发现问题，请先修改建议的更改，然后再继续操作。

1. 选择“接受”。

    `MainWindow` 类中的每个方法现在都包含生成的注释。

### 总结

在本演示中，你使用 GitHub Copilot 对话助手为 `APL2007M2Sample1` 应用生成了内联代码文档。 你已了解如何使用“聊天”视图、内联聊天和“生成文档”智能操作生成内联代码文档****。 通过生成代码注释，可以创建更具可读性和可维护性的代码库，让其他开发人员更容易理解和使用。 内联代码文档是软件开发的重要组成部分，可帮助开发人员了解代码库、其目的以及使用方法。
