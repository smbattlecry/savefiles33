# Архив — Android Studio проект

Полностью локальное приложение. Никакого интернета, никакого сервера.
Все данные и фото хранятся в IndexedDB на телефоне.

---

## Что нужно установить (бесплатно)

1. **Android Studio** → https://developer.android.com/studio
   Размер ~1 ГБ. При первом запуске скачает Android SDK (~2 ГБ).

---

## Как собрать APK

### Шаг 1 — Открыть проект
- Запусти Android Studio
- **File → Open** → выбери папку `archiv-app`
- Подожди пока Gradle синхронизируется (первый раз ~5 мин)

### Шаг 2 — Собрать APK
- В меню: **Build → Build Bundle(s) / APK(s) → Build APK(s)**
- Подождать ~1 мин
- Появится уведомление: **"Build successful"** → нажми **"locate"**
- APK лежит в: `app/build/outputs/apk/debug/app-debug.apk`

### Шаг 3 — Установить на телефон
- Перекинь APK на телефон (Telegram, кабель, Google Drive)
- Открой файл на телефоне
- **Настройки → Разрешить установку из этого источника → Установить**

---

## Как работает

- Всё хранится в **IndexedDB** внутри WebView Android
- Фото сжимаются до JPEG 1000px перед сохранением
- Данные не удаляются при выходе из приложения
- Полностью офлайн — интернет не нужен

---

## Структура проекта

```
archiv-app/
├── app/
│   ├── build.gradle
│   └── src/main/
│       ├── assets/
│       │   └── index.html       ← всё приложение здесь
│       ├── java/com/archiv/
│       │   └── MainActivity.java
│       ├── res/
│       │   ├── layout/activity_main.xml
│       │   ├── values/styles.xml
│       │   └── mipmap-*/ic_launcher.png
│       └── AndroidManifest.xml
├── build.gradle
└── settings.gradle
```
