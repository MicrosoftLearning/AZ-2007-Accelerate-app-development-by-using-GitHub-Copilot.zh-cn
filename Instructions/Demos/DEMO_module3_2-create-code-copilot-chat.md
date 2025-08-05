---
demo:
  title: 演示：使用 GitHub Copilot 内联聊天创建代码
  module: 'Module 3: Develop code features using GitHub Copilot tools'
---

# 演示：使用 GitHub Copilot 内联聊天创建代码

## 说明

这些演示活动专为包含以下资源的环境而设计：

- Visual Studio Code。
- 适用于 Visual Studio Code 的 C# 开发工具包扩展。
- 适用于 Visual Studio Code 的 GitHub Copilot 和 GitHub Copilot Chat 扩展。 需要具有 GitHub Copilot 活动订阅的 GitHub 帐户。
- 使用 C# 创建的示例代码项目。

注意****：我们建议讲师在演示过程中使用自己的 GitHub 帐户和 GitHub Copilot 订阅。 这样可以更好地控制和自定义开发环境。 此外，还可以更轻松地根据课堂需求调整演示内容。

**重要说明**：如果选择在托管实验室环境中运行演示，而不是在讲师电脑上进行演示，则可以在托管环境中解压缩示例应用。 在运行演示之前，需要在托管环境中配置 GitHub Copilot 扩展。 你可能会发现托管环境的运行速度较本地环境慢一些，因此在演示过程中可能需要相应地调整节奏。

### 演示简介

适用于 Visual Studio Code 的 GitHub Copilot 聊天扩展包括三个聊天界面：

- **“聊天”视图**提供可随时帮你忙的 AI 助手。
- **快速聊天**窗口可用于提出快速问题，然后返回到正在执行的操作。
- **内联聊天**界面可直接在编辑器中打开，以便在编码时进行上下文交互。

“聊天”视图和“快速聊天”窗口通过 AI 启用交互式多轮次对话。 这两个接口都提供了一种方法来提问、获取有关编码问题的帮助以及生成代码。 在对话期间，GitHub Copilot 响应包括自然语言文本、代码块和其他元素。 响应中提供代码块时，可以复制代码块或将其直接注入到代码编辑器中。

内联聊天界面旨在提供编码时的上下文帮助和代码建议。

在本演示中，你将使用 GitHub Copilot 的内联聊天功能生成新的代码功能。 本演示是对上一演示中项目方案的延续。 使用准备好的示例应用 `APL2007M3SalesReport-InlineChat` 开始演示。 在演示期间，你将更新 `SalesData` 数据结构和 `GenerateSalesData` 方法。 此外，还将更新 `QuarterlySalesReport` 方法以包含其他计算和显示选项。

#### 查看编码任务和项目目标

本演示重点介绍如何使用 GitHub Copilot 加速以下任务：

1. 你将更新 `SalesData` 数据结构和 `GenerateSalesData` 方法，以生成类似于“实际”数据的数据示例。

    - dateSold：无需更改。
    - departmentName：应从 8 个部门列表中随机选择字符串值。 对于每个部门名称，请创建一个可以包含在 productID 中的 4 个字符的缩写。
    - productID：从 `int` 更改为 `string` 数据类型。 应使用模式“`DDDD-###-SS-CC-MMM`”设置 productID 值的格式，其中 ID 的组件定义如下：

        - 一个表示部门的 4 个字符的代码。
        - 一个表示产品的 3 位数字。
        - 一个表示产品大小的 2 个字符代码。
        - 一个表示产品颜色的 2 个字符的代码。
        - 一个表示制造站点的 3 个字符的代码（从 10 个制造站点列表中随机选择）。 代码应为 2 个字母的 ISO 国家/地区代码，后跟数字（例如 US1、CA2、MX3 等）。

    - quantitySold：无需更改。
    - unitPrice：将价格范围的下限提高到 25，上限提高到 300。
    - baseCost：添加项目制造成本的字段。 应使用从 unitPrice 的随机生成的折扣（5% 到 20%）生成 baseCost 值。
    - volumeDiscount：为批量折扣百分比添加字段。 分配给 volumeDiscount 的值应为 quantitySold 的 10% 的整数部分（10% 的 19 个单位 = 1% volumeDiscount）。
    - 将生成的记录数增加到 10,000。

