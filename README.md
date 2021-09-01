# Памятка для первокурсников

## Что готово

- Страница в соответсвии с шаблоном
- Адаптивность

## Запустить
```sh
git clone
npm install
npm run serve
```

## Собрать
```sh
git clone
npm install
npm run build
```
Полученный сайт будет находится в каталоге dist в корне проекта. Для того что бы изменить путь к файлам при публикации нужно поменять переменную **publicPath** в файле конфигурации в корне проекта **vue.config.js**
Подробнее по настройкам файла конфигурации [документация vue-cli][vueclidoc]

[vueclidoc]: <https://cli.vuejs.org/guide/deployment.html#github-pages>