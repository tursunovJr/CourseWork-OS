# CourseWork-OS
Курсовая работа по курсу "Операционные системы"
### Задание: 
+ Необходимо реализовать загружаемый модуль ядра для отслеживания изменений в USB-портах и проверки на наличие доступа к секретным файлам. В случае отстутствия допуска - зашифровать все запрещенные для копирования файлы.
### Запуск
+ make - собрать проект.
+ sudo insmod md.ko - загрузить модуль.
+ sudo dmesg -wH | grep "USB MODULE" - показать действвия связанные с этим модулем.
+ sudo rmmod md.ko - выгрузить модуль.
### Содержимое файлов
+ В файле config.h - надо прописать id производителя и id устройства, которому будет доступно содержимое секретных файлов.
+ В файле crypto_config.h  - прописывается путь ко всем секретным файлам, которые надо скрыть. 
### Принцип работы
+ При подключении к компьютеру USB-устройства, начнется идентификация устройства. В случае если, оно находится в списке доверенных устройств, доступ к секретным файлам откроется, в противном случае - нет.