1. 你将更新 `QuarterlySalesReport` 方法，如下所示：

    1. 显示销售结果时，按逻辑顺序列出结果。 例如，按季度列出总销售额时，应按第 1 季度到第 4 季度的顺序列出季度。
    1. 使用区域设置显示货币值。
    1. 包括季度利润和利润百分比的计算
    1. 包括每个部门的季度销售额、利润和利润百分比的计算。

#### 说明为 GitHub Copilot 对话助手开发提示的方法

GitHub Copilot 的内联聊天功能使用你提交的提示来了解你正尝试解决的任务或问题。 提示应具体且简洁。 好的提示会产生较好的响应。

为 GitHub Copilot 开发提示时，请考虑以下最佳做法：

- 在具体化的同时保持简单：提供清晰且简洁的提示来描述你正尝试解决的任务或问题。 避免使用可能会使 AI 感到困惑的复杂语言或术语。
- 使用自然语言：用对话的语气写提示。 使用与同事或团队成员交谈时会使用的自然语言。
- 拆分复杂任务：如果任务很复杂，请将其拆分为较小的步骤。 为每个步骤提供提示，以帮助 GitHub Copilot 生成正确的代码。
- 提供上下文：包含有助于 GitHub Copilot 了解你正尝试解决的任务或问题的相关信息。 包括与提示相关的数据、变量或代码块的详细信息。
- 使用聊天参与者、斜杠命令和聊天变量：GitHub Copilot 的内联聊天功能支持聊天参与者、斜杠命令和聊天变量。 使用这些功能与 GitHub Copilot 交互并为提示提供额外的上下文。

### 使用内联聊天生成数据结构

项目通常从固定或已知的特征或参数开始。 通常从选择数据源或创建示例数据着手。

在演示的这一部分，你将使用数据结构来帮助创建模拟的销售数据。 更新 `QuarterlySalesReport` 方法时，数据为 GitHub Copilot 提供了有用的上下文。

> [!NOTE]
> 在实际的业务项目中，你可能使用历史数据来生成模拟数据。 在此训练中，生成模拟数据提供了使用 GitHub Copilot 工具练习的机会。 不建议将进行数据模拟作为业务项目的最佳做法。

项目目标指示需要处理以下数据结构：

- 需要 8 个部门名称的列表。 应使用 4 个字符的字符串缩写每个部门名称。 为虚构公司（如服装或体育设备）选择行业，然后让 GitHub Copilot 生成部门名称和 4 个字符代码的字典。
- 需要 10 个制造站点的列表。 每个站点都应由 3 个字符的代码表示。 这些代码可以是 2 个字母的 ISO 国家/地区代码，后跟数字（例如 US1、CA2、MX3 等）。 让 GitHub Copilot 使用 3-4 国家/地区代码生成 10 个制造站点的字典。
- 需要更新 `SalesData` 数据结构。 需要包括部门代码、制造站点代码的新字段。 还需要将 productID 的数据类型从 `int` 更改为 `string`。

若要创建和更新数据结构，请完成以下步骤：

1. 在 Visual Studio Code 中打开 **APL2007M3SalesReport-InlineChat** 项目文件夹。

1. 确保应用程序运行并生成类似于以下输出的报告：

    ```plaintext
    Quarterly Sales Report
    ----------------------
    Q3: $690095.7142725277
    Q4: $600536.3320750712
    Q2: $678194.7943550209
    Q1: $595963.0477790226
    ```

    由于数据是随机生成的，因此每次运行时数值都会有所不同。

