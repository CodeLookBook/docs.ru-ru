---
title: "Общие архитектурах веб-приложений"
description: "Архитектора современных веб-приложений с помощью ASP.NET Core и Microsoft Azure | Общие архитектурах веб-приложений"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: b6236cfab290211f930d6a1987075abeade4fd6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
#<a name="common-web-application-architectures"></a>Общие архитектурах веб-приложений

> «Если вы считаете, что расходуется хорошей архитектуры, попробуйте неправильный архитектуры».  
> _-Нижний колонтитул Брайан и Джозеф Yoder_

## <a name="summary"></a>Сводка

Большинство традиционных приложений .NET, развертываются как один элемент, соответствующий исполняемый файл или одного веб-приложения, запущенного в рамках одного домена приложений служб IIS. Это самая легкая модель развертывания и служит многие внутренние и более мелкие открытые приложения очень хорошо. Однако наиболее нетривиальной бизнес-приложения даже Учитывая это единый элемент развертывания, преимущества некоторых логическое разделение в нескольких уровней.

## <a name="what-is-a-monolithic-application"></a>Что такое монолитные приложения?

Монолитные приложения — это полностью замкнутую, с точки зрения его поведения. Он может взаимодействовать с другими хранилищами служб и данных во время выполнения операции, но ядро его поведение работает в собственном процессе и всего приложения обычно развертывается как единое целое. Если такого приложения должен горизонтальное масштабирование, обычно на нескольких серверах или виртуальных машин дублируется всего приложения.

## <a name="all-in-one-applications"></a>В одном приложений

Наименьшее возможное число проектов для архитектуры приложения является одним. В этой архитектуре вся логика приложения является содержится в одном проекте, компилируются в одну сборку и развернут как единое целое.

Новый проект ASP.NET Core, создается в Visual Studio или из командной строки ли начинается как простой монолита «все в одном». Он содержит все возможности приложения, включая доступ логики презентации, business и данных. Рис. 5-1 показана структура файла приложения один проект.

**Рис. 5-1.** Один проект приложения ASP.NET Core

![](./media/image5-1.png)

В одном проекте сценарии разделение достигается за счет использования папки. Шаблон по умолчанию включает в себя отдельные папки для обязанности шаблон MVC моделей, представлений и контроллеров, а также дополнительные папки для данных и служб. В этом случае представления сведений следует ограничиваться максимально папку Views и сведения о реализации данных access должна выполняться только для классов, которые хранятся в папке данных. Бизнес-логики должен находиться в службы и классы в папке «Models».

