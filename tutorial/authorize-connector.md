<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="4e7fa-101">Последняя настройка, позволяющая убедиться, что соединитель готов к использованию, — авторизация и тестирование настраиваемого соединителя для создания кэшированного подключения.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-101">The final configuration step to ensure the connector is ready for use is to authorize and test the custom connector to create a cached connection.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7fa-102">Для выполнения описанных ниже действий необходимо войти в систему с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-102">The following steps requires that you are logged in with administrator privileges.</span></span>

<span data-ttu-id="4e7fa-103">В [Microsoft Flow](https://flow.microsoft.com)перейдите к экрану конфигурация соединителя и выберите ссылку **проверить** в меню Навигация.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-103">In [Microsoft Flow](https://flow.microsoft.com), go to the Connector configuration screen and choose the **Test** link in the navigation menu.</span></span> <span data-ttu-id="4e7fa-104">Выберите ссылку **создать подключение** .</span><span class="sxs-lookup"><span data-stu-id="4e7fa-104">Choose the **New Connection** link.</span></span> <span data-ttu-id="4e7fa-105">Войдите с помощью учетной записи Azure Active Directory администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-105">Sign in with your Office 365 tenant administrator's Azure Active Directory account.</span></span>

<span data-ttu-id="4e7fa-106">При получении запроса на получение запрошенных разрешений проверяйте **согласие от имени вашей организации** , а затем нажмите кнопку **принять** для авторизации разрешений.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-106">When prompted for the requested permissions, check **Consent on behalf of your organization** and then choose **Accept** to authorize permissions.</span></span>

![Снимок экрана с запросом разрешений](./images/flow-conn8.png)

<span data-ttu-id="4e7fa-108">После авторизации разрешений будет создано подключение.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-108">After you authorize the permissions, a connection is created in Flow.</span></span>

![Снимок экрана созданного подключения в Microsoft Flow](./images/flow-conn9.png)

<span data-ttu-id="4e7fa-110">Настраиваемый соединитель теперь настроен и включен.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-110">The custom connector is now configured and enabled.</span></span> <span data-ttu-id="4e7fa-111">Возможна задержка, связанная с применением и доступностью разрешений, но соединитель настроен.</span><span class="sxs-lookup"><span data-stu-id="4e7fa-111">There may be a delay in permissions being applied and available, but the connector is now configured.</span></span>
