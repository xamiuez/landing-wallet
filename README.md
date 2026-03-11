# 💳 Landing Page - Wallet SaaS

Учебный лендинг для SaaS-продукта (цифровой кошелёк). Третий проект - заметный скачок в качестве

---

## 🚀 Функционал

- Hero-секция с заголовком, описанием и CTA-кнопкой
- Секция превью с логотипами партнёров и мокапом приложения
- Секция с тремя feature-карточками и блоком отзыва пользователя
- Секция поддержки с CTA и анимированным GIF
- Футер с навигацией, копирайтом и формой подписки на email-рассылку
- Адаптивная вёрстка на 4 брейкпоинта (1279px / 991px / 767px / 575px)
- Fluid typography через `clamp()`
- Hover-эффекты на кнопках с `translateY`
- `@mixin text-format` и `@mixin flex-center` для переиспользования стилей

---

## 🛠 Стек технологий

- HTML5
- CSS3 / SCSS
- Методология: BEM
- Flexbox
- `clamp()` для fluid typography
- Git & GitHub

---

## 📸 Скриншоты

> ![](assets/readme/hero-section.png)

---

## 📂 Структура проекта

```
landing-wallet/
├── src/
│   ├── css/
│   │   ├── style.css
│   │   └── style.css.map
│   ├── fonts/
│   │   ├── Poppins-Regular.ttf
│   │   └── Poppins-SemiBold.ttf
│   ├── icons/
│   │   ├── favicon/           ← полный набор favicon-файлов
│   │   ├── Cards icon.svg
│   │   ├── Coin icon.svg
│   │   ├── Logos.svg
│   │   ├── Purse icon.svg
│   │   ├── Star.svg
│   │   ├── User Feedback Image.svg
│   │   └── Wallet logo.svg
│   ├── img/
│   │   ├── app.svg
│   │   ├── cat.jpg
│   │   ├── diagram.svg
│   │   └── wallet.gif
│   ├── scss/
│   │   ├── style.scss         ← корневой файл
│   │   ├── _variables.scss    ← цвета + @font-face
│   │   ├── _mixins.scss       ← flex-center, text-format
│   │   ├── _reset.scss
│   │   └── _relative.scss     ← все медиа-запросы
│   └── index.html
└── README.md
```

---

## ⚙️ Запуск проекта

```bash
git clone https://github.com/username/landing-wallet.git
cd landing-wallet
```

Сборщика нет - открыть `src/index.html` в браузере

---

## 📌 Планы по улучшению

**BEM**

- Вынести навигацию хедера в отдельный блок `.nav-menu` вместо `main-section__nav-menu / __list / __item / __link`
- `footer__nav-menu` - заменить `<p>` на `<a>` / `<li>` для ссылок Privacy policy, Terms of use
- `.send-button` - вне BEM, переделать в `.footer__send-button` или `.button.button--send`

**SCSS**

- Переименовать `_relative.scss` → `_media.scss`
- Переименовать `$color-lightgray` → `$color-dark` (сейчас это `#333`)
- Вынести `@font-face` из `_variables.scss` в отдельный `_fonts.scss`
- Привести медиа-запросы к единому стилю: везде либо БЭМ-цепочки, либо SCSS-нестинг
- Удалить комментарий `// для текста???` из `.button`

**Шрифты**

- Конвертировать `.ttf` → `.woff2`
- Добавить `font-display: swap` в `@font-face`

**HTML / семантика**

- `<footer>` вынести из `<section class="section-support">` на верхний уровень
- `<h3>` в `.section-support__title` → заменить на `<h2>`
- 5 одинаковых `<img src="Star.svg">` → заменить на CSS или SVG-спрайт
- Добавить `width` / `height` всем `<img>` (CLS fix)
- Переименовать иконки в `kebab-case`: `cards-icon.svg`, `wallet-logo.svg`
- Удалить `cat.jpg` - нигде не используется

**Адаптивность**

- `Hero` на 575px: `left-wrapper` + `right-wrapper` не переключаются в колонку
- `.section-preview__bottom` - убрать фиксированные `width`/`height` на каждом брейкпоинте, заменить на `max-width: 100%` + `aspect-ratio`
- `.section-feedback__feedback-block` - фиксированный `padding: 80px 162px` ломается на мобиле