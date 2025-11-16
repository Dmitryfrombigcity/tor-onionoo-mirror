### Данный репозиторий является вспомогательным для [Scanner-for-TOR-Relays](https://github.com/Dmitryfrombigcity/Scanner-for-TOR-Relays).  
Его основная задача кэшировать данные с `https://onionoo.torproject.org/`, и использовать их,
если последний недоступен со стороны пользователя.  
Это происходит:
- по расписанию    [ссылка](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule),
- в ручном режиме  [ссылка](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#workflow_dispatch),
- через GitHub API [ссылка](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#repository_dispatch).

Интерес представляет последний вариант.  
Делая запрос:
```commandline
curl -L \
  -X POST \
  -H "Authorization: Bearer <TOKEN>" \
  https://api.github.com/repos/<USERNAME>/tor-onionoo-mirror/dispatches \
  -d '{"event_type":"manual"}'
```
где `TOKEN` - [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens).