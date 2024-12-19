---
lab:
  title: 实验室：使用 GitHub Copilot 加速应用开发
  type: Answer Key
  module: Modules 2-5
---

# 实验室：使用 GitHub Copilot 加速应用开发
# 学生实验室答案要点

## 第 1 部分：使用 GitHub Copilot 工具分析和记录代码

### 开始之前

#### 项目概述

假设你是一名为区域 IT 部门工作的软件开发人员。 你处理的大部分应用程序都支持本地社区。 最近，社区图书馆的服务器意外受损，需要数周时间才能获得授权来更换它们。 你的部门需要制定一个临时解决方案，让图书馆管理员能够执行基本功能。

你的团队已经见过了图书馆管理员。 他们需要一个最基础的解决方案，即他们能够为图书馆读者提供借书和还书等基本服务。 你的团队调查了可用的资源并制定了一个计划。 最初，只有你和另一位同事将分配到该项目。 在临时解决方案可用之前，地方政府已关闭该图书馆。 你有三天时间开发一个 v1 解决方案，使图书馆能够重开。

当同事开始处理该软件时，你使用图书馆记录创建 JSON 文件来表示图书馆的读者帐户、书籍和借书情况。 到第二天结束时，你可以开始帮助编写代码。 该解决方案是可在该图书馆的某个笔记本电脑上运行的控制台应用程序。 图书馆管理员们明白没有时间制作漂亮的界面，但重点是应用必须安全可靠。 在演示 1.0 版本的应用之前，你还有一天的时间。

你将使用 GitHub Copilot 帮助尽可能高效地完成工作。 如果一切顺利，你的应用今后将用于支持图书馆的图书募捐活动和其他场外活动。

#### 实验室方案（第 1 部分）

GitHub Copilot 可通过生成解释和文档来帮助你了解和记录代码库。

在本实验室的第 1 部分，你将使用 GitHub Copilot 分析和记录图书馆应用程序。 你还将为图书馆应用程序创建一个 GitHub 存储库，并使用 GitHub Copilot 为该存储库生成一个 README 文件。

第 1 部分包括以下练习：

- 为 Visual Studio Code 配置 GitHub Copilot 扩展。
- 使用 GitHub Copilot 解释图书馆应用程序代码库。
- 使用 Visual Studio Code 为图书馆应用程序创建一个 GitHub 存储库。
- 使用 GitHub Copilot 扩展为存储库创建一个 README.md 文件。

### 练习 1：为 Visual Studio Code 配置 GitHub Copilot 扩展

你将使用 GitHub 帐户授权 Visual Studio Code 来验证 GitHub Copilot 订阅。

按以下步骤安装 GitHub Copilot 扩展：

1. 打开一个浏览器窗口。

1. 若要打开 GitHub Enterprise 门户，请导航到以下 URL：

    ```plaintext
    https://github.com/enterprises/Microsoft-APL/sso
    ```

1. 使用以下凭据登录 GitHub 帐户：

    电子邮件地址或用户名：`@lab.CloudPortalCredential(1).Username`

    密码：`@lab.CloudPortalCredential(1).Password`

1. 打开 Visual Studio Code。

1. 在左侧菜单中，选择“扩展”。****

1. 在“搜索市场中的扩展”文本框中，键入“GitHub Copilot”，然后按 Enter****。

1. 在经过筛选的扩展列表中，选择由 GitHub 编写的 **GitHub Copilot** 扩展。

1. 在 GitHub Copilot 扩展页上，选择“安装”****。

1. 看到“登录以使用 GitHub Copilot”通知时，请选择“**登录到 GitHub**”。

    如果看到一个对话框，指出 GitHub Copilot 想要使用 GitHub 登录，请选择“**允许**”。

    由于你已在浏览器窗口中登录到 GitHub 帐户，因此新的“验证会话”选项卡应在浏览器窗口中打开。

1. 在“验证会话”页上，选择“**继续**”。

1. 在“授权应用程序”页，选择“**授权 Visual Studio Code**”。

1. 若要返回到 Visual Studio Code，请选择“**打开**”。

1. 关闭并重新打开 Visual Studio Code。

    重启 Visual Studio Code 有助于确保 GitHub Copilot 集成到 Visual Studio Code 用户界面中。

1. 请注意，如果 Visual Studio Code 窗口处于最大化状态，顶部命令中心的右侧现在会显示“**打开聊天**”按钮。

#### 摘要 - 练习 1

在本练习中，你在 Visual Studio Code 中安装了 GitHub Copilot 扩展。 你还授权 Visual Studio Code 访问你的 GitHub 帐户。 现在，你可以使用 GitHub Copilot 来分析和记录图书馆应用程序代码库。

### 练习 2：分析图书馆应用程序代码库

在创建代码存储库和 README 文件之前，应花一些时间检查代码库。 在记录项目之前，请务必了解应用的体系结构和关键功能。 还应运行应用程序，确保它按预期运行。

#### 任务 1：在开发环境中加载图书馆应用程序

你的同事开发了图书馆应用程序的初始版本，并以 .zip 文件的形式提供。 要准备此实验室，需要执行以下操作：

- 下载包含解决方案的 zip 文件。
- 提取代码文件。
- 在 Visual Studio Code 中打开图书馆应用程序，并确保它成功构建。

按以下步骤准备图书馆应用程序：

1. 确保 Web 浏览器已打开，然后打开新的浏览器选项卡。

1. 若要下载包含代码项目的 zip 文件，请导航到以下 URL：

    ```plaintext
    https://raw.githubusercontent.com/MicrosoftLearning/APL-2007-Accelerate-app-development-by-using-GitHub-Copilot/master/LearnModuleExercises/Downloads/GuidedProjectApp.zip
    ```

    包含解决方案代码的 zip 文件，即 GuidedProjectApp.zip，应自动下载。

1. 下载完成后，关闭浏览器选项卡。

    让 GitHub 帐户的浏览器页面保持打开状态。 你将在本实验室后面部分用到它。

1. 打开 Windows 文件资源管理器，导航到“下载”文件夹。

1. 解压缩下载的项目文件。

    在开发环境中解压缩代码项目。 例如：

    1. 在本地计算机上，导航到下载文件夹。

    1. 右键单击 GuidedProjectApp.zip，然后选择“全部提取”********。

    1. 选择“完成时显示解压缩的文件”，然后选择“解压缩”。

    1. 记下解压缩的文件夹位置。

1. 将解压的文件夹 AccelerateDevGitHubCopilot 复制到易于访问的位置，例如 Windows 桌面文件夹。

1. 在 Visual Studio Code 中打开 AccelerateDevGitHubCopilot 文件夹****。

    例如：

    1. 在电脑上打开 Visual Studio Code。

    1. 在 Visual Studio Code 中的“文件”菜单上，选择“打开文件夹” 。

    1. 导航到 Windows 桌面文件夹，然后找到 **AccelerateDevGitHubCopilot** 文件夹。

    1. 选择“AccelerateDevGitHubCopilot”，然后选择“选择文件夹”********。

    1. 选择“**是，我信任作者**”。

    > [!NOTE]
    > Visual Studio Code 加载项目文件和任何所需的 .NET 更新可能需要 10-20 秒的时间。

1. 在 Visual Studio Code 的“资源管理器”视图中，选择“解决方案资源管理器”，然后验证以下项目结构：

    - AccelerateDevGitHubCopilot\
        - src\
            - Library.ApplicationCore\
            - Library.Console\
            - Library.Infrastructure\
        - tests\
            - UnitTests\

1. 确保解决方案成功生成。

    例如，在“解决方案资源管理器”视图中，右键单击“AccelerateDevGitHubCopilot”，然后选择“生成”********。

    你将看到报告了几个**警告**，但不应出现任何错误。 在本练习的后面部分，你将运行该应用程序。

    > [!NOTE]
    > 请勿安装工作负载更新，除非讲师指示你这样做。

#### 任务 2：使用 GitHub Copilot 解释图书馆应用程序代码库

GitHub Copilot 可以在解决方案和功能层面生成解释，帮助你了解不熟悉的代码库。

请使用以下步骤完成本练习的这一部分：

1. 确保已在 Visual Studio Code 中打开 AccelerateDevGitHubCopilot 解决方案。

1. 打开“聊天”视图。

    可以通过以下方式打开聊天视图：

    - 点击位于 Visual Studio Code 窗口顶部、命令中心右侧的“**打开聊天**”按钮。
    - 使用键盘快捷方式：**Ctrl+Alt+I**。
    - 打开 GitHub Copilot 状态菜单，然后选择“GitHub Copilot Chat”****。

1. 输入一个提示，以使用 GitHub Copilot 的 **@workspace** 参与者生成项目说明。

    例如，在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace Describe this project
    ```

    如果出现 Visual Studio Code 对话框，提示“GitHub Copilot Chat 想要使用 GitHub 登录”，请选择“**允许**”，然后使用你的 GitHub 帐户完成授权过程。

1. 花点时间查看 GitHub Copilot 生成的答复。

    你应会看到类似于以下说明的答复：

    ```markdown
    This project is a library management system implemented in C#. It consists of three main components:
    
    1. **Library.ApplicationCore**: This is the core application library containing the main business logic, entities, enums, and interfaces. It includes:
        - Entities such as Book, Patron, Loan, etc.
        - Enums like MembershipRenewalStatus, LoanReturnStatus, and LoanExtensionStatus.
        - Services like LoanService and PatronService.
        - Interfaces like ILoanRepository, IPatronRepository, ILoanService, and IPatronService.
    2. **Library.Console**: This is a console application that interacts with the user. It includes:
        - The main entry point in Program.cs.
        - Configuration settings in appSettings.json.
        - Console interaction logic in ConsoleApp.cs.
    3. **Library.Infrastructure**: This library handles data persistence. It includes:
        - JSON-based repositories like JsonPatronRepository and JsonLoanRepository.
        - Data loading and saving logic in JsonData.

    Additionally, there are unit tests located in the UnitTests directory, which test the functionality of the core services using the NSubstitute mocking framework and xUnit.
    
    The project uses .NET 8.0 and is configured to build and test using GitHub Actions as defined in the build-test.yml file. The solution file is AccelerateDevGitHubCopilot.sln, which includes all the projects and their configurations.
    ```

1. 使用 Visual Studio Code 的“解决方案资源管理器”视图展开项目文件夹。

1. 找到并打开 **ConsoleApp.cs** 文件。

    ConsoleApp.cs 文件位于 src/Library.Console 项目中。

1. 在“聊天”视图中输入一个提示，以生成 ConsoleApp 类的说明。

    例如，在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace #editor Describe the ConsoleApp class
    ```

1. 花几分钟时间查看答复。

    你应会看到类似于以下说明的答复：

    ```markdown
    The ConsoleApp class in ConsoleApp.cs is responsible for managing the console-based user interface of the library management system. It handles user interactions, processes user inputs, and coordinates actions with the underlying services and repositories.

    ### Fields
    - _currentState: Tracks the current state of the console application.
    - matchingPatrons: A list of patrons that match a search query.
    - selectedPatronDetails: Holds details of the currently selected patron.
    - selectedLoanDetails: Holds details of the currently selected loan.
    - _patronRepository: An instance of IPatronRepository for accessing patron data.
    - _loanRepository: An instance of ILoanRepository for accessing loan data.
    - _loanService: An instance of ILoanService for performing loan-related operations.
    - _patronService: An instance of IPatronService for performing patron-related operations.

    ### Constructor
    - ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository): Initializes the ConsoleApp with the provided services and repositories.

    ### Methods
    - Run(): The main entry point for running the console application.
    - PatronSearch(): Handles the logic for searching patrons.
    - ReadPatronName(): Reads the patron's name from the console input.
    - PrintPatronsList(List<Patron> matchingPatrons): Prints a list of matching patrons to the console.
    - PatronSearchResults(): Handles the logic for displaying and selecting from the search results.
    - ReadInputOptions(CommonActions options, out int optionNumber): Reads input options from the console.
    - WriteInputOptions(CommonActions options): Writes the available input options to the console.
    - PatronDetails(): Displays details of the selected patron.
    - LoanDetails(): Displays details of the selected loan and handles actions like extending or returning the loan.

    The class uses a state machine approach to manage different states of the console application, such as searching for patrons, displaying search results, showing patron details, and handling loan details.
    ```

1. 打开 **Program.cs** 文件。

1. 在“聊天”视图中输入一个提示，以生成 Program.cs 文件的说明。

    例如，在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace #editor Describe the Program.cs file
    ```

1. 花几分钟时间查看答复。

    你应会看到类似于以下说明的答复：

    ```markdown
    The Program.cs file is the entry point for the console application. It sets up the dependency injection container, configures services, and starts the ConsoleApp.
    
    1. **Dependency Injection Setup**:
        - Creates a ServiceCollection to register services.
        - Builds a configuration object from the appSettings.json file.
        - Registers various services and repositories with different lifetimes (singleton, scoped).
    
    2. **Service Registration**:
        - Registers the repositories: JsonPatronRepository and JsonLoanRepository.
        - Registers the services: LoanService and PatronService.
        - Registers the JsonData class as a singleton.
        - Registers the ConsoleApp class as a singleton.
    
    3. **Service Provider**:
        - Builds the service provider from the registered services.
        - Retrieves the ConsoleApp service and runs it asynchronously.

    This setup ensures that all dependencies are properly injected and configured before the application starts running.
    ```

1. 展开 Library.Infrastructure 项目，然后展开“数据”文件夹。

1. 将 **JsonData.cs**、**JsonLoanRepository.cs** 和 **JsonPatronRepository.cs** 文件添加到聊天上下文。

    可以使用拖放操作将解决方案资源管理器中的文件添加到“聊天”视图。 还可以使用“聊天”视图中的“**附加上下文**”按钮（回形针）将文件添加到聊天上下文。

1. 在“聊天”视图中输入一个提示，以生成数据访问类的说明。

    例如，在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace /explain Explain how the data access classes work
    ```

