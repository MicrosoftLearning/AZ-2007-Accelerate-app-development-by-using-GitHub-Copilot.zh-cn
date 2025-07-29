---
demo:
  title: 演示：使用代码行补全创建代码
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# 演示：使用代码行补全创建代码

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

GitHub Copilot 可以为许多编程语言和各种框架提供代码补全建议，对于 Python、JavaScript、TypeScript、Ruby、Go、C# 和 C++ 尤其有效。 代码行补全是根据所编写代码的上下文生成的。 你可以接受、拒绝或部分接受 GitHub Copilot 提供的建议。

GitHub Copilot 提供了两种方法来生成代码行补全：

- **从注释中**：可以通过编写描述要生成的代码的注释来生成代码行补全。 GitHub Copilot 根据你编写的注释提供代码补全建议。

- **从代码**：可以通过启动代码行或按 Enter 在补全的代码行后生成代码行补全。 GitHub Copilot 根据你编写的代码提供代码补全建议。

在本演示中，你将使用 GitHub Copilot 在 Visual Studio Code 环境中生成代码行补全。

### 在 Visual Studio Code 环境中创建控制台应用

在本演示中，你将使用 GitHub Copilot 工具创建控制台应用。

请使用以下步骤完成本演示的这一部分：

1. 打开 Visual Studio Code 的新实例，然后打开“聊天”视图。

    可以通过从 Visual Studio Code 命令中心或使用 Ctrl+Alt+I**** 键盘快捷方式选择“**打开聊天**”来打开聊天视图。

1. 在“聊天”视图中，输入以下提示：

    ```plaintext
    @workspace /new console application named APL2007M3. Use C# LangVersion 12 and NET8.0. Only .cs and .csproj files. Enable ImplicitUsings and Nullable
    ```

1. 在“聊天”视图中，选择“创建工作区”****。

    GitHub Copilot 使用你的提示为新控制台应用程序创建工作区。 该应用程序使用 `C#` 和 `.NET8.0`。 代码项目命名为 `APL2007M3`，且包括 `.cs` 和 `.csproj` 文件。 `APL2007M3.csproj` 文件指定 C# `LangVersion 12`，并启用 `ImplicitUsings` 和 `Nullable`。

1. 在“选择文件夹”对话框中，导航到“桌面”文件夹，选择“桌面”****，然后选择“选择为父文件夹”****。

    系统会提示为新的工作区选择父文件夹。 选择“桌面”文件夹是本演示的一个不错的选择。 桌面文件夹很容易找到。 请记得在完成本培训时进行清理。

1. 当系统提示打开新项目时，选择“**打开**”。

1. 在“资源管理器”视图中，选择 **Program.cs**。

1. 将 Program.cs 文件的内容替换为以下代码：

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                // call the QuarterlySalesReport method
            }
            public void QuarterlySalesReport()
            {
                Console.WriteLine("Quarterly Sales Report");
            }
        }    
    }

    ```

设置要求已完成，可以继续演示了。

### 使用 GitHub Copilot 从注释生成代码行补全

GitHub Copilot 基于注释和应用的现有上下文生成代码补全建议。 可以使用注释来描述代码片段、方法、数据结构和其他代码元素。

请使用以下步骤完成本演示的这一部分：

1. 在 Program.cs 文件中，在 `Main` 方法下方创建两个空代码行****。

1. 若要创建可用于生成测试数据的数据结构，请创建以下代码注释，然后按 Enter 键：

    ```C#
    // public struct SalesData. Include the following fields: date sold, department name, product ID, quantity sold, unit price
    ```

    GitHub Copilot 根据代码注释及其在应用中找到的任何现有代码生成一个或多个代码补全建议。

1. 花一分钟时间查看 GitHub Copilot 提供的代码补全建议。

    > [!NOTE]
    > 如果 GitHub Copilot 为方法而不是数据结构生成建议，键入“public str”并等待代码补全建议更新****。 GitHub Copilot 使用其他信息来改进其建议。

    请注意用于声明数据结构的字段的数据类型。 GitHub Copilot 根据现有代码和代码注释选择数据类型和变量名称。 GitHub Copilot 尝试确定应用程序如何使用变量并相应地定义数据类型。

    当 GitHub Copilot 生成多个建议时，可以通过选择位于“接受”按钮左侧的向左或向右箭头（`>` 或 `<`）来循环浏览建议****。 这样，你可以查看并选择最适合你的需求的建议。

    可以接受与所需代码不完全匹配的代码补全建议。 但是，“修复”该建议所需的更改应该清晰明确。 在本例中，有些数据类型不是你需要的，但你可以在接受建议的自动补全后对其进行调整。

    如果建议的选项都不符合你的需求，可以尝试以下两种操作。 若要打开包含其他建议列表的新编辑器选项卡，请按 Ctrl + Enter 键********。 此热键组合将打开包含最多 10 条建议的新选项卡。 每个建议后跟一个可用于接受该建议的按钮。 接受建议后，选项卡会自动关闭。 另一个选项是按 Esc**** 键忽略建议，然后重试。 可以调整代码注释，以便为 GitHub Copilot 提供更多可以使用的上下文。

    > [!NOTE]
    > GitHub Copilot 有时可以分阶段提出建议。 如果发生这种情况，可以按 Enter 键查看按 Tab 键后的建议的其他阶段。

1. 若要接受建议的数据结构，请按 Tab 键或选择“接受****”。

1. 若要修改字段数据类型，请按如下所示更新代码：

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public int productID;
        public int quantitySold;
        public double unitPrice;
    }

    ```

    快速调整代码补全建议有助于确保生成所需的代码。 当代码库的大部分仍待开发时，在开发过程中尽早进行更正尤其重要。 后续的代码补全将基于已编写的代码，因此请务必确保代码尽可能准确。

