<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="ece4e-101">В этом упражнении вы создадите новый настраиваемый соединитель, который можно использовать в последовательности или в приложениях логики Azure.</span><span class="sxs-lookup"><span data-stu-id="ece4e-101">In this exercise, you will create a new custom connector which can be used in Flow or in Azure Logic Apps.</span></span> <span data-ttu-id="ece4e-102">В файле определения Open API предварительно создается правильный путь к конечной точке Microsoft Graph `$batch` и дополнительные параметры для включения простого импорта.</span><span class="sxs-lookup"><span data-stu-id="ece4e-102">The Open API definition file is prebuilt with the correct path for the Microsoft Graph `$batch` endpoint and additional settings to enable simple import.</span></span>

<span data-ttu-id="ece4e-103">С помощью текстового редактора создайте новый пустой файл с именем `MSGraph-Delegate-Batch.swagger.json` и добавьте приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="ece4e-103">Using a text editor, create a new empty file named `MSGraph-Delegate-Batch.swagger.json` and add the following code.</span></span>

[!code-json[](../LabFiles/MSGraph-Delegate-Batch.swagger.json)]

<span data-ttu-id="ece4e-104">Откройте браузер и перейдите в [Microsoft Flow](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ece4e-104">Open a browser and navigate to [Microsoft Flow](https://flow.microsoft.com).</span></span> <span data-ttu-id="ece4e-105">Войдите с помощью учетной записи администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="ece4e-105">Sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="ece4e-106">Щелкните значок шестеренки в правом верхнем углу и выберите элемент **настраиваемые соединители** в раскрывающемся меню.</span><span class="sxs-lookup"><span data-stu-id="ece4e-106">Choose the gear icon in the upper right, and select the **Custom Connectors** item in the drop-down menu.</span></span>

![Снимок экрана с раскрывающимся меню в Microsoft Flow](./images/flow-conn1.png)

<span data-ttu-id="ece4e-108">На странице " **настраиваемые соединители** " выберите ссылку **создать настраиваемый соединитель** в правом верхнем углу, а затем в расКрывающемся меню выберите пункт **импортировать файл открытого API** .</span><span class="sxs-lookup"><span data-stu-id="ece4e-108">On the **Custom Connectors** page choose the **Create custom connector** link in the top right, then select the **Import an Open API file** item in the drop-down menu.</span></span>

 ![Снимок экрана с раскрывающимся меню "создать настраиваемый соединитель" в Microsoft Flow](./images/flow-conn2.png)

<span data-ttu-id="ece4e-110">Введите `MS Graph Batch Connector` в текстовое поле **имя настраиваемого соединителя** .</span><span class="sxs-lookup"><span data-stu-id="ece4e-110">Enter `MS Graph Batch Connector` in the **Custom connector name** text box.</span></span> <span data-ttu-id="ece4e-111">Нажмите значок папки, чтобы отправить файл Open API.</span><span class="sxs-lookup"><span data-stu-id="ece4e-111">Choose the folder icon to upload the Open API file.</span></span> <span data-ttu-id="ece4e-112">Перейдите к созданному `MSGraph-Delegate-Batch.swagger.json` файлу.</span><span class="sxs-lookup"><span data-stu-id="ece4e-112">Browse to the `MSGraph-Delegate-Batch.swagger.json` file you created.</span></span> <span data-ttu-id="ece4e-113">Нажмите **продолжить** , чтобы отправить файл Open API.</span><span class="sxs-lookup"><span data-stu-id="ece4e-113">Choose **Continue** to upload the Open API file.</span></span>

 ![Снимок экрана диалогового окна "Создание настраиваемого соединителя"](./images/flow-conn3.png)

<span data-ttu-id="ece4e-115">На странице Конфигурация соединителя выберите ссылку **Безопасность** в меню Навигация.</span><span class="sxs-lookup"><span data-stu-id="ece4e-115">On the connector configuration page, choose the **Security** link in the navigation menu.</span></span> <span data-ttu-id="ece4e-116">ЗаПолните поля, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="ece4e-116">Fill in the fields as follows.</span></span>

- <span data-ttu-id="ece4e-117">**Выберите, какую проверку подлинности реализует ваш API**:`OAuth 2.0`</span><span class="sxs-lookup"><span data-stu-id="ece4e-117">**Choose what authentication is implemented by your API**: `OAuth 2.0`</span></span>
- <span data-ttu-id="ece4e-118">**Поставщик удостоверений**:`Azure Active Directory`</span><span class="sxs-lookup"><span data-stu-id="ece4e-118">**Identity Provider**: `Azure Active Directory`</span></span>
- <span data-ttu-id="ece4e-119">**Идентификатор клиента**: идентификатор приложения, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="ece4e-119">**Client id**: the application ID you created in the previous exercise</span></span>
- <span data-ttu-id="ece4e-120">**Секрет клиента**: ключ, созданный в предыдущем упражнении</span><span class="sxs-lookup"><span data-stu-id="ece4e-120">**Client secret**: the key you created in the previous exercise</span></span>
- <span data-ttu-id="ece4e-121">**URL-адрес входа**:`https://login.windows.net`</span><span class="sxs-lookup"><span data-stu-id="ece4e-121">**Login url**: `https://login.windows.net`</span></span>
- <span data-ttu-id="ece4e-122">**Идентификатор клиента**:`common`</span><span class="sxs-lookup"><span data-stu-id="ece4e-122">**Tenant ID**: `common`</span></span>
- <span data-ttu-id="ece4e-123">**URL-адрес ресурса**: `https://graph.microsoft.com` (без замыкающего/)</span><span class="sxs-lookup"><span data-stu-id="ece4e-123">**Resource URL**: `https://graph.microsoft.com` (no trailing /)</span></span>
- <span data-ttu-id="ece4e-124">**Область**: оставьте пустым</span><span class="sxs-lookup"><span data-stu-id="ece4e-124">**Scope**: Leave blank</span></span>

<span data-ttu-id="ece4e-125">Нажмите кнопку **создать соединитель** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="ece4e-125">Choose **Create Connector** on the top-right</span></span>

![Снимок экрана вкладки "безопасность" в конфигурации соединителя](./images/flow-conn4.png)

<span data-ttu-id="ece4e-127">После создания соединителя Скопируйте созданный **URL-адрес перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="ece4e-127">After the connector has been created, copy the generated **Redirect URL**.</span></span>

![Снимок экрана с созданным URL-АДРЕСом переНаправления](./images/flow-conn5.png)

<span data-ttu-id="ece4e-129">Вернитесь к зарегистрированному приложению на портале [Azure](https://aad.portal.azure.com) , созданному в предыдущем упражнении.</span><span class="sxs-lookup"><span data-stu-id="ece4e-129">Go back to the registered application in the [Azure Portal](https://aad.portal.azure.com) you created in the previous exercise.</span></span> <span data-ttu-id="ece4e-130">Выберите **Обзор** в колонке **Пакетное приложение MS Graph** , а затем выберите **Добавить URI перенаправления**.</span><span class="sxs-lookup"><span data-stu-id="ece4e-130">Select **Overview** on the **MS Graph Batch App** blade, then select **Add a Redirect URI**.</span></span> <span data-ttu-id="ece4e-131">Добавьте **URL-адрес перенаправления** , скопированный в поле **URI перенаправления** , и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ece4e-131">Add the **Redirect URL** you copied in the **Redirect URI** field and choose **Save**.</span></span>

![Снимок колонки "URL-адреса ответа" на портале Azure](./images/flow-conn-preview6.png)