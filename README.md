# Interactive map — by W.Willow

Статичный сайт. Публикуется на GitHub Pages без сборки.

## Как выложить

1. Создайте репозиторий на github.com (например `interactive-map`), Public.
2. Загрузите **содержимое этой папки** в корень репозитория (Add file → Upload files, папку `assets` тоже).
3. Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, папка `/ (root)` → Save.
4. Через 1–2 минуты сайт будет по адресу `https://<ваш-логин>.github.io/<имя-репозитория>/`.

## Состав

- `index.html` — сам сайт (стартовый экран, карта, слайд, лайтбокс)
- `support.js` — рантайм рендеринга (нужен рядом с index.html)
- `assets/` — видео, карта, слайд, материалы, текстура стола, логотип, шрифты
- `.nojekyll` — отключает обработку Jekyll на GitHub Pages

Требуется интернет: React подгружается с unpkg.com.

## Как добавить новую локацию на карту

В `index.html` найдите блок с `openSlide` — это кружок у Одихи:

```html
<div onClick="{{ openSlide }}" style="position: absolute; left: 53.2%; top: 49.6%; width: 5.4%; ...">
```

`left`/`top` — координаты в процентах от изображения карты. Скопируйте блок, поменяйте
проценты и повесьте свой обработчик по образцу `openSlide` в скрипте внизу файла.

## Материалы слайда

Кликабельные зоны слайда заданы в процентах от изображения `assets/slide-ch1.webp`
(`zoomOdiha`, `zoomTicket`, `zoomP1…P3`), крупные версии лежат в `assets/`.
