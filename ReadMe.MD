# Возвращаем Discord в строй через прокси


---
> [!CAUTION]
> Голосовые каналы могут не работать, так как [воис требует UDP](https://discord.com/developers/docs/topics/voice-connections). Для воисов лучше использовать **TUN**neling mode
>
> Подробнее: [1](https://github.com/MatsuriDayo/nekoray/issues/1444) [2](https://github.com/hiddify/hiddify-next/issues/1396)
---
> Используется проект [discord-proxy](https://github.com/aiqinxuancai/discord-proxy) от китайских друзей
---
> Тут речь идёт о Windows
>
> [Для Linux тут (English)](https://gist.github.com/mzpqnxow/ca4b4ae0accf2d3b275537332ccbe86e)

## Подготовка

Что понадобится?

- VPN (Stealth Proxy). Собственный или купленный. Желательно VLESS/VMESS
- Клиент, который поддерживает HTTP прокси
  - [Hiddify](https://github.com/hiddify/hiddify-next/releases/latest)
  - [NekoRay](https://github.com/MatsuriDayo/nekoray/releases/latest)

## Метод "ручками"

- Сначала качаем [отсюда архив](https://github.com/aiqinxuancai/discord-proxy/releases/latest)
- Файл `version.dll` распаковываем в папку `app-1...` рядом с .exe файлом Discord
- Находим ярлык Discord на рабочем столе или где-либо ещё
- Видим строку расположения. Добавляем к ней

```
 --a=--proxy-server=http://127.0.0.1:1081
```

- Порт зависит от настроек вашего клиента
- Стоит заметить, что в начале есть пробел
- Теперь запускать можно через этот ярлык

### Что-то не идёт

#### Точно ли ярлык правильно создан?

Обычно ярлык ведёт на `Update.exe`, не `Discord.exe`. Итог должен выглядеть как-то так

```
C:\Users\XXX\AppData\Local\Discord\Update.exe --processStart Discord.exe --a=--proxy-server=http://127.0.0.1:1081
```

#### Точно ли HTTP прокси на порту?

Socks прокси не поддерживается
