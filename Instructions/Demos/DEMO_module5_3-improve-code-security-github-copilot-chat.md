---
demo:
  title: 演示：使用 GitHub Copilot 对话助手提高代码安全性
  module: 'Module 5: Implement code improvements using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 对话助手提高代码安全性

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

代码安全性是指为保护软件免受未经授权的访问、数据外泄和其他安全威胁而采取的措施。 代码安全性是软件开发的一个重要方面，涉及到保护应用程序和系统免受安全威胁。 提高代码安全性可以帮助保护应用程序和系统免受安全威胁。

> [!IMPORTANT]
> 向学员说明，本演示不是讲解有关开发安全代码的最佳做法。 而是重点介绍如何使用 GitHub Copilot Chat 来生成建议，以便改进示例应用程序中的代码安全性。 这些建议并不代表开发安全代码的最佳做法或综合性的解决方案。 开发人员应利用自身的判断和专业知识来评估和实现 GitHub Copilot Chat 提供的建议。 实施 GitHub Copilot 提出的建议并不能取代全面代码评审和测试的需要。

#### 代码安全

确保代码安全性是每个人的责任，而不仅仅是开发人员的责任。 但是，开发人员通过确保他们编写的代码遵循安全编码实践来发挥关键作用。 安全编码实践有助于确保软件漏洞不会被攻击者利用。 通过遵循安全编码实践，开发人员可以帮助保护软件免受安全威胁并确保其安全可靠。

以下各节概述了学员应了解的代码安全流程。

##### 使用综合方法评估代码安全性

在评估代码安全性时，必须考虑涵盖软件开发生命周期各个方面的综合方法。 下面是一些关键注意事项：

- 安全编码实践：遵守安全编码标准和指南以防止漏洞。
- 代码分析工具：利用静态和动态代码分析工具来检测安全漏洞。
- 依赖项管理：确保第三方库和依赖项是最新的并且不存在已知漏洞。
- 身份验证和授权：实现强大的身份验证和授权机制，以防止未经授权的访问。
- 数据保护：对静态和传输中的敏感数据进行加密，以防止数据泄露。
- 错误处理：开发不会泄露敏感信息的安全错误处理过程。
- 安全测试：进行彻底的安全测试，包括渗透测试和漏洞评估。
- 合规性：确保代码符合相关安全标准和法规。
- 教育和培训：为开发人员提供持续的安全教育和培训，让他们了解最新的威胁和最佳做法。
- 事件响应：妥善定义事件响应计划。 如果发生安全漏洞，事件响应计划必须易于访问。

考虑这些因素并将安全最佳做法集成到开发过程将有助于创建安全的内容和应用程序。

##### 进行代码安全评审

在努力确保代码安全的同时，开发人员应检查代码的以下方面：

- 正确性：验证代码不存在可能导致安全漏洞的逻辑错误和缺陷。
- 安全性：确保代码遵循安全最佳做法且不包含漏洞。
- 诊断：提供适当的日志记录和诊断功能来检测和响应安全事件。
- 设计错误或限制：评审代码的设计以确保不存在可被利用的缺陷或限制。
- 缩放和性能：考虑代码的性能和可伸缩性。 性能和可伸缩性较差可能会影响高负载场景下的安全性。
- 本地化：确保代码可以安全处理不同的区域设置，因为这可能会影响数据的格式和表示。
- 易访问性 (UX)：验证安全措施不会对易访问性和用户体验产生负面影响。
- 测试：评审测试策略并确保安全测试范围全面且涵盖代码的所有方面。
- 检测：确保以支持安全监视和威胁检测的方式检测代码。
- 一致性和代码样式约定：保持遵循安全编码指南和标准的一致编码样式。

当开发人员评审代码的这些方面时，他们可以显著增强代码的安全性。 代码评审有助于开发人员为其开发的软件的整体安全态势做出贡献。

##### 分析代码漏洞

应用程序的某些部分更容易受到安全攻击，因此重点保护这些方面至关重要。 下面是一些较脆弱的方面：

