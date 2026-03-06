# HTML → Android App (Capacitor Guide)

Пошаговая инструкция как собрать **Android приложение из обычного HTML / CSS / JS проекта**  
без React, Angular, Vue и других фреймворков.

Используется **Capacitor**.

---

# Что нужно

Перед началом установите:

- Node.js
- npm
- Android Studio
- Java JDK

Проверить:

```bash
node -v
npm -v
```

---

# 1. Создать папку проекта

```bash
mkdir myapp
cd myapp
```

---

# 2. Инициализировать npm

```bash
npm init -y
```

---

# 3. Установить Capacitor

```bash
npm install @capacitor/core @capacitor/cli
```

---

# 4. Инициализировать Capacitor

```bash
npx cap init
```

Введите:

```
App name: MyApp
App id: com.example.myapp
```

---

# 5. Создать папку сайта

```bash
mkdir www
```

---

# 6. Создать index.html

Создайте файл:

```
www/index.html
```

Пример:

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Hello</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>

<body>

<h1>Hello World</h1>

<script>
console.log("App started")
</script>

</body>
</html>
```

---

# 7. Проверить capacitor.config.json

Файл должен выглядеть так:

```json
{
  "appId": "com.example.myapp",
  "appName": "MyApp",
  "webDir": "www",
  "bundledWebRuntime": false
}
```

---

# 8. Добавить Android

```bash
npm install @capacitor/android
npx cap add android
```

---

# 9. Скопировать сайт в Android

```bash
npx cap copy
```

---

# 10. Открыть Android Studio

```bash
npx cap open android
```

---

# 11. Запустить приложение

В Android Studio нажмите

```
Run ▶
```

---

# 12. Собрать APK

В Android Studio:

```
Build → Build APK(s)
```

APK появится в:

```
android/app/build/outputs/apk/debug/app-debug.apk
```

---

# Структура проекта

```
myapp
 ├── android
 ├── node_modules
 ├── www
 │   └── index.html
 ├── capacitor.config.json
 └── package.json
```

---

# Обновление приложения

После изменений в HTML/JS/CSS:

```bash
npx cap copy
```

---

# Полезные команды

```
npx cap copy
npx cap sync
npx cap open android
```

---

# Итог

Теперь любой **HTML/JS/CSS проект можно собрать как Android приложение**.
