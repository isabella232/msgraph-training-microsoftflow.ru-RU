<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="807b8-101">В этом упражнении вы создадите последовательность для использования настраиваемого соединителя, созданного в предыдущих упражнениях, для создания и настройки группы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="807b8-101">In this exercise, you will create a Flow to use the custom connector you created in previous exercises to create and configure a Microsoft Team.</span></span> <span data-ttu-id="807b8-102">Этот процесс использует настраиваемый соединитель для отправки запроса POST на создание единой группы Office 365, приостанавливается на задержку при завершении создания группы, а затем отправляет запрос PUT для связи группы с командой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="807b8-102">The Flow will use the custom connector to send a POST request to create an Office 365 Unified Group, will pause for a delay while the group creation completes, and then will send a PUT request to associate the group with a Microsoft Team.</span></span>

<span data-ttu-id="807b8-103">В конце ваш процесс будет выглядеть примерно так, как показано на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="807b8-103">In the end your Flow will look similar to the following image:</span></span>

![Снимок завершенного процесса](./images/flow-team1.png)

<span data-ttu-id="807b8-105">Откройте [Microsoft Flow](https://flow.microsoft.com) в браузере и войдите с помощью учетной записи администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="807b8-105">Open [Microsoft Flow](https://flow.microsoft.com) in your browser and sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="807b8-106">Выберите пункт **мои потоки** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="807b8-106">Choose **My Flows** in the left-hand navigation.</span></span> <span data-ttu-id="807b8-107">Выберите **создать**, а затем **Создайте из пустого**.</span><span class="sxs-lookup"><span data-stu-id="807b8-107">Choose **New**, then **Create from blank**.</span></span> <span data-ttu-id="807b8-108">Выберите **создать из пустого**.</span><span class="sxs-lookup"><span data-stu-id="807b8-108">Choose **Create from blank**.</span></span> <span data-ttu-id="807b8-109">Введите `Manual` в поле поиска и добавьте триггер **процесса вручную** .</span><span class="sxs-lookup"><span data-stu-id="807b8-109">Enter `Manual` in the search box and add the **Manually trigger a flow** trigger.</span></span>

<span data-ttu-id="807b8-110">Нажмите кнопку **Добавить вход**, выберите **текст** и введите `Name` название.</span><span class="sxs-lookup"><span data-stu-id="807b8-110">Choose **Add an input**, select **Text** and enter `Name` as the title.</span></span>

![Снимок экрана, запускающий триггер процесса вручную](./images/flow-team6.png)

<span data-ttu-id="807b8-112">Выберите **новый шаг** и введите `Batch` в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="807b8-112">Choose **New step** and type `Batch` in the search box.</span></span> <span data-ttu-id="807b8-113">Добавьте действие **пакетНого соединителя MS Graph** .</span><span class="sxs-lookup"><span data-stu-id="807b8-113">Add the **MS Graph Batch Connector** action.</span></span> <span data-ttu-id="807b8-114">Нажмите кнопку с многоточием и переименуйте это `Batch POST-groups`действие в.</span><span class="sxs-lookup"><span data-stu-id="807b8-114">Choose the ellipsis and rename this action to `Batch POST-groups`.</span></span>

<span data-ttu-id="807b8-115">Добавьте следующий код в поле **основного** текста действия.</span><span class="sxs-lookup"><span data-stu-id="807b8-115">Add the following code into the **body** text box of the action.</span></span>

```json
{
  "requests": [
    {
      "url": "/groups",
      "method": "POST",
      "id": 1,
      "headers": { "Content-Type": "application/json" },
      "body": {
        "description": "REPLACE",
        "displayName": "REPLACE",
        "groupTypes": ["Unified"],
        "mailEnabled": true,
        "mailNickname": "REPLACE",
        "securityEnabled": false
      }
    }
  ]
}
```

<span data-ttu-id="807b8-116">Замените каждый `REPLACE` заполнитель, выбрав `Name` значение из триггера вручную в меню **Добавление динамического содержимого** .</span><span class="sxs-lookup"><span data-stu-id="807b8-116">Replace each `REPLACE` placeholder by selecting the `Name` value from the manual trigger from the **Add dynamic content** menu.</span></span>

![Снимок меню динамического содержимого в Microsoft Flow](./images/flow-team2.png)

<span data-ttu-id="807b8-118">Выберите **новый шаг**, поиск `delay` и Добавление действия **задержки** и настройка в течение 1 минуты.</span><span class="sxs-lookup"><span data-stu-id="807b8-118">Choose **New step**, search for `delay` and add a **Delay** action and configure for 1 minute.</span></span>

<span data-ttu-id="807b8-119">Выберите **новый шаг** и введите `Batch` в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="807b8-119">Choose **New step** and type `Batch` in the search box.</span></span> <span data-ttu-id="807b8-120">Добавьте действие **пакетНого соединителя MS Graph** .</span><span class="sxs-lookup"><span data-stu-id="807b8-120">Add the **MS Graph Batch Connector** action.</span></span> <span data-ttu-id="807b8-121">Нажмите кнопку с многоточием и переименуйте это `Batch PUT-team`действие в.</span><span class="sxs-lookup"><span data-stu-id="807b8-121">Choose the ellipsis and rename this action to `Batch PUT-team`.</span></span>

<span data-ttu-id="807b8-122">Добавьте следующий код в поле **основного** текста действия.</span><span class="sxs-lookup"><span data-stu-id="807b8-122">Add the following code into the **body** text box of the action.</span></span>

```json
{
  "requests": [
    {
      "id": 1,
      "url": "/groups/REPLACE/team",
      "method": "PUT",
      "headers": {
        "Content-Type": "application/json"
      },
      "body": {
        "memberSettings": {
          "allowCreateUpdateChannels": true
        },
        "messagingSettings": {
          "allowUserEditMessages": true,
          "allowUserDeleteMessages": true
        },
        "funSettings": {
          "allowGiphy": true,
          "giphyContentRating": "strict"
        }
      }
    }
  ]
}
```

<span data-ttu-id="807b8-123">Выберите `REPLACE` заполнитель, а затем выберите **выражение** в области динамический контент.</span><span class="sxs-lookup"><span data-stu-id="807b8-123">Select the `REPLACE` placeholder, then select **Expression** in the dynamic content pane.</span></span> <span data-ttu-id="807b8-124">Добавьте в **выражение**следующую формулу.</span><span class="sxs-lookup"><span data-stu-id="807b8-124">Add the following formula into the **Expression**.</span></span>

```js
body('Batch_POST-groups').responses[0].body.id
```

![Снимок экрана с выражением в области динамического содержимого](./images/flow-formula.png)

<span data-ttu-id="807b8-126">Эта формула указывает, что мы хотим использовать идентификатор группы из результата первого действия.</span><span class="sxs-lookup"><span data-stu-id="807b8-126">This formula specifies that we want to use the group ID from the result of the first action.</span></span>

![Снимок экрана с обновленным текстом действия](./images/flow-team3.png)

<span data-ttu-id="807b8-128">Нажмите кнопку **сохранить**, а затем последовательно выберите пункты **тест** для выполнения последовательности.</span><span class="sxs-lookup"><span data-stu-id="807b8-128">Choose **Save**, then Flow and choose **Test** to execute the Flow.</span></span>

> [!TIP]
> <span data-ttu-id="807b8-129">Если возникнет ошибка `The template validation failed: 'The action(s) 'Batch_POST-groups' referenced by 'inputs' in action 'Batch_2' are not defined in the template'`, выражение является неверным и, скорее всего, ссылается на действие, которое не удается найти.</span><span class="sxs-lookup"><span data-stu-id="807b8-129">If you receive an error like `The template validation failed: 'The action(s) 'Batch_POST-groups' referenced by 'inputs' in action 'Batch_2' are not defined in the template'`, the expression is incorrect and likely references a Flow action it cannot find.</span></span> <span data-ttu-id="807b8-130">Убедитесь, что имя действия, на которое вы ссылаетесь, соответствует точно.</span><span class="sxs-lookup"><span data-stu-id="807b8-130">Ensure that the action name you are referencing matches exactly.</span></span>

<span data-ttu-id="807b8-131">Выберите переключатель **я** выполню действие триггера и выберите команду **сохранить тест _амп_**.</span><span class="sxs-lookup"><span data-stu-id="807b8-131">Choose the **I'll perform the trigger** action radio button and choose **Save & Test**.</span></span> <span data-ttu-id="807b8-132">Нажмите кнопку **продолжить** в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="807b8-132">Choose **Continue** in the dialog.</span></span> <span data-ttu-id="807b8-133">Введите имя без пробелов и выберите команду **выполнить поток** для создания команды.</span><span class="sxs-lookup"><span data-stu-id="807b8-133">Provide a name without spaces, and choose **Run flow** to create a Team.</span></span>

![Снимок экрана с диалоговым окном потока запуска](./images/flow-team4.png)

<span data-ttu-id="807b8-135">Наконец, щелкните ссылку **действие выполнение потока** , а затем выберите запущенный поток, чтобы просмотреть журнал действий.</span><span class="sxs-lookup"><span data-stu-id="807b8-135">Finally, choose the **See flow run activity** link, then select the running Flow to see the activity log.</span></span>

> [!NOTE]
> <span data-ttu-id="807b8-136">Чтобы просмотреть выполнение потока, может потребоваться щелкнуть запущенный экземпляр потока в списке Журнал выполнения.</span><span class="sxs-lookup"><span data-stu-id="807b8-136">You may have to click on your running Flow instance in the Run history list to view your Flow execution.</span></span>

<span data-ttu-id="807b8-137">По завершении процесса вы настроили группу и команду Office 365.</span><span class="sxs-lookup"><span data-stu-id="807b8-137">Once the Flow completes, your Office 365 Group and Team have been configured.</span></span> <span data-ttu-id="807b8-138">Выберите элементы пакетного действия, чтобы просмотреть результаты пакетных вызовов JSON.</span><span class="sxs-lookup"><span data-stu-id="807b8-138">Select the Batch action items to view the results of the JSON Batch calls.</span></span> <span data-ttu-id="807b8-139">`outputs` Действие должно иметь код состояния 201 для успешного сопоставления команды, как показано на рисунке `Batch PUT-team` ниже.</span><span class="sxs-lookup"><span data-stu-id="807b8-139">The `outputs` of the `Batch PUT-team` action should have a status code of 201 for a successful Team association similar to the image below.</span></span>

![Снимок журнала действий "успешный ход работы"](./images/flow-team5.png)