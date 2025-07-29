---
demo:
  title: 演示：使用 GitHub Copilot 对话助手提高代码可靠性和性能
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手提高代码可靠性和性能

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

代码可靠性和性能与软件质量密切相关。 它们在以下方面相互依赖：

- 一方面的改进会对另一方面产生积极影响。
- 一方面的缺陷会导致另一方面出现问题。

> [!IMPORTANT]
> 向学员说明，本演示不是讲解有关开发可靠或高性能代码的最佳做法。 而是重点介绍如何使用 GitHub Copilot Chat 来生成建议，以便改进示例应用程序中的代码可靠性和性能。 这些建议并不代表代码可靠性和性能的最佳做法或综合性的解决方案。 开发人员应利用自身的判断和专业知识来评估和实施 GitHub Copilot Chat 提供的建议。 实施 GitHub Copilot 提出的建议并不能取代全面代码评审和测试的需要。

#### 代码可靠性和性能

开发人员应努力在代码可靠性和性能之间实现平衡。 成功的平衡会产生以下互利的结果：

- 满足功能要求的应用程序。
- 提供无缝高效用户体验的应用程序。

以下各节概述了代码可靠性和性能，以及学员应了解的其他因素。

##### 检查代码可靠性

代码可靠性是指软件在特定条件下和某个时间段内正常运行的可能性。 提高代码可靠性有助于确保软件按预期执行并满足用户要求。

开发人员可以在改进代码可靠性时考虑以下因素：

- 潜在问题：识别代码中的潜在问题有助于防止出现 bug 和错误。 确定潜在问题应包括检查代码中的常见缺陷并主动解决这些问题。
- 测试：在发布产品之前，充分测试对于识别和修复 bug 至关重要。 充分的测试应包括单元测试、集成测试、系统测试和验收测试。
- 异常处理：当出现意外情况时，适当的异常处理机制可以防止系统失败。

> [!NOTE]
> 在开始处理代码可靠性之前，请确保高质量代码。 代码重构以及标准和准则有助于确保高质量代码。

还有其他因素会影响代码可靠性。 其中一些因素不是开发人员的责任，而其他因素应在代码可靠性之前或之后考虑。 这些其他因素包括：

- 开发做法：遵循软件开发中的最佳做法（如代码评审、结对编程和遵守编码标准）有助于生成更可靠的代码。
- 可靠性目标和指标：设置明确的可靠性目标并制定指标来衡量目标，可以指导开发过程创建更可靠的软件。
- 文档：全面的文档有助于了解系统及其组件，这对于维护系统并对其进行故障排除至关重要。
- 依赖项：代码依赖的外部库和服务可能会影响其可靠性。 如果第三方服务失败，则可能也会导致依赖系统失败。
- 性能：性能问题还会影响可靠性。 确保系统在不同负载下运行良好非常重要。
- 监视和故障排除：持续监视和可靠的故障排除指南可以通过快速识别和解决问题来帮助维护服务的可靠性。
- 设计和体系结构：具有坚实体系结构的设计良好的系统可以妥善处理错误，即使某些组件发生故障，也能保持功能。
- 外部因素：外部因素（如硬件和操作系统更新）可能会导致发布后可靠性问题，从而引发兼容性问题或系统故障。

提高代码可靠性有助于降低出现 bug、错误和意外行为的可能性。

##### 检查代码性能

代码性能是指程序或应用程序的运行效率，特别是在速度、内存使用和总体资源消耗方面的效率。 若要确保或改进代码性能，开发人员可以执行以下操作：

开发人员应在改进代码性能时考虑以下因素：

- 优化算法：为手头的任务选择最有效的算法和数据结构。 即使是较小的改进，也会对性能产生重要的影响。
- 避免不必要的计算：尽可能缓存成本高昂的操作的结果，并避免冗余计算。
- 使用多线程和异步编程：通过并行任务和异步执行 I/O 操作来利用现代 CPU 体系结构。
- 最大程度地减少 I/O 操作：磁盘和网络 I/O 可能很慢，因此，请务必最大程度地减少这些操作或异步执行它们以避免阻止主执行线程。

> [!NOTE]
> 在开始处理代码性能之前，请确保高质量代码。 代码重构以及标准和准则有助于确保高质量代码。

还有其他因素会影响代码性能。 其中一些因素不是开发人员的责任，而其他因素应在处理代码性能之前或之后考虑。 这些其他因素包括：

