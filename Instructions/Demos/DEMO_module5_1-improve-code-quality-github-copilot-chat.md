---
demo:
  title: 演示：使用 GitHub Copilot 对话助手提高代码质量
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手提高代码质量

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

术语“代码质量”是指代码库的整体质量，包括可读性、可维护性和模块化。 代码质量是衡量代码“结构良好”的程度，以及理解、维护和扩展代码的轻松程度的标准。

> [!IMPORTANT]
> 向学员说明，本演示不是讲解有关开发高质量代码的最佳做法。 而是重点介绍如何使用 GitHub Copilot Chat 来生成建议，以便改进示例应用程序中的代码质量。 这些建议并不代表开发高质量代码的最佳做法或综合性的解决方案。 开发人员应利用自身的判断和专业知识来评估和实现 GitHub Copilot Chat 提供的建议。 实施 GitHub Copilot 提出的建议并不能取代全面代码评审和测试的需要。

以下各节概述了学员应了解的代码重构和代码质量。

#### 代码重构和高质量代码

代码重构是重新构建现有代码，而不更改其外部行为的过程。 代码重构的目标是改进代码库的内部结构，使其更易于理解、维护和扩展。 代码重构可以通过提高可读性、降低复杂性、提高模块化和提高可重用性来帮助生成高质量的代码。 其中每个因素都有助于创建更易于管理且可维护的代码库。

开发人员应在改进代码质量时考虑以下因素：

- 可读性：提高或增强代码的可读性，使开发人员更容易理解它们。
- 复杂性：减少代码复杂性，使代码更易于理解、管理和维护。
- 模块化和可重用性：将代码分解为较小的可重用模块或组件，使代码更易于管理和维护。

上面列出的因素代表着开发人员在讨论代码质量时确定的三个常见领域。 可与代码质量关联的其他因素包括：

- 可测试性：测试代码以确保其正常工作的简便性。 通常是良好设计和模块化的副产品。
- 扩展性：扩展或增强代码以添加新特性或功能的简便性。 通常是良好设计和模块化的副产品。

代码质量并不是开发人员在代码评审期间考虑的唯一因素。 以下是开发人员除了代码质量外经常评估的一些因素：

- 可靠性：代码在指定条件下执行其预期功能的能力。
- 性能：代码的执行效率。
- 安全性：代码保护数据和资源免受未经授权的访问或修改的能力。
- 可伸缩性：代码处理将来增加的工作负载或增长的能力。
- 可用性：开发人员或最终用户使用代码的简便性。
- 可移植性：代码在不同平台或环境中运行的能力。

> [!NOTE]
> 本模块中的接下来两个单元介绍如何使用 GitHub Copilot Chat 提高代码可靠性、性能和安全性。

提高代码质量通常被认为是添加新特性或增强功能的先决条件。 在处理代码可靠性、性能或安全性之前，应考虑提高代码质量。

在本演示中，你将使用 GitHub Copilot 对话助手生成建议，以帮助提高示例应用程序中的代码质量。

### 为 GitHub Copilot Chat 开发提示

重申创建有用的提示的重要性。

为 GitHub Copilot Chat 编写的提示应提供明确定义的*上下文*和*意向*。 提示的*意向*部分描述了你要实现的目标。 例如，可以要求 GitHub Copilot“重构以改进代码模块化”。 提示的*上下文*部分告知 GitHub Copilot 要考虑哪些资源。 例如，你可能希望 GitHub Copilot 考虑整个工作区，但专注于特定的文件或代码部分。 在开发提示时请考虑以下建议：

- 定义一个范围级别比要更新的代码更高的外部上下文。 例如，如果你要重构某个方法，请将包含该方法的类或文件指定为外部上下文。 将方法标识为内部上下文。
- 使用聊天参与者和聊天变量来帮助指定上下文。 可以使用 `#file:` 和 `#selection` 聊天变量来标识关注的特定代码。 在适当的情况下还可以包含完整的工作区 (`@workspace`)。 假设你想要重构特定文件中的方法。 可以使用 `#file:` 聊天变量告知 GitHub Copilot 要查看的文件。 可以在编辑器中选择该方法，并使用 `#selection` 聊天变量告知 GitHub Copilot 要重构的代码。 还可以使用 `@workspace` 聊天变量让 GitHub Copilot 考虑整个工作区。 通过在提示的自然语言部分中引用所选内容或文件来强化指定的上下文。 例如，你可以说：“如何提高所选代码的可读性？”
- 意向应明确且具体，并应指定要改进的代码质量方面。 例如，可以问 GitHub Copilot Chat“如何改进所选代码的模块化”。