1. 打开 Program.cs 文件。

1. 将光标置于 `SalesData` 数据结构下方的空白行上。

1. 若要打开内联聊天界面，请按键盘上的 Ctrl+I****。

1. 输入以下提示：

    ```output
    I need a public struct ProdDepartments that contains a static string array for 8 clothing industry departments. Create separate string array containing 4-character abbreviations for each department name. The abbreviation must be unique. The department names should represent real department names for the clothing industry.
    ```

    如果你有特定的字段名称列表，则可以在提示中提供它们。 例如，实际公司数据可用于指定部门名称。

1. 查看 GitHub Copilot 提供的建议。

    只要提示明确且具体，GitHub Copilot 应提供有用的建议。 如果建议不是预期的，可以拒绝该建议，然后重试。 在这种情况下，部门的名称并不重要，因此你可以接受建议。

    数据结构应类似于以下代码：

    ```csharp

    public struct ProdDepartments
    {
        public static string[] DepartmentNames =  ["Men's Clothing", "Women's Clothing", "Children's Clothing", "Accessories", "Footwear", "Outerwear", "Sportswear", "Undergarments"];
        public static string[] DepartmentAbbreviations =  ["MENS", "WOMN", "CHLD", "ACCS", "FOOT", "OUTR", "SPRT", "UNDR" ];
    }

    ```

1. 若要接受建议，请按 Tab 键或选择“接受”****。

    还可以使用内联聊天功能来记录新代码。 选择代码，按 Ctrl+I**** 打开内联聊天，输入 `/doc`，查看建议的内联文档，然后接受更新。

1. 将光标置于 `ProdDepartments` 数据结构下方的空白行上。

1. 若要打开内联聊天界面，请按键盘上的 Ctrl+I****。

1. 输入以下提示：

    ```output
    I need a public struct ManufacturingSites that contains a static string array for 10 manSites. Manufacturing sites should be represented by a 3-character code that includes a 2-letter ISO country code followed by a digit. Use 3 ISO country codes.
    ```

    如果你有特定的字段名称列表，则可以在提示中提供它们。 例如，实际公司数据可用于指定字段名称。

1. 查看 GitHub Copilot 提供的建议。

    数据结构应类似于以下代码：

    ```csharp

    public struct ManufacturingSites
    {
        public static string[] manSites = [ "US1", "US2", "US3", "UK1", "UK2", "UK3", "JP1", "JP2", "JP3", "MX1" ];
    }

    ```

1. 若要接受建议，请按 Tab 键或选择“接受”****。

1. 选择 `SalesData` 数据结构，然后按 Ctrl+I**** 打开内联聊天界面。

    需要将 `baseCost` 和 `volumeDiscount` 字段添加到 `SalesData` 数据结构（`double` 和 `int`）。 还需要将 `productID` 的数据类型从 `int` 更改为 `string`。

1. 输入以下提示：

    ```output
    add double field baseCost and int field volumeDiscount to SalesData. Change productID from int to string.
    ```

    在实际操作中，手动进行这些更改可能更容易。 但是，使用 GitHub Copilot 可帮助你了解如何构建提示以获取更好的结果。

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”。****

    更新的 SalesData 数据结构应类似于以下代码：

    ```csharp

    public struct SalesData
    {
        public DateOnly dateSold;
        public string departmentName;
        public string productID;
        public int quantitySold;
        public double unitPrice;
        public double baseCost;
        public int volumeDiscount;
    }

    ```

有了新的和更新的数据结构，现在可以更新 `GenerateSalesData` 方法。

### 使用内联聊天更新 GenerateSalesData 方法

项目目标指示需要更新 `GenerateSalesData` 方法以生成类似于“实际”数据的数据示例。 你已更新 `SalesData` 数据结构，以包含部门代码和制造站点代码的新字段。 你还将 `productID` 的数据类型从 `int` 更改为 `string`。 现在，需要更新 `GenerateSalesData` 方法，以便为更新的字段生成数据。