- 配置文件和基准：使用分析工具确定性能瓶颈。 在进行更改之前和之后进行基准测试可以量化优化的影响。
- 有效管理内存：使用内存分析工具检测泄漏，并确保正确分配和解除分配内存。
- 优化数据库交互：使用高效的查询、适当的编制索引和数据库缓存来最大程度地减少数据库交互的性能开销。
- 代码评审：定期检查代码是否存在性能问题。 同级评审可以帮助发现原始开发人员可能错过的低效问题。
- 保持更新：使用最新版本的语言、库和框架，因为它们通常包括性能改进。
- 教育与协作：随时了解性能优化最佳做法，并与其他开发人员协作，以借鉴其经验。

当开发人员专注于这些方面时，他们可以显著提高其代码的性能，从而实现响应速度更快、更灵敏的应用程序。 性能优化是一个持续的过程，务必持续监视和改进应用程序的性能。

GitHub Copilot Chat 通过提供优化算法、减少不必要的计算、使用多线程和异步编程以及最大程度地减少 I/O 操作方面的建议，可帮助提高代码性能。

### 为 GitHub Copilot Chat 开发提示

为 GitHub Copilot Chat 编写的提示应提供明确定义的上下文和意向。 在开发提示时请考虑以下建议：

- 定义一个范围级别比要更新的代码更高的外部上下文。 例如，如果你要改进某个方法，请将包含该方法的类或文件指定为外部上下文。 将方法标识为内部上下文。
- 使用聊天参与者和聊天变量来帮助指定上下文。 可以使用 `#file:` 和 `#selection` 聊天变量来标识关注的特定代码。 在适当的情况下还可以包含完整的工作区 (`@workspace`)。 请参考提示的自然语言部分中的文件或代码选择。
- 意向应清晰、简洁且具体。 提示应指定你想要实现的改进类型。

在本演示的这一部分，你将查看 APL2007M5BankAccount-Reliability 项目，并为 GitHub Copilot 对话助手创建三个提示****。 提示侧重于提高代码可靠性和性能。

请按照以下步骤完成本演示的这一部分：

1. 在 Visual Studio Code 中打开“APL2007M5BankAccount-Reliability”示例应用****。

1. 打开“解决方案资源管理器”视图。

1. 展开 BankAccount**** 项目，然后查看 BankAccount.cs**** 和 Program.cs**** 代码文件。

    BankAccount.cs**** 文件包含 `BankAccount` 类的代码，该代码表示具有 AccountNumber、Balance、AccountHolderName、AccountType 和 DateOpened 等属性的银行帐户。 其中包含以下方法：

    - Credit(double amount)：此方法按指定金额增加帐户余额。
    - Debit(double amount)：此方法按指定金额减少帐户余额。 如果余额小于指定金额，则会引发异常，并显示消息“借记余额不足”。
    - GetBalance()：此方法返回帐户的当前余额。
    - Transfer(BankAccount toAccount, double amount)：此方法将指定金额从当前帐户转移到 toAccount。 如果余额小于指定金额，则会引发异常，并显示消息“转账余额不足”。 如果 AccountHolderName 不同且金额超过 500，则会引发异常，并显示消息“转账金额超出不同帐户所有者的最大限制”。
    - PrintStatement()：此方法将 AccountNumber 和 Balance 打印到控制台。
    - CalculateInterest(double interestRate)：此方法使用指定的 interestRate 计算当前余额的利息。

    Program.cs**** 文件包含模拟银行系统的控制台应用程序。 其中包括以下方法：

    - Main 方法：应用程序的入口点。 它创建银行帐户列表，并模拟这些帐户的交易和转账。
    - CreateBankAccounts 方法：此方法创建指定数量的银行帐户，其中包含随机初始余额、帐户持有人名称、帐户类型和开户日期。 它使用 try-catch 块来处理在创建帐户期间可能发生的任何异常。
    - SimulateTransactions 方法：此方法模拟提供列表中每个帐户指定数量的交易。 每笔交易都是随机的美元金额，可以是贷项（存款）也可以是借记（取款），具体取决于金额是正数还是负数。
    - SimulateTransfers 方法：此方法与 SimulateTransactions 相同。 它似乎旨在模拟帐户之间的传输，但目前，它只是复制 SimulateTransactions 的功能。
    - GenerateRandomDollarAmount 方法：此方法在指定范围内生成随机美元金额。 范围和计算方法因金额是帐户余额还是交易而异
    - GenerateRandomAccountHolder 方法：此方法从预定义列表中选择随机帐户持有人名称。
    - GenerateRandomAccountType 方法：此方法从预定义列表中选择随机帐户类型。
    - GenerateRandomDateOpened 方法：此方法在帐户开户日期的指定范围内生成一个随机日期。

