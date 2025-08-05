---
demo:
  title: 演示：使用 GitHub Copilot 对话助手创建单元测试
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手创建单元测试

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

Visual Studio Code 和 C# 开发工具包提供了一组丰富的功能，可帮助你创建和管理 C# 项目的单元测试。 可以使用 C# 开发工具包为项目启用测试、添加测试框架包、运行和管理单元测试以及生成单元测试用例。

GitHub Copilot 可以通过提供内联聊天建议来帮助生成代码的单元测试。

在本演示中，你将在 Visual Studio Code 中使用 GitHub Copilot 对话助手为一个代码项目创建单元测试。

### 为单元测试创建 xUnit 测试项目

单元测试项目通常在与你要测试的项目分开的文件夹中创建。 这种分离有助于使测试代码与生产代码分开。 在本演示中，你将为 APL2007M4PrimeService 项目创建 xUnit 测试项目。

若要创建新的 xUni 测试项目，请完成以下步骤：

1. 在 Visual Studio Code 中打开 APL2007M4PrimeService 文件夹。****

1. 在 Visual Studio Code 中打开“解决方案资源管理器”视图。

    可从 Visual Studio Code 的侧栏面板中访问“解决方案资源管理器”视图。 “解决方案资源管理器”视图类似于“资源管理器”视图，但它专门用于处理 Visual Studio Code 项目，而不是常规文件系统。

1. 在“解决方案资源管理器”视图中，右键单击 APL2007M4PrimeService，然后选择“新建项目”********。

    如果未看到“新建项目”选项，请确保使用的是“解决方案资源管理器”视图，而不是“资源管理器”******** 视图。

1. 当项目类型列表出现时，选择“xUnit 测试项目”。****

1. 对于项目名称，请键入“PrimeService.UnitTests”****，然后按 Enter。

    项目名称应当反映要测试的类的名称，并且在解决方案中应当是唯一的。 在本例中，该类名为 `PrimeService`，因此测试项目名为 `PrimeService.UnitTests`。

1. 选择默认目录位置。

    还可以使用 Visual Studio Code 终端创建 xUnit 测试项目。 打开终端，导航到 Numbers 文件夹，然后运行以下命令：

    ```plaintext
    dotnet new xunit -n PrimeService.UnitTests
    ```

1. 选择“创建项目”****，然后展开 PrimeService.UnitTests 文件夹。

1. 删除随 PrimeService.UnitTests 项目创建的 UnitTest1.cs 文件。

    在创建新的单元测试之前，你需要添加对指向要测试的类项目的单元测试项目的引用。

1. 若要添加对代码项目的引用，请右键单击 PrimeService.UnitTests，选择“添加项目引用”，然后选择“Numbers”。************

1. 要为单元测试创建一个类，请右键单击“PrimeService.UnitTests”，依次选择“新文件”和“类”，键入“PrimeServiceTests”，然后按 Enter。****************

    Visual Studio Code 应为你打开 PrimeServiceTests.cs 文件。