在本演示的这一部分，你将查看 APL2007M5BankAccount 项目，并为 GitHub Copilot 对话助手创建三个提示****。 提示侧重于提高代码可读性、可维护性和模块化。

请按照以下步骤完成本演示的这一部分：

1. 在 Visual Studio Code 中打开“APL2007M5BankAccount”示例应用****。

1. 打开 **Program.cs** 文件并查看代码。

    此程序是模拟银行系统的控制台应用程序。 以下是主要功能：

    - Main 方法：Main 方法是应用程序的入口点。 它会创建银行账户并使用帐户来模拟交易。

    - 常量：该程序在 Program 类的顶部定义了几个常量。 常量包括：要创建的帐户数、要模拟的交易数和交易限制。

1. 花点时间编写一些可用来提高代码可读性、可维护性和模块化的提示。

    对于 BankAccount 项目，需要将 BankAccount.cs 和/或 Program.cs 文件附加到聊天上下文中。 提示可能与以下示例类似：

    提示：`@workspace /explain How can I improve the readability of the [selected code]?`

    提示：`@workspace /explain #selection How can I improve the maintainability of the [selected code]?`

    提示：`@workspace /explainHow can I improve the modularity of the [selected code]?`

    提示：`#selection How can I refactor the [selected code] to improve modularity?`

    提示：`@workspace /explain What are some options for simplifying the [selected code]?`

1. 创建三个提示，用于演示的后续环节。

### 使用 GitHub Copilot Chat 重构代码

可以使用 GitHub Copilot Chat 来建议重构和改进代码的代码更新。 在决定如何重构应用程序之前，请务必了解你的代码和目标。

必须仔细查看 GitHub Copilot Chat 提供的建议。 在实施建议之前，请考虑哪些建议支持你的目标。 出于本演示的目的，你的时间可能也是决定实施哪些建议的一个因素。

请按照以下步骤完成本演示的这一部分：

1. 花点时间查看 Program.cs 文件中包含的方法。

    - CreateBankAccounts 方法：此方法会创建具有随机初始余额、帐户持有人名称、帐户类型和开户日期的指定数量的银行帐户。 它使用 try-catch 块来处理在创建帐户期间可能发生的任何异常。

    - SimulateTransactions 方法：此方法模拟银行账户列表中的指定数量的交易。 它为每个交易生成一个随机交易金额，然后根据金额是正数还是负数对帐户进行存入或取出。 它使用 try-catch 块来处理在交易期间可能发生的任何异常。

    - SimulateTransfers 方法：此方法与 SimulateTransactions 方法相同。 它似乎用于模拟帐户之间的转帐，但目前，它只模拟单个帐户上的交易。

    - GenerateRandomDollarAmount 方法：此方法在指定范围内生成随机美元金额。 它使用不同的公式来生成金额，具体取决于金额是用于帐户余额还是交易。

    - GenerateRandomAccountHolder 方法：此方法从预定义的名称列表中选择随机帐户持有人名称。

    - GenerateRandomAccountType 方法：此方法从预定义的类型列表中选择随机帐户类型。

    - GenerateRandomDateOpened 方法：该方法会随机生成一个日期，该日期在从当前日期往回的指定年份范围内。

1. 确保项目能够正确无误地生成和运行。

1. 从你准备的提示中选择你的第一个提示。

1. 选择要改进的代码，然后打开“聊天”视图。

