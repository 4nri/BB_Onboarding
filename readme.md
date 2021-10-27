# Как экспортировать JSON из After Effects с интегрированными файлами SVG вместо PNG

1. В настройках экспорта плагина Bodymovin необходимо активировать опцию "Include in JSON". Таким образом все изображения сконвертируются в формат base64
2. Чтобы заменить растровые изображения в файле data.json на векторные, svg файлы нужно прогнать через [энкодер](https://yoksel.github.io/url-encoder/).
3. В файле data.json находим строку "data:image/png;base64," и заменяем на "data:image/svg+xml;charset=utf-8," после вставляем полученный из энкодера текст и добавляем к нему ",

#####Пример

```
"data:image/svg+xml;charset=utf-8,%3Csvg xmlns... ",
```