1. 请花点时间查看 PrimeServiceTests.cs 文件。

    该文件应与以下代码片段相似：

    ```csharp

    namespace PrimeService.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. 为了在构建项目时避免出现命名空间问题，请按如下方式更新 PrimeServiceTests.cs 文件：

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

    C# 格式的命名空间用于组织相关的类和类型。 这是一种避免名称冲突并使代码组织方式更易于理解的方法。 测试项目的命名空间中的 `.UnitTests` 后缀是一种常见约定，指示此命名空间中的代码测试的是 System.Numbers 命名空间中的代码。 这样便可以在查看项目结构时可以清楚地看到哪些代码是生产代码，哪些代码是测试代码。

1. 请花些时间检查 PrimeService.UnitTests.csproj 文件。

    PrimeService.UnitTests.csproj 文件应该包括一个 `<ItemGroup>`，其中包含以下 `<PackageReference />` 元素：

    ```xml

    <PackageReference Include="coverlet.collector" Version="6.0.0" />
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
    <PackageReference Include="xunit" Version="2.5.3" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />

    ```

    若要使用 xUnit 作为测试库并配置测试运行程序，这些包引用是必需的。 在 PrimeService.UnitTests.csproj 文件中，应该还会看到以下 `<ItemGroup>` 元素：

    ```xml

    <ItemGroup>
        <Using Include="Xunit" />
    </ItemGroup>
    <ItemGroup>
        <ProjectReference Include="..\Numbers\Numbers.csproj" />
    </ItemGroup>

    ```

    若要引用 Numbers 项目并使用 xUnit 测试框架，这些元素是必需的。

1. 要生成解决方案，请按 Ctrl+Shift+B，然后选择“dotnet: build”。********

    还可以使用 .NET CLI 命令 (dotnet build) 或右键单击“解决方案资源管理器”视图中的解决方案节点并选择“生成”来生成解决方案。****

    > [!NOTE]
    > 如果看到任何生成错误****，请先更正错误，然后再继续演示。 你必须成功生成，然后才能继续操作。

现在，你已准备好使用 GitHub Copilot Chat 创建单元测试。

### 使用聊天视图创建单元测试

GitHub Copilot 和 GitHub Copilot Chat 可基于代码库的上下文提供建议，从而帮助你为代码生成单元测试。 可以使用 GitHub Copilot Chat 为代码中的特定方法或类生成单元测试。

请使用以下步骤完成本演示的这一部分：

1. 在“解决方案资源管理器”视图中的“数字”下，打开 PrimeService.cs 文件。

1. 选择“IsPrime”方法。****

1. 打开“聊天”视图。

1. 选择“附加上下文”按钮。****

    “附加上下文”按钮（回形针图标）用于通知 GitHub Copilot 代码库中的相关上下文。**** 额外的上下文可帮助 GitHub Copilot 聊天提供更准确的建议。 在这种情况下，你在提议单元测试时希望 GitHub Copilot 使用 PrimeServiceTests.cs 文件。

1. **** 在“搜索附件”下拉列表的“最近打开”部分中，选择“PrimeServiceTests.cs”********。

    “搜索附件”下拉列表提供了一些可供选择的默认选项。**** 它还包括最近打开的文件的列表。 PrimeServiceTests.cs 文件应列在最近打开的部分中。

    “搜索附件”选项包括

1. 再次选择“附加上下文”按钮。****

1. 在“搜索附件”文本框中，键入“PrimeService.Unit”，然后选择“PrimeService.UnitTests.csproj”。********

    > [!NOTE]
    > 演示如何从资源管理器视图中拖动文件并将其放置到“聊天”视图中。 在许多情况下，这是附加上下文的更快方法。

1. 请注意，“聊天”视图可使用其他上下文进行更新。

1. 在“聊天”视图中，选择“/tests 为我的代码添加单元测试”。****

    “/tests 为我的代码添加添加单元测试”选项用于为你在编辑器中选择的代码生成单元测试。**** 在本例中，你在 PrimeService.cs 文件中选择了 IsPrime 方法。****

1. 请花点时间查看 GitHub Copilot 的建议。

    GitHub Copilot 的建议包括两个部分：“计划”以及包含单元测试的代码示例。

    该计划建议为单元测试创建新的 PrimeServiceTest.cs 文件。 它还建议在“数字”项目文件夹中创建该文件。

1. 在“聊天”视图中，选择“应用编辑”。****

1. 请注意，“应用编辑”按钮将单元测试代码放在编辑器中的新选项卡上。

    可以使用此代码更新 PrimeService.UnitTests 项目中的 PrimeServiceTests.cs 文件。

1. 在“文件”菜单上，选择“另存为”，然后导航到 PrimeService.UnitTests 文件夹。********

1. 选择“PrimeServiceTests.cs”，然后选择“保存”。********

1. 当系统提示覆盖现有文件时，请选择“是”。****

1. 花点时间查看更新后的 PrimeServiceTests.cs 文件。

    GitHub Copilot 聊天建议的代码应包括面向特定质数和非质数的测试。 建议的代码可能包括参数化测试（使用 `[Theory]` 和 `[InlineData]` 属性），以便通过更简洁的方式测试多个数据集。

    提供的代码片段应该类似于以下代码片段：

    ```csharp

    using Xunit;
    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

    请注意，单元测试需要 PrimeService 类的实例。

    ```csharp

    private readonly PrimeService _primeService;
    public PrimeServiceTests()
    {
        _primeService = new PrimeService();
    }

    ```