需要实现以下更新：

- departmentName：更新分配的值。 从 `ProdDepartments` 数据结构中分配随机选择的部门名称。
- productID：更新分配的值。 使用模式“`DDDD-###-SS-CC-MMM`”设置 productID 的格式，其中 ID 的组件定义如下：

    - 一个表示部门的 4 个字符的代码。 使用与分配的部门名称对应的 `ProdDepartments` 数据结构中的缩写。
    - 一个表示产品的 3 位数。 第一个数字应该是随机选择的部门的索引号。 接下来的两位数字应该是从 1 到 99 的随机数，但包括前导 0。 例如，1 应格式化为 01。
    - 一个表示产品大小的 2 个字符的代码。 从 5 种大小的列表中选择产品大小：XS、S、M、L、XL。
    - 一个表示产品颜色的 2 个字符的代码。 从 8 个 2 位字符的颜色缩写列表中选择产品颜色：BK、BL、GR、RD、YL、OR、WT、GY。
    - 一个表示制造站点的 3 个字符的代码。 从 `ManufacturingSites` 数据结构中随机选择一个制造站点。

- unitPrice：将价格范围的下限提高到 25，上限提高到 300。 假设大小和颜色不会影响单位价格。
- baseCost：为代表制造成本的 baseCost 赋值。 可以使用从 unitPrice的随机生成的折扣（5% 到 20%）生成值。 虽然不够真实，但对于本次演示来说是可以接受的。
- volumeDiscount：向 volumeDiscount 分配一个值，该值代表向零售买家授予的百分比折扣。 分配给 volumeDiscount 的值应为 quantitySold 的 10% 的整数部分（10% 的 19 个单位 = 1% volumeDiscount）。

若要更新 `GenerateSalesData` 方法，请完成以下步骤：

1. 在 Program.cs 文件中找到 `GenerateSalesData` 方法。

1. 选择用于分配 `departmentName` 值的代码行。

1. 若要打开内联聊天界面，请按键盘上的 Ctrl+I****。

1. 输入以下提示：

    ```output
    Update the departmentName assignment to randomly select a department name. Use the ProdDepartments data structure. 
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 在 `departmentName` 赋值后创建三个空白代码行。

1. 花点时间考虑如何构造分配给 `productID` 的值。

    productID 值的格式应为“`DDDD-###-SS-CC-MMM`”，其中 ID 的组件定义如下：

    - `DDDD` 是表示部门的 4 个字符的代码。 使用与分配的部门名称对应的 `ProdDepartments` 数据结构中的缩写。
    - `###` 是表示产品的 3 个数字字符。 第一位数字是部门的索引号。 接下来是带前导 0 的随机数 1-99（例如：“07”）。
    - `SS` 是表示产品大小的 2 个字符的代码。 从 5 种大小的列表中选择产品大小：XS、S、M、L、XL。
    - `CC` 是表示产品颜色的 2 个字符的代码。 从 8 个 2 位字符的颜色缩写列表中选择产品颜色：BK、BL、GR、RD、YL、OR、WT、GY。
    - `MMM` 是表示制造站点的 3 个字符的代码。 从 `ManufacturingSites` 数据结构中随机选择一个制造站点。

    此格式设置规范太复杂，无法描述为单个提示。 它应分解为较小的步骤。

    值得注意的是，所选 departmentName 的索引号可用于选择 departmentAbbreviation 并计算产品编号的第一位数字。

1. 复制以下变量声明，并将其粘贴到所创建的第二个空白代码行的位置。

    ```csharp

    int indexOfDept = 0;
    string deptAbb = "";
    string firstDigit = "";
    string nextTwoDigits = "";
    string sizeCode = "";
    string colorCode = "";
    string manufacturingSite = "";

    ```

    变量声明之前和之后应该有一个空白代码行。

    内联聊天无需变量声明即可从提示生成代码更新建议，但变量声明确实有助于将 GitHub Copilot 定位到更新所属的特定代码行。

