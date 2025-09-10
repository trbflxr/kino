# Настройка Blender интеграции

> [!WARNING]  
> Этот гайд написан на примере CustomObjects (ресурс паков). Однако процесс аналогичен и для другого контента.

Импорт `.blend` файлов - это самый быстрый и простой способ добавления моделей в редактор.

Сохраните проект Blender в желаемую папку. Папка должна находится в `Assets` в проекте `Content SDK`.

```
📂 Assets
 └ 📁 Content
    └ 📁 CustomObjects
       └ 📁 Example
          └ 📁 Textures
          └ 📄 __objects_meta
          └ 📄 your_model_name.blend   <- на пример сюда
 └ 📁 SharedTextures
```

> [!WARNING]  
> Обратите внимание, что текстуры, которые вы используете в `Blender` для должны находится в папке `Assets` проекта, иначе Unity **не увидит** их.

Если после сохранения `.blend` файла вы видите в консоли **Unity** такую или подобную ошибку:

![blender_not_found_error.png](../Images/Blender/blender_not_found_error.png)

Исправить это очень просто. Откройте папку с `.blend` файлом, далее перейдите в его свойства: `RMB -> Properties`

![blend_file_properties.png](../Images/Blender/blend_file_properties.png)

После чего в поле `Open with` нажмите `Change`, а затем укажите путь к `blender-launcher.exe`, который лежит в **корневой директории** Blender. Затем нажмите **Apply** в окне свойств файла.

Затем откройте Unity, выберите `.blend` файл в списке, нажмите на `...` в инспекторе и выберите `Reset`.
![blend_reset_unity.png](../Images/Blender/blend_reset_unity.png)