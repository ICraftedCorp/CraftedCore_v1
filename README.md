# CraftedCore_v1

# Русский язык
CraftedCore_v1 - это проект для бэкпорта новой версии Minecraft: Pocket Edition, которая изменяется на более старые версии Pocketmine для лучшей стабильности и производительности, сохраняя при этом как можно больше функций из новых версий. Этот релиз совместим с производством Minecraft PE 0.12.X - 0.13.X Alpha и основан на Pocketmine-Soft-235 / Steadfast2.

Вещи, которые вы, возможно, захотите изменить перед построением:
  - Сохранение server.log отключен, так как запись на диск занимает много времени.
  - MOTD по умолчанию для ответа на запросы списка серверов MCPE устанавливается в RaklibInterface
  - Изменение IP, чтобы направить игроков, когда сервер полон в player.php - это помогает не отворачиваться от игроков, когда вы не можете с ними справиться, а вместо этого направлять их на другой сервер.

Известная ошибка:
   - Отбрасывание не работает должным образом 
   - Производительность не так хороша, как 1.4, некоторое профилирование должно быть сделано в будущем
   - Игроки могут иногда имеет глюк, проваливание сквозь земли
   - Броня иногда не может быть сохранена у игрока

Что вы хотите изменить в своих плагинах:
   - Игроки не выпадают из мира естественным образом, вы хотите обрабатывать PlayerMoveEvent по мере необходимости, чтобы убить их
   - AsyncTasks нужно использовать $This->postURL и $This->getURL, чтобы передать информацию серверам, вместо Utill class (проблема загрузчика)

Для сборки запустите сервер с установленным DevTools, затем запустите /makeserver. Он дропнит файл .phar в его каталог плагинов.

# English language
CraftedCore_v1 is a project for backporting new Minecraft: Pocket Edition changes to older Pocketmine versions for better stability and performance, while retaining as many features from the new versions as possible. This release is compatible with production Minecraft PE 0.12.X - 0.13.X Alpha and based off Pocketmine-Soft-235 / Steadfast2.

Things you might want to change before building:
  - Saving the server.log is disabled because it takes a lot of time to write to disk
  - The default MOTD for responding to MCPE server list queries is set in RaklibInterface
  - Change the IP to direct players to when the server is full in Player.php - this helps by not turning away players when you can't handle them but instead directing them to another server.

Known bugs:
   - Knockback doesn't work properly
   - Performance isn't as good as 1.4, some profiling needs to be done
   - Players can sometimes glitch into the ground
   - Armor can sometimes not be saved on the player

Things you'll want to change on your plugins:
   - Players don't fall out of the world naturally, you'll want to handle PlayerMoveEvent as needed to kill them
   - AsyncTasks need to reference $this->postURL and $this->getURL to communicate with ourside servers instead of the Utils class (loader problem)

To build, run the server with DevTools installed then run /makeserver. It'll drop a phar file in it's plugin directory.
