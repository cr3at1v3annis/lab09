# lab09
### Домашнее задание
```sh
1.gpg --list-secret-keys --keyid-format LONG
2.gpg --full-generate-key
3.gpg --list-secret-keys --keyid-format LONG
4.gpg -K ${GITHUB_USERNAME}
5.GPG_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep ssb | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
6.GPG_SEC_KEY_ID=$(gpg --list-secret-keys --keyid-format LONG | grep sec | tail -1 | awk '{print $2}' | awk -F'/' '{print $2}')
7.gpg --armor --export ${GPG_KEY_ID}
8.git config user.signingkey ${GPG_SEC_KEY_ID}
9.git config gpg.program gpg
```  
1. Эта команда выводит все ключи, которые есть у пользователя в режиме long
2. Эта команда создает ключ-пару.
3. Аналогично 1
4. Вывод на экран сектретных ключей по пользователю
5. Запись в переменную GPG_KEY_ID самого ключа, здесь публичного
6. Запись в переменную GPG_SEC_KEY_ID ключа, секретного
7. Экспорт публичного ключа по переменной, и параллельно вывод в текстовом формате
8. Сообщаем Git об использовании ключа, установка ключа для использования
9. Установка "шифровальной программой" gpg