- 集成点：必须在相关产品团队的配合下对集成点进行安全设计评审。 评审对于处理高业务影响 (HBI) 数据或企业应用程序和服务的产品至关重要。
- 内部系统：内部事件是安全漏洞的常见原因，尤其是在小型企业中。
- 电子邮件系统：电子邮件服务器，特别是那些不受支持或未修补的服务器，始终容易受到攻击。
- 数据库和存储：如果数据库在存储之前需要对敏感数据进行预加密，而数据没有按照预期进行加密，则数据库就容易受到攻击。
- 运行时环境：运行时应用程序自我保护 (RASP) 等技术可以实时检测对应用程序的攻击，使运行时环境成为需要保护的关键方面。
- Web 应用程序：Web 应用程序经常成为 SQL 注入、跨站点脚本 (XSS) 和缓冲区溢出等攻击方法的目标。
- 终结点：设备和应用程序面临网络攻击的风险。 使用勒索软件缓解、应用程序控制、Web 保护和网络防火墙等功能来减少攻击面至关重要。

开发人员和安全团队应优先考虑这些方面并实施强有力的安全措施以防止潜在的攻击。 定期安全评审、更新和遵守最佳做法有助于缓解这些漏洞。

##### 搜索常见安全缺陷

开发人员可能会在代码中遇到各种安全缺陷，如果处理不当，可能会导致漏洞。 一些典型的安全缺陷包括：

- 注入缺陷：例如 SQL、NoSQL、OS 和 LDAP 注入，它们会将不受信任的数据作为命令或查询的一部分发送到解释器。
- 身份验证失效：当身份验证和会话管理实施不当时，身份验证可能会失效。 正确的实施可确保密码、密钥和会话令牌不会被攻击者盗取。
- 敏感数据暴露：对敏感数据的保护不足可能会导致其在网络传输或静止时暴露。
- 访问控制失效：不正确实施控制授予经过身份验证的用户的访问权限的限制。
- 跨站脚本 (XSS)：当应用程序在网页中包含不受信任的数据且未经适当验证或转义时，就会出现 XSS 缺陷。
- 不安全的反序列化：这可能会导致远程代码执行、重播攻击、注入攻击和特权升级攻击。
- 日志记录和监视不足：日志记录和监视不足，加上与事件响应的整合缺失或无效，导致攻击持续发生。
- 不安全的直接对象引用（IDOR）：当应用程序根据用户提供的输入直接访问对象时，就会出现某种访问控制问题。
- 缺少功能级别访问控制：有时，应用程序无法正确保护功能级访问控制，从而允许攻击者在未经适当授权的情况下伪造访问功能的请求。

代码中还存在许多其他安全缺陷。 开发人员必须使用工具和最佳做法来主动识别和修复这些问题。

### 为 GitHub Copilot Chat 开发提示

为 GitHub Copilot Chat 编写的提示应提供明确定义的上下文和意向。 在开发提示时请考虑以下建议：

- 定义一个范围级别比要更新的代码更高的外部上下文。 例如，如果你要改进某个方法，请将包含该方法的类或文件指定为外部上下文。 将方法标识为内部上下文。
- 使用聊天参与者和聊天变量来帮助指定上下文。 可以使用 `#file:` 和 `#selection` 聊天变量来标识关注的特定代码。 在适当的情况下还可以包含完整的工作区 (`@workspace`)。 请参考提示的自然语言部分中的文件或代码选择。
- 意向应清晰、简洁且具体。 提示应指定你想要实现的改进类型。

在本演示的这一部分，你将查看 APL2007M5BankAccount-Security 项目，并为 GitHub Copilot 对话助手创建三个提示****。 这些提示主要用于提高代码安全性。

请按照以下步骤完成本演示的这一部分：

1. 打开 APL2007M5BankAccount-Security 项目，然后查看 Program.cs 和 BankAccount.cs 代码文件************。

    Program.cs 文件包含一个简单银行应用程序的代码，该应用程序模拟银行帐户的创建、交易和转帐****。

    BankAccount.cs 文件包含 ****`BankAccount` 类的代码，该类代表具有存款、取款和余额查询等基本功能的银行帐户。

1. 花一点时间简要说明一些可用于提升代码安全性的提示。

    对于此项目，可以使用以下提示生成提高代码安全性的建议：

    提示：`@workspace /explain How can I implement authentication in the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I protect sensitive data in the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I implement logging of suspicious account activities of the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve the security of exception handling in the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve the security of the [selected code]?`（将 BankAccount.cs 附加到聊天上下文）

    提示：`@workspace /explain How can I improve the security of the [selected code]?`（将 Program.cs 附加到聊天上下文）

