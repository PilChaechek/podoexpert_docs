# Микроразметка Schema.org

Микроразметка помогает поисковику понять содержимое страницы и показывать расширенные сниппеты в выдаче. Реализуется через **JSON-LD** — блок `<script>` в `<head>` страницы.

Проверить разметку: [Schema Markup Validator](https://validator.schema.org/)

---

## BreadcrumbList — Хлебные крошки

Показывает путь навигации в поисковой выдаче под заголовком страницы.

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Главная",
      "item": "https://example.ru/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Курсы",
      "item": "https://example.ru/courses/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Название страницы"
    }
  ]
}
```

---

## Organization — Организация

Базовая информация о школе: название, сайт, логотип, контакты.

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Школа Эксперт",
  "url": "https://example.ru",
  "logo": "https://example.ru/logo.png",
  "telephone": "+7 (XXX) XXX-XX-XX",
  "email": "info@example.ru",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Санкт-Петербург",
    "addressCountry": "RU"
  },
  "sameAs": [
    "https://vk.com/example",
    "https://t.me/example"
  ]
}
```

---

## Course — Курс

Разметка для каждого курса. Помогает поисковику показывать курсы в расширенных результатах.

```json
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Коррекция вросшего ногтя методом Arkadas Cube",
  "description": "Профессиональное обучение методу Arkadas Cube. Практика на реальных пациентах.",
  "provider": {
    "@type": "Organization",
    "name": "Школа Эксперт",
    "url": "https://example.ru"
  },
  "offers": {
    "@type": "Offer",
    "price": "105000",
    "priceCurrency": "RUB"
  },
  "hasCourseInstance": {
    "@type": "CourseInstance",
    "courseMode": ["onsite", "online"],
    "inLanguage": "ru"
  }
}
```

---

## Article — Статья блога

Разметка для страницы отдельной статьи. Помогает поисковику отображать дату публикации и автора в сниппете.

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Заголовок статьи",
  "description": "Краткое описание статьи",
  "image": "https://example.ru/blog/image.jpg",
  "datePublished": "2026-01-01",
  "dateModified": "2026-01-01",
  "author": {
    "@type": "Organization",
    "name": "Школа Эксперт",
    "url": "https://example.ru"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Школа Эксперт",
    "logo": {
      "@type": "ImageObject",
      "url": "https://example.ru/logo.png"
    }
  }
}
```

---

> **Важно:** все значения (`name`, `url`, `telephone`, `price` и др.) подставляются под конкретный сайт. Шаблоны выше — базовая структура.