1. 在 `SalesData` 数据结构下方创建两个空代码行。

1. 若要创建使用 `SalesData` 数据结构生成测试数据的方法，请编写以下代码注释，然后按 Enter 键：

    ```C#
    /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
    ```

1. 花一分钟时间查看 GitHub Copilot 提供的代码补全建议。

    请注意，`GenerateSalesData` 方法旨在返回 `SalesData` 对象的数组。 该方法生成 1000 条测试数据的记录，其中随机值分配给 `SalesData` 数据结构的每个字段。

    应始终审查 GitHub Copilot 和 GitHub Copilot Chat 给出的建议，即使它们看似正确。

    > [!NOTE]
    > 如果 GitHub Copilot 建议单个代码行而不是完整的 `GenerateSalesData` 方法，请按 Ctrl+Enter 打开 GitHub Copilot“建议”选项卡****。查看新选项卡上的建议。在下一步中，使用“接受建议 #”按钮接受建议。 GitHub Copilot 有时逐步提供建议。 虽然可以逐步接受代码补全，但最好在决定接受或放弃之前使用 GitHub Copilot“建议”选项卡查看完整建议。

1. 滚动浏览代码补全建议，并选择符合要求的最佳匹配项。

1. 若要接受代码补全，请按 Tab 键。

    请注意，代码补全建议在用于生成 `DateSold` 字段的代码中存在语法错误。 `DateOnly` 接受必须按正确顺序列出的三个整数值：年、月、日************。

1. 若要为用于生成 `DateSold` 字段的代码指定单个年份，请按如下所示更新代码行：

    ```C#
    salesData[i].DateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
    ```

1. 如有必要，请调整其他代码行以匹配以下代码片段：

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < salesData.Length; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = "Department " + random.Next(1, 11);
            salesData[i].productID = random.Next(1, 101);
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.NextDouble() * 100;
        }
        return salesData;
    }

    ```

从代码注释生成代码的功能是 GitHub Copilot 的强大功能。 只要两条注释，即可生成数据结构和生成测试数据的方法。

### 使用 GitHub Copilot 生成代码行补全

GitHub Copilot 可以根据输入的代码生成代码行补全。 可以通过两种方式生成代码行补全：

- 开始输入代码行，然后等待 GitHub Copilot 为未完成的代码行建议自动补全。
- 输入完整的代码行，按 **Enter** 键，然后等待 GitHub Copilot 为下一个代码行建议自动补全。

> [!NOTE]
> GitHub Copilot 根据输入的代码以及应用中代码定义的上下文生成建议的代码补全。 应用中的代码越多（假设代码质量好），GitHub Copilot 的上下文就越多。 随着现有代码的数量和质量的增加，GitHub Copilot 建议的代码行补全的质量和可靠性也是如此。 GitHub Copilot 非常善于为常见的编程任务和模式生成代码行补全，尤其是在需要生成一系列相关组件时。

在本演示的这一部分，你将使用 `QuarterlySalesReport` 方法。

下面是需要完成的任务：

- 使用接受 `SalesData` 对象集合的参数更新方法构造函数。
- 使用 GitHub Copilot 生成代码行补全，以处理季度报表的销售数据。
- 运行应用并查看季度收入报告。

请使用以下步骤完成本演示的这一部分：

1. 更新 `QuarterlySalesReport` 的方法构造函数，如下所示：

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    ```

1. 花点时间考虑开发所需的代码。

    这个概念是直截了当的。 你希望代码根据销售数据计算季度销售额，然后编写报表。 为此，代码需要：

    - 遍历 `salesData` 集合。
    - 根据所售数量和单价计算每笔销售交易的价值。
    - 使用销售日期确定销售所属季度。
    - 对每个季度的销售额求和。
    - 按季度撰写销售报告。

    一个选项是开始输入 `foreach` 循环的代码，然后查看 GitHub Copilot 的建议。

