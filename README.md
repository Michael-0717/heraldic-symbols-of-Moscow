# Геральдические символы Москвы
## Задание:
Сгенерируйте PDF документ из списка флагов и гербов районов Москвы:
https://video.ittensive.com/python-advanced/data-102743-2019-11-13.utf.csv
На каждой странице документа выведите название геральдического символа (Name), его описание (Description) и его изображение (Picture).
Для показа изображений используйте адрес
https://op.mos.ru/MEDIA/showFile?id=XXX
где XXX - это значение поля Picture в наборе данных. Например:
https://op.mos.ru/MEDIA/showFile?id=8466da35-6801-41a9-a71e-04b60408accb
В случае возникновения проблем с загрузкой изображений с op.mos.ru можно добавить в код настройку для форсирования использования дополнительных видов шифрования в протоколе SSL/TLS.
requests.packages.urllib3.util.ssl_.DEFAULT_CIPHERS = 'ALL:@SECLEVEL=1'
___
## Решение:
1) Подключаем необходимые библтотеки, загружаем данные (через делитель ";").
2) Формируем html – документ для отчета:
- Заголовок - Геральдические символы Москвы, 
- кодировка - кодировка.
3) Переберем в цикле наш набор данных построчно.
4) Стиль не задаем для 1-го заголовка, стиль для других задаем - разрыв страниц.
герб, ширина, отступ справа-слева; 
5) Источник геральдики + значение поля 'Picture' из кортежа данных.
6) Увеличим шрифт +150% и выведем свойство 'Description' нашего кортежа.
7) Сконфигурируем pdf-документ, указав путь до бинарного файла.
8) Зададим стандартные настройки: размер А4, опступ по умолчанию.
9) Сгенерируем из строки html-файл сохраним его в 'heraldic.pdf'