1. 花几分钟时间查看答复。

    你应会看到类似于以下说明的答复：

    ```markdown
    The data access classes in this project are designed to handle the loading, saving, and manipulation of data stored in JSON files. These classes include JsonData, JsonPatronRepository, and JsonLoanRepository. Here's an explanation of how each class works:
    
    ### JsonData Class
    The JsonData class is responsible for loading and saving data from and to JSON files. It also provides methods to populate related entities.
    
    #### Key Responsibilities:
    1. **Loading Data**: The LoadData method loads data from JSON files into in-memory collections (Authors, Books, BookItems, Patrons, Loans).
    2. **Saving Data**: The SaveJson method saves data to JSON files. Specific methods like SaveLoans and SavePatrons handle saving loans and patrons, respectively.
    3. **Ensuring Data is Loaded**: The EnsureDataLoaded method ensures that data is loaded into memory before any operations are performed.
    4. **Populating Related Entities**: Methods like GetPopulatedPatron, GetPopulatedLoan, GetPopulatedBookItem, and GetPopulatedBook populate related entities to provide a complete view of the data.
    
    #### Example Methods:
    - **LoadData**: Loads all data from JSON files.
    - **SaveLoans**: Saves loan data to the JSON file.
    - **GetPopulatedPatron**: Populates a patron with related loans.
    - **SearchBookByTitle**: Searches for a book by its title.
    
    ### JsonPatronRepository Class
    The JsonPatronRepository class implements the IPatronRepository interface and provides methods to interact with patron data.

    #### Key Responsibilities:
    1. **Searching Patrons**: The SearchPatrons method searches for patrons by name. 
    2. **Getting a Patron**: The GetPatron method retrieves a patron by ID and populates related data.
    3. **Updating a Patron**: The UpdatePatron method updates patron information and saves it to the JSON file.
    
    #### Example Methods:
    - **SearchPatrons**: Searches for patrons whose names contain the search input.
    - **GetPatron**: Retrieves a patron by ID and populates related loans.
    - **UpdatePatron**: Updates patron information and saves it to the JSON file.
    
    ### JsonLoanRepository Class
    The JsonLoanRepository class implements the ILoanRepository interface and provides methods to interact with loan data.
    
    #### Key Responsibilities:
    1. **Getting a Loan**: The GetLoan method retrieves a loan by ID and populates related data.
    2. **Updating a Loan**: The UpdateLoan method updates loan information and saves it to the JSON file.
    
    #### Example Methods:
    - **GetLoan**: Retrieves a loan by ID and populates related book items and patrons.
    - **UpdateLoan**: Updates loan information and saves it to the JSON file.
    
    ### How They Work Together
    1. **Loading Data**: When the application starts, the JsonData class loads data from JSON files into memory.
    2. **Searching and Retrieving Data**: The JsonPatronRepository and JsonLoanRepository classes use the JsonData class to search and retrieve data. They ensure data is loaded before performing operations.
    3. **Updating Data**: When data is updated, the repository classes call methods on the JsonData class to save the updated data back to the JSON files.
    4. **Populating Related Entities**: The JsonData class provides methods to populate related entities, ensuring that when a patron or loan is retrieved, it includes related data like loans or book items.
    
    ### Example Workflow
    1. **Search for a Patron**:
        - The SearchPatrons method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
        - It then searches the Patrons collection for matching names and returns the results.

    2. **Get a Loan**:
       - The GetLoan method in JsonLoanRepository calls EnsureDataLoaded to ensure data is loaded.
       - It retrieves the loan by ID and uses GetPopulatedLoan to include related book items and patrons.

    3. **Update a Patron**:
       - The UpdatePatron method in JsonPatronRepository calls EnsureDataLoaded to ensure data is loaded.
       - It updates the patron information and calls SavePatrons to save the updated data to the JSON file.

    By using these data access classes, the application can efficiently manage data stored in JSON files, ensuring that data is loaded, manipulated, and saved correctly.
    ```

1. 花几分钟时间检查用于模拟图书馆记录的 JSON 数据文件。

    JSON 数据文件位于 src/Library.Console/Json 文件夹中。

    数据文件使用 ID 属性来链接实体。 例如，Loan 对象有一个 PatronId 属性，该属性链接到具有相同 ID 的 Patron 对象。 JSON 文件包含作者、书籍、书籍项、借阅者和借阅记录的数据。

    > [!NOTE]
    > 请注意，出于本指导项目的目的，作者姓名、书籍标题和借阅者姓名已经过匿名化处理。

#### 任务 3：构建并运行应用程序

运行应用程序将帮助你了解用户界面、应用程序的关键功能以及应用组件的交互方式。

请使用以下步骤完成本练习的这一部分：

1. 确保已打开“解决方案资源管理器”视图****。

    “解决方案资源管理器”视图与“资源管理器”视图不同。 “解决方案资源管理器”视图使用项目和解决方案文件作为“目录”节点来显示解决方案的结构。

1. 若要运行该应用程序，请右键单击“Library.Console”，选择“调试”，然后选择“启动新实例”************。

    如果未显示“调试”和“启动新实例”选项，请确保使用的是“解决方案资源管理器”视图，而不是“资源管理器”视图********。

    以下步骤将引导你完成一个简单的用例。

1. 当系统提示你输入借阅者姓名时，请键入 1，然后按 Enter****。

    > [!NOTE]
    > 该应用程序使用区分大小写的搜索过程。 你必须输入大写”O”的“One”。

    你应会看到与搜索查询匹配的借阅者列表。

1. 在“输入选项”提示处键入 2，然后按 Enter****。

    输入 2 会选择列表中的第二位借阅者****。

    你应会看到借阅者的姓名和会员状态，以及书籍的借阅详细信息。

1. 在“输入选项”提示处键入 1，然后按 Enter****。

    输入 1 会选择列表中的第一本书****。

    你应会看到列出的书籍详细信息，包括到期日期和归还状态。

1. 在“输入选项”提示处键入 r，然后按 Enter****。

    输入 r 将归还书籍****。

1. 确认是否显示“书籍已成功归还。” 的消息。

    “书籍已成功归还。”的消息 后面应该是书籍详细信息。 归还的书籍标记为 **Returned: True**。

1. 若要开始新的搜索，请键入 s，然后按 Enter****。

1. 当系统提示你输入借阅者姓名时，请键入 1，然后按 Enter****。

1. 在“输入选项”提示处键入 2，然后按 Enter****。

1. 确认第一本书籍的借阅记录是否标记为 **Returned: True**。

1. 在“输入选项”提示处键入 q，然后按 Enter****。

1. 停止调试会话。

#### 摘要 - 练习 2

本练习让你了解了图书馆应用程序代码库以及应用程序如何与用户交互。 你使用 GitHub Copilot 为项目结构、所选文件和数据访问类生成说明。 你还运行了该应用程序，以了解控制台界面的工作原理以及应用程序组件如何交互。

### 练习 3：创建 GitHub 存储库和空自述文件

为代码创建 GitHub 存储库，可以方便你与他人分享工作成果并协作处理项目。

#### 任务 1：创建 GitHub 存储库

请使用以下步骤完成本练习的这一部分：

1. 确保在浏览器窗口中打开 GitHub 帐户。

    如有必要，请打开浏览器窗口并使用以下信息登录：

    URL：`https://github.com/enterprises/Microsoft-APL/sso`

    电子邮件地址或用户名：`@lab.CloudPortalCredential(1).Username`

    密码：`@lab.CloudPortalCredential(1).Password`

1. 打开 GitHub 帐户菜单，然后选择“你的存储库”****。

    你应该会看到一条消息，指示你还没有任何存储库。

1. 若要构造使用 GitHub 帐户凭据的 Git 配置命令，请打开“**记事本**”，然后生成以下 Git 命令：

    ```bash
    git config --global user.email "lab assigned email"
    git config --global user.name "user name"
    ```

    将 **"lab assigned email"** 替换为在实验室环境中定义的电子邮件：`@lab.CloudPortalCredential(1).Username`

    将 **"user name"** 替换为你自己的名字。

1. 切换到“Visual Studio Code”窗口。

1. 打开 Visual Studio Code 的集成终端。

    在“终端”菜单中，选择“新建终端”。****

1. 若要使用与 GitHub 帐户关联的凭据配置 Git，请输入你在记事本中构造的两个命令。

1. 在 Visual Studio Code 中，打开“源代码管理”视图。

1. 选择“发布到 GitHub”****。

    如果打开一个对话框，要求使用 GitHub 帐户登录，请完成以下步骤：

    1. 选择**允许**。
    1. 选择你在此实验室环境中使用的帐户。
    1. 如有必要，请再次选择“**发布到 GitHub**”。

1. 接受存储库的默认名称 (AccelerateDevGitHubCopilot)，然后选择“**发布到 GitHub 专用存储库**”。

    请注意，Visual Studio Code 会在发布过程中显示状态消息。

    系统可能会要求你再次授权 GitHub 帐户。 如果是这样，请按照屏幕上的说明在浏览器中授权帐户。 这可能导致使用“首次提交”提交消息发布到存储库。

1. 如果代码未发布到存储库，并且返回到“源代码管理”视图，请输入提交消息，然后选择“**发布分支**”。

    发布过程完成后，你将看到一条消息，告知你代码已成功发布到指定的 GitHub 存储库。

#### 任务 2：在 GitHub 中创建空自述文件

请使用以下步骤完成本练习的这一部分：

1. 切换到显示 GitHub 帐户的浏览器窗口。

1. 在 GitHub 帐户中打开新的 AccelerateDevGitHubCopilot 存储库。

    如果未看到 AccelerateDevGitHubCopilot 存储库，请刷新页面。 如果仍然看不到存储库，请尝试以下步骤：

    1. 切换到“Visual Studio Code”。
    1. 打开通知（发布新存储库时会生成一个通知）。
    1. 选择“在 GitHub 上打开”以打开存储库****。

1. 在 AccelerateDevGitHubCopilot 存储库的“代码”选项卡上，选择“添加 README 文件”****。

1. 在 README.md 编辑器中，键入“即将推出”，然后选择“提交更改”********。

1. 在“提交更改”对话框中，选择“**提交更改**”。

#### 任务 3：将更改拉取到本地存储库

请使用以下步骤完成本练习的这一部分：

1. 切换到 Visual Studio Code 并确保“源代码管理”视图处于打开状态。

1. 打开“**更多操作**”菜单，然后选择“**拉取**”。

    可以使用“源代码管理”视图右上角的省略号打开“更多操作”菜单。

1. 打开“资源管理器”视图（折叠“解决方案资源管理器”并使用 Visual Studio Code 的默认文件/文件夹资源管理器），然后展开 **AccelerateDevGitHubCopilot** 文件夹。

1. 打开 README.md 文件。

    你应会看到消息“即将推出”。

    > [!NOTE]
    > 可以直接在 Visual Studio Code 中创建自述文件内容，然后将更新推送到 GitHub 存储库。

在下一个练习中，你将使用 GitHub Copilot Chat 更新存储库的自述文件。

#### 摘要 - 练习 3

通过本练习，你为图书馆应用程序创建了 GitHub 存储库，并创建了一个空自述文件。 你还拉取了对本地存储库的更改，以确保你拥有最新的更新。

### 练习 4：为自述文件创建项目文档

README 文件是每个 GitHub 存储库的重要组成部分。 README 文件根据项目、项目参与者和利益干系人的需求提供信息。

对于本指导项目练习，README 文件应包含以下部分：

- **项目标题**：简明扼要的项目标题。
- **说明**：项目的详细介绍及用途说明。
- **项目结构**：对项目结构的分析，包括关键文件夹和文件。
- **关键类和接口**：项目中关键类和接口的列表。
- **用法**：有关如何使用项目的说明，通常包括代码示例。
- **许可证**：项目所使用的许可证。

#### 任务 1：使用 GitHub Copilot 生成项目文档

在本练习的这一部分中，你将使用 GitHub Copilot 创建项目文档，并将其添加到 README.md 文件。

请使用以下步骤完成本练习的这一部分：

1. 打开“聊天”视图。

    当你对特定的代码或文件感兴趣时，可以使用拖放操作将文件添加到“聊天”视图上下文。 在这种情况下，你对整个解决方案感兴趣，因此你将使用 `@workspace` 参与者，而不是添加单个文件。

1. 若要为 README 文件生成项目文档，请输入以下提示：

    ```plaintext
    @workspace Generate the contents of a README.md file for the code repository. Use "Library App" as the project title. The README file should include the following sections: Description, Project Structure, Key Classes and Interfaces, Usage, License. Format all sections as raw markdown. Use a bullet list with indents to represent the project structure. Do not include ".gitignore" or the ".github", "bin", and "obj" folders.
    ```

    > [!NOTE]
    > 使用多个提示，README 文件的每个部分分别对应一个提示，可以生成更详细的结果。 为了简化过程，本练习只使用一个提示。

1. 查看答复，确保每个部分的格式都设置为 Markdown。

    > [!NOTE]
    > 可以单独更新自述部分，以提供更详细的信息，或者在格式不正确时进行更正。 也可以将 GitHub Copilot 的答复复制到 README 文件中，然后直接在 Markdown 文件中进行更正。

1. 在编辑器中打开 Markdown 文件后，打开 GitHub Copilot 状态菜单，然后选择“**为 Markdown 启用补全**”。

1. 将建议的文档部分复制到 README.md 文件中。

    GitHub Copilot 可以为 Markdown 文档生成建议。 此功能可帮助你撰写 Markdown 文件并设置其格式。

    例如，可以选择 README.md 文件的内容，打开内联聊天，然后要求 GitHub Copilot“更正 Markdown 文档的格式”。

