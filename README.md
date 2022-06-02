Текстовый редактор vi (vim)
Vim (сокр. от Vi Improved, произносится Вим) — текстовый редактор, созданный на основе более старого Vi. Ныне это один из мощнейших текстовых редакторов с полной свободой настройки и автоматизации.

На выделенных серверах установлен vim, также создан alias который при вызове команды vi вызывает vim

В данной статье приводится практический опыт использования редактора, кратко описаны широко используемые команды для редактирования текста которые пригодятся начинающим осваивать этот редактор.

 

Режимы работы
Существует три основных режима работы: режим команд, режим редактирования и режим последней строки. Выход из режима редактирования осуществляется клавишей Escape (далее обозначена как (esc), переход в режим редактирования клавишами i или insert. Находясь в режиме команд, можно выполнять сложные операции редактирования текста с помощью клавиши "двоеточие"(:). При нажатии этой клавиши курсор устанавливается в последнюю строку экрана, поэтому данный режим называется режимом последней строки. Он считается особым типом режима команд.

Для того, чтобы открыть какой-то файл или создать новый надо выполнить команду:

# vi имя файла
Затем можно нажать клавишу i (или insert) и внести нужные изменения.

если вместо i нажать a, текст будет вставляться за символом на котором стоит курсор (обычно используется при редактировании файлов этот метод), если нажать o - будет вставлена новая строка.

Стирать текст следует выйдя из режима редактирования клавишей Escape и затем можно использовать клавишу x - она работает как клавиша del - стирает вперед, если нажимать shift+x, то будет стирать назад (по аналогии с backspace)

После редактирования нажмите (esc):wq чтобы выйти с сохранением текста

Включить/выключить нумерацию строк

set number / :set nonumber
Основные команды перемещения по тексту
Перейти к строке с номером
(esc):номер или (esc),номер,shift+g

Поиск по тексту
(esc)/слово_которое_ищем

(esc) shift+j в конце строки объединит строки вместе.

(esc) shift+g - переместит в конец текста

Перемещение на первый символ в режиме просмотра
1g

Работа с буфером
(esc) dd - удалит строку в буфер

(esc) 10dd - удалит 10 строк в буфер

(esc) yy - скопирует строку в буфер

(esc) 10yy - скопирует 10 строк в буфер

(esc) p - вставит содержимое буфера под курсором

(esc) P - вставит содержимое буфера над курсором

 

Замена текста
(esc):s/что_меняем/на_что_меняем/g

g - обозначает замену до конца строки

если надо менять по всему файлу, то тогда пишем (esc):%s/что_меняем/на_что_меняем/g

появился символ % в начале команды

 

Комментировать блок текста от курсора до строки номер 10
:.,10s/^/#/
Комментировать блок текста от курсора до конца
:.,$/^/#/
Как выйти из редактора vi
Выход осуществляется последовательностью нажатий
(esc):q

Выход без сохранения
(esc):q!

Выход с сохранением текста
(esc):wq или (esc):exit

Выход с принудительным сохранением (например, если файл read-only)
(esc):wq!
