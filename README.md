<p align="center">
  <img src="public/gitforum-logo.png" alt="GitForum Logo" width="120" />
</p>

<h1 align="center">🚀 GitForum</h1>

<p align="center">
  <b>A modern developer community platform with code sharing, discussions, and AI assistance</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=nextdotjs" />
  <img src="https://img.shields.io/badge/Django-5.0-092E20?style=for-the-badge&logo=django" />
  <img src="https://img.shields.io/badge/PostgreSQL-15-336791?style=for-the-badge&logo=postgresql" />
  <img src="https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript" />
  <img src="https://img.shields.io/badge/TailwindCSS-4.0-06B6D4?style=for-the-badge&logo=tailwindcss" />
</p>

---

## 📸 Screenshots

<!-- Replace with actual screenshots -->

| Landing Page | Feed |
|:---:|:---:|
| ![Landing Page](docs/screenshots/landing.png) | ![Feed](docs/screenshots/feed.png) |

| Post Detail | Profile |
|:---:|:---:|
| ![Post Detail](docs/screenshots/post-detail.png) | ![Profile](docs/screenshots/profile.png) |

---

## 🇬🇧 English

### ✨ Features

#### 👥 User System
- **JWT Authentication** — Secure token-based login & registration
- **OAuth Integration** — Sign in with Google, GitHub, GitLab, and Discord
- **User Profiles** — Customizable profiles with avatars, bio, and activity stats
- **Password Recovery** — Email-based password reset flow

#### 📝 Content & Community
- **Code Posts** — Share code snippets with syntax highlighting (powered by Shiki)
- **Rich Comments** — Threaded comment system with nested replies
- **Likes & Bookmarks** — Save and organize favorite posts
- **Tags & Categories** — Browse posts by programming language and topic
- **Trending & Explore** — Discover popular posts and new content
- **User Feed** — Personalized content feed

#### 🤖 AI Assistant
- **Built-in AI Chat** — Powered by Groq (Llama 3.1) for instant coding help
- **Multilingual** — Supports Russian and Kazakh languages

#### 🎨 UI/UX
- **Dark/Light Theme** — Seamless theme switching with next-themes
- **Responsive Design** — Mobile-first, works on all devices
- **Bilingual Interface** — Full Russian & Kazakh localization
- **Code Highlighting** — Beautiful syntax highlighting with customizable themes
- **Modern Components** — Built with Radix UI primitives

#### ⚙️ Settings & Customization
- **Account Settings** — Update email, password, and linked OAuth accounts
- **Appearance Settings** — Theme, font size, and code display preferences
- **Notification Preferences** — Fine-grained notification controls
- **Profile Editing** — Edit display name, bio, links, and avatar

---

### 🛠️ Tech Stack

#### Frontend
| Technology | Purpose |
|---|---|
| **Next.js 16** | React framework with App Router, SSR/SSG |
| **React 19** | UI library with latest features |
| **TypeScript 5** | Type-safe development |
| **Tailwind CSS 4** | Utility-first styling |
| **Radix UI** | Accessible, unstyled component primitives |
| **Shiki** | Code syntax highlighting |
| **Lucide React** | Beautiful icon library |
| **Recharts** | Data visualization & charts |
| **React Hook Form + Zod** | Form handling & validation |
| **next-themes** | Dark/light mode management |

#### Backend
| Technology | Purpose |
|---|---|
| **Django 5.0** | Python web framework |
| **Django REST Framework** | RESTful API |
| **SimpleJWT** | JWT token authentication |
| **django-allauth** | OAuth social authentication |
| **PostgreSQL** | Primary database |
| **Pillow** | Image processing |
| **django-filter** | API filtering |
| **django-cors-headers** | Cross-origin resource sharing |

---

### 📦 Installation Guide

#### Prerequisites
- **Node.js** ≥ 18.x
- **Python** ≥ 3.10
- **PostgreSQL** ≥ 14
- **Git**

#### 1. Clone the Repository

```bash
git clone https://github.com/Ataniyaz228/Git-forum.git
cd Git-forum
```

#### 2. Frontend Setup

```bash
# Install dependencies
npm install

# Create environment file
cp .env.example .env.local

# Edit .env.local and add your API keys
# NEXT_PUBLIC_GROQ_API_KEY=your_groq_api_key
```

#### 3. Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Create environment file
cp env.template .env
```

#### 4. Configure Environment Variables

Edit `backend/.env`:

```env
# Django
DEBUG=True
SECRET_KEY=your-secret-key-here

# Database (PostgreSQL)
DATABASE_NAME=gitforum
DATABASE_USER=postgres
DATABASE_PASSWORD=your_password
DATABASE_HOST=localhost
DATABASE_PORT=5432

# Frontend URL
FRONTEND_URL=http://localhost:3000

# OAuth (optional)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret

# Email (for password recovery)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_HOST_USER=your_email@gmail.com
EMAIL_HOST_PASSWORD=your_app_password
```

#### 5. Database Setup

```bash
# Create PostgreSQL database
psql -U postgres -c "CREATE DATABASE gitforum;"

# Run migrations
cd backend
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser
```

#### 6. Run the Application

```bash
# Terminal 1 — Backend (from /backend)
python manage.py runserver

# Terminal 2 — Frontend (from root)
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser 🎉

---

### 📁 Project Structure