1. 根据需要调整格式，然后保存更新后的 README.md 文件。

    你应该有一个自述文件，其中包含项目标题、描述、项目结构、关键类和接口、使用说明和许可证信息。

    ```markdown
    # Library App
    
    ## Description
    Library App is a console-based application for managing library operations such as patron management, book loans, and membership renewals. It uses a JSON-based data storage system and provides various services to handle library functionalities.
    
    ## Project Structure
    - AccelerateDevGitHubCopilot.sln
    - README.md
    - src
      - Library.ApplicationCore/
        - Entities/
          - `Author.cs`
          - `Book.cs`
          - `BookItem.cs`
          - `Loan.cs`
          - `Patron.cs`
        - Enums/
          - `LoanExtensionStatus.cs`
          - `LoanReturnStatus.cs`
          - `MembershipRenewalStatus.cs`
        - Interfaces/
          - `IPatronRepository.cs`
          - `IPatronService.cs`
          - `ILoanRepository.cs`
          - `ILoanService.cs`
        - `Library.ApplicationCore.csproj`
        - Services/
          - `PatronService.cs`
          - `LoanService.cs`
      - Library.Console/
        - `appSettings.json`
        - `CommonActions.cs`
        - `ConsoleApp.cs`
        - `ConsoleState.cs`
        - `Library.Console.csproj`
        - `Program.cs`
      - Library.Infrastructure/
        - Data/
          - `JsonData.cs`
          - `JsonLoanRepository.cs`
          - `JsonPatronRepository.cs`
        - `Library.Infrastructure.csproj`
    - tests
      - UnitTests/
        - ApplicationCore/
          - LoanService/
            - `ReturnLoan.cs`
            - `ExtendLoan.cs`
          - PatronService/
            - `RenewMembership.cs`
        - `UnitTests.csproj`
    
    ## Key Classes and Interfaces
    - **Entities**
      - **Author**: Represents an author with properties like Id and Name.
      - **Book**: Represents a book with properties like Id, Title, AuthorId, Genre, ImageName, and ISBN.
      - **BookItem**: Represents a specific copy of a book with properties like Id, BookId, AcquisitionDate, and Condition.
      - **Loan**: Represents a loan with properties like Id, BookItemId, PatronId, LoanDate, DueDate, and ReturnDate.
      - **Patron**: Represents a library patron with properties like Id, Name, MembershipStart, MembershipEnd, and Loans.
    
    - **Enums**
      - **LoanExtensionStatus**: Enum for loan extension statuses.
      - **LoanReturnStatus**: Enum for loan return statuses.
      - **MembershipRenewalStatus**: Enum for membership renewal statuses.
    
    - **Interfaces**
      - **IPatronRepository**: Interface for patron repository with methods like GetPatron, SearchPatrons, and UpdatePatron.
      - **IPatronService**: Interface for patron service with method RenewMembership.
      - **ILoanRepository**: Interface for loan repository with methods like GetLoan and UpdateLoan.
      - **ILoanService**: Interface for loan service with methods like ReturnLoan and ExtendLoan.
    
    - **Services**
      - **PatronService**: Implements IPatronService to handle patron-related operations.
      - **LoanService**: Implements ILoanService to handle loan-related operations.
    
    - **Console**
      - **ConsoleApp**: Main console application class that handles user interactions and application flow.
      - **ConsoleState**: Enum for different states of the console application.
      - **CommonActions**: Enum for common actions in the console application.
    
    - **Infrastructure**
      - **JsonData**: Handles loading and saving data to JSON files.
      - **JsonLoanRepository**: Implements ILoanRepository to manage loan data.
      - **JsonPatronRepository**: Implements IPatronRepository to manage patron data.
    
    ## Usage
    1. Clone the repository.
    2. Open the solution file AccelerateDevGitHubCopilot.sln in Visual Studio.
    3. Build the solution to restore dependencies.
    4. Run the Library.Console project to start the console application.
    5. Follow the on-screen instructions to search for patrons, view patron details, extend loans, return books, and renew memberships.
    
    ## License
    This project is licensed under the MIT License.
    ```

#### 任务 2：提交和推送自述文件更新

请使用以下步骤完成本练习的这一部分：

1. 打开 Visual Studio Code 的“源代码管理”视图。

1. 若要让 GitHub Copilot 生成提交消息，请选择消息框右侧的图标。

    你应会看到一条类似于以下消息的提交消息：

    ```plaintext
    Update README.md with project description, structure, key classes, usage instructions, and license information
    ```

1. 暂存并提交文件更新。

1. 将更新同步（或推送）到 GitHub 存储库。

    如果出现提示，请使用 GitHub 凭据授权同步/推送操作。

#### 任务 3：检查你的工作

若要检查工作成果，请完成以下步骤：

1. 打开 AccelerateDevGitHubCopilot 项目的 GitHub 存储库。

1. 使用“代码”选项卡查看更新后的 README.md 文件****。

    你可能需要刷新浏览器才能看到更新后的自述文件。

1. 确保 README 文件中描述的项目结构与存储库的文件夹结构一致。

    预览自述文件时，可以使用 GitHub 界面左侧的文件树展开和查看存储库结构。

1. 查看提交历史记录并找到 GitHub Copilot 生成的提交消息。

#### 摘要 - 练习 4

通过本练习，你使用 GitHub Copilot 为自述文件创建了项目文档。 你使用 GitHub Copilot 生成了项目描述、项目结构、关键类和接口、使用说明和许可证信息。 你还将自述文件更新提交并推送到 GitHub 存储库。

## 第 2 部分：使用 GitHub Copilot 工具开发代码功能

### 开始之前

#### 项目概述

你和同事正在开会讨论图书馆应用程序的开发目标。 你希望改善图书管理员和借阅者的用户体验。 你们讨论了可以添加到该应用程序的多项新功能。

你同意开发以下功能：

- 书籍可借状态：可让图书管理员确定书籍的可借状态。 此功能应显示一条消息，指出某书籍是否可供借阅，如果该书籍当前已借给其他借阅者，该消息会显示归还截止日期。

- 书籍借阅记录：可让图书管理员将书籍借给借阅者（如果该书籍可供借阅）。 此功能应显示借阅者接收借阅书籍的选项，使用新的借阅记录更新 Loans.json，并显示借阅者的已更新借阅详细信息。

- 书籍预留：可让图书管理员为借阅者预留书籍（除非该书籍已预留）。 此功能应实现新的书籍预留过程。 此功能可能需要创建新的 Reservations.json 文件，以及支持预留过程所需的新类和接口。

你们每个人将负责开发其中的一项新功能，然后重新组合。 你将负责开发用于确定书籍可借状态的功能。 你的同事负责开发向借阅者借书的功能。 最后一项功能（为借阅者预留书籍）将在上述两项功能完成后进行开发。

#### 实验室方案（第 2 部分）

GitHub Copilot 可帮助你为图书馆应用程序开发新功能。

在本实验室的第 2 部分，你将使用 GitHub Copilot 生成代码建议，帮助你更快、更准确地实现新功能。

第 2 部分包括以下练习：

- 开发新的“书籍可借状态”功能。
- 将更改合并到存储库的主分支中。

### 练习 5：开发新的“书籍可借状态”功能。

书籍可借状态功能应包括以下代码更新：

- 实现新的 CommonActions.SearchBooks 操作，使图书馆管理员能够选择搜索书籍的选项。
- 在 ConsoleApp.cs 中创建一个新的 SearchBooks 方法。 SearchBooks 方法应读取用户提供的书名。 检查某书籍是否可供借阅，并显示消息“book.title 可借出”或“book.title 已借给其他借阅者”。 归还截止日期为 loan.DueDate。

在本练习中，你将完成以下任务：

- 在代码存储库中创建“书籍可借状态”分支。
- 使用 GitHub Copilot 建议来帮助实现可由图书馆管理员选择的新的 SearchBooks 常见操作。
- 使用 GitHub Copilot 建议帮助开发 SearchBooks 方法。该方法可读取用户提供的书名，检查此书是否可供借阅，并显示一条消息，指示此书的可借状态。

#### 任务 1：在存储库中创建新分支

在开始开发新的“书籍可借状态”功能之前，需要在存储库中创建新分支。 这样便可以开发新功能且不会影响存储库的 main 分支。 准备就绪后，可以将新功能合并到 main 分支中。

请使用以下步骤完成本练习的这一部分：

1. 确保已在 Visual Studio Code 中打开 AccelerateDevGitHubCopilot 解决方案。

1. 选择“源代码管理”视图，并确保本地存储库已与远程存储库同步（“拉取”或“同步”）。

1. 在窗口左下角，选择“main”****。

1. 若要创建新分支，请键入“**书籍可借状态**”，然后选择“**+ 创建新分支**”。

1. 若要将新分支推送到远程存储库，请选择“发布分支”****。

#### 任务 2：实现新的“SearchBooks”常见操作

在本练习的这一部分，你将使用 GitHub Copilot 来帮助实现名为 SearchBooks 的菜单选项。 图书馆管理员将选择 SearchBooks 操作来检查书籍的可借状态。

以下是在此任务期间完成的文件更新：

- 更新 CommonActions.cs 中的 CommonActions 枚举：向 CommonActions 枚举添加新的 SearchBooks 操作。
- 更新 ConsoleApp.cs 中的 WriteInputOptions 方法：添加对显示新 CommonActions.SearchBooks 选项的支持。
- 更新 ConsoleApp.cs 中的 ReadInputOptions 方法：添加对读取（选择）新 CommonActions.SearchBooks 选项的支持。
- 更新 ConsoleApp.cs 中的 PatronDetails 方法：添加对在选中新的 CommonActions.SearchBooks 选项时对处理该选项的支持。

请使用以下步骤完成本练习的这一部分：

1. 打开“解决方案资源管理器”视图。

1. 打开 CommonActions.cs 文件，然后选择 **CommonActions** 枚举。

    需要向 CommonActions 添加新的 SearchBooks 操作。

1. 打开内联聊天，然后输入以下提示：

    ```plaintext
    Update selection to include a new `SearchBooks` action.
    ```

    GitHub Copilot 应该建议进行代码更新，以将新的 SearchBooks 操作添加到 CommonActions 枚举。

1. 查看建议的更新，然后选择“接受”****。

    ```csharp

    public enum CommonActions
    {
        Repeat = 0,
        Select = 1,
        Quit = 2,
        SearchPatrons = 4,
        RenewPatronMembership = 8,
        ReturnLoanedBook = 16,
        ExtendLoanedBook = 32,
        SearchBooks = 64
    }

    ```

1. 打开 ConsoleApp.cs 文件。

1. 找到并选择 **WriteInputOptions** 方法。

    需要添加对新 CommonActions.SearchBooks 选项的支持。 显示用于检查书籍是否可供借阅的选项。