1. 花一点时间说明有助于提高代码可靠性和性能的提示。

    为 BankAccount 类和 Program 类开发提示。 开发提示时，请考虑以下可靠性和性能因素：

    - 潜在问题：识别代码中的潜在问题有助于防止出现 bug 和错误。 其中包括检查代码中的常见缺陷并主动解决这些问题。
    - 测试：在发布产品之前，充分测试对于识别和修复 bug 至关重要。 其中包括单元测试、集成测试、系统测试和验收测试。
    - 异常处理：当出现意外情况时，适当的异常处理机制可以防止系统失败。

    - 优化算法：为手头的任务选择最有效的算法和数据结构。 即使是较小的改进，也会对性能产生重要的影响。
    - 避免不必要的计算：尽可能缓存成本高昂的操作的结果，并避免冗余计算。
    - 使用多线程和异步编程：通过并行任务和异步执行 I/O 操作来利用现代 CPU 体系结构。
    - 最大程度地减少 I/O 操作：磁盘和网络 I/O 可能很慢，因此，请务必最大程度地减少这些操作或异步执行它们以避免阻止主执行线程。

    对于此项目，可以使用以下提示生成提高代码可靠性的建议：

    提示：`@workspace /explain How can I improve exception handling the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I reduce unexpected issues for the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve unit test support for the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I avoid future bugs or issues in the [selected code]?`（将 Program.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve exception handling for the [selected code]?`（将 Program.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve the efficiency of algorithms or data structures for the [selected code]?`（将 Program.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve performance with asynchronous tasks or methods in the [selected code]?`（将 Program.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve unit test support for the [selected code]?`（将 BankAccountTests.cs 和 BankAccount.cs 附加到聊天上下文）

1. 在此演示中，选择两个可用于改进 BankAccount 类的提示。

    对于 BankAccount 类，请尝试选择专注于可靠性的提示。

1. 在此演示中，选择两个可用于改进 Program 类的提示。

    对于 Program 类，请尝试选择一个侧重于可靠性的提示和一个侧重于性能的提示。

### 使用 GitHub Copilot Chat 提高 BankAccount 类的代码可靠性

确保生产代码的可靠性对任何软件项目都至关重要。 APL2007M5BankAccount-Reliability 示例应用使用 Program 类来模拟银行方案，但它是部署到生产环境的 BankAccount 类。 提高 BankAccount 类的可靠性有助于确保它按预期执行并满足用户要求。

可以使用 GitHub Copilot Chat 来帮助提高代码的可靠性。 提示可以指导 GitHub Copilot 生成改进异常处理、减少意外问题以及改进单元测试支持的建议。 还可以创建范围广泛的提示，以征求提高代码可靠性的一般建议。 具体提示和一般提示的组合可帮助你识别需要改进的方面并实施所需的更改。

> [!NOTE]
> 实施和测试建议的更新需要时间，因此时间可能是本演示的一个因素。 选择注重于特定改进方面的提示可帮助你控制好时间。 过于宽泛的提示可能会生成大量的建议或复杂的建议，而这些建议很难在短时间内评估和实施。 开始后，如果你发现建议的更新范围太广或太复杂，可以使用更具体的详细信息来更新提示。

请按照以下步骤完成本演示的这一部分：

1. 确保项目能够正确无误地生成和运行。

    只要应用程序能够运行，警告就是可以接受的，但在开始使用 GitHub Copilot Chat 之前必须解决导致应用程序故障的未处理错误。

1. 在 Visual Studio Code 中打开 BankAccount.cs 文件，然后选择文件中的所有代码。

1. 打开“聊天”视图。

