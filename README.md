# Задание B6.5.1

1.Напишите плейбук, который будет на удаленной системе создавать пользователя user1 и задавать ему SSH-ключ (создавая заданный ключ в /home/user1/.ssh/id_rsa.pub). Ключ не должен передаваться в открытом виде. Используйте для шифрования ключа ansible-vault. Ключ можете сгенерировать, используя SSH-keygen.  

Запустить для шифрования ключа: ansible-vault encrypt --ask-vault-pass ~/.ssh/id_rsa.pub  
Запустить плейбук: ansible-playbook user1.yaml -u root --ask-pass --ask-vault-pass  

root - учетная запись на удаленном хосте

2.Создайте плейбук, который устанавливает, либо удаляет почтовый сервер postfix в зависимости от тега.  

Установить postfix: ansible-playbook --tags "init postfix" postfix.yaml --ask-become-pass

Удалить postfix: ansible-playbook --tags "drop postfix" postfix.yaml --ask-become-pass  
