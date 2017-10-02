YetAnotherBookCollection
=======

Author: Polyakov Igor

SibirCTF 2017 `YetAnotherBookCollection` service

Installation
------------

Required: postgresql, ruby, bundler, rails

Install dependencies:
```
apt-get update
apt-get install ruby ruby-dev
gem install bundler
```

Run
------------
```
RAILS_ENV=production bundle exec rake db:create db:schema:load db:seed DISABLE_DATABASE_ENVIRONMENT_CHECK=1
RAILS_ENV=production bundle exec rake assets:precompile
RAILS_ENV=production bundle exec rails server
```
[Explotation]:
------------

- [x] A4 – Нарушение контроля доступа

- [x] A1 – Внедрение кода

- [x] A* – [Mass Assignment]

ToDo:
------------
- [ ] Bugs
  - [x] DOS - to_sym. Symbol — это особый тип данных в Ruby, являющийся, по сути, константой, при этом сами символы никогда не удаляются сборщиком мусора. Соответственно можно забить память пользовательским вводом.

- [x] Docker

- [x] Juri

Dependency:
------------
- Rails

- ImageMagic

- PostgreSQL

[Explotation]: https://habrahabr.ru/company/pentestit/blog/326272/
[Mass Assignment]: https://xakep.ru/2013/12/03/ruby-on-rails-safe-problem/#toc06.


Checker
=======

checker.py

URL
---

http://host:9999

Checker input params
--------------------

```
$1 = CMD
$2 = HOST
$3 = ID
$4 = FLAG
```

Example checker call
--------------------

```
#!/bin/bash

echo "TEST CHECK"
./checker.py check 127.0.0.1
echo "TEST PUT"
./checker.py put 127.0.0.1 user_name e23dewf43r3q4r8efd4
echo "TEST GET"
./checker.py get 127.0.0.1 user_name e23dewf43r3q4r8efd4
```

Exit codes
----------
```
110 - ERROR
104 - DOWN
103 - MUMBLE
102 - CORRUPT
101 - SUCCESS
```

License
-------

MIT License

Copyright (c) 2017 Igor Polyakov