1. 打开内联聊天，然后输入以下提示：

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action. Use the letter "b" and the message "to check for book availability".
    ```

    GitHub Copilot 应建议进行代码更新，为 SearchBooks 操作添加新的“if”块。

1. 查看建议的更新，然后选择“接受”****。

    建议的更新应类似于以下代码片段：

    ```csharp

    static void WriteInputOptions(CommonActions options)
    {
        Console.WriteLine("Input Options:");
        if (options.HasFlag(CommonActions.ReturnLoanedBook))
        {
            Console.WriteLine(" - \"r\" to mark as returned");
        }
        if (options.HasFlag(CommonActions.ExtendLoanedBook))
        {
            Console.WriteLine(" - \"e\" to extend the book loan");
        }
        if (options.HasFlag(CommonActions.RenewPatronMembership))
        {
            Console.WriteLine(" - \"m\" to extend patron's membership");
        }
        if (options.HasFlag(CommonActions.SearchPatrons))
        {
            Console.WriteLine(" - \"s\" for new search");
        }
        if (options.HasFlag(CommonActions.SearchBooks))
        {
            Console.WriteLine(" - \"b\" to check for book availability");
        }
        if (options.HasFlag(CommonActions.Quit))
        {
            Console.WriteLine(" - \"q\" to quit");
        }
        if (options.HasFlag(CommonActions.Select))
        {
            Console.WriteLine("Or type a number to select a list item.");
        }
    }

    ```

1. 稍微向上滚动，找到 **ReadInputOptions** 方法。

1. 选择 **ReadInputOptions** 方法。

    需要添加对新 CommonActions.SearchBooks 选项的支持。 包括一个处理用户选择 SearchBooks 操作的案例。

1. 打开内联聊天，然后输入以下提示：

    ```plaintext
    Update selection to include an option for the `CommonActions.SearchBooks` action.
    ```

    GitHub Copilot 应该会建议一个代码更新，添加一个新的“案例”来处理用户选择 SearchBooks 操作。

1. 查看建议的更新，然后选择“接受”****。

    建议的更新应类似于以下代码片段：

    ```csharp

    static CommonActions ReadInputOptions(CommonActions options, out int optionNumber)
    {
        CommonActions action;
        optionNumber = 0;
        do
        {
            Console.WriteLine();
            WriteInputOptions(options);
            string? userInput = Console.ReadLine();
            action = userInput switch
            {
                "q" when options.HasFlag(CommonActions.Quit) => CommonActions.Quit,
                "s" when options.HasFlag(CommonActions.SearchPatrons) => CommonActions.SearchPatrons,
                "m" when options.HasFlag(CommonActions.RenewPatronMembership) => CommonActions.RenewPatronMembership,
                "e" when options.HasFlag(CommonActions.ExtendLoanedBook) => CommonActions.ExtendLoanedBook,
                "r" when options.HasFlag(CommonActions.ReturnLoanedBook) => CommonActions.ReturnLoanedBook,
                "b" when options.HasFlag(CommonActions.SearchBooks) => CommonActions.SearchBooks,
                _ when int.TryParse(userInput, out optionNumber) => CommonActions.Select,
                _ => CommonActions.Repeat
            };
            if (action == CommonActions.Repeat)
            {
                Console.WriteLine("Invalid input. Please try again.");
            }
        } while (action == CommonActions.Repeat);
        return action;
    }

    ```

1. 向下滚动，找到并选择 **PatronDetails** 方法。

    需要完成以下两项操作：

    - 在调用 ReadInputOptions 之前，需要将 CommonActions.SearchBooks 添加到选项。
    - 还需要添加 else if 来处理 SearchBooks 操作。 else if 块应调用名为 SearchBooks 的新方法。

    可以同时处理这两项操作。

1. 打开内联聊天，然后输入以下提示：

    ```plaintext
    Update selection to add `CommonActions.SearchBooks` to `options` before calling `ReadInputOptions`. Add an `else if` block to handle the `SearchBooks` action. The `else if` block should call a new method named `SearchBooks`.
    ```

    GitHub Copilot 应建议进行代码更新，在调用 ReadInputOptions 之前将 CommonActions.SearchBooks 添加到选项中。

1. 查看建议的更新，然后选择“接受”****。

    ```csharp

    async Task<ConsoleState> PatronDetails()
    {
        Console.WriteLine($"Name: {selectedPatronDetails.Name}");
        Console.WriteLine($"Membership Expiration: {selectedPatronDetails.MembershipEnd}");
        Console.WriteLine();
        Console.WriteLine("Book Loans:");
        int loanNumber = 1;
        foreach (Loan loan in selectedPatronDetails.Loans)
        {
            Console.WriteLine($"{loanNumber}) {loan.BookItem!.Book!.Title} - Due: {loan.DueDate} - Returned: {(loan.ReturnDate != null).ToString()}");
            loanNumber++;
        }
        CommonActions options = CommonActions.SearchPatrons | CommonActions.Quit | CommonActions.Select | CommonActions.RenewPatronMembership | CommonActions.SearchBooks;
        CommonActions action = ReadInputOptions(options, out int selectedLoanNumber);
        if (action == CommonActions.Select)
        {
            if (selectedLoanNumber >= 1 && selectedLoanNumber <= selectedPatronDetails.Loans.Count())
            {
                var selectedLoan = selectedPatronDetails.Loans.ElementAt(selectedLoanNumber - 1);
                selectedLoanDetails = selectedPatronDetails.Loans.Where(l => l.Id == selectedLoan.Id).Single();
                return ConsoleState.LoanDetails;
            }
            else
            {
                Console.WriteLine("Invalid book loan number. Please try again.");
                return ConsoleState.PatronDetails;
            }
        }
        else if (action == CommonActions.Quit)
        {
            return ConsoleState.Quit;
        }
        else if (action == CommonActions.SearchPatrons)
        {
            return ConsoleState.PatronSearch;
        }
        else if (action == CommonActions.RenewPatronMembership)
        {
            var status = await _patronService.RenewMembership(selectedPatronDetails.Id);
            Console.WriteLine(EnumHelper.GetDescription(status));
            // reloading after renewing membership
            selectedPatronDetails = (await _patronRepository.GetPatron(selectedPatronDetails.Id))!;
            return ConsoleState.PatronDetails;
        }
        else if (action == CommonActions.SearchBooks)
        {
            return await SearchBooks();
        }
        throw new InvalidOperationException("An input option is not handled.");
    }

    ```

    > [!NOTE]
    > 内联聊天建议还可以为 SearchBooks 方法创建存根代码。

#### 任务 3：开发 SearchBooks 方法

完成后，SearchBooks 方法应读取用户提供的书名，检查此书是否可供借阅，并显示一条消息，指示此书的可借状态。 该方法应使用 Books.json 和 Loans.json 文件来查找匹配的书名并确定该书的可借状态。

请使用以下步骤完成本练习的这一部分：

1. 请花点时间思考一下 SearchBooks 方法的过程要求。

    该方法需要执行哪些操作？ 它应该返回哪些信息？ 它是否需要参数？

    SearchBooks 方法应实现以下过程：

    1. 提示用户输入书籍标题。
    1. 读取用户提供的书籍标题。
    1. 检查书籍是否可供借阅
    1. 显示一条消息，其中指明了以下选项之一：

        - “book.title 可供借阅”
        - “book.title 已借给其他借阅者”。 归还截止日期为 loan.DueDate。

    若要生成消息选项，代码需要访问以下 JSON 文件：

    - 需要 Books.json 才能找到匹配的 Title 和 BookId。
    - 需要 Loans.json 才能找到匹配 BookItemId 的 ReturnDate 和 DueDate。 BookItemId 与 Books.json 中的 BookId 相同。

1. 确保在 ConsoleApp.cs 文件中创建了以下 **SearchBooks** 方法：

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > 请务必删除 GitHub Copilot 创建的所有代码注释。 不必要和不准确的注释会对 GitHub Copilot 的建议产生负面影响。

1. 选择 **SearchBooks** 方法。

1. 打开内联聊天，然后输入以下提示：

    ```plaintext
    Update selection to obtain a book title. Prompt the user to "Enter a book title to search for". Read the user input and ensure the book title isn't null.
    ```

    GitHub Copilot 应该建议进行代码更新，以捕获用户提供的书籍标题。

1. 查看建议的更新，然后选择“接受”****。

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string? bookTitle = null;
        while (String.IsNullOrWhiteSpace(bookTitle))
        {
            Console.Write("Enter a book title to search for: ");
            bookTitle = Console.ReadLine();
        }
        // Perform book search logic here
        return ConsoleState.PatronDetails;
    }

    ```

    > [!NOTE]
    > GitHub Copilot 可能会创建一个单独的方法来处理用户输入的书名。 可以接受该建议，并继续在 SearchBooks 方法中开发主要逻辑。

1. 删除 GitHub Copilot 生成的任何占位符注释，然后选择 **SearchBooks** 方法。

1. 打开“聊天”视图。

1. 将以下文件添加到“聊天”上下文：ConsoleApp.cs、JsonData.cs、JsonLoanRepository.cs、Books.json、Loans.json、BookItems.json。

1. 输入以下提示：

    ```plaintext
    @workspace  Explain how to update the `SearchBooks` method and ConsoleApps class to determine whether a book title is available for loan. Inside the SearchBooks method, use a LINQ query and the user supplied book title to return a matching book. If a book is found, use a LINQ query and Loans.json to check if the book is available for loan. If the book has been returned, display a message stating "`book.title` is available for loan". If the book is on loan, display a message stating "`book.title` is on loan to another patron. The return due date is `loan.DueDate`".
    ```

1. 请花点时间来查看建议的更新。

    GitHub Copilot 应提出类似于以下建议的更新：

    要更新 SearchBooks 方法和 ConsoleApp 类以确定某书名是否可借出，请按照以下步骤操作：

    a. 在 JsonData 类中添加按书名搜索书籍的方法。
    b. 更新 ConsoleApp 类中的 SearchBooks 方法以使用这个新方法。
    c. 检查书籍的借阅状态并显示相应的消息。

    以下是更新后的代码：

    步骤 1：在 JsonData 类中添加按书名搜索书籍的方法

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

    步骤 2：更新 ConsoleApp 类中的 SearchBooks 方法

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        // ensure data is loaded
        await _jsonData.LoadData();
        // find the book by title
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        // find the loan status of the book
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

    步骤 3：更新 ConsoleApp 类构造函数以包含 JsonData

    ```csharp

    public class ConsoleApp
    {
        // Existing fields...
        JsonData _jsonData;
        public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
        {
            _patronRepository = patronRepository;
            _loanRepository = loanRepository;
            _loanService = loanService;
            _patronService = patronService;
            _jsonData = jsonData;
        }
        // Other methods...

    }

    ```

    步骤 4：更新 Program.cs 以将 JsonData 传递给 ConsoleApp

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
    .SetBasePath(Directory.GetCurrentDirectory())
    .AddJsonFile("appSettings.json")
    .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    通过这些更改，ConsoleApp 类中的 SearchBooks 方法现在将在 Books.json 文件中按书名搜索书籍，并在 Loans.json 文件中检查其借阅状态。 如果书籍可供借阅，它将显示一条消息，指明该书可供借阅。 如果书籍已借出，它将显示一条消息，指明该书已借出，并提供归还截止日期。

    > [!NOTE]
    > GitHub Copilot 可能建议在 SearchBooks 方法中使用 LINQ 查询来返回书籍对象，而不是使用 JsonData 类中的方法。 但是，它还可能建议在 `JsonData` 类中创建用于返回书名和检查借阅状态的方法（而不是使用对 SearchBooks 方法的 LINQ 查询）。 以下说明基于将这些方法结合使用的 GitHub Copilot 建议。

1. 将建议的 SearchBookByTitle 方法添加到 **JsonData** 类的末尾。

    ```csharp

    public Book? SearchBookByTitle(string title)
    {
        return Books?.FirstOrDefault(b => b.Title.Equals(title, StringComparison.OrdinalIgnoreCase));
    }

    ```

1. 将 _jsonData 字段声明添加到 ConsoleApp 类的类构造函数之前。

    ```csharp

    JsonData _jsonData;

    ```

1. 将 JsonData jsonData 参数添加到 ConsoleApp 类构造函数中，并使用它来初始化构造函数内的 _jsonData 字段。

    更新的类构造函数应类似于以下代码片段：

    ```csharp

    public ConsoleApp(ILoanService loanService, IPatronService patronService, IPatronRepository patronRepository, ILoanRepository loanRepository, JsonData jsonData)
    {
        _patronRepository = patronRepository;
        _loanRepository = loanRepository;
        _loanService = loanService;
        _patronService = patronService;
        _jsonData = jsonData;
    }

    ```

1. 请注意，JsonData 在 ConsoleApp 类中无法识别。

    需要将“using Library.Infrastructure.Data;”添加到ConsoleApp.cs文件的顶部。

1. 确保将以下“using”语句添加到 ConsoleApp.cs 文件的顶部。

    ```csharp

    using Library.Infrastructure.Data;

    ```

1. 使用代码建议来更新 **SearchBooks** 方法：

    建议的代码应使用 SearchBookByTitle 方法（或 LINQ 查询）按书名搜索书籍。 如果找到该书，则使用 LINQ 查询来确定该书是否已借出。 该代码还包含可根据搜索结果显示书籍可借状态的逻辑。 可以通过多种方式实现用于显示响应消息的逻辑。 以下代码片段中提供了一个示例。

    以下代码片段演示了 SearchBooks 方法一种可能的实现：

    ```csharp

    async Task<ConsoleState> SearchBooks()
    {
        string bookTitle = ReadBookTitle();
        Book? book = _jsonData.SearchBookByTitle(bookTitle);
        if (book == null)
        {
            Console.WriteLine($"No book found with title: {bookTitle}");
            return ConsoleState.PatronDetails;
        }
        Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);
        if (loan == null)
        {
            Console.WriteLine($"{book.Title} is available for loan.");
        }
        else
        {
            Console.WriteLine($"{book.Title} is on loan to another patron. The return due date is {loan.DueDate}.");
        }
        return ConsoleState.PatronDetails;
    }

    ```

1. 将现有 **Program.cs** 文件与建议的更新进行比较。

    ```csharp

    using Microsoft.Extensions.DependencyInjection;
    using Library.Infrastructure.Data;
    using Library.ApplicationCore;
    using Microsoft.Extensions.Configuration;
    var services = new ServiceCollection();
    var configuration = new ConfigurationBuilder()
        .SetBasePath(Directory.GetCurrentDirectory())
        .AddJsonFile("appSettings.json")
        .Build();
    services.AddSingleton<IConfiguration>(configuration);
    services.AddScoped<IPatronRepository, JsonPatronRepository>();
    services.AddScoped<ILoanRepository, JsonLoanRepository>();
    services.AddScoped<ILoanService, LoanService>();
    services.AddScoped<IPatronService, PatronService>();
    services.AddSingleton<JsonData>();
    services.AddSingleton<ConsoleApp>();
    var servicesProvider = services.BuildServiceProvider();
    var consoleApp = servicesProvider.GetRequiredService<ConsoleApp>();
    consoleApp.Run().Wait();

    ```

    如果 Program.cs 文件已经包含告知 ASP.NET Core 依赖注入系统创建 JsonData 类的单个实例并在请求 JsonData 时使用该实例的代码，则无需更新。

1. 选择 **SearchBooks** 方法。

1. 打开“聊天”视图，然后输入以下提示：

    ```plaintext
    Explain the LINQ queries and the evaluation of the book's availability status.
    ```

1. 请花点时间查看 GitHub Copilot 提供的解释。

    对于检查书籍是否已借出的查询，应会看到类似于以下解释的说明：

    ```markdown
    **Search for the Loan Status of the Book**
    ```

    ```csharp

    Loan? loan = _jsonData.Loans?.FirstOrDefault(l => l.BookItemId == book.Id && l.ReturnDate == null);

    ```

    ```markdown
    - _jsonData.Loans: Accesses the list of loans from the JsonData class.

    - ?.: The null-conditional operator ensures that if _jsonData.Loans is null, the entire expression will return null without throwing a NullReferenceException.

    - FirstOrDefault: A LINQ method that returns the first element in the collection that matches the specified condition, or null if no such element is found.

    - Lambda Expression: l => l.BookItemId == book.Id && l.ReturnDate == null

        - l.BookItemId == book.Id: Checks if the BookItemId of the loan matches the Id of the book being searched.

        - l.ReturnDate == null: Checks if the loan's ReturnDate is null, indicating that the book is currently on loan and has not been returned.

    - Result: If a matching loan is found, it is assigned to the loan variable. If no matching loan is found, loan is null.

    **Evaluation of the Book's Availability Status**

    After executing the LINQ queries, the method evaluates the availability status of the book:

      - If loan is null, the book has been returned. The method prints that the book is available for loan.
      - If loan is not null, the book is currently on loan (no return date). The method prints that the book is on loan and provides the date when the book should be returned.

    ```

1. 验证“检查书籍是否已借出”查询所实现的逻辑****。

    Null 条件运算符：“?.” 运算符是一个 null 条件运算符。 它确保如果 _jsonData.Loans 为 null，则整个表达式将求值为 null，而不会抛出 NullReferenceException。

    Lambda 表达式：Lambda 表达式“l => l.BookItemId == book.Id && l.ReturnDate == null”定义了 FirstOrDefault 方法的条件。 它会检查每个借出对象 “l”，看其 BookItemId 是否与图书对象的 Id 匹配，以及其 ReturnDate 是否为空。

    此代码尝试在 _jsonData.Loans 集合中查找第一项借阅，其中 BookItemId 与给定图书的 Id 匹配，且 ReturnDate 为空。 如果未找到此类借阅，或者“_jsonData.Loans”为空，则借阅将设置为空。

    > [!NOTE]
    > 大多数现代图书馆都藏有同一本书的多个复印本。 此代码假设每本书只有一个复印本。 如果图书馆藏有同一本书的多个复印本，则需要更新代码以处理同一本书的多个借阅记录。 对于此次培训，我们假设每本书只有一个复印本，并且提供的逻辑足以解决需要。

