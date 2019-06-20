1. git clone repo
2. Копируем в roles/server-tftpd/files/images файлы согласно "copy_here"
3. Правим inventories/custom

Имя хоста
vboxastra

Адрес хоста, на котором будет развернуто окружение
ansible_ssh_host=127.0.0.1

Пароль
ansible_ssh_pass=123456789

Интерфейс на котором будет работать DHCP
dhcp_interface="eth1"

Настройки DHCP сервера
dhcp_subnet="10.11.12.0"
dhcp_netmask="255.255.255.0"
dhcp_range_start="10.11.12.100"
dhcp_range_end="10.11.12.150"
dhcp_option_routers="10.11.12.13"
dhcp_next_server="10.11.12.13"
dhcp_domain_name_servers="10.11.12.13"

4. При необходимости правим меню в roles/server-tftpd/templates/default-pxe.conf.j2

5. Изучаем там же preseed файлы, по необходимости правим

6. Запускаем выполнение командой
ansible-playbook -i inventories/custom custom.yml -l vboxastra
