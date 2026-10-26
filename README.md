# ИС «Мнение» — лендинг

Статический сайт для GitHub Pages: https://mnenie.headmade.pro/

## Состав

| Файл | Назначение |
|---|---|
| `index.html` | Страница целиком: разметка и стили в одном файле |
| `404.html` | Страница «не найдено» |
| `favicon.svg` | Иконка сайта |
| `CNAME` | Свой домен `mnenie.headmade.pro` для GitHub Pages |
| `.nojekyll` | Отключает обработку Jekyll: файлы отдаются как есть |

## Публикация

1. Создайте на GitHub репозиторий, например `headmade/mnenie`. Он может быть публичным, а на платных тарифах и приватным.
2. Загрузите в корень репозитория все файлы из этой папки, включая скрытый `.nojekyll`:
   ```bash
   git init
   git add .
   git commit -m "Лендинг ИС «Мнение»"
   git branch -M main
   git remote add origin git@github.com:<организация>/mnenie.git
   git push -u origin main
   ```
3. Откройте в репозитории **Settings → Pages**:
   - **Source**: *Deploy from a branch*
   - **Branch**: `main`, папка `/ (root)` → **Save**
   - **Custom domain** заполнится значением `mnenie.headmade.pro` из файла `CNAME`.
4. В DNS-зоне домена `headmade.pro` добавьте запись:

   | Имя | Тип | Значение |
   |---|---|---|
   | `mnenie` | CNAME | `<организация>.github.io.` |

   `<организация>` — это владелец репозитория на GitHub: ваш логин или название организации.
5. Когда DNS обновится (от нескольких минут до пары часов) и GitHub выпустит сертификат, включите в **Settings → Pages** флажок **Enforce HTTPS**.

## Рекомендуется: подтвердить домен

Подтверждение защищает поддомен от захвата чужими репозиториями. На GitHub откройте **Settings организации или профиля → Pages → Add a domain**, введите `headmade.pro` и добавьте в DNS предложенную TXT-запись `_github-pages-challenge-...`.

## Обновление

Измените `index.html` и сделайте `git push`. Сайт обновится примерно за минуту.