1. 选择 `int indexOfDept = 0;` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Assign the array index for departmentName to indexOfDept.
    ```

1. 查看 GitHub Copilot 提供的建议。

    应会看到一个建议，该建议将对应于所选 departmentName 的数组索引号分配给 indexOfDept。

    如果未收到预期建议，可以选择“放弃”**** 拒绝建议，然后重试。 以下提示为分配提供其他上下文：

    ```output
    Create an int named indexOfDept. Assign the array index number corresponding to the selected departmentName to indexOfDept.
    ```

    此提示指定创建名为 `indexOfDept` 的整数变量以及如何赋值。 可以在不创建/选择变量声明的情况下运行此提示，但在未选择任何代码的情况下打开内联聊天时，GitHub Copilot 有时会丢失其定位点。

    > [!NOTE]
    > 可通过“**切换更改**”按钮（位于“**接受**”和“**放弃**”按钮右侧的“**更多操作**”下拉菜单中）来显示或隐藏建议更新中删除的代码。 想要查看原始代码和建议的代码更新时，这会很有用。

1. 若要接受 GitHub Copilot 提供的建议，请选择“接受”****。

1. 选择 `string deptAbb = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Use indexOfDept to assign a department abbreviation to deptAbb.
    ```

1. 查看 GitHub Copilot 提供的建议。

    应会看到一个建议，该建议将对应于所选 departmentName 的数组索引号分配给 indexOfDept。

1. 若要接受 GitHub Copilot 提供的建议，请选择“接受”****。

1. 选择 `string firstDigit = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Assign indexOfDept + 1 to firstDigit.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 选择 `string string nextTwoDigits = ""; = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Assign a random number 1-99 to nextTwoDigits. Include a leading 0 for numbers less than 10.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 选择 `string sizeCode = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    From the list {XS, S, M, L, XL}, randomly select a product size and assign it to sizeCode.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

    在这种情况下，应会看到一个建议，该建议将随机选择的产品大小分配给 `sizeCode` 变量。 GitHub Copilot 可能会建议使用一行或多行代码行来满足此提示的要求。 无论哪种方式，它都可能会建议创建一个产品大小的字符串数组，然后使用 `random` 将其中一个大小分配给 `sizeCode`。

1. 选择 `string colorCode = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    From the list {BK, BL, GR, RD, YL, OR, WT, GY}, randomly select a product color and assign it to colorCode.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 选择 `string manufacturingSite = "";` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Assign a randomly selected manufacturing site to manufacturingSite.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 花点时间查看你的代码。

    应该有一系列代码行，这些代码行将值分配给用于构造 productID 的变量。 下一步是构造 productID 值。

    ```csharp

    int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
    string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
    string firstDigit = (indexOfDept + 1).ToString();
    string nextTwoDigits = random.Next(1, 100).ToString("D2");
    string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
    string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
    string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];

    ```

1. 选择 `salesData[i].productID = random.Next(1, 101);` 代码行，打开内联聊天，然后输入以下提示：

    ```output
    Add a "-" to deptAbb, nextTwoDigits, sizeCode, and colorCode. Combine deptAbb, firstDigit, nextTwoDigits, sizeCode, colorCode, and manufacturingSite to create the productID.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

    应会看到使用前面分配的变量构造 productID 值的建议。 建议应包含将 productID 格式化为“`DDDD-###-SS-CC-MMM`”的必要代码。

1. 手动更新 `unitPrice` 分配，以使用范围 25 到 300，如下所示：

    ```csharp
    salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
    ```

1. 在 `unitPrice` 分配后创建一个空白行。

