# Татьяна Кузьмина · сайт

Одностраничный сайт психолога. Сборка не нужна: чистый HTML, CSS и JS.
Анимации подключены с CDN: GSAP + ScrollTrigger, плавный скролл Lenis. Если CDN не загрузится, сайт работает без анимаций.
Шрифт Onest лежит в проекте (`assets/fonts`), от Google Fonts сайт не зависит.

## Структура

```
index.html              главная
404.html                страница «не найдено»
assets/img/tanya.webp   фото (вырезано, прозрачный фон)
assets/fonts/           шрифт Onest (кириллица + латиница)
favicon.svg, apple-touch-icon.png
og-image.jpg            превью для соцсетей и мессенджеров (1200×630)
robots.txt
vercel.json             кэш для /assets и заголовки безопасности
```

## Посмотреть локально

```bash
npx serve .
# или
python3 -m http.server 8000
```

Открывать через сервер, а не двойным кликом: иначе не подгрузятся шрифты.

## Залить на GitHub

```bash
git init
git add .
git commit -m "Сайт Татьяны Кузьминой"
git branch -M main
git remote add origin https://github.com/<логин>/tatyana-kuzmina.git
git push -u origin main
```

Репозиторий заранее создайте на github.com → New repository, без README.

## Задеплоить на Vercel

1. vercel.com → Add New → Project → Import репозитория.
2. Framework Preset: **Other**. Build Command и Output Directory оставить пустыми.
3. Deploy. Каждый следующий `git push` в `main` деплоится сам.

## Когда будет домен

1. Vercel → Project → Settings → Domains → добавить домен.
2. У регистратора прописать DNS, которые покажет Vercel (обычно `A @ 76.76.21.21` и `CNAME www cname.vercel-dns.com`).
3. В `index.html` поменять `og:image` на полный адрес: `https://домен/og-image.jpg`
   (без полного адреса некоторые мессенджеры не покажут превью) и добавить
   `<link rel="canonical" href="https://домен/">`.
4. В `robots.txt` добавить строку `Sitemap: https://домен/sitemap.xml`, если нужен sitemap.

## Что проверить у Татьяны

- Ссылка ВКонтакте: на старой странице встречались и `vk.me/tanyakuzmins`, и `vk.me/tatyanakuzmins`. Сейчас стоит второй.
- Запись: кнопка открывает окно, текст заявки копируется и открывается Telegram или ВК. Сервер для заявок не нужен.
- Аналитика: счётчик Яндекс Метрики вставить перед `</head>` в `index.html`.
