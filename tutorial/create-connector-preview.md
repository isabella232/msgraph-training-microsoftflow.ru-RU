<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="f5749-101">В этом упражнении вы создадите новый настраиваемый соединитель, который можно использовать в последовательности или в приложениях логики Azure.</span><span class="sxs-lookup"><span data-stu-id="f5749-101">In this exercise, you will create a new custom connector which can be used in Flow or in Azure Logic Apps.</span></span> <span data-ttu-id="f5749-102">В файле определения Open API предварительно создается правильный путь к конечной точке Microsoft Graph `$batch` и дополнительные параметры для включения простого импорта.</span><span class="sxs-lookup"><span data-stu-id="f5749-102">The Open API definition file is prebuilt with the correct path for the Microsoft Graph `$batch` endpoint and additional settings to enable simple import.</span></span>

<span data-ttu-id="f5749-103">С помощью текстового редактора создайте новый пустой файл с именем `MSGraph-Delegate-Batch.swagger.json` и добавьте приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="f5749-103">Using a text editor, create a new empty file named `MSGraph-Delegate-Batch.swagger.json` and add the following code.</span></span>

[!code-json[](../LabFiles/MSGraph-Delegate-Batch.swagger.json)]

<span data-ttu-id="f5749-104">Откройте браузер и перейдите в [Microsoft Flow](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f5749-104">Open a browser and navigate to [Microsoft Flow](https://flow.microsoft.com).</span></span> <span data-ttu-id="f5749-105">Войдите с помощью учетной записи администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5749-105">Sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="f5749-106">В меню слева разверните пункт **данные** и выберите пункт **настраиваемые соединители**.</span><span class="sxs-lookup"><span data-stu-id="f5749-106">In the left-hand menu, expand **Data** and choose **Custom connectors**.</span></span>

![Снимок экрана с элементом меню настраиваемых соединителей в Microsoft Flow](./images/flow-conn1.png)

<span data-ttu-id="f5749-108">На странице " **настраиваемые соединители** " выберите ссылку **создать настраиваемый соединитель** в правом верхнем углу, а затем в раскрывающемся меню выберите пункт **импортировать файл опенапи** .</span><span class="sxs-lookup"><span data-stu-id="f5749-108">On the **Custom connectors** page choose the **New custom connector** link in the top right, then select the **Import an OpenAPI file** item in the drop-down menu.</span></span> <span data-ttu-id="f5749-109">Введите `MS Graph Batch Connector` в текстовом поле **имя соединителя** .</span><span class="sxs-lookup"><span data-stu-id="f5749-109">Enter `MS Graph Batch Connector` in the **Connector name** text box.</span></span> <span data-ttu-id="f5749-110">Нажмите кнопку **Импорт** , чтобы отправить файл Open API.</span><span class="sxs-lookup"><span data-stu-id="f5749-110">Choose **Import** button to upload the Open API file.</span></span> <span data-ttu-id="f5749-111">Перейдите к созданному `MSGraph-Delegate-Batch.swagger.json` файлу.</span><span class="sxs-lookup"><span data-stu-id="f5749-111">Browse to the `MSGraph-Delegate-Batch.swagger.json` file you created.</span></span> <span data-ttu-id="f5749-112">Нажмите **продолжить** , чтобы отправить файл опенапи.</span><span class="sxs-lookup"><span data-stu-id="f5749-112">Choose **Continue** to upload the OpenAPI file.</span></span>

 ![Снимок экрана диалогового окна "Создание настраиваемого соединителя"](./images/flow-conn3.png)

<span data-ttu-id="f5749-114">На странице Конфигурация соединителя выберите ссылку **Безопасность** в меню Навигация.</span><span class="sxs-lookup"><span data-stu-id="f5749-114">On the connector configuration page, choose the **Security** link in the navigation menu.</span></span> <span data-ttu-id="f5749-115">Заполните поля, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="f5749-115">Fill in the fields as follows.</span></span>

- <span data-ttu-id="f5749-116">**Выберите, какую проверку подлинности реализует ваш API**:`OAuth 2.0`</span><span class="sxs-lookup"><span data-stu-id="f5749-116">**Choose what authentication is implemented by your API**: `OAuth 2.0`</span></span>
- <span data-ttu-id="f5749-117">**Поставщик удостоверений**:`Azure Active Directory`</span><span class="sxs-lookup"><span data-stu-id="f5749-117">**Identity Provider**: `Azure Active Directory`</span></span>
- <span data-ttu-id="f5749-118">**Идентификатор клиента**: идентификатор приложения, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="f5749-118">**Client id**: the application ID you created in the previous exercise</span></span>
- <span data-ttu-id="f5749-119">**Секрет клиента**: ключ, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="f5749-119">**Client secret**: the key you created in the previous exercise</span></span>
- <span data-ttu-id="f5749-120">**URL-адрес входа**:`https://login.windows.net`</span><span class="sxs-lookup"><span data-stu-id="f5749-120">**Login url**: `https://login.windows.net`</span></span>
- <span data-ttu-id="f5749-121">**Идентификатор клиента**:`common`</span><span class="sxs-lookup"><span data-stu-id="f5749-121">**Tenant ID**: `common`</span></span>
- <span data-ttu-id="f5749-122">**URL-адрес ресурса**: `https://graph.microsoft.com` (без замыкающего/)</span><span class="sxs-lookup"><span data-stu-id="f5749-122">**Resource URL**: `https://graph.microsoft.com` (no trailing /)</span></span>
- <span data-ttu-id="f5749-123">**Область**: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="f5749-123">**Scope**: Leave blank</span></span>

<span data-ttu-id="f5749-124">Нажмите кнопку **создать соединитель** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="f5749-124">Choose **Create Connector** on the top-right</span></span>

![Снимок экрана вкладки "безопасность" в конфигурации соединителя](./images/flow-conn4.png)

<span data-ttu-id="f5749-126">После создания соединителя Скопируйте созданный **URL-адрес перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="f5749-126">After the connector has been created, copy the generated **Redirect URL**.</span></span>

![Снимок экрана с созданным URL-адресом перенаправления](./images/flow-conn5.png)

<span data-ttu-id="f5749-128">Вернитесь к зарегистрированному приложению на [портале Azure](https://aad.portal.azure.com) , созданному в предыдущем упражнении.</span><span class="sxs-lookup"><span data-stu-id="f5749-128">Go back to the registered application in the [Azure Portal](https://aad.portal.azure.com) you created in the previous exercise.</span></span> <span data-ttu-id="f5749-129">Выберите **Обзор** в колонке **Пакетное приложение MS Graph** , а затем выберите **Добавить URI перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="f5749-129">Select **Overview** on the **MS Graph Batch App** blade, then select **Add a Redirect URI**.</span></span> <span data-ttu-id="f5749-130">Добавьте **URL-адрес перенаправления** , скопированный в поле **URI перенаправления** , и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f5749-130">Add the **Redirect URL** you copied in the **Redirect URI** field and choose **Save**.</span></span>

![Снимок колонки "URL-адреса ответа" на портале Azure](./images/flow-conn-preview6.png)
