# Налаштування Windows
* 
## Заміна поведінки Win+E
Мета: при натисканні Win+E відкривати не Провідник Windows, а свій файловий менеджер  
Рішення: редагування реєстру на прикладі Total Commander  
```reg
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Folder\shell\explore\command]
@="\"C:\\Program Files\\totalcmd\\TOTALCMD64.EXE\" /O"
"DelegateExecute"=-
"DelegateExecute.old"="{11dbb47c-a525-400b-9e80-a54615a090c0}"

[HKEY_CLASSES_ROOT\Folder\shell\opennewwindow\command]
"DelegateExecute"=-
"DelegateExecute.old"="{11dbb47c-a525-400b-9e80-a54615a090c0}"
@="\"C:\\Program Files\\totalcmd\\TOTALCMD64.EXE\" /O"
```
Відновлення значення за умовчанням:
```reg
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Folder\shell\explore\command]
@=-
"DelegateExecute.old"=-
"DelegateExecute"="{11dbb47c-a525-400b-9e80-a54615a090c0}"

[HKEY_CLASSES_ROOT\Folder\shell\opennewwindow\command]
@=-
"DelegateExecute.old"=-
"DelegateExecute"="{11dbb47c-a525-400b-9e80-a54615a090c0}"
```
