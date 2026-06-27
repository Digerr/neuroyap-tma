# NeuroYap — хайповая AI-озвучка 🎙️

Telegram Mini App для генерации голосовых сообщений голосами стримеров, мемов и селебрити для пранков и общения в чатах.

**🤖 Бот:** [@NeuroYapbot](https://t.me/NeuroYapbot)
**🌐 Live demo:** https://digerr.github.io/neuroyap-tma/

## 🎯 Концепт
Пользователь выбирает голос из каталога (124 голоса в 8 категориях) → пишет текст → AI генерирует голосовое сообщение → отправляет в чат Telegram / скачивает / шарит.

## ✨ Фичи
- **124 голоса** в 8 категориях: Стримеры, Мемы, Аниме, Гейминг, Кино, Музыка, AI, VIP
- **PRO-голоса** (.locked) — 12 VIP + 2 кино + 0 AI — открываются через подписку
- **Telegram WebApp SDK**: MainButton, BackButton, HapticFeedback, theme params
- **TTS Engine Stub** с интерфейсом под ElevenLabs / Silero / MiniMax (mock сейчас)
- **Уникальный waveform** для каждого голоса (детерминированный паттерн)
- **Интерактивный плеер**: scrubbing по waveform, скорость (0.5×–2.0×), луп, громкость
- **Избранное** голосов
- **Поиск и фильтры** по категориям
- **Статистика** пользователя (генераций / избранное / минуты аудио)
- **PRO-подписка** через Telegram Stars (XTR) — UI готов, покупка отключена
- **Yap-коины** — внутренняя валюта

## 🎨 Дизайн
- Тёмная неоновая эстетика (lime → cyan → violet)
- Glassmorphism, плавающие blob-градиенты
- Mobile-first 430px, Telegram WebApp-совместимый layout
- Шрифты: Manrope (body) + Unbounded (display)
- Theme params подстраиваются под тему пользователя (light/dark)

## 🛠 Стек
- Single-file HTML/CSS/JS (без зависимостей, мгновенный деплой)
- Vanilla JS, ~700 строк
- Telegram WebApp SDK подключён
- Голоса инлайнены (124 шт, 24KB) — не требуют внешних запросов

## 📁 Структура
```
index.html              # весь фронтенд (83KB, single-file)
README.md               # этот файл
scripts/
  gen_voices.py         # генератор каталога 124 голосов
  inline_voices.py      # инлайнинг голосов в index.html
  voices_data.js        # сгенерированные данные (для dev)
```

## 🚀 Деплой
Деплой автоматический через GitHub Pages при пуше в `main`:
```bash
git add . && git commit -m "feat: ..." && git push
```
Через ~30 сек обновление живёт на https://digerr.github.io/neuroyap-tma/

## 📋 Roadmap
- [x] Telegram WebApp SDK (MainButton, BackButton, HapticFeedback, theme)
- [x] TTS engine stub с интерфейсом под 3 провайдера
- [x] Каталог 124 голоса в 8 категориях
- [x] PRO UI готов (через Telegram Stars, покупка отключена)
- [ ] Реальный TTS backend (ElevenLabs / Silero / MiniMax)
- [ ] Активация PRO через Telegram Stars (XTR) — нужны права бота
- [ ] Бэкенд для истории (sync между устройствами)
- [ ] Реферальная программа
- [ ] Sound preview через WebAudio API
