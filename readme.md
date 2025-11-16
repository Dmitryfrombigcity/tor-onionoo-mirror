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
где `TOKEN` - [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)  
вы обновляете данные на текущий момент.  
***

### This repository is an auxiliary one for Scanner-for-TOR-Relays.  
Its main purpose is to cache data from https://onionoo.torproject.org/ and use it if the latter is unavailable to the user.  
This happens:
- on schedule        [link](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule),
- manually           [link](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#workflow_dispatch),
- via the GitHub API [link](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#repository_dispatch).
  
The last option is of interest.  
Making a request:  
```commandline
curl -L \
  -X POST \
  -H "Authorization: Bearer <TOKEN>" \
  https://api.github.com/repos/<USERNAME>/tor-onionoo-mirror/dispatches \
  -d '{"event_type":"manual"}'
```
where `TOKEN` - [personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens),  
you update the current data.