1. 保存更新文件：

1. 生成解决方案以确保不会出现错误。

    你将看到**警告**消息，但不应出现任何错误。

    若要在“解决方案资源管理器”视图中生成解决方案，请右键单击“AccelerateDevGitHubCopilot”，然后选择“生成”********。

#### 摘要 - 练习 5

你将使用 GitHub Copilot 来帮助为图书馆应用程序实现一项新功能。 你在存储库中创建了一个新分支，然后使用 GitHub Copilot 生成代码建议，帮助你更快、更准确地实现新功能。 你向 CommonActions 添加了新的 SearchBooks 操作，更新了 ConsoleApp.cs 中的 WriteInputOptions 和 ReadInputOptions 方法，并创建了一个新的 SearchBooks 方法来确定书籍的可用性状态。

### 练习 6：现在需要将更改合并到存储库的主分支中

创建的新功能使图书管理员能够确定书籍的可用状态。 现在需要验证该功能是否按预期工作，并将更改合并到存储库的主分支中。

在本练习中，你将完成以下任务：

- 验证新功能是否按预期工作
- 将更改与远程存储库同步
- 创建一个拉取请求，以将更改合并到存储库的主支中。

#### 任务 1：验证新功能是否按预期工作

由于没有自动化测试，你可以使用手动测试来验证新功能是否按预期工作。 必须使用可验证的数据源。 在这种情况下，使用 Books.json 和 Loans.json 文件来验证新功能是否正确报告书籍的可借状态。

请使用以下步骤完成本练习的这一部分：

1. 打开“解决方案资源管理器”视图。

1. 若要运行该应用程序，请右键单击“Library.Console”，选择“调试”，然后选择“启动新实例”************。

1. 当系统提示你输入借阅者姓名时，请键入 1，然后按 Enter****。

    你应会看到与搜索查询匹配的借阅者列表。

1. 在“输入选项”提示处键入 2，然后按 Enter****。

    输入 2 会选择列表中的第二位借阅者****。

    你应会看到借阅者的姓名和会员状态，以及书籍的借阅详细信息。

1. 在“输入选项”提示处键入 b，然后按 Enter****。

    输入 b 会选择用于搜索书籍可借状态的选项****。

    你应会看到用于输入书籍标题的提示。

1. 键入“书籍 1”，然后按 Enter****。

    在下载的原始数据中，“书籍 1”当前已借给“借阅者 49”，因此不可借阅********。

1. 验证应用程序是否显示了一条消息，指出该书籍已借给另一位借阅者。

    可能需要向上滚动才能看到消息。

1. 验证“书籍 9”是否已由“借阅者 1”归还********。

    在上一个练习中，在对图书馆应用程序进行测试期间，你已让“借阅者 1”归还“书籍 9”********。 如果应用程序显示“书籍 9”尚未由“借阅者 1”归还，请使用输入选项选择并归还“书籍 9”，然后继续************。

    > [!NOTE]
    > Library.Console.csproj 文件确保在生成应用程序时将 JSON 数据文件复制到输出目录。 但是，执行“清理”或“重新生成”操作实际上会重置数据。 重复“生成”操作不会重置输出目录 ("/bin/Debug/net8.0/") 中的数据。

1. 在“输入选项”提示处键入 b，然后按 Enter****。

1. 键入“书籍 9”，然后按 Enter****。

1. 验证应用程序是否显示了一条消息，指出该书籍可供借阅。

1. 在“输入选项”提示处键入 q，然后按 Enter****。

1. 停止调试会话。

1. 打开 **Loans.json** 文件。

    Loans.json 文件用于跟踪每本书籍的借阅状态。 可以使用 Loans.json 文件来验证 Book One 和 Book Nine 的可借状态是否正确。

    更新后的 Loans.json 文件应位于“Library.Console\bin\Debug\net8.0\Json”文件夹或“Library.Console\Json”文件夹中。

    - 如果使用 Visual Studio Code 调试程序运行应用，则更新后的 Loans.json 文件应位于“Library.Console\bin\Debug\net8.0\Json”文件夹中。

    - 如果使用“AccelerateDevGitHubCopilot\src\Library.Console”文件夹中的“dotnet run”命令来运行应用，则更新后的 Loans.json 文件应位于“Library.Console\ Json“文件夹中。

1. 验证借阅 ID 37 和借阅 ID 46 是否均适用于 Book One ("BookItemId": 1)。

    - 借阅 ID 37 应包含 ReturnDate 值 (2024-01-17)
    - 借阅 ID 46 不应包含 ReturnDate 值。 ReturnDate 值应为 null。

    ReturnDate 值用于确定该书籍当前是否已借出。 如果 ReturnDate 值为 null，则认为该书已借出。

1. 验证借阅 ID 22 是否适用于 Book Nine ("BookItemId": 9)，并且 ReturnDate 值是否设置为今天的日期。

    如果你当前正在调试程序中运行，并且在对 Loans.json 文件进行更改后清理了解决方案，则这些更改将会丢失。 清理解决方案后，Loans.json 文件将在下次运行应用程序时重置为原始数据。 可以手动更新 Loans.json 文件来测试 Book One 和 Book Nine 的可借状态。

#### 任务 2：将更改与远程存储库同步

可以使用 Visual Studio Code 中的“源代码管理”视图将更改提交到本地存储库。 提交更改后，可以将它们与远程存储库同步。

请使用以下步骤完成本练习的这一部分：

1. 选择“源代码管理”视图。

1. 确保 CommonActions.cs、ConsoleApp.cs 和 JsonData.cs 文件列在“**更改**”下。

    如果 GitHub Copilot 使用 LINQ 查询直接在 SearchBooks 方法中确定书籍的可借状态，则可能不会在“**更改**”下看到 JsonData.cs。

1. 使用 GitHub Copilot 为“提交”生成消息****。

1. 若要暂存并提交更改，请选择“提交”，然后选择“是”********。

1. 将更改同步（或推送）到远程存储库。

    如果已请求，请使用 GitHub 帐户来验证和授权同步。

#### 任务 3：创建一个拉取请求，以将更改合并到存储库的主分支中。

你可以使用拉取请求来建议对存储库的主分支进行更改。 创建拉取请求后，可以查看更改，验证检查是否通过，然后将更改合并到主分支中。 GitHub Copilot 可以帮助你生成拉取请求摘要，以帮助审阅者了解更改。

请使用以下步骤完成本练习的这一部分：

1. 在 Web 浏览器中打开 GitHub 存储库。

1. 打开“拉取请求”选项卡****。

1. 选择“新建拉取请求”。

1. 在“比较更改”下，确保为 main 分支配置了 base************。

1. 确保为 book-availability 分支配置了 compare********。

    配置分支后，将显示 main 和 book-availability 之间的更改比较结果********。 你应该会看到对 CommonActions.cs、ConsoleApp.cs 和 JsonDaa.cs 文件所做的更改。

1. 选择“创建拉取请求”。

1. 输入拉取请求的标题。

    订阅了 GitHub Copilot Enterprise 的企业成员可以使用 GitHub Copilot 为拉取请求生成摘要说明。 详细摘要可帮助审阅者了解所做的更改。

1. 使用 GitHub Copilot 生成拉取请求的摘要。

    若要生成摘要，请选择 Copilot 操作按钮，然后选择“**摘要**”。

    可以使用“预览”选项卡查看 GitHub Copilot 生成的拉取请求摘要。

1. 确保标题和说明反映了你的代码更新，然后选择“创建拉取请求”****。

1. 等待检查完成，然后验证是否通过了所有检查，并且与 base 分支不会冲突。

    检查可能需要大约一分钟才能完成。 需要解决识别到的所有问题，然后才能将更改合并到 main 分支。

1. 若要将更改合并到 main 分支，请选择“合并拉取请求”，然后选择“确认合并”********。

    请注意，合并更改后可以删除“图书可用性”分支。

1. 打开 Visual Studio Code。

1. 切换到存储库的 main 分支****。

1. 从远程存储库拉取更改****。

    如果系统提示，请使用 GitHub 帐户对拉取进行身份验证和授权。

1. 验证你在 book-availability 分支中所做的更改现在是否已反映在 main 分支中********。

    对 CommonActions.cs 和 ConsoleApp.cs 文件所做的更改应出现在主分支中。

#### 摘要 - 练习 6

在本练习中，你测试了代码，然后将更改合并到存储库的主分支中。 你已将更改提交到本地存储库，与远程存储库同步，然后创建了拉取请求以将更改合并到存储库的主分支中。 你使用 GitHub Copilot 生成拉取请求摘要，以帮助审阅者了解所做的更改。

## 第 3 部分：使用 GitHub Copilot 工具开发单元测试

### 开始之前

#### 项目概述

同事创建了名为 UnitTests 的测试项目。 现有单元测试部分涵盖 Library.ApplicationCore 项目中的服务类。 Library.ApplicationCore 项目包含库管理系统的业务逻辑。 UnitTests 项目使用 xUnit 框架编写和运行单元测试。 该项目还使用 NSubstitute 库创建模拟对象进行测试。

需要扩展 UnitTests 项目，以涵盖 Library.Infrastructure 项目中的数据访问类。

#### 实验室方案（第 3 部分）

GitHub Copilot 有助于为代码编写单元测试。 可通过多种方式使用 GitHub Copilot 生成单元测试：

- 生成测试用例****：可使用 GitHub Copilot 为代码生成测试用例。 Copilot 可根据你已编写的代码来建议测试用例。 你随后可使用这些测试用例为代码创建单元测试。
- 生成测试方法****：Copilot 还可为代码生成测试方法。 你可使用这些测试方法为代码创建单元测试。
- 生成测试断言****：Copilot 可推荐你可在单元测试中使用的断言。 这些断言可帮助你验证代码的行为。
- 生成测试模拟****：Copilot 可生成你可在单元测试中使用的模拟对象。 这些模拟对象有助于将要测试的代码与其依赖项隔离。
- 生成测试数据****：Copilot 可生成你可在单元测试中使用的测试数据。 此测试数据有助于使用不同的输入测试代码。
- 生成测试设置代码****：Copilot 可为单元测试生成设置代码。 此代码有助于在运行测试之前设置测试环境。
- 生成测试清理代码****：Copilot 可为单元测试生成清理代码。 此代码有助于在运行测试之后清理测试环境。

在本实验室的第 3 部分中，你为 Library.Infrastructure 项目开发单元测试。

部分包括以下练习：

- 使用 GitHub Copilot 评估和扩展 UnitTests 项目。

### 练习 7：使用 GitHub Copilot 评估和扩展 UnitTests 项目

在本练习中，使用 GitHub Copilot 完成以下任务：

1. 使用 GitHub Copilot 评估现有的 UnitTests 项目。

1. 扩展 UnitTests 项目以开始测试数据访问类。

#### 任务 1：使用 GitHub Copilot 评估现有 UnitTests 项目

UnitTests 项目当前实现以下文件夹结构：

- UnitTests\
  - ApplicationCore\
    - LoanService\
      - ExtendLoan.cs
      - ReturnLoan.cs
    - PatronService\
      - RenewMembership.cs
  - LoanFactory.cs
  - PatronFactory.cs

该结构反映并支持 ApplicationCore 项目的 Services 部分。

- ApplicationCore\
  - Services\
    - LoanService.cs：包含 ExtendLoan 和 ReturnLoan 方法。
    - PatronService.cs：包含 RenewMembership 方法。

评估现有单元测试将帮助你为 Library.Infrastructure 项目中的数据访问类开发单元测试。

请使用以下步骤完成本练习的这一部分：

1. 关闭已在编辑器中打开的所有文件。

1. 打开“聊天”视图。

1. 将以下文件添加到聊天上下文：**LoanFactory.cs**, **PatronFactory.cs**, **ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanService.cs**, **PatronService.cs**。

    这些文件位于“tests/UnitTests”、“tests/UnitTests/ApplicationCore/LoanService”、“tests/UnitTests/ApplicationCore/PatronService”和“src/Library.ApplicationCore/Services”文件夹中。

1. 输入以下提示：

    ```plaintext
    @workspace Explain the approach to unit testing that's been implemented in this workspace.
    ```

    此提示要求 GitHub Copilot 说明工作区上下文中的单元测试方法。 提示中包含多个文件，以提供响应的上下文。

1. 花点时间查看 GitHub Copilot 的响应。

    你应会看到类似于以下描述的说明：

    - 模拟依赖项：测试使用 NSubstitute 创建接口的模拟实现。
    - 测试组织：测试根据要测试的方法被组织到单独的文件中。 例如，ExtendLoan 和 ReturnLoan 方法是在 LoanService 文件夹下的单独文件中测试的。
    - 断言：断言用于验证每个测试的预期结果。
    - 测试场景：测试涵盖每种方法的各种场景，例如基于输入返回不同的状态。
    - 隔离性：每个测试都与其他测试相隔离，以防止副作用。
    - 工厂方法：工厂方法用于一致地创建测试数据。

1. 输入以下提示：

    ```plaintext
    @workspace What are the benefits of this approach to unit testing?
    ```

1. 花点时间查看 GitHub Copilot 的响应。

    你应会看到一个说明，它标识了类似于以下列表的优势列表：

    - 依赖项的隔离：使用模拟可将工作单元与其依赖项隔离开来。
    - 可重复性和一致性：工厂方法提供了创建测试数据的一致方法。
    - 可读性和可维护性：描述性测试方法和明确的测试步骤安排提高了测试的可读性。
    - 全面覆盖：测试各种场景可确保代码可靠并处理不同的边缘情况。
    - 分离关注点：测试数据创建与测试逻辑本身的分离使测试保持干净，并专注于要测试的行为。
    - 即时反馈：运行单元测试提供了关于代码正确性的即时反馈。

