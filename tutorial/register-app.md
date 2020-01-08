<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="8177f-101">В этом упражнении вы создадите новое приложение Azure Active Directory, которое будет использоваться для предоставления делегированных разрешений для настраиваемого соединителя.</span><span class="sxs-lookup"><span data-stu-id="8177f-101">In this exercise, you will create a new Azure Active Directory Application which will be used to provide the delegated permissions for the custom connector.</span></span>

<span data-ttu-id="8177f-102">Откройте браузер и перейдите в [центр администрирования Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8177f-102">Open a browser and navigate to [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="8177f-103">Выберите ссылку **Azure Active Directory** в левом меню навигации, а затем выберите запись **регистрации приложений** в разделе **Управление** в колонке **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="8177f-103">Choose the **Azure Active Directory** link in the left navigation menu, then choose the **App registrations** entry in the **Manage** section of the **Azure Active Directory** blade.</span></span>

![Снимок колонки Azure Active Directory в центре администрирования Azure Active Directory](./images/app-reg1.png)

<span data-ttu-id="8177f-105">Выберите новый элемент меню **Регистрация приложения** в верхней части колонки **Регистрация приложений** .</span><span class="sxs-lookup"><span data-stu-id="8177f-105">Choose the **New application registration** menu item at the top of the **App Registrations** blade.</span></span>

![Снимок колонки "Регистрация приложений" в центре администрирования Azure Active Directory](./images/app-reg2.png)

<span data-ttu-id="8177f-107">Введите `MS Graph Batch App` в поле **имя** , а `https://localhost.com/$batch` в поле **URL-адрес входа** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="8177f-107">Enter `MS Graph Batch App` in the **Name** field, and `https://localhost.com/$batch` in the **Sign-on URL** field and choose **Create**.</span></span>

![Снимок экрана с формой создания для новой регистрации приложения в центре администрирования Azure Active Directory](./images/app-reg3.png)

<span data-ttu-id="8177f-109">На странице **Пакетное приложение MS Graph** скопируйте **идентификатор** приложения.</span><span class="sxs-lookup"><span data-stu-id="8177f-109">On the **MS Graph Batch App** page, copy the **Application ID** of the application.</span></span> <span data-ttu-id="8177f-110">Это потребуется в следующем упражнении.</span><span class="sxs-lookup"><span data-stu-id="8177f-110">You'll need this in the next exercise.</span></span>

![Снимок экрана со страницей "зарегистрированное приложение"](./images/app-reg4.png)

<span data-ttu-id="8177f-112">Выберите **Параметры** в разделе Имя приложения, а затем выберите элемент меню **необходимые разрешения** в колонке параметры.</span><span class="sxs-lookup"><span data-stu-id="8177f-112">Choose the **Settings** gear under the application name, then choose the **Required Permissions** menu item in the Settings blade.</span></span> <span data-ttu-id="8177f-113">В верхней части **обязательных разрешений** нажмите кнопку **Добавить** .</span><span class="sxs-lookup"><span data-stu-id="8177f-113">Choose **Add** at the top of the **Required Permissions** blade.</span></span>

![Снимок экрана, на котором находится требуемая колонка разрешений](./images/app-perms1.png)

<span data-ttu-id="8177f-115">В колонке **Добавить API Access** выберите параметр **выбрать API** , а затем выберите элемент **Microsoft Graph** и нажмите **кнопку Выбрать** в нижней части колонки.</span><span class="sxs-lookup"><span data-stu-id="8177f-115">Choose the **Select an API** option in the **Add API access** blade, then select the **Microsoft Graph** item and choose **Select** at the bottom of the blade.</span></span>

![Снимок экрана "Выбор элемента API"](./images/app-perms2.png)

<span data-ttu-id="8177f-117">В колонке **включить доступ** прокрутите окно вниз до раздела **делегированные разрешения** .</span><span class="sxs-lookup"><span data-stu-id="8177f-117">On the **Enable Access** blade, scroll down to the **Delegated Permissions** section.</span></span> <span data-ttu-id="8177f-118">Выберите разрешения на **чтение и запись всех групп** , а затем нажмите кнопку **выбрать** в нижней части колонки.</span><span class="sxs-lookup"><span data-stu-id="8177f-118">Select the **Read and write all groups** delegated permission, then choose **Select** at the bottom of the blade.</span></span> <span data-ttu-id="8177f-119">Нажмите кнопку **done (Готово** ) в нижней части колонки **Add API Access** .</span><span class="sxs-lookup"><span data-stu-id="8177f-119">Choose **Done** at the bottom of the **Add API access** blade.</span></span>

 ![Снимок экрана, на котором разрешите доступ](./images/app-perms3.png)

<span data-ttu-id="8177f-121">Выберите пункт меню **клавиши** в колонке **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="8177f-121">Choose the **Keys** menu item on the **Settings** blade.</span></span> <span data-ttu-id="8177f-122">Введите `forever` в поле **ключевое описание** и выберите **срок действия не ограничен** в раскрывающемся меню **Длительность** .</span><span class="sxs-lookup"><span data-stu-id="8177f-122">Enter `forever` in the **Key description** and select **Never expires** from the **Duration** drop down menu.</span></span> <span data-ttu-id="8177f-123">Нажмите кнопку **сохранить** в верхней части колонки " **ключи** ".</span><span class="sxs-lookup"><span data-stu-id="8177f-123">Choose **Save** at the top of the **Keys** blade.</span></span> <span data-ttu-id="8177f-124">Скопируйте значение ключа для нового ключа.</span><span class="sxs-lookup"><span data-stu-id="8177f-124">Copy the key value for the new key.</span></span> <span data-ttu-id="8177f-125">Это потребуется в следующем упражнении.</span><span class="sxs-lookup"><span data-stu-id="8177f-125">You'll need this in the next exercise.</span></span>

![Снимок колонки "клавиши"](./images/app-key1.png)

> [!IMPORTANT]
> <span data-ttu-id="8177f-127">Этот шаг очень важен, так как при закрытии этой колонки ключ будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="8177f-127">This step is critical as the key will not be accessible once you close this blade.</span></span> <span data-ttu-id="8177f-128">Сохраните этот ключ в текстовом редакторе, чтобы использовать его в предстоящих упражнениях.</span><span class="sxs-lookup"><span data-stu-id="8177f-128">Save this key to a text editor for use in upcoming exercises.</span></span>

<span data-ttu-id="8177f-129">Чтобы включить управление дополнительными службами через Microsoft Graph, в том числе свойства Teams, необходимо выбрать дополнительные, соответствующие области, чтобы разрешить управление определенными службами.</span><span class="sxs-lookup"><span data-stu-id="8177f-129">To enable management of additional services accessible via the Microsoft Graph, including Teams properties, you would need to select additional, appropriate scopes to enable managing specific services.</span></span> <span data-ttu-id="8177f-130">Например, чтобы расширить решение для создания записных книжек OneNote или планов планировщика, сегментов и задач, необходимо добавить необходимые области разрешений для соответствующих API.</span><span class="sxs-lookup"><span data-stu-id="8177f-130">For example, to extend our solution to enable creating OneNote Notebooks or Planner plans, buckets and tasks you would need to add the required permission scopes for the relevant APIs.</span></span>
