# Образ сцены

1. Берем предыдущий [образ.](hotel.md)
2. Создаем еще одного пользователя - имя **Admin** пароль **"your_password"** с правами администратора. 
3. Отключение браузеров **Chrome/Internet Explorer/Edge** - открываем местоположение **Chrome** "C:\Program Files\Google" в свойствах папки выбираем **Security/Edit** выбираем **Users** и нажимаем **Remove**. Такие же действия проделать с **Edge** "C:\Windows\SystemApps" папка **Microsoft.MicrosoftEdge_8wekyb3d8bbwe.** Для того чтобы отключить **Internet Explorer** - нужно зайти в **"Programs and Features"** в панеле управления и во вкладке **"Turn Windows features on or off"** снять галочку с **Internet Explorer 11.**
4. Отключаем USB порты, нажимаем **Win+R**, пишем **gpedit.msc** и заходим **Local Computer Policy > Computer Configuration > Administrative Templates > System > Removable Storage Access** и включаем правило запрета **Deny all access** 
5. Запрет на **powershell.exe**, нужно зайти в **"Programs and Features"** в панеле управления и во вкладке **"Turn Windows features on or off"** снять галочку с **Windows PowerShell 2.0**. Для запрета **cmd.exe** пишем **gpedit.msc**, заходим в **User Configuration > Administrative Templates > System** и выбираем **Запрет использвания командной строки**, ставим галочку **Включено** и в параметрах выбираем **Да**, после в **Win+R** пишем команду **gpupdate /force** для обновления политики
6. Удаляем для визуала с **Мой компьютера** папки **Download, Picture, Video** и другие:
Нажимаем **Win+R**, пишем **gpedit.msc**, заходим **HKEY­_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Explorer > FolderDescriptions**, и ищем нужные нам папки:
```sh

Desktop: {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
Documents: {f42ee2d3-909f-4907-8871-4c22fc0bf756}
Downloads: {7d83ee9b-2244-4e70-b1f5-5393042af1e4}
Music: {a0c69a99-21c8-4671-8703-7934162fcf1d}
Pictures: {0ddd015d-b06c-45d5-8c4c-f59713854639}
Videos: {35286a68-3c57-41a1-bbb1-0eae73d76c95}
```
Открываем папку **PropertyBag**, и меняем значение **ThisPCPolicy** с **Show** на **Hide** 

7. Возвращаемся в папку IT которая на диске С, создаем папку Software. В неё качаем программы для [SteelSeries Engine](https://steelseries.com/gg/engine)  / Razer Synapse [2](https://www.razer.com/synapse-2) + [3](https://www.razer.com/synapse-3) / [Corsair](https://www.corsair.com/s/icue) / [Logitech](https://www.logitechg.com/en-eu/innovation/g-hub.html) / [HyperX](https://row.hyperx.com/ru/pages/ngenuity). Так же и [FocusRite](https://downloads.focusrite.com/focusrite/scarlett-3rd-gen/scarlett-2i2-3rd-gen) который сразу устанавливаем.
8. Переходим в **Admin**, меняем аккаунт для игрока делая его без прав администратора, после переходим в него, проверяем чтобы нельзя было воспользоваться не одним из вышеперечисленных браузеров. Проверка **Steam** + запуск игры (После проверки выходим из **Steam** сменой пользователя, чтобы поле логина было пустое). Проверка **TeamSpeak 3** и **ASIO (Focusrite).** 
9. Ну вот и всё, сохраняем в **Acronis True Image**, название то же что и для отеля но без подписи **"Hotel"**.


## Индивидуально на каждом ПК
1. Установить пароль на **BIOS**
2. Включаем профиль **XPM-I**, нажмите **F7**, перейдите во вкладку **Ai Tweaker** и выберете **Ai Overclock Tuner**
2. Включите безопасную загрузку, установите для загрузки только **UEFI**, удалите все загрузочные устройства, кроме диска ОС (в частности, убедитесь, что загрузка через USB невозможна) и включите **VT-d (Virtualization)**, если оборудование поддерживает его.


## Обьязательные пункты на Major Stage
1. При создание образа аккаунт **Steam** должен быть с доступом к **PerfectWorld**
2. Добавить карты с Мастерской 
3. Добавить переменную **USRLOCALCSGO** для папки **C:\configs**
4. Насройка **disk auditing** на просмотр всех изменений на диске, нажимаем **Win+R** пишем **secpol.msc**, заходим **Security Settings > Local Policies > Audit Policy** выбираем **Audit object access**, ставим две галочки на **Success** и **Failure**. Далее на диске нажимаем правой клавишей **Properties > Security > Advanced > Auditing**, нажимаем **Add**, выбираем **Principal** и добавляем обьект **Everyone**, после добавления выберите все разрешения и сохраняем все. `Для просмотра логов, заходим Win+R > compmgmt.msc > Event Viewer > Windows Logs > Security `