1. 从中选择三个提示，用于演示的后续环节。

    尝试选择两个提示来解决 BankAccount.cs 文件中的安全问题，并选择一个提示来解决 Program.cs 文件中的安全问题。 在本演示中，BankAccount 类代表你的“产品”。 Program.cs 文件使用 BankAccount 类来模拟帐户活动和交易。

### 使用 GitHub Copilot Chat 提高 BankAccount 类的代码安全性

对于任何软件项目而言，开发安全代码都至关重要。 所需的安全级别取决于应用程序的性质及其处理的数据。

在本演示中，你将使用 GitHub Copilot 对话助手生成有关改进 APL2007M5BankAccount-Security 项目中 BankAccount 类的安全性的建议****。

可以使用 GitHub Copilot Chat 来帮助提高代码安全性。 提示可以指示 GitHub Copilot 生成有关改进身份验证、数据保护、日志记录和其他数十个主题的建议。 还可以创建范围广泛的提示，以征求提高代码安全性的一般建议。 具体提示和一般提示的组合可帮助你识别需要改进的方面并实施所需的更改。

> [!TIP]
> 实施和测试建议的更新需要时间，因此时间可能是本演示的一个因素。 选择注重于特定改进方面的提示可帮助你控制好时间。 过于宽泛的提示可能会生成大量的建议或复杂的建议，而这些建议很难在短时间内评估和实施。 开始后，如果你发现建议的更新范围太广或太复杂，可以使用更具体的详细信息来更新提示。

1. 确保项目能够正确无误地生成和运行。

    只要应用程序能够运行，警告就可以接受，但在开始使用 GitHub Copilot Chat 之前必须解决错误。

1. 在 Visual Studio Code 中打开 BankAccount.cs 文件，然后选择文件中的所有代码。

1. 打开“聊天”视图。

1. 在“聊天”视图中，使用“附加上下文”按钮将相关文件添加到聊天上下文，然后输入提示。****

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 打开 BankAccount.cs 文件并选择所有代码。
    - 选择以下提示：`@workspace /explain How can I implement authentication in the BankAccount.cs file?`
    - 打开“聊天”视图并将 BankAccount.cs 和 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    GitHub Copilot Chat 会建议类似于以下响应的更新：

    ** 在当前上下文中，实现身份验证通常需要在 BankAccount 类中添加一个方法，用于在允许执行某些操作之前验证帐户持有人的身份。这可以通过使用密码、PIN 或其他形式的身份验证来实现。

    以下简单示例演示如何将基于密码的身份验证添加到 BankAccount 类**：

    ```csharp

    public class BankAccount
    {
        // Existing code...
        private string password;
        public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string password)
        {
            // Existing code...
    
            this.password = password;
        }
        public bool Authenticate(string password)
        {
            return this.password == password;
        }
        public void Credit(double amount, string password)
        {
            if (!Authenticate(password))
            {
                throw new Exception("Authentication failed.");
            }
            // Existing code...
        }
        // Similar changes would be made to the Debit, Transfer, and other methods...
    }

    ```

    ** 在此示例中，密码作为参数添加到 BankAccount 构造函数中，并存储在一个专用字段中。添加了一个 Authenticate 方法，用于检查提供的密码是否与存储的密码匹配。Credit 方法（以及其他需要身份验证的方法）已修改为使用密码作为参数，并在执行操作之前调用 Authenticate。

    ** 这是一种非常基本的身份验证形式，对于实际应用程序来说不够安全。在真实的应用程序中，你可能希望在存储密码之前对其进行哈希处理和加盐处理，并且需要使用安全的方法将用户提供的密码传输到应用程序。你还可能需要使用双因素身份验证或其他更安全的方法。