Хотя простой, один проект решения монолитные имеет свои недостатки. При увеличении размера и сложности проекта количество файлов и папок будет продолжать расти также. Проблемы пользовательского интерфейса (модели, представления и контроллеры) находятся в нескольких папках, которые не сгруппированы вместе в алфавитном порядке. Эта проблема только усугубляется, когда дополнительные конструкции уровня пользовательского интерфейса, таких как фильтры или ModelBinders, добавляются в разные папки. Бизнес-логика является разбросаны между папками моделей и службы, и никак не очистить которого классы, в каких папках должны зависеть от какие другие. Отсутствие организации на уровне проекта, часто приводят к [тестированию кода](http://deviq.com/spaghetti-code/).

Для решения этих проблем, часто развития приложений в решений для нескольких проектов, где каждый проект считается должна находиться в определенном *слой* приложения.

## <a name="what-are-layers"></a>Что такое слоев

По мере роста сложности приложения для управления этой сложности можно разбить приложения в соответствии с его обязанности или проблемы. Это следует разделение принцип проблемы и обеспечения растущих codebase организации, чтобы разработчики можно легко находить, где реализуется определенные функции. Многоуровневой архитектуры обеспечивает ряд преимуществ за пределами организации код так же, хотя.

Организуя кода в слои, общие низкоуровневые функции может быть использован в приложении. Повторное использование будет полезно, так как это означает, что необходимо записать меньший объем кода и она позволяет приложению стандартизировать одной реализации, следуя ТОНЕРА принцип.

С помощью многоуровневой архитектуры приложения могут принудительно применять ограничения, на которых слои могут взаимодействовать с другими слоями. Это помогает добиться инкапсуляции. При изменении или заменить слоя, должен влиять только те слои, которые работают с ним. Ограничивая которой слои, зависят от на которых другие слои, влияние изменений могут быть уменьшены одно изменение влияет всего приложения.

Слои (и инкапсуляции) стала намного проще замена функциональных возможностей в приложении. Например приложение изначально может использовать собственную базу данных SQL Server для постоянного хранения, но позже можно использовать стратегию сохраняемости на основе облака, или один за веб-API. Если приложение правильно инкапсулированы его реализация сохраняемости в логический слой, конкретного слоя, SQL Server может быть заменен новый реализации один и тот же открытый интерфейс.

Помимо возможности замены реализаций в ответ на будущие изменения в требования к уровней приложения можно также упростить его выгрузить реализации для целей тестирования. Вместо того, чтобы создать тесты, которые работают с реальными данными уровень или уровень пользовательского интерфейса приложения, эти слои можно заменить во время тестирования фиктивное реализациями, которые предоставляют известных ответы на запросы. Обычно в результате тесты намного проще и быстрее для выполнения по сравнению с выполняется повторная проверка реальные инфраструктуры приложений.

Логических слоев-это стандартная техника улучшения организации кода в корпоративных приложениях программного обеспечения, и существует несколько способов, в которых код могут быть организованы в слои.

> [!NOTE]
> *Слои* представляют логическое разделение в приложении. В случае, если логику приложения физически распределенным для разделения серверов или процессов, эти целевые объекты отдельное развертывание физических называются *уровни*. Это возможно и довольно часто уровня N приложение развертывается для одного уровня.

## <a name="traditional-n-layer-architecture-applications"></a>Традиционные приложения архитектуры «N-слоя»

Наиболее распространенные организацию логику приложения в уровнях его показано на рисунке 5-2.

**Рис. 5-2.** Типичное приложение слои.

![](./media/image5-2.png)

Часто эти уровни обозначаются как пользовательский Интерфейс, уровень бизнес-ЛОГИКИ (уровень бизнес-логики) и DAL (уровень доступа к данным). С помощью этой архитектуры, пользователям выполнять запросы через уровень пользовательского интерфейса, который взаимодействует только с помощью МЕТОДА. Уровень бизнес-ЛОГИКИ, в свою очередь, может вызывать DAL для запросов доступа к данным. Уровень пользовательского интерфейса не следует вносить любые запросы DAL непосредственно, и не должно взаимодействовать с сохраняемости другими способами. Аналогичным образом уровень бизнес-ЛОГИКИ необходимо взаимодействовать только с сохраняемости через DAL. Таким образом каждый уровень имеет свои собственные хорошо известных ответственности.

Недостаток этого подхода традиционных слоев означает, что зависимости времени компиляции работать сверху вниз. То есть уровень пользовательского интерфейса зависит от МЕТОДА, который зависит от DAL. Это означает, что уровень бизнес-ЛОГИКИ, который обычно содержит наиболее важные логики в приложении, зависимые на сведения о реализации данных access (и часто на существование базы данных). Тестирование бизнес-логики в такой архитектуры сложно часто, требующие тестовую базу данных. Принципом инверсии зависимостей можно использовать для решения этой проблемы, как будет показано в следующем разделе.

Рис. 5-3 показан пример решения, остановом три проекта приложения ответственности (или уровень).

**Рис.** Простое приложение монолитные с трех проектов.

![](./media/image5-3.png)

Несмотря на то, что в данном приложении используется несколько проектов в организационных целях, он по-прежнему развертывается как единое целое, и его клиенты будут взаимодействовать с ней как одного веб-приложения. Это обеспечивает очень простой процесс развертывания. Рис. 5-4 показано, как могут быть такие приложения размещенного с помощью Windows Azure.

![](./media/image5-4.png)

**Рис.** Простое развертывание веб-приложения Azure

По мере роста приложения может потребоваться более сложным и надежным решений для развертывания. Рис. 5-5 показан пример более сложные плана развертывания, которая поддерживает дополнительные возможности.

![](./media/image5-5.png)

**Рис.** Развертывание веб-приложения на службу приложений Azure

На внутреннем уровне организации этого проекта на несколько проектов, в зависимости от ответственности повышает удобство поддержки приложения.

Это устройство может масштабироваться вверх или вниз, чтобы воспользоваться преимуществами облачного масштабируемость по запросу. Масштабирование вверх означает добавление дополнительных ЦП, памяти, места на диске или других ресурсов для серверов размещения приложения. Горизонтальное масштабирование означает добавление дополнительных экземпляров такие серверы ли это физических серверах или виртуальных машин. При размещении приложения на нескольких экземплярах подсистемы балансировки нагрузки используется для назначения запросы для отдельных экземпляров.

Самый простой способ масштабирования веб-приложения в Azure — настроить масштабирование вручную в план служб приложений приложения. Рис. 5-6 отображение экрана соответствующую панель мониторинга Azure для настройки того, сколько экземпляров обслуживающих приложение.

![](./media/image5-6.png)

**Рис. 5-6.** План службы приложений, масштабирование в Azure.

## <a name="clean-architecture"></a>Очистить архитектуры

Приложения, с которыми принципом инверсии зависимостей, а также принципы проектирования сей (DDD), как правило, чтобы образовать схожую архитектуру. Эта архитектура прошел много имен за несколько лет. Одно из имен первого был шестиугольник архитектуры, следуют порты адаптеров. Раньше, его является был указан как [архитектура режим](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/) или [чистой архитектура](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). Это это Фамилия чистой архитектуры, который используется в качестве основы для описания архитектура эта электронная книга.

> [!NOTE]
> Термин чистой архитектура могут быть применены для приложений, построенных с использованием принципов DDD также для тех, которые не были собраны с помощью ддд. В случае первое из них, эта комбинация может называться «Чистая DDD архитектура».

Очистить архитектура помещает бизнес-логики и приложение модели в центральной части приложения. Вместо того, бизнес-логики, которые зависят от доступа к данным или других проблем инфраструктуры, инвертировано эту зависимость: сведения инфраструктуры и реализация зависит от основных приложений. Это достигается путем определения абстрактные классы или интерфейсы, в основном приложения, который впоследствии реализуется типов, определенных на уровне инфраструктуры. Распространенным способом визуализации этой архитектуры является использование ряда концентрических окружностей аналогично режим. На рисунке 5 X показан пример этого стиля представления архитектуры.

![](./media/image5-7.png)

**Рис.** Очистка архитектура; режим представления

На этой диаграмме зависимостей потока к внутренней окружности. Таким образом вы увидите, что основные приложения (который будет использовано имя его положение в основе этой схеме) не имеет зависимостей от других уровней приложения. В центре очень являются сущностями приложения и интерфейсов. За пределами, но по-прежнему в основном приложении являются доменных служб, которые обычно реализуют интерфейсы, определенные в внутренней окружности. За пределами ядро приложения пользовательского интерфейса и слои инфраструктуры зависят от на основные приложения, но не на друг с другом (обязательно).

5 X рисунке более традиционным схема горизонтальной слоев, которая лучше отражает зависимости между пользовательского интерфейса и на других уровнях.

![](./media/image5-8.png)

**Рис.** Очистка архитектура; Горизонтальная уровень представления

Обратите внимание, что сплошной стрелки обозначают зависимости времени компиляции, пока штриховая стрелка представляет зависимость только для среды выполнения. С помощью чистой архитектуры, уровень пользовательского интерфейса работает с интерфейсы, определенные в основном приложения во время компиляции, и в идеале следует знания типы реализации определен на уровне инфраструктуры. Во время выполнения Однако эти типы реализации будет необходимые приложению для выполнения, им необходимо будет присутствовать и проводных до приложения базовых интерфейсов через внедрения зависимостей.

Рис. 5-9 показан более подробное представление архитектуры приложения ASP.NET Core при построении, следуя приведенным ниже рекомендациям.

![Базовая архитектура ASPNET](./media/image5-9.png)

**Рис. 5-9.** Диаграмма архитектуры ASP.NET Core после чистой архитектуры.

Поскольку ядро приложения не зависит от инфраструктуры, легко создавать автоматических модульных тестов для этого слоя. Фигуры 5 – 10 и 5 11 показано, как тесты помещаются в этой архитектуре.

![UnitTestCore](./media/image5-10.png)

**Рис. 5-10.** Тестирование приложения ядра в изоляции.

![IntegrationTests](./media/image5-11.png)

**Рис. 5-11.** Интеграция тестирования реализации инфраструктуры с внешними зависимостями.

Поскольку уровень пользовательского интерфейса не имеет прямой зависимости в типах, определенных в проекте инфраструктуры, аналогичным образом можно очень легко поменять местами реализаций, либо для тестирования или в ответ на изменения требований приложения. Использование встроенных ASP.NET Core и поддержка внедрения зависимостей становится эта архитектура наиболее подходящий способ структуры нетривиальной монолитные приложения.

Для приложений, объединенный проекты основных приложений, инфраструктуры и пользовательский интерфейс запускаются как одно приложение. Архитектура приложения среды выполнения может выглядеть как на рисунке 5-12.

![Базовая архитектура ASPNET 2](./media/image5-12.png)

**Рис. 5-12.** Архитектура среды выполнения примера приложения ASP.NET Core.

### <a name="organizing-code-in-clean-architecture"></a>Организация кода в чистую архитектуры

В решении чистой архитектура каждый проект имеет очистить обязанности. Таким образом будет принадлежать определенных типов в каждом проекте, и вы найдете часто папки соответствующие для таких типов в соответствующий проект.

Основные приложения содержит бизнес-модели, которое содержит сущности, служб и интерфейсов. Среди этих интерфейсов: абстракции для операций, которые будут выполняться с помощью инфраструктуры, такие как доступ к данным, доступ к файловой системе, сетевых вызовов, и т. д. Иногда служб или интерфейсы, определенные на этом уровне нужно для работы с несущностные типы, которые не имеют зависимостей на пользовательский Интерфейс или инфраструктуры. Они могут определяться как простые объекты передачи данных (DTO).

> ### <a name="application-core-types"></a>Типы основных приложений
> -   Сущности (business классов модели, которые сохраняются)
> -   Интерфейсы
> -   Службы
> -   Спроектируйте

Как правило, проект инфраструктуры включает данные удаленного доступа. В типичных веб-приложений ASP.NET Core Сюда входят класс DbContext Entity Framework, любой миграции Core EF, были определены и классов для реализации доступа к данным. Является наиболее распространенным способом абстрагировать код реализации для доступа к данным, использования [шаблон репозитория](http://deviq.com/repository-pattern/).

Помимо данных удаленного доступа инфраструктура проект должен содержать реализации службы, которые должны взаимодействовать с вопросами инфраструктуры. Эти службы должны реализовывать интерфейсы, определенные в основном приложения и поэтому инфраструктура должна иметь ссылку на проект основных приложений.

> ### <a name="infrastructure-types"></a>Типы инфраструктуры
> -   Базовые типы EF (DbContext, миграция)
> -   Реализация типов доступа к данным (репозиториев)
> -   Зависящие от инфраструктуры службы (FileLogger, SmtpNotifier, и т. д.)

Уровень пользовательского интерфейса в приложении ASP.NET Core MVC будет точкой входа для приложения и будут проекта ASP.NET Core MVC. Этот проект должен ссылаться на проект основных компонентов приложения и его типы должны взаимодействовать с инфраструктурой исключительно через интерфейсы, определенные в основных приложений. Нет прямого создания экземпляра (или статические вызовы) типы инфраструктуры слой должен быть разрешен в уровень пользовательского интерфейса.

> ### <a name="ui-layer-types"></a>Типы пользовательского интерфейса слоя
> -   Контроллеры
> -   Фильтры
> -   Представления
> -   ViewModels
> -   Запуск

Класс Startup отвечает для настройки приложения и типы реализации подключение к интерфейсам, позволяя внедрения зависимостей для правильной работы во время выполнения.

> [!NOTE]
> Чтобы подключить внедрение зависимостей в ConfigureServices в файле Startup.cs файле проекта пользовательского интерфейса, проект может потребоваться ссылки на проект инфраструктуры. Эту зависимость можно устранить, проще всего с помощью настраиваемого DI контейнера. Для целей этого образца самым простым подходом является предоставление проекта пользовательского интерфейса для ссылки на проект инфраструктуры.

## <a name="monolithic-applications-and-containers"></a>Монолитные приложения и контейнеров 

Можно построить одно- и монолитные развертывания на основе веб-приложения или службы и развернуть его как контейнер. В приложении может оказаться монолитные но организованных в несколько библиотек, компонентов или уровней. Внешне это одного контейнера как единый процесс, одного веб-приложения или одной службы.

Для управления этой модели, развернуть один контейнер для представления приложения. Чтобы масштабировать, просто добавьте дополнительные копии с балансировкой нагрузки на переднем плане. Простота поступает из управления одно развертывание в одном контейнере или виртуальной Машины.

![](./media/image5-13.png)

Как показано на рисунке 5 X могут включать несколько компонентов и библиотек или внутренней уровней в каждом контейнере. Но, следуя участника контейнера *» выполняет один контейнер и делает это в одном процессе*», монолитные шаблон может возникнуть конфликт.

Недостаток этого подхода поставляется при роста приложения, требующие масштабирование. Если масштабировать приложение в целом, это не действительно проблемы. Однако в большинстве случаев несколько частей приложения являются стягиванием точки, требующие масштабирование, пока другие компоненты находятся в используется реже.

Используя пример типичных электронной коммерции; что вы скорее всего, потребуется выполнить масштабирование — это компонент сведения продукта. Многие Дополнительные клиенты просматривать продукты, чем их приобретение. Дополнительные клиенты использовать свою корзину не использовать конвейер оплаты. Меньшее количество клиентов, добавить комментарии или Просмотр истории покупок. И вы скорее всего лишь небольшое число сотрудников в одной области, необходимые для управления содержимым и маркетинговых кампаний. По масштабирование монолитные конструкции, весь код разворачивается несколько раз.

Помимо шкалы проблем, все изменения к одному компоненту требуется полное повторное тестирование всего приложения и завершить повторное развертывание всех экземпляров.

Объединенный подход часто, и во многих организациях разрабатываемом с помощью этого архитектурный подход. Многие возникают блага достаточное количество результатов, пока другие, достигнуты ограничения. Многие предназначены свои приложения в этой модели, так как средства и инфраструктура были слишком трудно реализовать ориентированные на службы архитектуры (SOA), и он не увидит необходимость -, пока его размер увеличивается. Если обнаружится, что встретились ограничения монолитные подхода, разделить приложения, чтобы он мог лучше использовать контейнеры и микрослужбами может быть следующим логическим шагом.

![](./media/image5-14.png)

Развертывание монолитные приложений в Microsoft Azure может осуществляться с помощью выделенных виртуальных машин для каждого экземпляра. С помощью [набора масштабирования виртуальных Машин Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), можно легко масштабировать виртуальных машин. [Службы приложений Azure](https://azure.microsoft.com/services/app-service/) можно запускать монолитные приложения и легко масштабировать экземпляры без необходимости управления виртуальными машинами. Службы приложений Azure можно запустить отдельные экземпляры контейнеры Docker, а также упрощения развертывания. С помощью Docker, можно развернуть узел Docker одной виртуальной Машины и запустить несколько экземпляров. С помощью балансировки Azure, как показано в на рисунке 5-14, вы можете управлять масштабирования.

Развертывание на различных узлах осуществляется с помощью традиционные методы. Узлах Docker можно управлять с помощью команды **запуска docker** выполнить вручную или с помощью автоматизации, такие как конвейеров непрерывной поставки (CD).

### <a name="monolithic-application-deployed-as-a-container"></a>Монолитные приложения, развернуть как контейнер

Имеется ряд преимуществ использования контейнеров для управления развертываниями монолитные приложения. Масштабирование экземпляров контейнеров гораздо быстрее и проще, чем развертывание дополнительных виртуальных машин. Даже при использовании набора масштабирования виртуальных Машин для масштабирования виртуальных машин, они принимают время к экземпляру. При развертывании в качестве экземпляров приложения, конфигурацию приложения осуществляется в рамках виртуальной машины.

Развертывание обновлений, как образы Docker гораздо быстрее и эффективно сети. Образы docker, как правило, начинается в секундах, что позволяет ускорить процесс развертывания. То закрытие экземпляра Docker можно так же легко, как выдача **docker stop** команду, обычно Завершение менее чем за секунду.

Как контейнеры являются по своей природе неизменяемыми намеренно, вам никогда не потребуется беспокоиться о поврежденных виртуальных машин, а может забыть сценарии обновления с учетом некоторых определенной конфигурации или влево файла на диске.

Монолитные приложения могут использовать преимущества Docker, разделить монолитные приложения в sub системы, которые можно масштабировать, разработки и развертывания по отдельности может выполняться в точку входа в область микрослужбами.

> ### <a name="references--common-web-architectures"></a>Ссылки — общих архитектур Web
> - **Очистить архитектуры**  
> <https://8thlight.com/blog/uncle-Bob/2012/08/13/the-Clean-Architecture.HTML>
> - **Архитектура режим**  
> <http://jeffreypalermo.com/blog/the-Onion-Architecture-Part-1/>
> - **Шаблон репозитория**  
> <http://deviq.com/Repository-pattern/>
> - **Образец чистой архитектура решения**  
> <https://github.com/ardalis/cleanarchitecture>
> - **Проектирование архитектуры электронная книга Микрослужбами** <http://aka.ms/MicroservicesEbook>

>[!div class="step-by-step"]
[Предыдущие] (архитектуры principles.md) [Далее] (общий клиент стороны web-technologies.md)