1. 在“聊天”视图中，使用“附加上下文”按钮将相关文件添加到聊天上下文，然后输入提示。****

    此外，还可以演示如何使用拖放操作，将文件从解决方案资源管理器视图附加到“聊天”上下文。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 你决定处理 Program.cs 文件。
    - 选择以下提示：`@workspace /explain #selection How can I improve the readability of the GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`
    - 打开 Program.cs 文件并选择以下方法：`GenerateRandomBalance`、`GenerateRandomAccountHolder`、`GenerateRandomAccountType`、`GenerateRandomDateOpened`。
    - 打开“聊天”视图并将 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    完成这些操作后，GitHub Copilot Chat 会建议与以下响应类似的更新：

    要增加这些方法的可读性，可按以下步骤操作：**

    *1.将重复的代码提取到单独的方法中：Random 对象在不同的方法中进行了多次创建。可以在类级别创建静态 Random 对象，并将其用于所有方法。这不仅能提高可读性，还能提供更好的随机性。*

    `private static readonly Random random = new Random();`

    ** 2.使用有意义的变量名称：GenerateRandomDateOpened 方法中的变量名称 `range` 略显模糊。可以使用更具描述性的名称，例如 daysRange。

    *3.添加注释：虽然代码大多不言自明，但添加注释以解释每个方法的作用对其他开发人员阅读你的代码很有帮助。*

    *4.对魔术数字使用常数：在 GenerateRandomDateOpened 方法中，数字 `10` 用于表示开始日期可以追溯的年数。可以将它提取为一个具有描述性名称的常数，例如 `MaxYearsBack`。*

    *5.使用 var 关键字：在 C# 中，当赋值右侧已经明确表明了类型时，可以使用 var 关键字。这样可以使代码更简洁、更易于阅读。*

   *下面是你的代码在这些改进后的样子：*

    ```csharp

    private static readonly Random random = new Random();
    private const int MaxYearsBack = 10;
    static double GenerateRandomBalance(double min, double max)
    {
        double balance = random.NextDouble() * (max - min) + min;
        return Math.Round(balance, 2);
    }
    static string GenerateRandomAccountHolder()
    {
        string[] accountHolderNames = {  /* names here */  };
        var accountHolderName = accountHolderNames[random.Next(0, accountHolderNames.Length)];
        return accountHolderName;
    }
    static string GenerateRandomAccountType()
    {
        string[] accountTypes = {  /* types here */  };
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

    ```

    > [!IMPORTANT]
    > 请注意 `GenerateRandomAccountHolder` 和 `GenerateRandomAccountType` 方法中的占位符值（如 `/* types here */`）。 GitHub Copilot Chat 偶尔会将代码详细信息替换为占位符。 如果你注意的话，很容易发现它们。 实现更新时，需要将占位符值替换为你的应用中的值。 如果看到占位符，则应在实现建议的更新之前复制现有代码。 如果建议的代码块与应用中的代码一致，则可以使用块注释来注释禁止现有代码，然后使用“聊天”视图的“在光标处插入”按钮来实现建议的更新，从而避免命名冲突。**** 验证建议的更新是否按预期工作后，可以移除块注释。

1. 实现建议的更新，以帮助提高代码可读性、可维护性、模块化。

    如果使用了块注释来注释禁止现有代码，则可以使用“聊天”视图的“在光标处插入”来插入建议的更新。**** 还可以使用“复制”选项并将更新粘贴到你想要的位置。

    在选择要实现的更新建议之前，请考虑在工作场所实施的编码标准和策略。

1. 为了确保在实现更新时不会引入任何错误，请在继续之前生成并运行解决方案。

1. 输入第二个提示并查看 GitHub Copilot Chat 建议的更新。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 实现 GitHub Copilot Chat 针对第一个示例提示建议的更新。
    - 你决定继续处理 Program.cs 文件。
    - 选择以下提示：`@workspace /explain How can I improve the maintainability of the Main, GenerateRandomBalance, GenerateRandomAccountHolder, GenerateRandomAccountType, and GenerateRandomDateOpened methods?`。
    - 选择以下方法：`Main`、`GenerateRandomBalance`、`GenerateRandomAccountHolder`、`GenerateRandomAccountType`、`GenerateRandomDateOpened`。
    - 打开“聊天”视图并将 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    完成这些操作后，GitHub Copilot Chat 会建议与以下响应类似的更新：

    要增加这些方法的可维护性，可按以下步骤操作：**

    *1.分离关注点：Main 方法执行了大量操作：创建帐户、模拟交易、模拟转帐。为了提高代码的可读性和可维护性，可以将这些功能拆分成独立的方法。*

    ** 2.错误处理：代码使用通用的“异常”进行错误处理。更好的做法是创建特定于应用程序的自定义异常。这样可以更轻松地理解和处理错误。

    *3.魔术数字：该代码包含魔术数字（如帐户数 20、交易数 100 等）。应将它们替换为命名常数。*

    *4.代码重复：生成随机值的代码在多个位置重复出现。可以将其重构为实用工具类或方法。*

    ```csharp

    class Program
    {
        private static readonly Random random = new Random();
        private const int MaxYearsBack = 10;
        private const int NumberOfAccounts = 20;
        private const int NumberOfTransactions = 100;
        static void Main(string[] args)
        {
            List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
            SimulateTransactions(accounts, NumberOfTransactions);
            SimulateTransfers(accounts);
        }
        static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
        {
            List<BankAccount> accounts = new List<BankAccount>();
            int createdAccounts = 0;
            while (createdAccounts < numberOfAccounts)
            {
                try
                {
                    // same code as before...
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Account creation failed: {ex.Message}");
                }
            }
            return accounts;
        }
        static void SimulateTransactions(List<BankAccount> accounts, int numberOfTransactions)
        {
            // same code as before...
        }
        static void SimulateTransfers(List<BankAccount> accounts)
        {
            // same code as before...
        }
        // same helper methods as before...
    }

    ```