1. 实施建议的更新，以帮助提高 `BankAccount` 类的代码安全性。

    必须更新 Program.cs 文件才能使用添加到 BankAccount 类的密码和身份验证。 可以使用 GitHub Copilot Chat 生成更新 Program.cs 文件的建议。

    1. 选择 Program.cs 文件的内容，将 Program.cs 和 BankAccount.cs 文件附加到聊天上下文，然后在“聊天”视图中输入以下提示：

        ```plaintext
        @workspace /Explain How can I update the Program.cs file to use the password and authentication added to BankAccount.cs?
        ```

    1. 检查 GitHub Copilot Chat 提供的建议，然后实现建议的更新。

    1. 为了确保更改不会造成错误，请在继续之前生成并运行解决方案。

        使用 GitHub Copilot 帮助解决生成过程中发现的任何问题。

    > [!IMPORTANT]
    > 这种非常基础的身份验证方式对于实际应用程序来说不够安全，确保学员了解这一点。 在真实的应用程序中，你可能希望在存储密码之前对其进行哈希处理和加盐处理，并且需要使用安全的方法将用户提供的密码传输到应用程序。 你还可能想要使用双因素身份验证或其他更安全的方法。

1. 在继续操作之前，请确保应用程序能够生成并运行。

1. 选择 BankAccount.cs 文件中的所有代码，然后在“聊天”视图中输入第二个提示。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 打开 BankAccount.cs 文件并选择所有代码。
    - 选择以下提示：`@workspace /explain How can I protect account numbers and account holder names in the selected code?`
    - 打开“聊天”视图并将 BankAccount.cs 和 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    GitHub Copilot Chat 会建议类似于以下响应的更新：

    *若要保护 BankAccount 类中的敏感数据（如帐号和帐户持有者姓名），可以执行以下步骤：*

    *1.使用封装：*

    *- 使敏感属性变为私密，并通过方法提供受控的访问。*

    *2.加密敏感数据：*

    *-使用加密安全地存储敏感数据。*

    *3.避免明文存储：*

    *- 确保敏感数据未以明文形式存储或传输。*

    *更新后的实现*

    *下面是对帐号和帐户持有者姓名使用加密的 BankAccount.cs 的更新版本：*

    ```csharp

    using System;
    using System.Security.Cryptography;
    using System.Text;
    namespace BankAccountApp
    {
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
        public class InvalidAccountTypeException : Exception
        {
            public string AccountType { get; }
            public InvalidAccountTypeException(string accountType)
                : base($"Invalid account type: {accountType}.")
            {
                AccountType = accountType;
            }
        }
        public class InvalidAccountNumberException : Exception
        {
            public string AccountNumber { get; }
            public InvalidAccountNumberException(string accountNumber)
                : base($"Invalid account number: {accountNumber}.")
            {
                AccountNumber = accountNumber;
            }
        }
        public class InvalidAccountHolderNameException : Exception
        {
            public string AccountHolderName { get; }
            public InvalidAccountHolderNameException(string accountHolderName)
                : base($"Invalid account holder name: {accountHolderName}.")
            {
                AccountHolderName = accountHolderName;
            }
        }
        public class InvalidDateOpenedException : Exception
        {
            public DateTime DateOpened { get; }
            public InvalidDateOpenedException(DateTime dateOpened)
                : base($"Invalid date opened: {dateOpened}.")
            {
                DateOpened = dateOpened;
            }
        }
        public class InvalidInitialBalanceException : Exception
        {
            public double InitialBalance { get; }
            public InvalidInitialBalanceException(double initialBalance)
                : base($"Invalid initial balance: {initialBalance}.")
            {
                InitialBalance = initialBalance;
            }
        }
        public class InvalidInterestRateException : Exception
        {
            public double InterestRate { get; }
            public InvalidInterestRateException(double interestRate)
                : base($"Invalid interest rate: {interestRate}.")
            {
                InterestRate = interestRate;
            }
        }
        public class InvalidTransferAmountException : Exception
        {
            public double TransferAmount { get; }
            public InvalidTransferAmountException(double transferAmount)
                : base($"Invalid transfer amount: {transferAmount}.")
            {
                TransferAmount = transferAmount;
            }
        }
        public class InvalidCreditAmountException : Exception
        {
            public double CreditAmount { get; }
            public InvalidCreditAmountException(double creditAmount)
                : base($"Invalid credit amount: {creditAmount}.")
            {
                CreditAmount = creditAmount;
            }
        }
        public class InvalidDebitAmountException : Exception
        {
            public double DebitAmount { get; }
            public InvalidDebitAmountException(double debitAmount)
                : base($"Invalid debit amount: {debitAmount}.")
            {
                DebitAmount = debitAmount;
            }
        }
        public class AuthenticationException : Exception
        {
            public AuthenticationException(string message) : base(message) { }
        }
        public class BankAccount
        {
            public enum AccountTypes
            {
                Savings,
                Checking,
                MoneyMarket,
                CertificateOfDeposit,
                Retirement
            }
            private string EncryptedAccountNumber { get; }
            private string EncryptedAccountHolderName { get; }
            public double Balance { get; private set; }
            public AccountTypes AccountType { get; }
            public DateTime DateOpened { get; }
            private const double MaxTransferAmountForDifferentOwners = 500;
            private string Username { get; }
            private string Password { get; }
            public BankAccount(string accountNumber, double initialBalance, string accountHolderName, string accountType, DateTime dateOpened, string username, string password)
            {
                if (accountNumber.Length != 10)
                {
                    throw new InvalidAccountNumberException(accountNumber);
                }
                if (initialBalance < 0)
                {
                    throw new InvalidInitialBalanceException(initialBalance);
                }
                if (accountHolderName.Length < 2)
                {
                    throw new InvalidAccountHolderNameException(accountHolderName);
                }
                if (dateOpened > DateTime.Now)
                {
                    throw new InvalidDateOpenedException(dateOpened);
                }
                EncryptedAccountNumber = Encrypt(accountNumber);
                EncryptedAccountHolderName = Encrypt(accountHolderName);
                Balance = initialBalance;
                AccountType = (AccountTypes)Enum.Parse(typeof(AccountTypes), accountType);
                DateOpened = dateOpened;
                Username = username;
                Password = password;
            }
            public void Credit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidCreditAmountException(amount);
                }
                Balance += amount;
            }
            public void Debit(double amount)
            {
                if (amount < 0)
                {
                    throw new InvalidDebitAmountException(amount);
                }
                if (Balance >= amount)
                {
                    Balance -= amount;
                }
                else
                {
                    throw new InsufficientFundsException(amount, Balance);
                }
            }
            public double GetBalance()
            {
                return Balance;
            }
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
                if (Decrypt(EncryptedAccountHolderName) != Decrypt(toAccount.EncryptedAccountHolderName) && amount > MaxTransferAmountForDifferentOwners)
                {
                    throw new Exception("Transfer amount exceeds maximum limit for different account owners.");
                }
            }
            public void PrintStatement()
            {
                Console.WriteLine($"Account Number: {Decrypt(EncryptedAccountNumber)}, Balance: {Balance}");
            }
            public double CalculateInterest(double interestRate)
            {
                if (interestRate < 0)
                {
                    throw new InvalidInterestRateException(interestRate);
                }
                return Balance * interestRate;
            }
            public void Authenticate(string username, string password)
            {
                if (Username != username || Password != password)
                {
                    throw new AuthenticationException("Invalid username or password.");
                }
            }
            private string Encrypt(string plainText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform encryptor = aes.CreateEncryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream())
                    {
                        using (var cs = new CryptoStream(ms, encryptor, CryptoStreamMode.Write))
                        {
                            using (var sw = new System.IO.StreamWriter(cs))
                            {
                                sw.Write(plainText);
                            }
                        }
                        return Convert.ToBase64String(ms.ToArray());
                    }
                }
            }
            private string Decrypt(string cipherText)
            {
                using (Aes aes = Aes.Create())
                {
                    aes.Key = Encoding.UTF8.GetBytes("A very strong key"); // Use a secure key
                    aes.IV = Encoding.UTF8.GetBytes("A strong IV123456"); // Use a secure IV
                    ICryptoTransform decryptor = aes.CreateDecryptor(aes.Key, aes.IV);
                    using (var ms = new System.IO.MemoryStream(Convert.FromBase64String(cipherText)))
                    {
                        using (var cs = new CryptoStream(ms, decryptor, CryptoStreamMode.Read))
                        {
                            using (var sr = new System.IO.StreamReader(cs))
                            {
                                return sr.ReadToEnd();
                            }
                        }
                    }
                }
            }
        }
    }

    ```

    *用法：*

    **- 确保你具备必要的加密库。为简单起见，上面的示例使用具有硬编码密钥和 IV 的 AES 加密。在实际应用程序中，应使用密钥管理服务安全地管理密钥和 IV。

    > [!IMPORTANT]
    > 在实际应用程序中，应使用密钥管理服务安全地管理密钥和 IV。 此培训中提供的示例确定了改进领域，但并不代表安全加密的最佳做法。 可以使用 GitHub Copilot Chat 来寻求改进应用程序中的加密和数据保护的其他建议。