1. 在“聊天”视图中，将相关文件添加到聊天上下文，然后输入提示。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 打开 BankAccount.cs 文件并选择所有代码。
    - 选择以下提示：`@workspace /explain How can I improve exception handling in the BankAccount.cs file?`
    - 打开“聊天”视图并将 BankAccount.cs 和 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    GitHub Copilot Chat 会建议类似于以下响应的更新：

    若要改进 BankAccount.cs 文件中的异常处理，请考虑以下建议：**

    *1.使用具体异常****：使用更具体的异常，而不是引发基础的 `Exception` 类。这样，调用代码可以更轻松地理解和处理特定类型的错误。例如，在资金不足情况下尝试借记或转账时，可能会引发 InvalidOperationException。*

    ** 2.在异常消息中包含详细信息****：异常消息会提供有关操作失败的更多详细信息。例如，在 `Debit` 方法中，异常消息可能包括尝试的借记金额和当前余额。

    *3.考虑自定义异常****：如果存在应用程序特有的特定错误条件，则可能需要创建自定义异常类。创建自定义异常可以封装有关错误条件的详细信息，并使代码更具自记录性。*

    下面介绍了如何通过这些建议改进 `Debit` 方法：**

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InvalidOperationException($"Insufficient balance for debit. Attempted to debit {amount}, but current balance is {Balance}.");
        }
    }

    ```

    下面是自定义异常类的示例：**

    ```csharp

    public class InsufficientFundsException : Exception
    {
        public double AttemptedAmount { get; }
        public double CurrentBalance { get; }
        public InsufficientFundsException(double attemptedAmount, double currentBalance)
            : base($"Insufficient balance for debit. Attempted to debit {attemptedAmount}, but current balance is {currentBalance}.")
        {
            AttemptedAmount = attemptedAmount;
            CurrentBalance = currentBalance;
        }
    }

    ```

    然后，可以在借记方法中引发此自定义异常：**

    ```csharp

    public void Debit(double amount)
    {
        if (Balance >= amount)
        {
            Balance -= amount;
        }
        else
        {
            throw new InsufficientFundsException(amount, Balance);
        }
    }

    ```

    这样，调用代码可以捕获 InsufficientFundsException 并有权访问 AttemptedAmount 和 CurrentBalance 属性，以更有效地处理错误条件。**

1. 实施建议的更新，以帮助提高 `BankAccount` 类的代码可靠性。

1. 为了确保更改不会造成错误，请在继续之前生成并运行解决方案。

    > [!TIP]
    > 在上面的示例中，聊天视图提供了实施建议更新的一个示例的代码片段（使用具体异常，包括异常消息中的详细信息以及创建自定义异常）。 实施建议后，请尝试使用代码行补全来生成重复更新的新代码。 在本示例中，代码行补全可用于创建更多自定义异常类。 然后，可以使用代码行补全来使用新的自定义异常更新其他方法。 还可以重新运行原始提示以查看其他建议。

1. 选择 BankAccount.cs 文件中的所有代码。

1. 打开“聊天”视图。

1. 使用“附加上下文”按钮将相关文件添加到聊天上下文，然后输入第二个“可靠性”提示。****

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，如果在“聊天”视图中输入 `@workspace /explain How can I reduce unexpected issues for the selected code?`，GitHub Copilot Chat 会建议类似于以下响应的更新：

    为了减少 BankAccount 类中的意外问题，可以实施以下改进：**

    *1.使用枚举表示帐户类型：考虑使用枚举，而不是对帐户类型使用字符串并检查它是“Savings”还是“Current”。这可以防止字符串比较时可能出现的问题（例如区分大小写），并将帐户类型限制为预定义值。*

    ```csharp

    public enum AccountType
    {
        Savings,
        Current
    }

    ```

    *2.使用小数表示货币值：通常建议对货币值使用小数类型而不是双精度值，以避免舍入错误。*

    *3.添加更多验证：可以在方法中添加更多验证。例如，在 Transfer 方法中，可以在继续转账之前检查 toAccount 是否不为 null。*

    *4.对魔术数字使用常数：在 Transfer 方法中，有一个魔术数字 500。最好将其定义为类顶部具有有意义名称的常数。*

    ```csharp
    private const double MaxTransferAmountForDifferentOwners = 500;
    ```

    *5.传输限制的自定义异常：如果转账金额超出不同帐户所有者的限制，请考虑创建自定义异常，例如 ExceededTransferLimitException，而不是引发一般异常。*

    *6.日志记录：考虑向应用程序添加日志记录。这有助于了解应用程序流并诊断问题。*

    ** 7.单元测试：为方法编写单元测试，以确保它们在各种应用场景下都能按预期运行。这有助于在开发过程中尽早发现问题。

1. 考虑 GitHub Copilot Chat 提供的建议的范围和广度。

    某些提示可能会生成大量影响范围广泛的建议。 如果发生这种情况，请检查是否可以使用单个建议项来定义提供更具体的意向和/或上下文的新提示。

1. 使用建议列表构造包含更详细的意向和/或上下文的提示。

    GitHub Copilot Chat 提供的每个建议都可以单独调查和实施。 从列表顶部开始，逐步完成每个建议可以帮助你一次专注于一项改进。

1. 在“聊天”视图中输入详细提示，然后查看 GitHub Copilot Chat 提供的建议。

    假设使用了第二个可靠性提示示例。 GitHub Copilot Chat 响应包括以下建议项：

    ** 添加更多验证：可以在方法中添加更多验证。例如，在 Transfer 方法中，可以在继续转账之前检查 toAccount 是否不为 null。

    可以使用此建议创建新的提示，该提示侧重于向 Transfer 方法添加更多验证。 可以选择 Transfer 方法，然后在“聊天”视图中输入以下提示：

    `@workspace /explain #file:BankAccount.cs How can I improve method validations for the selected code?`

    在这种情况下，GitHub Copilot Chat 会建议类似于以下响应的更新：

    你提供的代码结构良好，并且遵循了异常处理的良好做法。** 不过，仍有一些方面可以进一步改进：

    *1.合并验证逻辑：可以创建单独的验证类或方法来处理所有验证逻辑。这将使你的 BankAccount 类更精简，从而更专注于其主要职责。*

    ** 2.使用自定义验证属性：对于某些验证，可以使用自定义验证属性。这样，就可以对需要验证的属性进行批注，并使验证逻辑与业务逻辑分离。

    *3.使用 Fluent 验证：Fluent Validation 是一个 .NET 库，它使用 Fluent 界面和 Lambda 表达式来生成验证规则。这可以使验证代码更直观、更易于阅读。*

    *4.避免使用魔术数字：在 Transfer 方法中，硬编码值为 500。通常，最好避免使用“魔术数字”，而是将它们定义为类顶部具有有意义名称的常数。*

    以下示例演示如何实施这些建议：

    ```csharp

    public class BankAccount
    {
        private const double MaxTransferAmountForDifferentOwners = 500;
        // ...
        public void Transfer(BankAccount toAccount, double amount)
        {
            ValidateTransferAmount(amount);
            ValidateTransferLimitForDifferentOwners(toAccount, amount);
    
            if (Balance >= amount)
            {
                Debit(amount);
                toAccount.Credit(amount);
            }
            else
            {
                throw new InsufficientFundsException(amount, Balance);
            }
        }
        private void ValidateTransferAmount(double amount)
        {
            if (amount < 0)
            {
                throw new InvalidTransferAmountException(amount);
            }
        }
        private void ValidateTransferLimitForDifferentOwners(BankAccount toAccount, double amount)
        {
            if (AccountHolderName != toAccount.AccountHolderName && amount > MaxTransferAmountForDifferentOwners)
            {
                throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
            }
        }
    }

    ```

    可以继续完成 GitHub Copilot Chat 提供的建议，直到实现所有你认为必要的改进。

