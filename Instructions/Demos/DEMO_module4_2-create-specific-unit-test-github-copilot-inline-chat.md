---
demo:
  title: 演示：使用 GitHub Copilot 针对特定条件创建单元测试
  module: 'Module 4: Develop unit tests using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 针对特定条件创建单元测试

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

GitHub Copilot 扩展可帮助你为代码中的特定条件创建单元测试。 例如，可以使用 GitHub Copilot Chat 测试某个方法在收到特定输入时的行为。

在本演示中，你将使用 GitHub Copilot 扩展为特定条件创建单元测试。

### 使用 GitHub Copilot 创建单元测试

你可以使用 GitHub Copilot 自动补全建议创建单元测试。 使用自动补全建议可帮助你快速生成代码的单元测试。

在演示的这一部分，你将使用 GitHub Copilot 为 `PrimeService` 类的 `IsPrime` 方法创建单元测试。

请使用以下步骤完成本演示的这一部分：

1. 在 Visual Studio Code 中打开 APL2007M4PrimeService-UnitTests 项目文件夹****。

1. 在编辑器中打开 PrimeServiceTests.cs 文件。

1. 删除 `PrimeServiceTests` 类中的所有代码。

    PrimeServiceTests.cs 文件的内容应类似于以下代码片段：

    ```csharp

    namespace System.Numbers.UnitTests;
    public class PrimeServiceTests
    {
    }

    ```

1. 保存 PrimeServiceTests.cs 文件，然后重新生成解决方案。

1. 若要让 GitHub Copilot 生成内联补全，请在 `PrimeServiceTests` 类中创建一个空白行。

    如果等待一两秒，GitHub Copilot 会建议 `PrimeServiceTests` 类的补全内容。

1. 选择“接受”，然后花点时间查看 GitHub Copilot 生成的单元测试。****

1. 花点时间查看 GitHub Copilot 为 `IsPrime` 方法生成的单元测试集合。

    本演示的下一部分将介绍如何使用 GitHub Copilot 对话助手来要求 GitHub Copilot 建议应测试的其他边缘案例。

    ```csharp

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
            public void IsPrime_ReturnsFalse_ForNegativeNumbers()
            {
                // Arrange
                int candidate = -5;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForZero()
            {
                // Arrange
                int candidate = 0;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsFalse_ForOne()
            {
                // Arrange
                int candidate = 1;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.False(result);
            }
            [Fact]
            public void IsPrime_ReturnsTrue_ForPrimeNumbers()
            {
                // Arrange
                int candidate = 7;
                // Act
                bool result = _primeService.IsPrime(candidate);
                // Assert
                Assert.True(result);
            }
        }
    }

    ```

### 使用 GitHub Copilot 和 GitHub Copilot Chat 为特定条件创建单元测试

1. 选择 `PrimeServiceTests` 类的内容。

1. 打开“聊天”视图。

1. 若要将 PrimeService.cs 文件添加到“聊天”视图上下文，请将 PrimeService.cs 文件从资源管理器视图拖放到“聊天”视图中。

1. 在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace #selection are there any edge cases that should also be tested 
    ```

1. 花点时间查看 GitHub Copilot 提供的建议。

    ```plaintext
    Yes, there are a few edge cases that should also be tested:
    
    1. Large Prime Numbers: Ensure the function can handle large prime numbers.

    2. Large Non-Prime Numbers: Ensure the function can handle large non-prime numbers.

    3. Even Numbers Greater Than 2: Ensure the function returns false for even numbers greater than 2.

    4. Small Prime Numbers: Ensure the function correctly identifies small prime numbers like 2 and 3.

    Here are the additional test cases:
    ```

    ```csharp

    [Fact]
    public void IsPrime_ReturnsTrue_ForTwo()
    {
        // Arrange
        int candidate = 2;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForThree()
    {
        // Arrange
        int candidate = 3;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForEvenNumbersGreaterThanTwo()
    {
        // Arrange
        int candidate = 4;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }
    [Fact]
    public void IsPrime_ReturnsTrue_ForLargePrimeNumber()
    {
        // Arrange
        int candidate = 7919;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.True(result);
    }
    [Fact]
    public void IsPrime_ReturnsFalse_ForLargeNonPrimeNumber()
    {
        // Arrange
        int candidate = 8000;
        // Act
        bool result = _primeService.IsPrime(candidate);
        // Assert
        Assert.False(result);
    }

    ```

1. 在 `PrimeServiceTests` 类的最后一个测试方法之后创建一个空行。

1. 在聊天视图中，将鼠标悬停在代码片段上，然后选择“在光标处插入”****。

1. 保存 PrimeServiceTests.cs 文件，然后重新生成解决方案。

1. 花点时间查看 GitHub Copilot 为 `IsPrime` 方法生成的单元测试集合。

    与往常一样，请务必查看 GitHub Copilot 补全的工作，以确保测试有效并且涵盖你想要测试的边缘情况。 对测试感到满意后，可以运行测试来验证其是否通过。

1. 将鼠标指针悬停在绿色“测试箭头”之一上。

    请注意工具提示消息，告知你可以单击以运行测试，或右键单击以查看更多选项。

1. 右键单击其中一个绿色的“测试箭头”。

1. 选择“在测试资源管理器中显示”****。

    请注意，“测试资源管理器”视图随即打开。 测试资源管理器视图可用于运行和调试测试，以及查看测试运行的结果。 若要手动打开“测试资源管理器”视图，请从 Visual Studio Code 窗口左侧的活动栏中选择“测试”****。 “测试”视图的图标看起来像一个实验室烧瓶****。

1. 在“测试资源管理器”视图顶部，选择“运行测试”****。

    几秒钟后，测试资源管理器会显示测试运行的结果。 你应看到所有测试全都通过了。 测试资源管理器和编辑器中单元测试左侧的绿色复选标记指示测试已通过。

### 总结

在本演示中，你使用 GitHub Copilot 和 GitHub Copilot 对话助手针对 `PrimeService` 类中的特定条件创建了单元测试。 你使用了代码行补全来生成断言，以确保函数输入参数有效，并且你使用了聊天视图来要求 GitHub Copilot 建议应测试的其他边缘情况。 你查看了 GitHub Copilot 提供的建议并运行了测试以验证其是否通过。 你还了解了如何使用 Visual Studio Code 中的测试资源管理器来运行和查看测试运行的结果。