1. 将以下文件添加到聊天上下文：**ExtendLoan.cs**, **ReturnLoan.cs**, **RenewMembership.cs**, **LoanFactory.cs**, **PatronFactory.cs**, **LoanService.cs**, **PatronService.cs**。

1. 输入以下提示：

    ```plaintext
    @workspace How can I extend the `UnitTests` project to begin testing methods in the `Library.Infrastructure` project? Provide a process overview.
    ```

    此提示要求 GitHub Copilot 提供扩展 UnitTests 项目以开始测试 Library.Infrastructure 项目中的方法的流程概述。 提示中包含多个文件，以提供响应的上下文。

1. 花点时间查看 GitHub Copilot 的响应。

    你应会看到类似于以下描述的说明：

    ```markdown
    1. Add Project Reference:

      - Open the UnitTests.csproj file located at tests/UnitTests/UnitTests.csproj.
      - Add a reference to the Library.Infrastructure project.

    2. Identify methods to test:

      - Identify the methods in the Library.Infrastructure project that need to be tested. For example, if you want to test the LoanService class, identify the methods in the LoanService class that need to be tested.

    3. Create Test Classes:

      - Create new test classes in the tests/UnitTests directory to test the methods in the Library.Infrastructure project. For example, if you want to test LoanService, create a file named LoanServiceTests.cs.

    4. Write Unit Tests:

      - In the newly created test classes, write unit tests for the methods in the Library.Infrastructure project. Use the xUnit framework for writing tests and NSubstitute for mocking dependencies.

    5. Run Tests:

      - Use Visual Studio Code's integrated terminal or the Test Explorer to run the tests.
      - Ensure that the tests are discovered and executed correctly.
    ```

#### 任务 2：扩展 UnitTests 项目以开始测试数据访问类

在本练习的此部分中，你将使用 GitHub Copilot 帮助你为 Library.Infrastructure 项目创建单元测试。

Library.Infrastructure 项目包含与文件系统交互以加载和保存数据的数据访问类。 该项目包括以下类：

- JsonData：加载和保存 JSON 数据的类。
- JsonLoanRepository：实现 ILoanRepository 接口并使用 JsonData 类加载和保存贷款数据的类。
- JsonPatronRepository：实现 IPatronRepository 接口并使用 JsonData 类加载和保存顾客数据的类。

首先，你将为 JsonLoanRepository 类编写单元测试。

请使用以下步骤完成本练习的这一部分：

1. 将以下项目文件添加到“聊天”上下文：**UnitTests.csproj**。

1. 在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace Explain how to add a reference to the Library.Infrastructure project inside `UnitTests.csproj`.
    ```

    此提示要求 GitHub Copilot 说明如何在 UnitTests.csproj 文件中添加对 Library.Infrastructure 项目的引用。

1. 使用 GitHub Copilot 响应更新 UnitTests.csproj 文件。

    更新后的 UnitTests.csproj 文件应类似于以下 XML 代码：

    ```xml

    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
        <Nullable>enable</Nullable>
        <IsPackable>false</IsPackable>
        <IsTestProject>true</IsTestProject>
      </PropertyGroup>
      <ItemGroup>
        <PackageReference Include="coverlet.collector" Version="6.0.0" />
        <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
        <PackageReference Include="NSubstitute" Version="5.1.0" />
        <PackageReference Include="xunit" Version="2.5.3" />
        <PackageReference Include="xunit.runner.visualstudio" Version="2.5.3" />
      </ItemGroup>
      <ItemGroup>
        <Using Include="Xunit" />
      </ItemGroup>
      <ItemGroup>
        <ProjectReference Include="..\..\src\Library.ApplicationCore\Library.ApplicationCore.csproj" />
        <ProjectReference Include="..\..\src\Library.Infrastructure\Library.Infrastructure.csproj" />
      </ItemGroup>
    </Project>

    ```

1. 打开 **JsonLoanRepository.cs** 文件。

    JsonLoanRepository.cs 位于“src/Library.Infrastructure/Data/”文件夹中。

1. 花点时间查看 **JsonLoanRepository.cs** 文件。

    ```csharp

    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    namespace Library.Infrastructure.Data;
    public class JsonLoanRepository : ILoanRepository
    {
        private readonly JsonData _jsonData;
        public JsonLoanRepository(JsonData jsonData)
        {
            _jsonData = jsonData;
        }
        public async Task<Loan?> GetLoan(int id)
        {
            await _jsonData.EnsureDataLoaded();
    
            foreach (Loan loan in _jsonData.Loans!)
            {
                if (loan.Id == id)
                {
                    Loan populated = _jsonData.GetPopulatedLoan(loan);
                    return populated;
                }
            }
            return null;
        }
        public async Task UpdateLoan(Loan loan)
        {
            Loan? existingLoan = null;
            foreach (Loan l in _jsonData.Loans!)
            {
                if (l.Id == loan.Id)
                {
                    existingLoan = l;
                    break;
                }
            }
            if (existingLoan != null)
            {
                existingLoan.BookItemId = loan.BookItemId;
                existingLoan.PatronId = loan.PatronId;
                existingLoan.LoanDate = loan.LoanDate;
                existingLoan.DueDate = loan.DueDate;
                existingLoan.ReturnDate = loan.ReturnDate;
                await _jsonData.SaveLoans(_jsonData.Loans!);
                await _jsonData.LoadData();
            }
        }
    }

    ```

1. 注意以下有关 **JsonLoanRepository** 类的详细信息：

    - JsonLoanRepository 类包含两种方法：GetLoan 和 UpdateLoan。
    - JsonLoanRepository 类使用 JsonData 对象来加载和保存借阅数据。

    首先，你将为 GetLoan 方法编写单元测试。

1. 在 **UnitTests** 项目下创建以下文件夹结构。

    - Infrastructure\
        - JsonLoanRepository\

    此文件夹结构反映了用于 Library.ApplicationCore 单元测试的方法。

1. 在 JsonLoanRepository 文件夹中，创建一个名为 **GetLoan** 的类文件。

1. 请花点时间思考 GetLoan 单元测试的字段和类构造函数要求。

    JsonLoanRepository.GetLoan 方法在调用时接收借阅 ID 参数。 该方法使用“_jsonData.EnsureDataLoaded”来获取最新的 JSON 数据，并使用“_jsonData.Loans”来搜索匹配的借阅。 如果该方法找到匹配的借阅 ID，它将返回一个已填充的借阅对象 (populated)。 如果该方法找不到匹配的借阅 ID，则返回 null。

    对于 GetLoan 单元测试：

    - 可以使用模拟借阅存储库对象 ("_mockLoanRepository") 来帮助测试找到匹配 ID 的情况。 使用要查找的 ID 加载模拟。 ReturnLoanTest 类演示如何模拟 ILoanRepository 接口并实例化模拟借阅存储库对象。

    - 可使用一个非模拟借阅存储库对象 ("_jsonLoanRepository") 来测试未找到匹配 ID 的情况。 只需指定一个文件中没有的贷款 ID 即可（任何超过 100 的 ID 均可）。

    - 需要一个 JsonData 对象来创建非模拟 JsonLoanRepository 对象。 由于 UnitTests 项目无权访问 ConsoleApp 项目创建的 JsonData 对象，因此你需要使用 IConfiguration 接口创建一个 JsonData 对象。

1. 将以下文件添加到“聊天”上下文：**JsonLoanRepository.cs**、**ReturnLoan.cs**、**LoanService.cs**、**LoanFactory.cs**、**JsonData.cs**。

1. 输入以下提示：

    ```plaintext
    @workspace Create fields and a class constructor for the `GetLoan.cs` file. The class will be used to create unit tests for the GetLoan method in the `JsonLoanRepository.cs` file. Create the following private readonly fields: `_mockLoanRepository`, `_jsonLoanRepository`, `_configuration`, and `_jsonData`. Instantiate the fields in the `GetLoanTest` constructor. Use `ConfigurationBuilder` to create a `_configuration` object that can be used to instantiate the JsonData object.
    ```

    此提示要求 GitHub Copilot 推荐字段和类构造函数。

1. 花点时间查看 GitHub Copilot 的响应。

    你应会看到类似于以下代码片段的代码建议：

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.ApplicationCore.Interfaces;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepository;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder()
                .AddJsonFile("appsettings.json")
                .Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        // Add test methods here
    }

    ```

1. 使用 GitHub Copilot 提供的代码建议更新 **GetLoan.cs**。

1. 注意以下问题：

    - 命名空间与代码中 JsonLoanRepository 的使用之间存在冲突。 应更新 GetLoans.cs 中的命名空间，以遵循 ReturnLoan.cs 和 RenewMembership.cs 文件中使用的模式。

    - 如果代码中无法识别 ILoanRepository，则可能需要将 Library.ApplicationCore 的 using 指令添加到文件顶部。

    - 如果 _configuration 对象未正确实例化，则可能需要更新包含 ConfigurationBuilder 的代码行。 可以简化代码以使用“_configuration = new ConfigurationBuilder().Build();”。

    - 如果 GitHub Copilot 建议“使用 Library.ApplicationCore.Interfaces”，则可以从文件顶部将其删除。

