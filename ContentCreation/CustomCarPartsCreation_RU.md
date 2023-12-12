# Создание паков кастомных деталей

## Установка Unity

Если у вас уже установлен Unity, то убедитесь, что версия редактора именно `2020.3.25f1`. В противном случае установите необходимую версию по гайду ниже.

Установите редактор Unity используя [этот гайд](https://github.com/trbflxr/kino/blob/master/ContentCreation/UnityInstallation/UnityInstallation.md).

## Установка SDK

Если у вас уже установлен `kino_content_sdk`, то этот шаг можно пропустить.

1. Скачайте и распакуйте в удобное для вас место [kino_content_sdk](https://github.com/trbflxr/kino_content_sdk/releases).

2. Добавьте `kino_content_sdk` в UnityHub.

![unity_hub_sdk_add](Images/unity_hub_sdk_add.png)

![unity_hub_sdk_open](Images/unity_hub_sdk_open.png)

3. Запустите проект и дождитесь загрузки

![unity_hub_open_project](Images/unity_hub_open_project.png)

## Создание контента

Можно приступать к созданию кастомных деталей.

> [Диски](https://github.com/trbflxr/kino/blob/master/ContentCreation/CustomCarParts/CustomWheels_RU.md)

> [Обвесы](https://github.com/trbflxr/kino/blob/master/ContentCreation/CustomCarParts/CustomExterior_RU.md)

> [Интерьер](https://github.com/trbflxr/kino/blob/master/ContentCreation/CustomCarParts/CustomInterior_RU.md)

## Сборка паков

После того, как вы закончили создание пака и заполнили его метаданные, можно приступать к сборке пака.

Сборка паков происходит через утилиту **PacksTool**. Для того что бы открыть её, перейдите `Kino -> Packs build tool`

![packs_build_tool_open](Images/packs_build_tool_open.png)

## Настройка инструментов сборки

При первом запуске у вас может отсутствовать некоторые данные и SDK предложит их сгененировать.

> [!NOTE]
> Если вы уже настроили инструменты, то этот шаг можно пропустить.

Окно инструментов сборки на данный момент выглядит так.

![packs_build_tool_window](Images/packs_build_tool_window.png)

В верхней его части можно посмотреть информацию об авторе пака (вас). Если поля пустые, то нажмите на кнопку **Edit** что бы открыть редактор.

Заполните информацию об авторе пака.

Если вы не знаете как получить SteamID или DiscordID, то воспользуйтесь кнопками ниже, что бы открыть гайд.

![packs_author_meta](Images/packs_author_meta.png)

## Запуск сборки

Отметьте чекбоксы для паков которые хотите собрать и нажмите **Build for ...** в нижней части окна сборщика.

![packs_select_and_build](Images/packs_select_and_build.png)

По окончанию сборки готовые паки будут лежать в папке **Build**, перейти в которую можно нажав на кнопку **Open Build folder**, или выбрав пункт меню `Kino -> Open Build folder`.