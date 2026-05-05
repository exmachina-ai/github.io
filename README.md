# EXMACHINA-AI Landing Page

**Современная landing page для EXMACHINA-AI** — инженерного проекта по автоматизации производственной логистики CKD и SKD.

🔗 **Сайт:** https://exmachina-ai.ru

---

## 📋 Структура проекта

```
├── index.html                    # Главная страница
├── docs.html                     # Документация (HU Drawing Generator)
├── bot.html                      # EXMACHINA Knowledge Bot
├── dictionary.html               # Интерактивный словарь терминов
├── materials.html                # Инженерные публикации
│
├── style.css                     # Главная таблица стилей
├── favicon.ico                   # Favicon
│
├── assets/                       # Ресурсы (инструменты, PDF)
│   └── Draw_HU.rar              # HU Drawing Generator инструмент
│
├── exmachina_logo.png           # Логотип проекта
├── logo_xai_engineering.png     # Логотип инженерной экосистемы
│
├── robots.txt                    # Инструкции для поисковиков
├── sitemap.xml                   # Карта сайта
├── ads.txt                       # Реклама контакт
├── CNAME                         # Custom domain для GitHub Pages
│
├── README.md                     # Этот файл
└── .gitignore                    # Git конфигурация
```

---

## 🎨 Особенности дизайна

### Темная тема с минималистичным подходом
- **Цветовая схема:** Тёмный фон (#09090b) с акцентным оранжевым (#e06820)
- **Типография:** Inter font семейство с переменными размерами
- **CSS переменные:** Полная система дизайн-токенов (цвета, тени, радиусы)

### Анимации и интерактивность
- **Вращающиеся шестерёнки (gears)** — декоративный элемент, синхронизированный с прокруткой страницы
- **Карточки с fade-in эффектом** — появляются по мере прокрутки (IntersectionObserver)
- **Плавные переходы** — все элементы имеют graceful transitions

### Responsiveness
- Полная поддержка мобильных устройств
- Media queries для breakpoints: 760px и 480px
- Адаптивная типография с `clamp()`

---

## 🔍 SEO & Meta информация

✅ **Оптимизировано для поисковиков:**
- Canonical URLs на каждой странице
- Open Graph meta tags (OG)
- Twitter Card meta tags
- JSON-LD структурированные данные (Organization, SoftwareApplication, CollectionPage)
- Файл `robots.txt` и `sitemap.xml`
- Google Search Console & Yandex Search Console верификация

---

## 🚀 Развёртывание

Этот репозиторий хостится на **GitHub Pages** с custom domain **exmachina-ai.ru**.

### Для локального тестирования:
```bash
# Клонировать репозиторий
git clone https://github.com/exmachina-ai/github.io.git
cd github.io

# Запустить локальный сервер (Python 3)
python3 -m http.server 8000

# Открыть в браузере
# http://localhost:8000
```

### Для деплоя:
```bash
# Просто сделайте push на main ветку
git add .
git commit -m "Update: описание изменений"
git push origin main

# GitHub Pages автоматически обновит сайт в течение 30-60 секунд
```

---

## 📖 Содержание страниц

### 🏠 `index.html` — Главная страница
- Hero секция с логотипом и манифестом проекта
- 6 карточек с ключевыми возможностями (RAG, SQL Access Control, Knowledge Flow и т.д.)
- Интерактивная контактная форма
- Анимированные вращающиеся шестерёнки справа

### 📚 `docs.html` — Документация
- HU Drawing Generator — инженерный инструмент на базе Excel + VBA + КОМПАС-3D
- Описание инженерной проблемы и решения
- Ссылка на скачивание инструмента (Draw_HU.rar)
- Ссылка на презентацию (HU_Drawing_Generator.pdf)

### 🤖 `bot.html` — Knowledge Bot
- Описание EXMACHINA Knowledge Bot
- RAG-based архитектура без галлюцинаций
- Контролируемый контекст
- Прямая ссылка на Telegram-бота: @exmachina_info_bot

### 📖 `dictionary.html` — Интерактивный словарь
- **Полностью отдельное SPA приложение** с встроенным JavaScript
- Поиск по терминам, определениям, формулам
- Фильтры по группам терминов
- Модальное окно для детальной информации
- Поддержка поиска на русском и английском языках
- Вкладки: Словарь, Методология, Конфликтные термины, Практические правила

### 📰 `materials.html` — Публикации
- Каталог инженерных статей и исследований
- Фильтры по типу материала (Методология, Исследование, Заметка)
- Карточки с метаданными (теги, статус версии)
- Ссылки на полные материалы в отдельных HTML-страницах

---

## ⚙️ Технический стек

- **HTML5** — семантическая разметка
- **CSS3** — CSS переменные, Grid, Flexbox, Media Queries
- **Vanilla JavaScript** — без фреймворков
- **GitHub Pages** — бесплатный хостинг

**Размер:** ~3.6 MB (включая ассеты и изображения)  
**Production-ready:** ✅ Да

---

## 🎯 Документация для разработчиков

### CSS система

Вся стилизация организована через CSS переменные в `:root`:

```css
:root {
  /* Цвета */
  --bg: #09090b;                    /* Основной фон */
  --text: #f0f0f2;                  /* Основной текст */
  --acc: #e06820;                   /* Акцентный цвет */
  
  /* Размеры */
  --max: 1040px;                    /* Max-width контентера */
  --r: 12px;                        /* Border-radius */
  
  /* Тени */
  --shadow-soft: 0 8px 24px rgba(0, 0, 0, 0.22);
  --shadow-card: 0 14px 34px rgba(0, 0, 0, 0.28);
}
```

### JavaScript события

**Главная страница (index.html):**
- Scroll events для вращения шестерёнок
- IntersectionObserver для анимации карточек
- requestAnimationFrame для плавности анимаций

**Словарь (dictionary.html):**
- Полнофункциональное SPA приложение с state management
- Поиск с рангированием результатов
- Фильтрация по группам
- Modal dialogs для детальной информации

---

## 🔐 Безопасность

- ✅ HTML escaping всех пользовательских данных
- ✅ ARIA labels для доступности
- ✅ Правильное использование `aria-hidden` для декоративных элементов
- ✅ Meta tags для CSP и security headers
- ✅ Нет inline JavaScript в HTML (где это возможно)

---

## 📧 Контакты

- **Email:** admin@exmachina-ai.ru
- **Telegram бот:** https://t.me/exmachina_info_bot
- **GitHub:** https://github.com/exmachina-ai
- **Сайт:** https://exmachina-ai.ru

---

## 📝 Лицензия

© 2026 EXMACHINA-AI™. Все права защищены.

**Девиз проекта:** *Никакого шума. Никаких иллюзий.*

---

## 🚦 Статус проекта

| Статус | Описание |
|--------|---------|
| ✅ Landing Page | Полностью функциональна |
| ✅ SEO Оптимизация | Настроена (robots.txt, sitemap.xml, meta tags) |
| ✅ Mobile Ready | Responsive дизайн работает |
| ✅ Интерактивный контент | Словарь, animations, модали |
| ⏳ GitHub Actions CI/CD | Можно настроить для автопроверок |
| ⏳ Performance optimization | Можно минифицировать CSS, добавить lazy loading |

---

## 🤝 Как помочь проекту

1. **Найти ошибку?** Создайте Issue
2. **Улучшить дизайн?** Отправьте Pull Request
3. **Дополнить контент?** Добавьте новые материалы
4. **Распространить?** Поделитесь ссылкой на сайт

---

**Последнее обновление:** 5 мая 2026  
**Версия:** 2.0 (с .gitignore и README)