1. 重新生成解决方案。

    如果生成成功，应会在每个单元测试旁边看到绿色的“测试箭头”。

    你会在下一部分创建更多单元测试，因此目前无需运行测试。

    但是，有多种方法可以运行测试。 例如：

    - 可以从 Visual Studio Code 终端中使用 `dotnet test` 命令运行测试。
    - 可以从 Visual Studio Code 测试资源管理器视图运行测试。
    - 可以从 Visual Studio Code 命令面板使用“Test:**** Run All Tests”命令来运行测试。
    - 可以在 Visual Studio Code 编辑器中通过从上下文菜单中选择“在当前文件中运行测试”选项来运行测试。****

    在本演示的这一部分创建的测试应能够成功运行。 单元测试旁边的绿色“测试箭头”将变为带有复选标记的绿色圆圈。

### 使用内联聊天创建单元测试

请使用以下步骤完成本演示的这一部分：

1. 在“解决方案资源管理器”视图中，打开 PrimeService.cs 文件。

    PrimeService.cs 位于 Numbers 文件夹中。

1. 选择 IsPrime 方法。

1. 打开一个内联聊天会话，然后输入以下提示：

    ```plaintext
    Create unit tests for the IsPrime method using the xUnit framework.
    ```

1. 花点时间查看内联聊天提供的建议。

    ```csharp

    using Xunit;
    namespace System.Numbers.UnitTests
    {
        public class PrimeServiceTests
        {
            private readonly PrimeService _primeService;
            public PrimeServiceTests()
            {
                _primeService = new PrimeService();
            }
            [Fact]
            public void IsPrime_InputIs1_ReturnsFalse()
            {
                var result = _primeService.IsPrime(1);
                Assert.False(result, "1 should not be prime");
            }
            [Fact]
            public void IsPrime_InputIs2_ReturnsTrue()
            {
                var result = _primeService.IsPrime(2);
                Assert.True(result, "2 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs3_ReturnsTrue()
            {
                var result = _primeService.IsPrime(3);
                Assert.True(result, "3 should be prime");
            }
            [Fact]
            public void IsPrime_InputIs4_ReturnsFalse()
            {
                var result = _primeService.IsPrime(4);
                Assert.False(result, "4 should not be prime");
            }
            [Theory]
            [InlineData(5, true)]
            [InlineData(6, false)]
            [InlineData(7, true)]
            [InlineData(8, false)]
            [InlineData(9, false)]
            [InlineData(10, false)]
            public void IsPrime_Values_ReturnExpectedResult(int value, bool expected)
            {
                var result = _primeService.IsPrime(value);
                Assert.Equal(expected, result);
            }
        }
    }

    ```

1. 请注意，“聊天”视图和内联聊天会产生相似的测试覆盖率。

1. 要放弃内联聊天建议，请选择“放弃”，然后关闭内联聊天创建的文件选项卡。****

    请注意，在本次演示中 GitHub Copilot 所建议的单元测试可能并不完整。 接下来的演示将探讨你可能需要测试的其他边缘案例。

### 总结

在本演示中，你在 Visual Studio Code 中使用 GitHub Copilot 对话助手为一个代码项目创建了单元测试。 你创建了一个 xUnit 测试项目，添加了对要测试的项目的引用，并为 `PrimeService` 类中的 `IsPrime` 方法生成了单元测试。 你使用 GitHub Copilot Chat 在“聊天”视图和内联聊天中生成了单元测试。