1. 在 `QuarterlySalesReport` 方法中，在代码块顶部创建一个新的代码行。

    新代码行与包含 `Console.WriteLine()` 的代码行之间应至少有一个空白代码行。

1. 若要生成代码行补全，请键入 `foreach (`，然后等待 GitHub Copilot 建议代码行补全选项。

1. 查看 GitHub Copilot 建议的代码补全。

    建议的代码补全不符合你的需求。

    尽管 GitHub Copilot 建议循环访问 `salesData` 的 `foreach`循环，但循环内没有分析或计算。 每个建议的选项都包含你不想要或不需要的 `Console.WriteLine` 语句。

1. 花点时间考虑 GitHub Copilot 为何建议 `Console.WriteLine` 语句。

    回想一下，GitHub Copilot 根据代码的上下文生成代码补全建议。 在这种情况下，你实际上没有太多代码可供 GitHub Copilot 考虑。 情况变得更差。

    GitHub Copilot 在方法中看到的代码是一个 `Console.WriteLine` 语句。 由于在方法中没有其他可用的上下文，并且代码库中没有其他类似的方法可供借鉴，GitHub Copilot 得出的结论是，你可能希望在 `foreach` 循环内使用 `Console.WriteLine` 语句。**

    GitHub Copilot 在代码干净且集中时效果最佳。 如果在代码中看到多余的代码注释或语句，可能需要先移除它们，然后再尝试使用 GitHub Copilot 代码补全。

1. 若要在授予 GitHub Copilot 另一次尝试之前清理代码，请完成以下步骤：

    - 取消建议 `foreach (` 的代码补全。
    - 删除输入的部分 `foreach (` 语句。
    - 从 `QuarterlySalesReport` 方法中删除 `Console.WriteLine` 语句。

    现在，你应该准备好再次尝试 GitHub Copilot。

1. 确保 `QuarterlySalesReport` 方法看起来类似于以下代码：

    ```C#
    public void QuarterlySalesReport(SalesData[] salesData)
    {


    }
    ```

1. 将光标置于 `QuarterlySalesReport` 方法内的空白代码行上，然后按 Enter 键。

    GitHub Copilot 可能需要一段时间才能生成建议的代码补全。

1. 花一分钟时间查看建议的代码补全情况。

    > [!NOTE]
    > 尽管 GitHub Copilot 只有一个要使用的方法名称和参数，但这可能足以生成有用的建议。 应会看到按季度计算销售额的建议。 拒绝建议并重试可提供不同的结果。

    可以通过选择 `>` 或 `<` 来循环浏览建议。

    请注意，建议的代码补全会循环访问销售数据并执行季度销售计算。

1. 若要接受建议的代码补全，请按 Tab 键。

    建议的代码补全会根据销售数据计算并显示季度收入。

    ```csharp

    // create a dictionary to store the quarterly sales data
    Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
    // iterate through the sales data
    foreach (SalesData data in salesData)
    {
        // calculate the total sales for each quarter
        string quarter = GetQuarter(data.dateSold.Month);
        double totalSales = data.quantitySold * data.unitPrice;
        if (quarterlySales.ContainsKey(quarter))
        {
            quarterlySales[quarter] += totalSales;
        }
        else
        {
            quarterlySales.Add(quarter, totalSales);
        }
    }
    // display the quarterly sales report
    Console.WriteLine("Quarterly Sales Report");
    Console.WriteLine("----------------------");
    foreach (KeyValuePair<string, double> quarter in quarterlySales)
    {
        Console.WriteLine(entry.Key + ": $" + entry.Value);
    }

    ```

1. 请注意，`GetQuarter` 方法用于根据销售月份确定季度。

    此方法未在代码中实现，但为了生成和运行代码，需要此方法。

1. 在 `QuarterlySalesReport` 方法下方创建两个空白代码行。

1. 请注意，GitHub Copilot 建议为 `GetQuarter` 方法补全代码。

    借助 `QuarterlySalesReport` 方法提供的上下文，GitHub Copilot 可以轻松地为 `GetQuarter` 方法生成代码补全，该方法根据销售月份确定季度。

1. 花点时间查看针对 `GetQuarter` 方法的建议代码行补全。

1. 若要接受建议的代码补全，请按 Tab 键。

    ```csharp

    public string GetQuarter(int month)
    {
        if (month >= 1 && month <= 3)
        {
            return "Q1";
        }
        else if (month >= 4 && month <= 6)
        {
            return "Q2";
        }
        else if (month >= 7 && month <= 9)
        {
            return "Q3";
        }
        else
        {
            return "Q4";
        }
    }

    ```