1. 更新 **GetLoan.cs** 文件以匹配以下代码片段：

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
    }

    ```

    代码更新解决了上一步中标识的问题。 生成项目将解决编辑器中标识的问题。

1. 将以下文件添加到聊天上下文：**JsonLoanRepository.cs**, **ReturnLoan.cs**, **LoanService.cs**, **LoanFactory.cs**, **JsonData.cs**, **Loans.json**。

1. 选择 GetLoan.cs 文件的内容，然后在“聊天”视图中输入以下提示：

    ```plaintext
    @workspace Update the selection to include a unit test for the `JsonLoanRepository.GetLoan` method. The unit test should test the case where a loan ID is found in the data. Use `_mockLoanRepository` to arrange the expected return loan. Use `_jsonLoanRepository` to return an actual loan. Asserts should verify that the return loan ID matches the expected loan ID. Use a loan ID that exists in the `Loans.json` file.
    ```

    此提示要求 GitHub Copilot 为 JsonLoanRepository.GetLoan 方法推荐单元测试。 该单元测试应测试在数据中找到贷款 ID 的情况。 测试应使用“_mockLoanRepository ”来安排预期的归还借阅，使用“_jsonLoanRepository ”来返回实际的借阅，并使用断言来验证归还借阅 ID 是否与预期的借阅 ID 相匹配。 借阅 ID 应存在于 Loans.json 文件中。

1. 花点时间查看 GitHub Copilot 的响应。

    你应会看到类似于以下代码片段的代码建议：

    ```csharp

    using NSubstitute;
    using Library.ApplicationCore;
    using Library.ApplicationCore.Entities;
    using Library.Infrastructure.Data;
    using Microsoft.Extensions.Configuration;
    using Xunit;
    namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;
    public class GetLoanTest
    {
        private readonly ILoanRepository _mockLoanRepository;
        private readonly JsonLoanRepository _jsonLoanRepository;
        private readonly IConfiguration _configuration;
        private readonly JsonData _jsonData;
        public GetLoanTest()
        {
            _mockLoanRepository = Substitute.For<ILoanRepository>();
            _configuration = new ConfigurationBuilder().Build();
            _jsonData = new JsonData(_configuration);
            _jsonLoanRepository = new JsonLoanRepository(_jsonData);
        }
        [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when loan ID is found")]
        public async Task GetLoan_ReturnsLoanWhenLoanIdIsFound()
        {
            // Arrange
            var loanId = 1; // Use a loan ID that exists in the Loans.json file
            var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
            _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
            await _jsonData.EnsureDataLoaded(); // Ensure data is loaded
            // Act
            var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
            // Assert
            Assert.NotNull(actualLoan);
            Assert.Equal(expectedLoan.Id, actualLoan?.Id);
        }
    }

    ```

1. 使用 GitHub Copilot 提供的代码建议更新 **GetLoan.cs**。

    JsonLoanRepository.GetLoan 方法会调用“_jsonData.EnsureDataLoaded”，以确保 JSON 数据已加载。 如果测试方法中包含调用“_jsonData.EnsureDataLoaded ”的代码行，可以将其删除。

    如果代码中无法识别 Loan 类，请确保 GetLoan.cs 文件的顶部有“using Library.ApplicationCore.Entities”语句。 Loan 类位于 Library.ApplicationCore.Entities 命名空间中。

1. 生成 AccelerateDevGitHubCopilot 解决方案，确保没有任何错误。

1. 对于找不到贷款 ID 的情况，使用 GitHub Copilot 的自动完成功能创建测试。

    在 GetLoan_ReturnsLoanWhenLoanIdIsFound 方法后面创建一个空白行。

    接受自动完成建议以创建新的测试方法。

1. 花点时间查看 GitHub Copilot 的响应。

    GitHub Copilot 的自动完成功能可能会模拟预期的贷款（即使不需要它）。 可删除模拟预期借阅的代码，但需要一个 Loans.json 文件中不存在的借阅 ID。

    你应会看到类似于以下代码片段之一的代码建议：

    ```csharp

    [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns null when loan ID is not found")]
    public async Task GetLoan_ReturnsNullWhenLoanIdIsNotFound()
    {
        // Arrange
        var loanId = 999; // Use a loan ID that does not exist in the Loans.json file
        var expectedLoan = new Loan { Id = loanId, BookItemId = 101, PatronId = 202, LoanDate = DateTime.Now, DueDate = DateTime.Now.AddDays(14) };
        _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);
        // Act
        var actualLoan = await _jsonLoanRepository.GetLoan(loanId);
        // Assert
        Assert.Null(actualLoan);
    }

    ```

1. 接受自动完成建议，该建议会指定一个数据集中没有的 loanId 值。

    如果没有任何建议分配不在数据集中的 loanId 号码，则可以使用 **Ctrl+Enter** 键盘快捷方式列出其他建议。

1. 注意，单元测试需要对 JSON 数据文件的访问权限。

    JsonLoanRepository.GetLoan 方法使用 JsonData 对象来加载和保存借阅数据。

    JSON 数据文件位于“Library.Console\Json”文件夹中。 需要更新 UnitTests.csproj 文件以在测试项目中包括这些文件。

1. 将以下 XML 代码段添加到 **UnitTests.csproj** 文件中：

    ```xml

    <ItemGroup>
        <None Include="..\..\src\Library.Console\Json\**\*">
            <Link>Json\%(RecursiveDir)%(FileName)%(Extension)</Link>
            <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
        </None>
    </ItemGroup>

    ```

    这可确保在运行测试时将 JSON 数据文件复制到输出目录。

#### 任务 3：检查你的工作

有多种方法可运行 JsonLoanRepository 类的单元测试。 可使用 Visual Studio Code 的测试资源管理器、集成终端或“dotnet test”命令。

请使用以下步骤完成本练习的这一部分：

1. 确保已在编辑器中打开 GetLoans.cs 文件。

1. 生成解决方案并确保没有错误。

    右键单击“AccelerateDevGitHubCopilot”，然后选择“生成”********。

1. 注意测试方法左侧的“绿色播放按钮”。

1. 打开 Visual Studio Code 的“测试资源管理器”视图。

    若要打开“测试资源管理器”视图，请选择左侧活动栏上的烧杯状图标。 测试资源管理器在用户界面中标记为“正在测试”。

    测试资源管理器是一个树状视图，显示了工作区中的所有测试用例。 可使用测试资源管理器运行/调试测试用例并查看测试结果。

1. 展开 **UnitTests** 和基础节点，找到 **GetLoanTest**。

1. 运行“JsonLoanRepository.GetLoan：**** 找到贷款 ID 时返回贷款”测试用例。

    > [!NOTE]
    > GitHub Copilot 可能以不同的方式命名了测试方法。 运行使用数据中存在的借阅 ID 的测试方法。

1. 注意“测试资源管理器”视图和编辑器中的测试结果。

    你应会看到一个绿色复选标记，指示测试已通过。

1. 使用编辑器运行“JsonLoanRepository.GetLoan：**** 找不到贷款 ID 时返回 null”测试用例。

1. 注意“测试资源管理器”视图和编辑器中的测试结果。

    若要从编辑器运行测试，请选择测试方法左侧的绿色“开始”按钮。

1. 确保“JsonLoanRepository.GetLoan：**** 找不到贷款 ID 时返回 null”测试通过。

    你应会在两个测试的左侧看到一个绿色的复选标记。

#### 摘要 - 练习 7

在本练习中，你使用 GitHub Copilot 评估了现有的 UnitTests 项目，并扩展了该项目以开始测试 Library.Infrastructure 项目中的数据访问类。 你已在 UnitTests.csproj 文件中添加了对 Library.Infrastructure 项目的引用，并为 JsonLoanRepository 类创建了单元测试。 你借助 GitHub Copilot 为 JsonLoanRepository 类中的 GetLoan 方法编写单元测试。 你使用 Visual Studio Code 的测试资源管理器运行了单元测试，并验证了测试已通过。

## 第 4 部分：使用 GitHub Copilot 工具重构和改进代码部分

### 开始之前

#### 项目概述

你和同事已完成项目的初始开发阶段，现在正在研究重构和改进代码库的方法。

代码重构是重新构建现有代码，而不更改其外部行为的过程。 重构通常用于改进代码的特定方面。 GitHub Copilot 通过建议改进代码的质量、可靠性、性能和安全性的更改来帮助重构代码。

#### 实验室方案（第 4 部分）

在本练习的第 4 部分，你将使用 GitHub Copilot 重构以下代码部分：

- 将 EnumHelper 类重构为使用字典，而不是反射。 使用字典可降低反射开销来提高性能。 消除反射还可以提高代码可读性、可维护性和安全性。

- 重构数据访问方法以使用 LINQ（语言集成查询），而不是 foreach 循环。 使用 LINQ 可以更简洁、更易读地查询集合、数据库和 XML 文档。 使用 LINQ 可以提高代码可读性、可维护性和性能。

该部分包括以下练习：

- 使用 GitHub Copilot 重构 EnumHelper 类。
- 使用 GitHub Copilot 通过 LINQ 改进数据访问类。

### 练习 8：使用 GitHub Copilot 重构 EnumHelper 类

反射是一项强大的功能，可用于在运行时检查和操作对象。 但是，反射可能很慢，并且存在与应考虑的反射相关的潜在安全风险。

现有的 EnumHelper 类使用反射来检索枚举值的说明属性。 可以将 EnumHelper 类重构为使用字典，而不是反射。 使用字典可以提高性能，并消除与使用反射相关的任何安全问题。

在本练习中，你将使用 GitHub Copilot 来帮助重构 EnumHelper 类。

请按以下步骤完成本练习：

1. 使用解决方案资源管理器视图打开 EnumHelper.cs 文件。

    EnumHelper.cs 位于“src/Library.ApplicationCore/Enums”文件夹中。

    ```csharp

    using System.ComponentModel;
    using System.Reflection;
    namespace Library.ApplicationCore.Enums;
    public static class EnumHelper
    {
        public static string GetDescription(Enum value)
        {
            if (value == null)
                return string.Empty;
            FieldInfo fieldInfo = value.GetType().GetField(value.ToString())!;
            DescriptionAttribute[] attributes =
                (DescriptionAttribute[])fieldInfo.GetCustomAttributes(typeof(DescriptionAttribute), false);
            if (attributes != null && attributes.Length > 0)
            {
                return attributes[0].Description;
            }
            else
            {
                return value.ToString();
            }
        }
    }

    ```

1. 打开“聊天”视图，然后将以下文件添加到“聊天”上下文：**EnumHelper.cs**、**LoanExtensionStatus.cs**、**LoanReturnStatus.cs**、**MembershipRenewalStatus.cs**。

1. 输入以下提示：

    ```plaintext
    @workspace I want to refactor the `EnumHelper` class using dictionaries rather than reflection to get enum description attributes. I want a separate dictionary for each enum. The enum values are in the `LoanExtensionStatus.cs`, `LoanReturnStatus.cs`, and `MembershipRenewalStatus.cs` files. Explain how to update the EnumHelper class to use dictionaries and provide the updated code.
    ```

    此提示要求 GitHub Copilot 提供有关如何更新 EnumHelper 类以使用字典而不是反射的说明。 它还要求更新的代码，代码使用每个枚举值的字典。

1. 请花点时间查看 GitHub Copilot 提供的解释。

    解释应类似于以下说明：

    ```markdown
    To refactor the EnumHelper class to use dictionaries for each enum, you need to create a dictionary for each enum type that maps the enum values to their descriptions. This will eliminate the need for reflection at runtime.

    Here's how you can update the EnumHelper class:

    1. Create dictionaries for each enum type.
    2. Populate these dictionaries with the enum values and their corresponding descriptions.
    3. Update the GetDescription method to use these dictionaries.

    Below is the updated code for the EnumHelper class:

    ```

    ```csharp

    using System.ComponentModel;
    using System.Collections.Generic;
    namespace Library.ApplicationCore.Enums
    {
        public static class EnumHelper
        {
            private static readonly Dictionary<MembershipRenewalStatus, string> MembershipRenewalStatusDescriptions = new()
            {
                { MembershipRenewalStatus.Success, "Membership renewal was successful." },
                { MembershipRenewalStatus.PatronNotFound, "Patron not found." },
                { MembershipRenewalStatus.TooEarlyToRenew, "It is too early to renew the membership." },
                { MembershipRenewalStatus.LoanNotReturned, "Cannot renew membership due to an outstanding loan." },
                { MembershipRenewalStatus.Error, "Cannot renew membership due to an error." }
            };
            private static readonly Dictionary<LoanReturnStatus, string> LoanReturnStatusDescriptions = new()
            {
                { LoanReturnStatus.Success, "Book was successfully returned." },
                { LoanReturnStatus.LoanNotFound, "Loan not found." },
                { LoanReturnStatus.AlreadyReturned, "Cannot return book as the book is already returned." },
                { LoanReturnStatus.Error, "Cannot return book due to an error." }
            };
            private static readonly Dictionary<LoanExtensionStatus, string> LoanExtensionStatusDescriptions = new()
            {
                { LoanExtensionStatus.Success, "Book loan extension was successful." },
                { LoanExtensionStatus.LoanNotFound, "Loan not found." },
                { LoanExtensionStatus.LoanExpired, "Cannot extend book loan as it already has expired. Return the book instead." },
                { LoanExtensionStatus.MembershipExpired, "Cannot extend book loan due to expired patron's membership." },
                { LoanExtensionStatus.LoanReturned, "Cannot extend book loan as the book is already returned." },
                { LoanExtensionStatus.Error, "Cannot extend book loan due to an error." }
            };
            public static string GetDescription(Enum value)
            {
                if (value == null)
                    return string.Empty;
                return value switch
                {
                    MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
                    LoanReturnStatus status => LoanReturnStatusDescriptions[status],
                    LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
                    _ => value.ToString()
                };
            }
        }
    }

    ```

    ```markdown

    This refactored EnumHelper class uses dictionaries to store the descriptions for each enum type. The GetDescription method now uses pattern matching to determine the type of the enum and retrieves the description from the appropriate dictionary. This approach avoids the use of reflection and improves performance.

    ```

    > [!NOTE]
    > 如果 GitHub Copilot 未使用正确的说明填充字典，请确保 GitHub Copilot 扩展不会请求重启。 如果是，请重启扩展，然后重试提示。

1. 使用 GitHub Copilot 建议的 EnumHelper 类更新 EnumHelper.cs 文件。

1. 确保更新后的 EnumHelper 类使用 LoanExtensionStatus.cs、LoanReturnStatus.cs 和 MembershipRenewalStatus.cs 文件中的枚举值。

    打开每个枚举文件，并验证字典中的枚举值是否正确。 如果存在差异，请让 GitHub Copilot 分别更新每个枚举的字典。 例如，可以对 LoanExtensionStatus 枚举使用以下提示：

    ```plaintext
    @workspace Use the description values in LoanExtensionStatus.cs to update the LoanExtensionStatus dictionary in the EnumHelper class. Provide the updated code for the LoanExtensionStatus dictionary in the EnumHelper class.
    ```

    如有必要，对 LoanReturnStatus 和 MembershipRenewalStatus 枚举使用相同的方法。

1. 花点时间查看 **GetDescription** 方法。

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        return value switch
        {
            MembershipRenewalStatus status => MembershipRenewalStatusDescriptions[status],
            LoanReturnStatus status => LoanReturnStatusDescriptions[status],
            LoanExtensionStatus status => LoanExtensionStatusDescriptions[status],
            _ => value.ToString()
        };
    }

    ```

    此代码使用模式匹配来确定枚举的类型，并从相应的字典中检索说明。 切换语句会检查枚举值的类型，并从字典中返回相应的说明。 如果在字典中找不到枚举值，该方法将枚举值作为字符串返回。

    如果要求 GitHub Copilot 重构此代码并消除 lambda 表达式，则更易于阅读：

    ```csharp

    public static string GetDescription(Enum value)
    {
        if (value == null)
            return string.Empty;
        switch (value)
        {
            case MembershipRenewalStatus status:
                return MembershipRenewalStatusDescriptions[status];
            case LoanReturnStatus status:
                return LoanReturnStatusDescriptions[status];
            case LoanExtensionStatus status:
                return LoanExtensionStatusDescriptions[status];
            default:
                return value.ToString();
        }
    }

    ```

1. 保存对 EnumHelper.cs 文件的更改。

1. 生成解决方案以确保不会出现错误。

    你将看到警告。 现在可以忽略这些文件。

#### 摘要 - 练习 8

在本练习中，使用 GitHub Copilot 重构了 EnumHelper 类，使其使用字典而非反射。 使用字典可降低反射开销来提高性能。 消除反射还可以提高代码可读性、可维护性和安全性。

### 练习 9：使用 GitHub Copilot 改进 LINQ 的数据访问类

LINQ（语言集成查询）是 C# 中的一项强大功能，可用于以统一的方式查询集合、数据库和 XML 文档。 与传统的 foreach 循环相比，LINQ 提供了一种更简洁、更易读的方式来查询数据。

本练习包括以下任务：

- 重构 JsonData.cs 中的方法来使用 LINQ。
- 重构 JsonLoanRepository.cs 中的方法来使用 LINQ。
- 重构 JsonPatronRepository.cs 中的方法来使用 LINQ。

#### 任务 1：重构 JsonData.cs 中的方法来使用 LINQ

JsonData 类包括以下数据访问方法：GetPopulatedPatron、GetPopulatedLoan、GetPopulatedBookItem、GetPopulatedBook。 这些方法使用 foreach 循环来循环访问集合并填充对象。 可以重构这些方法，以使用 LINQ 来提高代码可读性和可维护性。

请使用以下步骤完成本练习的这一部分：

1. 打开 JsonData.cs 文件。

1. 选择 **GetPopulatedPatron** 方法。

    GetPopulatedPatron 方法旨在创建一个完全填充的 Patron 对象。 它复制 Patron 的基本属性，并使用详细的 Loan 对象填充其 Loans 集合。

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        Patron populated = new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = new List<Loan>()
        };
        foreach (Loan loan in Loans!)
        {
            if (loan.PatronId == p.Id)
            {
                populated.Loans.Add(GetPopulatedLoan(loan));
            }
        }
        return populated;
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    ```plaintext
    #selection refactor selection to `return new Patron` using LINQ
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public Patron GetPopulatedPatron(Patron p)
    {
        return new Patron
        {
            Id = p.Id,
            Name = p.Name,
            ImageName = p.ImageName,
            MembershipStart = p.MembershipStart,
            MembershipEnd = p.MembershipEnd,
            Loans = Loans!
                .Where(loan => loan.PatronId == p.Id)
                .Select(GetPopulatedLoan)
                .ToList()
        };
    }

    ```

    首先，LINQ 查询用于替换“foreach (Loan loan in Loans!)”循环。 有了 LINQ 代码，可以使用对象初始值设定项将对象属性分配给新的 Patron 对象。 这可以缓解对 Patron 对象的单独填充实例的需求。 总的来说，更新的代码更短且更易于阅读。

    该代码使用输入借阅者“p”将一些基本属性分配给新的 Patron 对象。 然后，它使用与输入 Patron 关联的借阅填充 Loans 集合，并使用 GetPopulatedLoan 方法转换每个借阅。

    可以分解填充 Loans 集合的 LINQ 代码行：

    - `Loans!`：“借阅！” 表达式访问 Loans 集合。 “！”运算符是一个允许为空的运算符，表示开发人员确信 Loans 不为空。 在调用 GetPopulatedPatron 方法之前，应确保 Loans 已正确初始化。
    - `.Where(loan => loan.PatronId == p.Id)`：此代码筛选借阅，仅包含属于输入借阅者“p”的借阅。
    - `.Select(GetPopulatedLoan)`：此代码使用 GetPopulatedLoan 方法转换每个筛选的借阅。
    - `.ToList()`：将结果转换为 Loan 对象列表。