1. 接受出现的代码行完成：

    GitHub Copilot 应提供一个建议，该建议将值分配给与以下代码行类似的 `baseCost`：

    ```csharp
    salesData[i].baseCost = random.Next(10, 100) + random.NextDouble();
    ```

1. 选择用于为 `salesData[i].baseCost` 赋值的代码行，打开内联聊天，然后输入以下提示：

    ```output
    Discount the unitPrice by a random percentage between 5 and 20. Assign the result to baseCost.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 在 `baseCost` 分配后创建一个空白行，并接受出现的代码行完成。

    GitHub Copilot 应提供为 `volumeDiscount` 赋值的建议。

1. 选择用于为 `salesData[i].volumeDiscount` 赋值的代码行，打开内联聊天，然后输入以下提示：

    ```output
    Assign 10 percent of quantitySold to volumeDiscount. Truncate any fractional values.
    ```

1. 查看 GitHub Copilot 提供的建议，然后选择“接受”****。

1. 更新的 GenerateSalesData 方法现在应类似于以下代码片段：

    ```csharp

    public SalesData[] GenerateSalesData()
    {
        SalesData[] salesData = new SalesData[1000];
        Random random = new Random();
        for (int i = 0; i < 1000; i++)
        {
            salesData[i].dateSold = new DateOnly(2023, random.Next(1, 13), random.Next(1, 29));
            salesData[i].departmentName = ProdDepartments.departmentNames[random.Next(0, ProdDepartments.departmentNames.Length)];
            int indexOfDept = Array.IndexOf(ProdDepartments.departmentNames, salesData[i].departmentName);
            string deptAbb = ProdDepartments.departmentAbbreviations[indexOfDept];
            string firstDigit = (indexOfDept + 1).ToString();
            string nextTwoDigits = random.Next(1, 100).ToString("D2");
            string sizeCode = new string[] { "XS", "S", "M", "L", "XL" }[random.Next(0, 5)];
            string colorCode = new string[] { "BK", "BL", "GR", "RD", "YL", "OR", "WT", "GY" }[random.Next(0, 8)];
            string manufacturingSite = ManufacturingSites.manufacturingSites[random.Next(0, ManufacturingSites.manufacturingSites.Length)];
            salesData[i].productID = $"{deptAbb}-{firstDigit}{nextTwoDigits}-{sizeCode}-{colorCode}-{manufacturingSite}";
            salesData[i].quantitySold = random.Next(1, 101);
            salesData[i].unitPrice = random.Next(25, 300) + random.NextDouble();
            salesData[i].baseCost = salesData[i].unitPrice * (1 - (random.Next(5, 21) / 100.0));
            salesData[i].volumeDiscount = (int)(salesData[i].quantitySold * 0.1);
        }
        return salesData;
    }

    ```

1. 保存所做更改。

### 使用内联聊天更新 QuarterlySalesReport 方法

需要更新 `QuarterlySalesReport` 方法。 根据项目目标，需要实现以下更新：

- 显示销售结果时，按逻辑顺序列出结果。 例如，按季度列出总销售额时，应按第 1 季度到第 4 季度的顺序列出季度。
- 使用区域设置显示货币值。
- 添加季度利润和利润百分比的计算
- 添加特定于各个部门的计算：季度销售额、利润和利润百分比。
- 添加特定制造位置的计算：季度销售额、利润和利润百分比。

此时，方法 `QuarterlySalesReport` 应类似于以下代码片段：

```csharp

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
        Console.WriteLine("{0}: ${1}", quarter.Key, quarter.Value);
    }
}