```
Git-forum/
├── app/                    # Next.js App Router pages
│   ├── auth/               # Auth callback page
│   ├── bookmarks/          # Bookmarks page
│   ├── explore/            # Explore & discover
│   ├── feed/               # User feed
│   ├── login/              # Login page
│   ├── register/           # Registration page
│   ├── post/               # Post detail page
│   ├── profile/            # User profile
│   ├── settings/           # Settings page
│   ├── tags/               # Tags browsing
│   ├── trending/           # Trending posts
│   └── page.tsx            # Landing page
├── backend/                # Django backend
│   ├── gitforum/           # Django project settings
│   ├── posts/              # Posts app (models, views, API)
│   ├── users/              # Users app (auth, OAuth, profiles)
│   └── manage.py
├── components/             # React components
│   ├── ui/                 # Radix UI primitives
│   ├── navbar.tsx          # Navigation bar
│   ├── ai-assistant-widget.tsx  # AI chat widget
│   ├── comments.tsx        # Comment system
│   └── ...
├── contexts/               # React contexts
│   ├── AuthContext.tsx      # Authentication state
│   ├── LanguageContext.tsx  # i18n (RU/KZ)
│   └── CodeSettingsContext.tsx  # Code display settings
├── hooks/                  # Custom React hooks
├── lib/                    # Utilities & API client
└── public/                 # Static assets
```

---

## 🇷🇺 Русский

### ✨ Возможности

#### 👥 Система пользователей
- **JWT Аутентификация** — безопасная авторизация на основе токенов
- **OAuth** — вход через Google, GitHub, GitLab и Discord
- **Профили** — настраиваемые профили с аватарами, био и статистикой
- **Восстановление пароля** — сброс пароля через email

#### 📝 Контент и сообщество
- **Посты с кодом** — публикация сниппетов с подсветкой синтаксиса (Shiki)
- **Комментарии** — древовидная система комментариев с вложенными ответами
- **Лайки и закладки** — сохранение и организация избранных постов
- **Теги и категории** — фильтрация по языкам программирования и темам
- **Тренды и исследование** — подборка популярных постов
- **Персональная лента** — индивидуальная лента контента

#### 🤖 AI Ассистент
- **Встроенный AI чат** — на базе Groq (Llama 3.1) для помощи с кодом
- **Мультиязычный** — поддержка русского и казахского языков

#### 🎨 Интерфейс
- **Тёмная/светлая тема** — плавное переключение тем
- **Адаптивный дизайн** — Mobile-first, работает на всех устройствах
- **Двуязычный интерфейс** — полная локализация на русский и казахский языки
- **Подсветка кода** — красивая подсветка синтаксиса с настраиваемыми темами
- **Современные компоненты** — на основе Radix UI

#### ⚙️ Настройки
- **Аккаунт** — обновление email, пароля и привязанных OAuth аккаунтов
- **Внешний вид** — тема, размер шрифта, настройки отображения кода
- **Уведомления** — гибкое управление уведомлениями
- **Профиль** — редактирование имени, био, ссылок и аватара

---

### 🛠️ Технологический стек

#### Фронтенд
| Технология | Назначение |
|---|---|
| **Next.js 16** | React-фреймворк с App Router, SSR/SSG |
| **React 19** | UI библиотека |
| **TypeScript 5** | Типобезопасная разработка |
| **Tailwind CSS 4** | Утилитарный CSS |
| **Radix UI** | Доступные UI-компоненты |
| **Shiki** | Подсветка синтаксиса кода |
| **Lucide React** | Библиотека иконок |
| **Recharts** | Визуализация данных |
| **React Hook Form + Zod** | Формы и валидация |

#### Бэкенд
| Технология | Назначение |
|---|---|
| **Django 5.0** | Python веб-фреймворк |
| **Django REST Framework** | RESTful API |
| **SimpleJWT** | JWT аутентификация |
| **django-allauth** | OAuth социальная авторизация |
| **PostgreSQL** | Основная база данных |
| **Pillow** | Обработка изображений |

---

### 📦 Руководство по установке

#### Требования
- **Node.js** ≥ 18.x
- **Python** ≥ 3.10
- **PostgreSQL** ≥ 14
- **Git**

#### 1. Клонирование репозитория

```bash
git clone https://github.com/Ataniyaz228/Git-forum.git
cd Git-forum
```

#### 2. Настройка фронтенда

```bash
# Установка зависимостей
npm install

# Создание файла окружения
cp .env.example .env.local

# Отредактируйте .env.local и добавьте API ключи
```

#### 3. Настройка бэкенда

```bash
cd backend

# Создание виртуального окружения
python -m venv venv

# Активация (Windows)
venv\Scripts\activate

# Установка зависимостей
pip install -r requirements.txt

# Создание файла окружения
cp env.template .env
# Отредактируйте .env — укажите данные БД и OAuth ключи
```

#### 4. Настройка базы данных

```bash
# Создание базы данных PostgreSQL
psql -U postgres -c "CREATE DATABASE gitforum;"

# Применение миграций
python manage.py migrate

# Создание суперпользователя (опционально)
python manage.py createsuperuser
```

#### 5. Запуск

```bash
# Терминал 1 — Бэкенд (из папки /backend)
python manage.py runserver

# Терминал 2 — Фронтенд (из корня проекта)
npm run dev
```

Откройте [http://localhost:3000](http://localhost:3000) в браузере 🎉

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/Ataniyaz228">Ataniyaz</a>
</p>