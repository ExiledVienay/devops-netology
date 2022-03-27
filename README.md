# devops-netology

#### *Домашнее задание к занятию «2.4. Инструменты Git»*

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на `aefea`.
1. Какому тегу соответствует коммит `85024d3`?
1. Сколько родителей у коммита `b8d720`? Напишите их хеши.
1. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами  v0.12.23 и v0.12.24.
1. Найдите коммит в котором была создана функция `func providerSource`, ее определение в коде выглядит 
так `func providerSource(...)` (вместо троеточего перечислены аргументы).
1. Найдите все коммиты в которых была изменена функция `globalPluginDirs`.
1. Кто автор функции `synchronizedWriters`?

 
#### *Ответы на вопросы:*

1. Используя команду git show нашел полный хеш "aefead2207ef7e2aa5dc81a34aedf0cad4c32545" и комментарий "Update CHANGELOG.md" комминта хеш которого начинается на aefea.
 
2. Используя команду git show 85024d3 нашел тег этого коммита - "tag: v0.12.23"

3. Используя команду git show b8d720 нашел двух родителей у коммита b8d720, их хэши найдены с помощью команды git show b8d720^ и git show b8d720^2:       56cd7859e05c36c06b56d013b55a252d0bb7e158 и 9ea88f22fc6269854151c571162c5bcf958bee2b соответственно.
 
4. Используя команду git log v0.12.23..v0.12.24 я обнаружил все хеши и комментарии которые были сделаны между этими тэгами:


commit 33ff1c03bb960b332be3af2e333462dde88b279e (tag: v0.12.24)
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 19 15:04:05 2020 +0000

    v0.12.24

commit b14b74c4939dcab573326f4e3ee2a62e23e12f89
Author: Chris Griggs <cgriggs@hashicorp.com>
Date:   Tue Mar 10 08:59:20 2020 -0700

    [Website] vmc provider links

commit 3f235065b9347a758efadc92295b540ee0a5e26e
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Mar 19 10:39:31 2020 -0400

    Update CHANGELOG.md

commit 6ae64e247b332925b872447e9ce869657281c2bf
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Mar 19 10:20:10 2020 -0400

    registry: Fix panic when server is unreachable

    Non-HTTP errors previously resulted in a panic due to dereferencing the
    resp pointer while it was nil, as part of rendering the error message.
    This commit changes the error message formatting to cope with a nil
    response, and extends test coverage.

    Fixes #24384

commit 5c619ca1baf2e21a155fcdb4c264cc9e24a2a353
Author: Nick Fagerlund <nick.fagerlund@gmail.com>
Date:   Wed Mar 18 12:30:20 2020 -0700

    website: Remove links to the getting started guide's old location

    Since these links were in the soon-to-be-deprecated 0.11 language section, I
    think we can just remove them without needing to find an equivalent link.

commit 06275647e2b53d97d4f0a19a0fec11f6d69820b5
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Wed Mar 18 10:57:06 2020 -0400

    Update CHANGELOG.md

commit d5f9411f5108260320064349b757f55c09bc4b80
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Tue Mar 17 13:21:35 2020 -0400

    command: Fix bug when using terraform login on Windows

commit 4b6d06cc5dcb78af637bbb19c198faff37a066ed
Author: Pam Selle <pam@hashicorp.com>
Date:   Tue Mar 10 12:04:50 2020 -0400

    Update CHANGELOG.md

commit dd01a35078f040ca984cdd349f18d0b67e486c35
Author: Kristin Laemmert <mildwonkey@users.noreply.github.com>
Date:   Thu Mar 5 16:32:43 2020 -0500

    Update CHANGELOG.md

commit 225466bc3e5f35baa5d07197bbc079345b77525e
Author: tf-release-bot <terraform@hashicorp.com>
Date:   Thu Mar 5 21:12:06 2020 +0000

    Cleanup after v0.12.23 release



5. Коммит в котором была создана функция `func providerSource` - 5af1e6234ab6da412fb8637393c5a17a1b293663, он был найден с помощью команды git log -L:providerSource:provider_source.go. Файл в котором находилась данная функция, был найден с помощью команды git grep --break -p 'func providerSource'


6. Коммиты в которых была изменена функция globalPluginDirs(найдено с помощью команды git log -L:globalPluginDirs:plugins.go):
                        
>commit 78b12205587fe839f10d946ea3fdc06719decb05
Author: Pam Selle <204372+pselle@users.noreply.github.com>                          
Date:   Mon Jan 13 16:50:05 2020 -0500                                              
                                                                                      
>commit 52dbf94834cb970b510f2fba853a5b49ad9b1a46
Author: James Bardin <j.bardin@gmail.com>
Date:   Wed Aug 9 17:46:49 2017 -0400

>commit 41ab0aef7a0fe030e84018973a64135b11abcd70
Author: James Bardin <j.bardin@gmail.com>
Date:   Wed Aug 9 10:34:11 2017 -0400

>commit 66ebff90cdfaa6938f26f908c7ebad8d547fea17
Author: James Bardin <j.bardin@gmail.com>
Date:   Wed May 3 22:24:51 2017 -0400




7. Автор функции `synchronizedWriters` Martin Atkins, был найден с помощью команды git log -S"func synchronizedWriters(" и затем просмотром коммитов с помощью git show

>commit 5ac311e2a91e381e2f52234668b49ba670aa0fe5
Author: Martin Atkins <mart@degeneration.co.uk>
Date:   Wed May 3 16:25:41 2017 -0700




  

  



