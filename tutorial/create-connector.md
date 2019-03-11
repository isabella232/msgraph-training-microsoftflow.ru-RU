<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="a7bd5-101">В этом упражнении вы создадите новый настраиваемый соединитель, который можно использовать в последовательности или в приложениях логики Azure.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-101">In this exercise, you will create a new custom connector which can be used in Flow or in Azure Logic Apps.</span></span> <span data-ttu-id="a7bd5-102">В файле определения Open API предварительно создается правильный путь к конечной точке Microsoft Graph `$batch` и дополнительные параметры для включения простого импорта.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-102">The Open API definition file is prebuilt with the correct path for the Microsoft Graph `$batch` endpoint and additional settings to enable simple import.</span></span>

<span data-ttu-id="a7bd5-103">С помощью текстового редактора создайте новый пустой файл с именем `MSGraph-Delegate-Batch.swagger.json` и добавьте приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-103">Using a text editor, create a new empty file named `MSGraph-Delegate-Batch.swagger.json` and add the following code.</span></span>

[!code-json[](../LabFiles/MSGraph-Delegate-Batch.swagger.json)]

<span data-ttu-id="a7bd5-104">Откройте браузер и перейдите в [Microsoft Flow](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a7bd5-104">Open a browser and navigate to [Microsoft Flow](https://flow.microsoft.com).</span></span> <span data-ttu-id="a7bd5-105">Войдите с помощью учетной записи администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-105">Sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="a7bd5-106">Щелкните значок шестеренки в правом верхнем углу и выберите элемент **настраиваемые соединители** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-106">Choose the gear icon in the upper right, and select the **Custom Connectors** item in the drop-down menu.</span></span>

![Снимок экрана с раскрывающимся меню в Microsoft Flow](./images/flow-conn1.png)

<span data-ttu-id="a7bd5-108">На странице " **настраиваемые соединители** " выберите ссылку **создать настраиваемый соединитель** в правом верхнем углу, а затем в расКрывающемся меню выберите пункт **импортировать файл открытого API** .</span><span class="sxs-lookup"><span data-stu-id="a7bd5-108">On the **Custom Connectors** page choose the **Create custom connector** link in the top right, then select the **Import an Open API file** item in the drop-down menu.</span></span>

 ![Снимок экрана с раскрывающимся меню "создать настраиваемый соединитель" в Microsoft Flow](./images/flow-conn2.png)

<span data-ttu-id="a7bd5-110">Введите `MS Graph Batch Connector` в текстовое поле **имя настраиваемого соединителя** .</span><span class="sxs-lookup"><span data-stu-id="a7bd5-110">Enter `MS Graph Batch Connector` in the **Custom connector name** text box.</span></span> <span data-ttu-id="a7bd5-111">Нажмите значок папки, чтобы отправить файл Open API.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-111">Choose the folder icon to upload the Open API file.</span></span> <span data-ttu-id="a7bd5-112">Перейдите к созданному `MSGraph-Delegate-Batch.swagger.json` файлу.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-112">Browse to the `MSGraph-Delegate-Batch.swagger.json` file you created.</span></span> <span data-ttu-id="a7bd5-113">Нажмите **продолжить** , чтобы отправить файл Open API.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-113">Choose **Continue** to upload the Open API file.</span></span>

 ![Снимок экрана диалогового окна "Создание настраиваемого соединителя"](./images/flow-conn3.png)

<span data-ttu-id="a7bd5-115">На странице Конфигурация соединителя выберите ссылку **Безопасность** в меню Навигация.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-115">On the connector configuration page, choose the **Security** link in the navigation menu.</span></span> <span data-ttu-id="a7bd5-116">ЗаПолните поля, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-116">Fill in the fields as follows.</span></span>

- <span data-ttu-id="a7bd5-117">**Выберите, какую проверку подлинности реализует ваш API**:`OAuth 2.0`</span><span class="sxs-lookup"><span data-stu-id="a7bd5-117">**Choose what authentication is implemented by your API**: `OAuth 2.0`</span></span>
- <span data-ttu-id="a7bd5-118">**Поставщик удостоверений**:`Azure Active Directory`</span><span class="sxs-lookup"><span data-stu-id="a7bd5-118">**Identity Provider**: `Azure Active Directory`</span></span>
- <span data-ttu-id="a7bd5-119">**Идентификатор клиента**: идентификатор приложения, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="a7bd5-119">**Client id**: the application ID you created in the previous exercise</span></span>
- <span data-ttu-id="a7bd5-120">**Секрет клиента**: ключ, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="a7bd5-120">**Client secret**: the key you created in the previous exercise</span></span>
- <span data-ttu-id="a7bd5-121">**URL-адрес входа**:`https://login.windows.net`</span><span class="sxs-lookup"><span data-stu-id="a7bd5-121">**Login url**: `https://login.windows.net`</span></span>
- <span data-ttu-id="a7bd5-122">**Идентификатор клиента**:`common`</span><span class="sxs-lookup"><span data-stu-id="a7bd5-122">**Tenant ID**: `common`</span></span>
- <span data-ttu-id="a7bd5-123">**URL-адрес ресурса**: `https://graph.microsoft.com` (без замыкающего/)</span><span class="sxs-lookup"><span data-stu-id="a7bd5-123">**Resource URL**: `https://graph.microsoft.com` (no trailing /)</span></span>
- <span data-ttu-id="a7bd5-124">**Область**: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="a7bd5-124">**Scope**: Leave blank</span></span>

<span data-ttu-id="a7bd5-125">Нажмите кнопку **создать соединитель** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-125">Choose **Create Connector** on the top-right</span></span>

![Снимок экрана вкладки "безопасность" в конфигурации соединителя](./images/flow-conn4.png)

<span data-ttu-id="a7bd5-127">После создания соединителя Скопируйте созданный **URL-адрес перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-127">After the connector has been created, copy the generated **Redirect URL**.</span></span>

![Снимок экрана с созданным URL-АДРЕСом переНаправления](./images/flow-conn5.png)

<span data-ttu-id="a7bd5-129">Вернитесь к зарегистрированному приложению на портале [Azure](https://aad.portal.azure.com) , созданному в предыдущем упражнении.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-129">Go back to the registered application in the [Azure Portal](https://aad.portal.azure.com) you created in the previous exercise.</span></span> <span data-ttu-id="a7bd5-130">Выберите **URL-адреса ответа** в колонке **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="a7bd5-130">Select **Reply URLs** in the **Settings** blade.</span></span> <span data-ttu-id="a7bd5-131">Добавьте **URL-адрес перенаправления** , скопированный в качестве дополнительного **URL-адреса ответа**.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-131">Add the **Redirect URL** you copied as an additional **Reply URL**.</span></span> <span data-ttu-id="a7bd5-132">Сохраните приложение на портале Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-132">Save the application in Azure Active Directory portal.</span></span>

![Снимок колонки "URL-адреса ответа" на портале Azure](./images/flow-conn6.png)