1. 请注意，必须先完成 `Main` 方法，然后才能运行代码。

    可以使用 `Main` 方法中的注释来更新代码。

1. 将光标置于 `// call the GenerateSalesData method` 代码注释的末尾，然后按 Enter 键。

    GitHub Copilot 使用注释来建议方法的调用语句。

1. 查看并接受 GitHub Copilot 建议的代码补全。

1. 对 `// call the QuarterlySalesReport method` 代码注释重复此过程。

1. `Main` 方法不应包含以下代码：

    ```csharp

    static void Main(string[] args)
    {
        // create a new instance of the class
        QuarterlyIncomeReport report = new QuarterlyIncomeReport();
        // call the GenerateSalesData method
        SalesData[] salesData = report.GenerateSalesData();
        // call the QuarterlySalesReport method
        report.QuarterlySalesReport(salesData);
    }

    ```

1. 花点时间查看 `QuarterlyIncomeReport` 类中的代码。

    ```csharp

    namespace ReportGenerator
    {
        class QuarterlyIncomeReport
        {
            static void Main(string[] args)
            {
                // create a new instance of the class
                QuarterlyIncomeReport report = new QuarterlyIncomeReport();
                // call the GenerateSalesData method
                SalesData[] salesData = report.GenerateSalesData();
                // call the QuarterlySalesReport method
                report.QuarterlySalesReport(salesData);
            }
            /* public struct SalesData includes the following fields: date sold, department name, product ID, quantity sold, unit price */
            public struct SalesData
            {
                public DateOnly dateSold;
                public string departmentName;
                public int productID;
                public int quantitySold;
                public double unitPrice;
            }
            /* the GenerateSalesData method returns 1000 SalesData records. It assigns random values to each field of the data structure */
            public SalesData[] GenerateSalesData()
            {
                SalesData[] salesData = new SalesData[1000];
                Random random = new Random();
                for (int i = 0; i < 1000; i++)
                {
                    salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
                    salesData[i].departmentName = "Department " + random.Next(1, 11);
                    salesData[i].productID = random.Next(1, 101);
                    salesData[i].quantitySold = random.Next(1, 101);
                    salesData[i].unitPrice = random.NextDouble() * 100;
                }
                return salesData;
            }
            public void QuarterlySalesReport(SalesData[] salesData)
            {
                // create a dictionary to store the quarterly sales data
                Dictionary<string, double> quarterlySales = new Dictionary<string, double>();
                // iterate through the sales data
                foreach (SalesData data in salesData)
                {
                    // calculate the total sales for each quarter
                    string quarter = GetQuarter(data.dateSold.Month);
                    double totalSales = data.quantitySold * data.unitPrice;
                    if (quarterlySales.ContainsKey(quarter))
                    {
                        quarterlySales[quarter] += totalSales;
                    }
                    else
                    {
                        quarterlySales.Add(quarter, totalSales);
                    }
                }
                // display the quarterly sales report
                Console.WriteLine("Quarterly Sales Report");
                Console.WriteLine("----------------------");
                foreach (KeyValuePair<string, double> quarter in quarterlySales)
                {
                    Console.WriteLine(entry.Key + ": $" + entry.Value);
                }
            }
            public string GetQuarter(int month)
            {
                if (month >= 1 && month <= 3)
                {
                    return "Q1";
                }
                else if (month >= 4 && month <= 6)
                {
                    return "Q2";
                }
                else if (month >= 7 && month <= 9)
                {
                    return "Q3";
                }
                else
                {
                    return "Q4";
                }
            }
        }
    }
    
    ```

    此代码几乎完全是使用 GitHub Copilot 生成的代码行补全创建的。 但是，对代码建议的评审非常重要，需要更正。 应始终检查 GitHub Copilot 提供的代码补全建议，以确保代码符合你的要求。

1. 若要查看报表输出，请运行应用。

    在 Visual Studio Code 中打开终端窗口，然后输入以下命令：

    ```bash
    dotnet run
    ```

    输出应显示季度收入报告，显示测试数据中每个部门和季度的部门名称、季度和收入。

1. 查看“终端”窗口中的输出。

    尽管季度结果基于随机数值，但应会看到格式类似于以下输出的报告：

    ```output

    Quarterly Sales Report
    ----------------------
    Q3: $635637.5019563352
    Q4: $672247.315297204
    Q2: $667269.194630603
    Q1: $642769.2700531208

    ```

    补全 `QuarterlyIncomeReport` 类还需要完成一些其他工作。 在下一单元中，你将使用 GitHub Copilot Chat 扩展和更新应用。

### 总结

在本演示中，你使用 GitHub Copilot 在 Visual Studio Code 环境中生成了代码行补全。 你使用了代码注释来生成数据结构和生成测试数据的方法。 还使用了代码行补全来生成处理季度收入报表中销售数据的代码。