1. 实施建议的更新，然后在继续操作之前生成并运行解决方案。

    在继续之前，请修复更改引入的任何错误。

### 使用 GitHub Copilot Chat 提高 Program 类的代码可靠性和性能

1. 在 Visual Studio Code 中打开 Program.cs 文件，然后选择文件中的所有代码。

1. 在 Visual Studio Code 中打开 Program.cs 文件，然后选择文件中的所有代码。

1. 打开“聊天”视图。

1. 在“聊天”视图中，使用“附加上下文”按钮将相关文件添加到聊天上下文，然后输入提示。****

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，如果在“聊天”视图中输入 `@workspace /explain How can I improve performance with asynchronous tasks or methods in the Program.cs file?`，GitHub Copilot Chat 会建议类似于以下响应的更新：

    为了提高 Program.cs 文件中异步任务或方法的性能，可以使用通过 async 和 await 关键字进行的异步编程。** 这将允许程序执行 I/O 绑定操作而不阻塞主线程，从而使其响应更快、更高效。

    以下是包含异步方法的 Program.cs 文件的改进版本：**

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

1. 实施建议的更新，以帮助提高 `Program` 类的代码性能（或可靠性）。

1. 为了确保更改不会造成错误，请在继续之前生成并运行解决方案。

1. 选择 Program.cs 文件中的所有代码，然后在“聊天”视图中输入“可靠性”提示。