1. 若要接受建议的更新，请选择“接受”****。

    现在，你已了解如何重构 GetPopulatedPatron 方法，也可以重构 GetPopulatedLoan、GetPopulatedBookItem 和 GetPopulatedBook 方法，使其也使用 LINQ。

1. 使用相同的方法重构 **GetPopulatedLoan**、**GetPopulatedBookItem** 和 **GetPopulatedBook** 方法。

    例如，使用以下提示重构三种方法：

    对于 **GetPopulatedLoan** 方法：

    ```plaintext
    #selection refactor selection to `return new Loan` using LINQ. Use `GetPopulatedBookItem` for the `BookItem` property. Use `Single` for BookItem and Patron properties.
    ```

    对于 **GetPopulatedBookItem** 方法：

    ```plaintext
    #selection refactor selection to `return new BookItem` using LINQ. Use `GetPopulatedBook` and `Single` for the `BookItem` property.
    ```

    对于 **GetPopulatedBook** 方法：

    ```plaintext
    #selection refactor selection to `return new Book` using LINQ. Use `Where` and `Select` for `Author` property. Use `First` author.
    ```

1. 接受建议的更新后，花时间查看代码更改。

    更新的代码看起来应该类似于：

    ```csharp

    public Loan GetPopulatedLoan(Loan l)
    {
        return new Loan
        {
            Id = l.Id,
            BookItemId = l.BookItemId,
            PatronId = l.PatronId,
            LoanDate = l.LoanDate,
            DueDate = l.DueDate,
            ReturnDate = l.ReturnDate,
            BookItem = GetPopulatedBookItem(BookItems!.Single(bi => bi.Id == l.BookItemId)),
            Patron = Patrons!.Single(p => p.Id == l.PatronId)
        };
    }
    public BookItem GetPopulatedBookItem(BookItem bi)
    {
        return new BookItem
        {
            Id = bi.Id,
            BookId = bi.BookId,
            AcquisitionDate = bi.AcquisitionDate,
            Condition = bi.Condition,
            Book = GetPopulatedBook(Books!.Single(b => b.Id == bi.BookId))
        };
    }
    public Book GetPopulatedBook(Book b)
    {
        return new Book
        {
            Id = b.Id,
            Title = b.Title,
            AuthorId = b.AuthorId,
            Genre = b.Genre,
            ISBN = b.ISBN,
            ImageName = b.ImageName,
            Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
                Id = a.Id,
                Name = a.Name
            }).First()
        };
    }

    ```

1. 使用“说明”**** 智能操作查看 LINQ 查询的说明。

    “说明”**** 智能操作提供代码中使用的 LINQ 查询的详细说明。

    例如，可以对 GetPopulatedBook 方法使用“**说明**”智能操作，以查看用于填充 Book 对象 Author 属性的 LINQ 查询的说明。

    ```csharp

    Author = Authors!.Where(a => a.Id == b.AuthorId).Select(a => new Author {
        Id = a.Id,
        Name = a.Name
    }).First()

    ```

    “**说明**”智能操作提供了用于填充 Book 对象 Author 属性的 LINQ 查询的详细说明。

    例如，说明可能类似这样：

    ```plaintext
    The active selection is a C# code snippet that assigns a value to the Author property. This value is derived from a collection of Author objects named Authors. The code uses LINQ (Language Integrated Query) to filter and transform the data within this collection.
    
    First, the Authors! expression uses the null-forgiving operator (!) to indicate that Authors is not null, even if the compiler might think otherwise. This is a way to suppress nullable warnings. The Where method is then called on the Authors collection to filter the elements. The lambda expression a => a.Id == b.AuthorId is used to find all Author objects where the Id matches the AuthorId property of another object b.
    
    After filtering, the Select method is used to project each filtered Author object into a new Author object. This is done by creating a new instance of the Author class and copying the Id and Name properties from the original Author object.
    
    Finally, the First method is called to retrieve the first element from the resulting sequence. This means that the Author property will be assigned the first Author object that matches the filter criteria and has been projected into a new Author instance.
    
    This approach ensures that the Author property is set to a new Author object with the same Id and Name as the first matching Author in the Authors collection.
    ```

1. 将更改保存到 JsonData.cs 文件。

1. 生成解决方案以确保不会出现错误。

    你将看到警告。 现在可以忽略这些文件。

#### 任务 2：重构 JsonLoanRepository.cs 中的方法以使用 LINQ

JsonLoanRepository 类包括 GetLoan 和 UpdateLoan 数据访问方法。 你将重构这两种方法，将 foreach 循环替换为 LINQ，以提高代码可读性和可维护性。

请使用以下步骤完成本练习的这一部分：

1. 打开 **JsonLoanRepository.cs** 文件。

1. 选择 **GetLoan** 方法。

    GetLoan 方法旨在按借阅 ID 检索借阅。

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Loan loan in _jsonData.Loans!)
        {
            if (loan.Id == id)
            {
                Loan populated = _jsonData.GetPopulatedLoan(loan);
                return populated;
            }
        }
        return null;
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    例如，输入以下提示：

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Loans!. Use `Where`, `Select` and `GetPopulatedLoan` to return `FirstOrDefault`.
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? loan = _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
        return loan;
    }

    ```

    更新的代码使用 LINQ 筛选借阅集合，以仅包含具有指定 ID 的借阅。 请注意，应将借阅声明为可为可为空 (`Loan? loan`)。 然后，它使用 GetPopulatedLoan 方法转换借阅，并返回第一个结果。 如果未找到匹配的借阅，FirstOrDefault 返回 null。 然后，该方法返回此借阅对象，如果没有具有指定“id”的借阅，该对象可能为 null。 此方法可确保返回的借阅完全填充所有必要的相关数据，从而全面了解借阅记录。

    可以进一步简化此代码：

    ```csharp

    public async Task<Loan?> GetLoan(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Loans!
            .Where(l => l.Id == id)
            .Select(l => _jsonData.GetPopulatedLoan(l))
            .FirstOrDefault();
    }

    ```

1. 若要接受更新后的 GetLoan 方法，请选择“**接受**”。

1. 选择 **UpdateLoan** 方法。

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = null;
        foreach (Loan l in _jsonData.Loans!)
        {
            if (l.Id == loan.Id)
            {
                existingLoan = l;
                break;
            }
        }
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    例如，输入以下提示：

    ```plaintext
    #selection refactor selection using LINQ find an existing loan `_jsonData.Loans!. Replace existing loan.
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

    更新的代码使用 LINQ 查找借阅集合中的现有借阅。 然后，它会使用新的借阅数据更新现有借阅。 然后，该方法保存更新后的借阅集合，并重新加载数据。 此方法可确保正确更新借阅数据，并将更改保存到数据存储。

    还可以添加代码，以确保在执行方法之前加载数据：

    ```csharp

    public async Task UpdateLoan(Loan loan)
    {
        await _jsonData.EnsureDataLoaded();
        Loan? existingLoan = _jsonData.Loans!.FirstOrDefault(l => l.Id == loan.Id);
        if (existingLoan != null)
        {
            existingLoan.BookItemId = loan.BookItemId;
            existingLoan.PatronId = loan.PatronId;
            existingLoan.LoanDate = loan.LoanDate;
            existingLoan.DueDate = loan.DueDate;
            existingLoan.ReturnDate = loan.ReturnDate;
            await _jsonData.SaveLoans(_jsonData.Loans!);
            await _jsonData.LoadData();
        }
    }

    ```

1. 若要接受更新后的 UpdateLoan 方法，请选择“**接受**”。

1. 将更改保存到 JsonLoanRepository.cs 文件。

1. 生成解决方案以确保不会出现错误。

    你将看到警告。 现在可以忽略这些文件。

#### 任务 3：重构 JsonPatronRepository 中的方法以使用 LINQ

JsonPatronRepository 类包括 SearchPatrons、GetPatron 和 UpdatePatron 方法，非常适合进行优化。 你将重构这两种方法，将 foreach 循环替换为 LINQ，以提高代码可读性和可维护性。

请使用以下步骤完成本练习的这一部分：

1. 打开 **JsonPatronRepository.cs** 文件。

1. 选择 **SearchPatrons** 方法。

    SearchPatrons 方法旨在按姓名搜索借阅者。

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = new List<Patron>();
        foreach (Patron patron in _jsonData.Patrons)
        {
            if (patron.Name.Contains(searchInput))
            {
                searchResults.Add(patron);
            }
        }
        searchResults.Sort((p1, p2) => String.Compare(p1.Name, p2.Name));
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    例如，输入以下提示：

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Replace the loop with `Where`, `OrderBy`, and `GetPopulatedPatrons`.
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public async Task<List<Patron>> SearchPatrons(string searchInput)
    {
        await _jsonData.EnsureDataLoaded();
        List<Patron> searchResults = _jsonData.Patrons!
            .Where(patron => patron.Name.Contains(searchInput))
            .OrderBy(patron => patron.Name)
            .ToList();
        searchResults = _jsonData.GetPopulatedPatrons(searchResults);
        return searchResults;
    }

    ```

1. 若要接受更新后的 SearchPatrons 方法，请选择“**接受**”。

1. 选择 **GetPatron** 方法。

    GetPatron 方法旨在返回与指定“id”匹配的借阅者。

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        foreach (Patron patron in _jsonData.Patrons!)
        {
            if (patron.Id == id)
            {
                Patron populated = _jsonData.GetPopulatedPatron(patron);
                return populated;
            }
        }
        return null;
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    例如，输入以下提示：

    ```plaintext
    #selection refactor selection using LINQ with `_jsonData.Patrons!. Use `Where`, `Select` and `GetPopulatedPatron` to return `FirstOrDefault`
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        var patron = _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
        return patron;
    }

    ```

    可以进一步简化此代码：

    ```C#

    public async Task<Patron?> GetPatron(int id)
    {
        await _jsonData.EnsureDataLoaded();
        return _jsonData.Patrons!
            .Where(p => p.Id == id)
            .Select(p => _jsonData.GetPopulatedPatron(p))
            .FirstOrDefault();
    }

    ```

1. 若要接受更新后的 GetPatron 方法，请选择“**接受**”。

1. 选择 **UpdatePatron** 方法。

    UpdatePatron 方法旨在更新具有指定“id”的借阅者。

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        Patron existingPatron = null;
        foreach (var p in patrons)
        {
            if (p.Id == patron.Id)
            {
                existingPatron = p;
                break;
            }
        }
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. 打开内联聊天，然后使用 LINQ 输入重构方法的提示。

    例如，输入以下提示：

    ```plaintext
    #selection refactor selection using LINQ to find `patron` in `_jsonData.Patrons!. Replace existing patron with `patron`.
    ```

1. 请花点时间来查看建议的更新。

    建议的更新看起来应类似于以下代码：

    ```csharp

    public async Task UpdatePatron(Patron patron)
    {
        await _jsonData.EnsureDataLoaded();
        var patrons = _jsonData.Patrons!;
        var existingPatron = patrons.FirstOrDefault(p => p.Id == patron.Id);
        if (existingPatron != null)
        {
            existingPatron.Name = patron.Name;
            existingPatron.ImageName = patron.ImageName;
            existingPatron.MembershipStart = patron.MembershipStart;
            existingPatron.MembershipEnd = patron.MembershipEnd;
            existingPatron.Loans = patron.Loans;
            await _jsonData.SavePatrons(patrons);
            await _jsonData.LoadData();
        }
    }

    ```

1. 若要接受更新后的 UpdatePatron 方法，请选择“**接受**”。

#### 任务 4：检查你的工作

使用以下步骤检查工作：

1. 若要清理解决方案，右键单击 **AccelerateAppDevGitHubCopilot**，然后选择“**清理**”。

    此操作从上一个生成中删除任何生成项目。 清理解决方案会有效地将 JSON 数据文件重置为其原始值（在输出目录中）。

1. 生成应用程序，并确保没有任何错误。

1. 运行该应用程序。

    可以从“解决方案资源管理器”视图中通过右击“**Library.Console**”项目，选择“**调试**”，然后选择“**启动新实例**”来运行应用程序。

1. 当系统提示你输入借阅者姓名时，请键入 1，然后按 Enter****。

1. 在“匹配借阅者”提示处键入 2，然后按 Enter****。

1. 在“图书借阅”提示处键入 1，然后按 Enter****。

1. 在“输入选项”提示处键入 r，然后按 Enter****。

1. 确认是否显示 **“书籍已成功归还。”** 的消息。 显示。

1. 若要开始新的搜索，请键入 s，然后按 Enter****。

1. 当系统提示你输入借阅者姓名时，请键入 1，然后按 Enter****。

1. 在“匹配借阅者”提示处键入 2，然后按 Enter****。

1. 确认第一本书籍的借阅记录是否标记为 **Returned: True**。

1. 在“输入选项”提示处键入 q，然后按 Enter****。

1. 停止应用程序。

#### 摘要 - 练习 9

在本练习中，你重构了 JsonData、JsonLoanRepository 和 JsonPatronRepository 类中的数据访问方法以使用 LINQ。 这些更改可以提高代码可读性、可维护性和性能。