```

若要更新 `QuarterlySalesReport` 方法，请完成以下步骤：

1. 若要验证当前季度销售报告输出，请运行应用程序。

    应会看到控制台窗口中显示的季度销售结果列表。 使用随机值，因此数值数据因每次运行而异。

    季度销售报告输出应如下所示：

    ```output
    Quarterly Sales Report
    ----------------------
    Q3: $2060165.1045630067
    Q2: $2000706.5521363618
    Q4: $2168920.603583816
    Q1: $2174302.3663762277
    ```

    请注意，季度未按顺序列出，货币值的格式不正确。

    你的第一个任务是解决这些问题。

1. 在 Program.cs 文件中找到 `QuarterlySalesReport` 方法。

1. 选择整个方法。

1. 打开内联聊天界面，然后输入以下提示：

    ```output
    Update the QuarterlySalesReport method to display quarterly results in order. Format currency using regional settings. 
    ```

1. 花点时间查看 GitHub Copilot 提供的建议。

    应会看到一个建议，其中包含计算季度利润和利润百分比所需的代码。 建议应包括必要的代码来计算每个季度的利润和利润百分比。

1. 若要接受 GitHub Copilot 提供的建议，请选择“接受”****。

1. 保存所做更改。

1. 运行应用程序并验证季度销售结果现在是否按顺序显示，并正确设置货币值的格式。

    虽然数值不同，但季度销售报告输出的格式应与以下输出类似：

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: $2,174,302.37
    Q2: $2,000,706.55
    Q3: $2,060,165.10
    Q4: $2,168,920.60

    ```

    下一步是添加季度利润和利润百分比的计算。

1. 在 Program.cs 文件中找到 `QuarterlySalesReport` 方法。

1. 选择整个方法。

1. 打开内联聊天界面，然后输入以下提示：

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly profit and profit percentage. Include the new calculations in the report output.
    ```

1. 花点时间查看 GitHub Copilot 提供的建议。

    应会看到一个建议，其中包含计算季度利润和利润百分比所需的代码。 建议应包括必要的代码来计算每个季度的利润和利润百分比。

1. 若要接受 GitHub Copilot 提供的建议，请选择“接受”****。

1. 针对剩余的建议继续选择“接受”****。

1. 保存所做更改。

1. 运行应用程序并验证季度销售结果现在是否包括利润和利润百分比的计算。

    虽然数值不同，但季度销售报告输出的格式应与以下输出类似：

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $1,881,091.17, Profit: $231,351.24, Profit Percentage: 12.00%
    Q2: Sales: $1,949,240.91, Profit: $244,649.35, Profit Percentage: 11.00%
    Q3: Sales: $2,298,017.35, Profit: $273,622.53, Profit Percentage: 5.00%
    Q4: Sales: $2,279,185.96, Profit: $272,548.80, Profit Percentage: 16.00%    

    ```

    下一步是按部门添加季度销售额、利润和利润百分比的计算。

1. 选择整个方法。

1. 打开内联聊天界面，然后输入以下提示：

    ```output
    Update the QuarterlySalesReport method to include calculations for quarterly sales, profit, and profit percentage by department. Include the new calculations in the report output. 
    ```

1. 花点时间查看 GitHub Copilot 提供的建议。

    应会看到一个建议，其中包含计算季度利润和利润百分比所需的代码。 建议应包括必要的代码来计算每个季度的利润和利润百分比。

1. 若要接受 GitHub Copilot 提供的建议，请选择“接受”****。

1. 针对剩余的建议继续选择“接受”****。

1. 保存所做更改。