1. 查看 GitHub Copilot Chat 提供的建议。

    > [!NOTE]
    > 无需实施 GitHub Copilot 从第四个提示生成的更新建议，但应查看这些建议。

    例如，如果在“聊天”视图中输入 `@workspace /explain How can I improve exception handling for the selected code?`，GitHub Copilot Chat 会建议类似于以下响应的更新：

    若要改进 Program.cs 文件中的异常处理，可以实施以下建议：**

    *1.使用特定异常类型：* 不要捕获一般的异常，而要尽可能捕获特定的异常。

    *2.* 向异常添加更多上下文：在异常消息中提供更多上下文，使调试更容易。

    *3.* 日志异常：不要只将异常输出到控制台，还应考虑将其记录下来，以便能够更好地进行跟踪。

    以下是 Program.cs 文件的改进版本，具有更好的异常处理功能：**

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Threading.Tasks;
    namespace BankAccountApp
    {
        class Program
        {
            private static readonly Random random = new Random();
            private const int MaxYearsBack = 10;
            private const int NumberOfAccounts = 20;
            private const int NumberOfTransactions = 100;
            private const double minTransactionAmount = -500.0;
            private const double maxTransactionAmount = 500.0;
            private const double minAccountStart = 200.0;
            private const double maxAccountStart = 1000.0;
            static async Task Main(string[] args)
            {
                List<BankAccount> accounts = await CreateBankAccountsAsync(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static async Task<List<BankAccount>> CreateBankAccountsAsync(int numberOfAccounts)
            {
                List<BankAccount> accounts = new List<BankAccount>();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        BankAccount account = new BankAccount($"Account {createdAccounts + 1}", initialBalance, accountHolderName, accountType, dateOpened);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                    }
                    await Task.Yield(); // Yield control to allow other tasks to run
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                List<Task> tasks = new List<Task>();
                foreach (BankAccount account in accounts)
                {
                    tasks.Add(Task.Run(async () =>
                    {
                        for (int i = 0; i < numberOfTransactions; i++)
                        {
                            double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                            try
                            {
                                if (transactionAmount >= 0)
                                {
                                    account.Credit(transactionAmount);
                                    Console.WriteLine($"Credit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                                else
                                {
                                    account.Debit(-transactionAmount);
                                    Console.WriteLine($"Debit: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                                }
                            }
                            catch (ArgumentException ex)
                            {
                                Console.WriteLine($"Transaction failed due to invalid argument: {ex.Message}");
                            }
                            catch (InsufficientBalanceException ex)
                            {
                                Console.WriteLine($"Transaction failed due to insufficient balance: {ex.Message}");
                            }
                            catch (Exception ex)
                            {
                                Console.WriteLine($"Transaction failed: {ex.Message}");
                            }
                            await Task.Yield(); // Yield control to allow other tasks to run
                        }
                        Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                    }));
                }
                await Task.WhenAll(tasks);
            }
            static double GenerateRandomDollarAmount(bool isAccount, double min, double max)
            {
                if (isAccount)
                {
                    double accountStartingValue = random.NextDouble() * (max - min) + min;
                    return Math.Round(accountStartingValue, 2);
                }
                else
                {
                    double transactionAmount = random.NextDouble() * random.Next((int)min, (int)max) + random.NextDouble();
                    return Math.Round(transactionAmount, 2);
                }
            }
            static string GenerateRandomAccountHolder()
            {
                string[] accountHolderNames = { "John Smith", "Maria Garcia", "Mohammed Khan", "Sophie Dubois", "Liam Johnson", "Emma Martinez", "Noah Lee", "Olivia Kim", "William Chen", "Ava Wang", "James Brown", "Isabella Nguyen", "Benjamin Wilson", "Mia Li", "Lucas Anderson", "Charlotte Liu", "Alexander Taylor", "Amelia Patel", "Daniel Garcia", "Sophia Kim" };
                var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
                return accountHolderName;
            }
            static string GenerateRandomAccountType()
            {
                string[] accountTypes = { "Savings", "Checking", "Money Market", "Certificate of Deposit", "Retirement" };
                return accountTypes[random.Next(0, accountTypes.Length)];
            }
            static DateTime GenerateRandomDateOpened()
            {
                DateTime startDate = new DateTime(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
        }
    }

    ```

## 总结

在本演示中，你已使用 GitHub Copilot 对话助手生成建议，用于帮助提高示例应用程序中的代码可靠性和性能。 你开发了提示，指导 GitHub Copilot 提供改进异常处理、减少意外问题以及改进单元测试支持的建议。 还创建了提示，这些提示侧重于使用异步任务或方法来提高性能。