1. 查看 GitHub Copilot Chat 提供的建议。

1. 实现建议的更新，以帮助提高代码可读性、可维护性、模块化。

    如果使用了块注释来注释禁止现有代码，则可以使用“聊天”视图的“在光标处插入”来插入建议的更新。**** 还可以使用“复制”选项并将更新粘贴到你想要的位置。

1. 为了确保更改不会造成错误，请在继续之前生成并运行解决方案。

1. 输入第三个提示，然后花点时间查看建议。

    例如，假设你已完成以下操作：

    - 你实现了 GitHub Copilot Chat 针对第一个和第二个提示所建议的更新。
    - 你决定继续处理 Program.cs 文件。
    - 选择以下提示：`@workspace /explain How can I improve the modularity of the Program.cs file?`。
    - 选择以下代码：选择所有 Program.cs 文件。
    - 打开“聊天”视图并将 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    完成这些操作后，GitHub Copilot Chat 会建议与以下响应类似的更新：

    要提升 Program.cs 文件的模块化水平，可按以下步骤操作：**

    *1.分离关注点：`Program` 类执行了太多操作。它要创建帐户、模拟交易、生成随机数据。每个职责都可以是一个单独的类。例如，可以有一个负责创建银行账户的 `BankAccountFactory` 类、用于模拟交易的 `TransactionSimulator` 类，以及用于生成随机数据的 `RandomDataGenerator` 类。*

    ** 2.使用接口：可以使用接口来定义类的协定。这可以使代码更加灵活、更易于测试。例如，可以使用 `Create` 方法定义 `IAccountFactory` 接口，然后让 `BankAccountFactory` 实现此接口。

    *3.魔术数字：代码中有几个“魔术数字”（如 10、50000、-500、500 等）。应将这些数字替换为命名常数，使代码更易于阅读和维护。*

    *4.重复：`SimulateTransactions` 和 `SimulateTransfers` 方法中有几乎相同的代码。可以通过创建一个公共方法供两个方法调用，来消除这种重复。*

   *下面是关于如何重构 CreateBankAccounts 方法的示例：*

    **代码片段 A：使用接口**

    ```csharp

    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }
    // In the `Program` class, you would then use the `IAccountFactory` to create accounts:
    interface IAccountFactory
    {
        BankAccount Create(int index);
    }
    class BankAccountFactory : IAccountFactory
    {
        private readonly RandomDataGenerator _randomDataGenerator;
        public BankAccountFactory(RandomDataGenerator randomDataGenerator)
        {
            _randomDataGenerator = randomDataGenerator;
        }
        public BankAccount Create(int index)
        {
            double initialBalance = _randomDataGenerator.GenerateRandomBalance(10, 50000);
            string accountHolderName = _randomDataGenerator.GenerateRandomAccountHolder();
            string accountType = _randomDataGenerator.GenerateRandomAccountType();
            DateTime dateOpened = _randomDataGenerator.GenerateRandomDateOpened();
            return new BankAccount($"Account {index + 1}", initialBalance, accountHolderName, accountType, dateOpened);
        }
    }

    ```

    **代码片段 B：重复**

    ```csharp

    static void SimulateOperations(List<BankAccount> accounts, int numberOfOperations, Action<BankAccount, double> operation)
    {
        foreach (BankAccount account in accounts)
        {
            for (int i = 0; i < numberOfOperations; i++)
            {
                double transactionAmount = GenerateRandomBalance(-500, 500);
                try
                {
                    operation(account, transactionAmount);
                    Console.WriteLine($"Operation: {transactionAmount}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Operation failed: {ex.Message}");
                }
            }
            Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
        }
    }
    // Then you can call this method like this:
    SimulateOperations(accounts, NumberOfTransactions, (account, amount) => {
        if (amount >= 0)
        {
            account.Credit(amount);
        }
        else
        {
            account.Debit(-amount);
        }
    });

    ```

    > [!NOTE]
    > 无需实现 GitHub Copilot 根据你的第三个提示生成的更新建议。 查看建议可能会获得有关代码改进过程进度的见解。

接下来的两个演示涵盖以下主题：

- 使用 GitHub Copilot Chat 提高代码的可靠性和性能
- 使用 GitHub Copilot Chat 提高代码安全性

## 总结

在本演示中，你使用 GitHub Copilot 对话助手生成了建议，以帮助提高示例应用程序中的代码质量。 你开发了侧重于提高代码可读性、可维护性和模块化的提示。 你查看了 GitHub Copilot Chat 提供的建议，并实施了有助于提高代码质量的更新。 你还考虑了可以进一步改进代码的其他建议。
