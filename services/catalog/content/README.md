# content — данные каталога

Эта папка не хранится в git: здесь шаблоны, медиа, шрифты и превью (~370 МБ).
Структура:

```
templates.json          каталог шаблонов
templates/<id>.json     шаблон
media/                  картинки, видео, музыка
fonts/, fonts.css       шрифты
previews/<id>.webp|jpg  превью для каталога и соцсетей
prices.json             (необязательно) своя цена для отдельных шаблонов: { "296": 5000 }
```

Заполнить (из папки `services/catalog`):

```
node tools/update.js     скачать шаблоны и медиа
node tools/clean.js      убрать чужую рекламу и контакты
node tools/previews.js   снять превью (нужен запущенный сайт и: cd tools && npm install)
```

Или взять готовый архив `shaqyru-content-<дата>.zip` (лежит у владельца сайта в Google Drive).
Ссылку на архив не публикуйте в открытом репозитории. На сервере, из корня проекта:

```
pip install gdown
gdown --fuzzy "<ссылка на архив в Google Drive>" -O content.zip
unzip -o content.zip -d services/catalog/ && rm content.zip
```

Собрать такой архив заново (Windows, из папки `services/catalog`): `tar.exe -a -c -f ..\..\..\shaqyru-content.zip content`.
