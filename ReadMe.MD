# Возвращаем Discord в строй через прокси

---
> Используется проект [drover](https://github.com/hdrover/discord-drover) от великолепного @hdrover
---
> Тут речь идёт о Windows
>
> [Для Linux тут (English)](https://gist.github.com/mzpqnxow/ca4b4ae0accf2d3b275537332ccbe86e)

## Подготовка

Что понадобится?

- VPN (Stealth Proxy). Собственный или купленный. Желательно VLESS/VMESS
- Клиент, который поддерживает HTTP/SOCKS5 прокси
  - [NekoRay](https://github.com/MatsuriDayo/nekoray/releases/latest)
  - [Hiddify](https://github.com/hiddify/hiddify-next/releases/latest)
- Как альтернативу VPN, можно использовать [Tor-Portable](https://github.com/Verity-Freedom/Tor-Portable) от @Verity-Freedom

## Метод через установщик

- Сначала качаем [отсюда архив](https://github.com/hdrover/discord-drover/releases/latest)
- Открываем `drover.exe`
- Указываем информацию о прокси
- Жмём `Install`

## Метод "ручками"

- Сначала качаем [отсюда архив](https://github.com/hdrover/discord-drover/releases/latest)
- Файл `version.dll` распаковываем в папку `app-1...` рядом с .exe файлом Discord
- Добавляем конфигурацию `drover.ini` в ту же папку

### Пример конфигурации

```ini
[drover]
; http / socks5 прокси
proxy = http://127.0.0.1:1080
```