1. 运行应用程序并验证季度销售结果现在是否包括利润和利润百分比的计算。

    虽然数值不同，但季度销售报告输出的格式应与以下输出类似：

    ```output
    Quarterly Sales Report
    ----------------------
    Q1: Sales: $2,043,493.57, Profit: $262,571.72, Profit Percentage: 14.00%
    By Department:
    Department: Accessories, Sales: $188,977.90, Profit: $25,229.53, Profit Percentage: 14.00%
    Department: Children's Clothing, Sales: $186,552.49, Profit: $25,511.74, Profit Percentage: 13.00%
    Department: Footwear, Sales: $293,706.49, Profit: $39,224.99, Profit Percentage: 19.00%
    Department: Men's Clothing, Sales: $301,385.47, Profit: $36,756.06, Profit Percentage: 19.00%
    Department: Outerwear, Sales: $238,099.65, Profit: $24,371.92, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $251,349.38, Profit: $34,142.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $297,690.60, Profit: $35,305.13, Profit Percentage: 9.00%
    Department: Women's Clothing, Sales: $285,731.58, Profit: $42,029.95, Profit Percentage: 19.00%
    
    Q2: Sales: $1,925,948.90, Profit: $232,929.95, Profit Percentage: 17.00%
    By Department:
    Department: Accessories, Sales: $251,572.42, Profit: $33,250.17, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $311,862.99, Profit: $36,537.33, Profit Percentage: 8.00%
    Department: Footwear, Sales: $203,148.87, Profit: $23,041.46, Profit Percentage: 11.00%
    Department: Men's Clothing, Sales: $229,781.14, Profit: $26,226.68, Profit Percentage: 9.00%
    Department: Outerwear, Sales: $211,610.47, Profit: $23,684.65, Profit Percentage: 9.00%
    Department: Sportswear, Sales: $204,083.63, Profit: $20,750.56, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $264,733.26, Profit: $35,155.66, Profit Percentage: 15.00%
    Department: Women's Clothing, Sales: $249,156.13, Profit: $34,283.45, Profit Percentage: 17.00%
    
    Q3: Sales: $2,113,223.50, Profit: $256,591.16, Profit Percentage: 7.00%
    By Department:
    Department: Accessories, Sales: $288,161.91, Profit: $32,279.54, Profit Percentage: 10.00%
    Department: Children's Clothing, Sales: $198,313.55, Profit: $24,146.72, Profit Percentage: 7.00%
    Department: Footwear, Sales: $205,840.60, Profit: $27,630.49, Profit Percentage: 5.00%
    Department: Men's Clothing, Sales: $229,279.26, Profit: $26,618.62, Profit Percentage: 13.00%
    Department: Outerwear, Sales: $353,696.46, Profit: $44,634.82, Profit Percentage: 14.00%
    Department: Sportswear, Sales: $229,490.12, Profit: $27,697.91, Profit Percentage: 5.00%
    Department: Undergarments, Sales: $316,942.44, Profit: $40,518.71, Profit Percentage: 5.00%
    Department: Women's Clothing, Sales: $291,499.15, Profit: $33,064.35, Profit Percentage: 10.00%
    
    Q4: Sales: $1,896,279.88, Profit: $248,226.28, Profit Percentage: 15.00%
    By Department:
    Department: Accessories, Sales: $336,698.68, Profit: $44,714.55, Profit Percentage: 11.00%
    Department: Children's Clothing, Sales: $193,345.18, Profit: $23,261.33, Profit Percentage: 13.00%
    Department: Footwear, Sales: $215,183.23, Profit: $29,616.00, Profit Percentage: 15.00%
    Department: Men's Clothing, Sales: $171,663.38, Profit: $24,299.37, Profit Percentage: 5.00%
    Department: Outerwear, Sales: $229,791.52, Profit: $28,211.17, Profit Percentage: 15.00%
    Department: Sportswear, Sales: $230,031.90, Profit: $32,732.40, Profit Percentage: 8.00%
    Department: Undergarments, Sales: $300,824.19, Profit: $34,649.79, Profit Percentage: 6.00%
    Department: Women's Clothing, Sales: $218,741.80, Profit: $30,741.67, Profit Percentage: 20.00%

    ```

### 总结

在本演示中，你使用内联聊天功能更新了 `GenerateSalesData` 和 `QuarterlySalesReport` 方法。 已将新字段添加到 `SalesData` 数据结构，然后更新 `GenerateSalesData` 方法以生成新字段的数据。 你还更新了 `QuarterlySalesReport` 方法，以包括季度利润和利润百分比的计算。 此外，还按部门添加了季度销售额、利润和利润百分比的计算。
