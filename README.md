# os-1-msinstall
## Отчет по заданию 1 (Создание скрипта для автоматизации установки под Windows)
Был написан скрипт (install_script.bat), выполняющий установку ПО согласно условию задачи.
### ЧАСТЬ 1
1.1 7-zip
```
7z1900-x64.msi /passive /norestart /le "D:\Study\OS\7zip-log.txt" INSTALLDIR="C:\Program Files\7-Zip"
```
| Параметр       | Цель                |
| ------------- |:------------------|
| /passive | автоматический режим - только указатель хода выполнения |
| /norestart | без перезагрузки |
| /le "D:\Study\OS\7zip-log.txt" | вести журнал установки с отображением все сообщений об ошибках в файл 7zip-log.txt |
| INSTALLDIR="C:\Program Files\7-Zip" | каталог для установки указать явно "C:\Program Files\7-Zip" |

1.2 Paint.net
```
paintnet_4.2.10.exe /auto DESKTOPSHORTCUT=1 TARGETDIR="C:\Program Files\Graphics\Paint"
```
| Параметр       | Цель                |
| ------------- |:------------------|
| /auto | полностью автоматическая установка (в том числе и согласие с лицензией) |
| DESKTOPSHORTCUT=1 | на рабочий стол вывести ярлык для запуска приложения |
| TARGETDIR="C:\Program Files\Graphics\Paint" | каталог для установки — "C:\Program Files\Graphics\Paint" |

1.3 Inkscape
```
inkscape-0.92.4-x64.msi /qr /norestart /lw "D:\Study\OS\inkscape-log.txt" INSTALLDIR="C:\Program Files\Graphics\Inkscape"
```
| Параметр       | Цель                |
| ------------- |:------------------|
| /qr | установка с сокращенным интерфейсом |
| /norestart | без перезапуска |
| /lw "D:\Study\OS\inkscape-log.txt" | вести журнал установки с отображением всех сообщений об устранимых ошибках в файл inkscape-log.txt |
| INSTALLDIR="C:\Program Files\Graphics\Inkscape" | каталог для установки указать явно "C:\Program Files\Graphics\Inkscape" |

1.4 LibreOffice
```
LibreOffice_6.4.2_Win_x64.msi /passive /norestart /le "D:\Study\OS\libreoffice-install-log.txt"
LibreOffice_6.4.2_Win_x64_helppack_ru.msi /passive /forcerestart
```
| Параметр       | Цель                |
| ------------- |:------------------|
| /passive | установка с сокращенным интерфейсом |
| /norestart | без перезагрузки после установки LibreOffice |
| /le "D:\Study\OS\libreoffice-install-log.txt" | вести журнал установки с отображением все сообщений об ошибках в файл libreoffice-install-log.txt |
| /forcerestart | перезагрузка после установки языкового расширения |

1.5 Notepad++
```
npp.7.5.6.Installer.x64.exe /S
```
| Параметр       | Цель                |
| ------------- |:------------------|
| /S | полностью автоматическая установка |

### ЧАСТЬ 2
2.1 Конфиг. файл jre8_cfg
```
INSTALL_SILENT=1
INSTALLDIR=C:\Java\JRE
WEB_ANALYTICS=0
WEB_JAVA=1
```
| Параметр       | Цель                |
| ------------- |:------------------|
| INSTALL_SILENT=1 | автономный режим установки (без задания вопросов пользователю) |
| INSTALLDIR=C:\Java\JRE | каталог для установки java: "C:\Java\JRE" |
| WEB_ANALYTICS=0 | отключить отправку веб-аналитики на сервера Oracle |
| WEB_JAVA=1 | разрешить запуск веб-приложений Java в браузере |

2.2 Установка jre8
```
jre-8u221-windows-x64.exe INSTALLCFG="D:\Study\OS\jre8_cfg.txt" /L*V "D:\Study\OS\jre-log.txt"
```
| Параметр       | Цель                |
| ------------- |:------------------|
| INSTALLCFG="D:\Study\OS\jre8_cfg.txt" | установка с использованием конфигурационного файла |
| /L*V "D:\Study\OS\jre-log.txt" | создание лог-файла с результатами установки (имя лог-файла в текущей директории: jre-log.txt) |