1. 不需要为第二个提示实现建议的更新。

    在此示例中，建议的更新有助于提高应用程序的安全性，但它们需要对 Program.cs 代码进行重大配置和更新，这不在本演示涵盖的范围内。

### 使用 GitHub Copilot Chat 提高 Program 类的代码安全性

1. 在 Visual Studio Code 中打开 Program.cs 文件，然后选择文件中的所有代码。

1. 打开“聊天”视图，然后输入你为 Program 类准备的第一个提示。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，假设你已完成以下操作：

    - 打开 Program.cs 文件并选择所有代码。
    - 选择以下提示：`@workspace /explain How can I improve the security of the Program.cs file?`
    - 打开“聊天”视图并将 BankAccount.cs 和 Program.cs 文件附加到聊天上下文。
    - 在“聊天”视图中输入提示。

    GitHub Copilot Chat 会建议类似于以下响应的更新：

    *若要提高 Program.cs 文件的安全性，应关注以下方面：*

    *1.安全密码处理：*

    - 使用安全密码哈希，避免以纯文本形式存储密码。**
    - 使用类似 BCrypt.Net 的库对密码进行哈希处理。**

    *2.加密敏感数据：*

    *- 加密敏感数据，例如帐号和帐户持有者姓名。*

    *3.避免硬编码的密码：*

    - 避免使用硬编码的密码。** 应生成强随机密码，或提示用户自行创建密码。

    *4.使用安全随机数生成：*

    *- 使用加密安全的随机数生成器生成敏感数据。*

    *更新后的实现*

    *下面是包含这些改进的 Program.cs 的更新版本：*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
        }
    }

    ```

1. 请注意，Program.cs 的更新侧重于安全随机数生成。

    其他建议适用于 BankAccount 类，而实现超出了此培训的范围。

1. 为寻求保护异常处理的 Program.cs 构造额外的提示。

1. 查看 GitHub Copilot Chat 提供的建议。

    例如，如果在“聊天”视图中输入 `@workspace /explain How can I implement secure exception handling in the Program.cs file?`，GitHub Copilot Chat 会建议类似于以下响应的更新：

    *若要在 Program.cs 文件中实现安全异常处理，应遵循以下最佳做法：*

    *1.捕获特定异常：*

    - 捕获特定异常，而不是使用通用的 catch (Exception ex) 块。** 这有助于正确理解和处理不同类型的错误。

    *2.安全记录异常：*

    - 在不公开敏感信息的情况下安全地记录异常。** 使用记录框架管理日志。

    *3.提供用户友好消息：*

    *- 提供用户友好的错误消息，而不显示内部详细信息。*

    *4.使用 Finally 块进行清理：*

    *- 使用 finally 块来确保执行任何必要的清理，而不考虑是否引发了异常。*

    *5.避免捕获非关键异常：*

    *- 避免捕获应允许传播的异常，例如 OutOfMemoryException 或 StackOverflowException。*

    *下面是具有安全异常处理的 Program.cs 的更新版本：*

    ```csharp

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Security.Cryptography;
    using System.Text;
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
            static async Task Main()
            {
                List<BankAccount> accounts = CreateBankAccounts(NumberOfAccounts);
                await SimulateTransactionsAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
                await SimulateTransfersAsync(accounts, NumberOfTransactions, minTransactionAmount, maxTransactionAmount);
            }
            static List<BankAccount> CreateBankAccounts(int numberOfAccounts)
            {
                List<BankAccount> accounts = new();
                int createdAccounts = 0;
                while (createdAccounts < numberOfAccounts)
                {
                    try
                    {
                        double initialBalance = GenerateRandomDollarAmount(true, minAccountStart, maxAccountStart);
                        string accountHolderName = GenerateRandomAccountHolder();
                        string accountType = GenerateRandomAccountType();
                        DateTime dateOpened = GenerateRandomDateOpened();
                        string accountNumber = "102000" + random.Next(1000, 9999).ToString();
                        string username = "user" + createdAccounts;
                        string password = GenerateSecurePassword();
                        BankAccount account = new(accountNumber, initialBalance, accountHolderName, accountType, dateOpened, username, password);
                        accounts.Add(account);
                        createdAccounts++;
                    }
                    catch (ArgumentException ex)
                    {
                        Console.WriteLine($"Account creation failed due to invalid argument: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    catch (Exception ex)
                    {
                        Console.WriteLine($"Account creation failed: {ex.Message}");
                        // Log the exception securely
                        LogException(ex);
                    }
                    finally
                    {
                        // Any cleanup code would go here.
                    }
                }
                return accounts;
            }
            static async Task SimulateTransactionsAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transaction
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
                        catch (InvalidCreditAmountException ex)
                        {
                            Console.WriteLine($"Invalid credit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InvalidDebitAmountException ex)
                        {
                            Console.WriteLine($"Invalid debit amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transaction failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
                await Task.WhenAll(tasks);
            }
            static async Task SimulateTransfersAsync(List<BankAccount> accounts, int numberOfTransactions, double minTransactionAmount, double maxTransactionAmount)
            {
                var tasks = accounts.Select(async account =>
                {
                    for (int i = 0; i < numberOfTransactions; i++)
                    {
                        double transactionAmount = GenerateRandomDollarAmount(false, minTransactionAmount, maxTransactionAmount);
                        try
                        {
                            account.Authenticate(account.Username, account.Password); // Authenticate before transfer
                            BankAccount toAccount = accounts[random.Next(accounts.Count)];
                            toAccount.Authenticate(toAccount.Username, toAccount.Password); // Authenticate target account
                            account.Transfer(toAccount, transactionAmount);
                            Console.WriteLine($"Transfer: {transactionAmount}, From: {account.AccountNumber}, To: {toAccount.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                        }
                        catch (InvalidTransferAmountException ex)
                        {
                            Console.WriteLine($"Invalid transfer amount: {ex.Message}");
                            LogException(ex);
                        }
                        catch (InsufficientFundsException ex)
                        {
                            Console.WriteLine($"Insufficient funds: {ex.Message}");
                            LogException(ex);
                        }
                        catch (AuthenticationException ex)
                        {
                            Console.WriteLine($"Authentication failed: {ex.Message}");
                            LogException(ex);
                        }
                        catch (Exception ex)
                        {
                            Console.WriteLine($"Transfer failed: {ex.Message}");
                            LogException(ex);
                        }
                    }
                    Console.WriteLine($"Account: {account.AccountNumber}, Balance: {account.Balance.ToString("C")}, Account Holder: {account.AccountHolderName}, Account Type: {account.AccountType}");
                });
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
                DateTime startDate = new(DateTime.Today.Year - MaxYearsBack, 1, 1);
                int daysRange = (DateTime.Today - startDate).Days;
                DateTime randomDate = startDate.AddDays(random.Next(daysRange));
                if (randomDate.Year == DateTime.Today.Year && randomDate >= DateTime.Today)
                {
                    randomDate = randomDate.AddDays(-1);
                }
                return randomDate;
            }
            static string GenerateSecurePassword()
            {
                const int passwordLength = 12;
                const string validChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()";
                StringBuilder password = new StringBuilder();
                using (RNGCryptoServiceProvider rng = new RNGCryptoServiceProvider())
                {
                    byte[] uintBuffer = new byte[sizeof(uint)];
                    while (passwordLength > password.Length)
                    {
                        rng.GetBytes(uintBuffer);
                        uint num = BitConverter.ToUInt32(uintBuffer, 0);
                        password.Append(validChars[(int)(num % (uint)validChars.Length)]);
                    }
                }
                return password.ToString();
            }
            static void LogException(Exception ex)
            {
                // Implement a secure logging mechanism here
                // For example, log to a file, database, or external logging service
                Console.WriteLine($"Logged exception: {ex.Message}");
            }
        }
    }

    ```

1. 实现建议的更新，以帮助提高 `Program.cs` 文件的代码安全性。

1. 为了确保更改不会造成错误，请生成并运行解决方案。

## 总结

在本演示中，你已使用 GitHub Copilot 对话助手生成了建议，以提高示例应用程序中的代码安全性。 你开发了提示，以指示 GitHub Copilot 提供有关改进身份验证、数据保护、日志记录和其他安全相关主题的建议。 你实施了建议的更新，以提高 APL2007M5BankAccount-Security 项目中 BankAccount 类和 Program 类的安全性****。
