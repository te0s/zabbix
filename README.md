# zabbix

#1.Cоздайте файл вашего плейбука (например, zabbix_setup.yml):
nano zabbix_setup.yml
#Скопируйте содержимое плейбука, которое вы хотите выполнить, и сохраните файл.

#2. Проверьте доступ к узлам: Убедитесь, что у вас настроен инвентарь с IP-адресами или хостами серверов: Создайте файл hosts или используйте /etc/ansible/hosts:
nano hosts

[zabbix_servers]
192.168.1.10 ansible_user=your_username ansible_ssh_private_key_file=/path/to/private/key
#проверяем связь узлов
ansible all -m ping -i hosts

#3. Запускаем плейбук

ansible-playbook -i hosts zabbix_setup.yml

