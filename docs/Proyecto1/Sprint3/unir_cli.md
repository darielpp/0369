# __Unir un Cliente a nuestro Dominio LDAP__

## __Comprobaciones Previas__

Es importante que las máquinas se encuentren en la misma red, en caso contrario no podríamos conectar el cliente al servidor, para ello hacemos:

Verificación de la Red en el cliente:

![PING](./imagenes/unir_cli/unir_cli1.png)

Hacer un ping al servidor:

![PING](./imagenes/unir_cli/unir_cli2.png)

En caso no satisfactorio, verificar la configuración de red y corregir cualquier problema de conectividad.

## __Unir el Cliente al Dominio LDAP__

Instalación los paquetes necesarios:

```bash
sudo apt update
sudo apt install ldap-utils libnss-ldap libpam-ldap nslcd
```

![PING](./imagenes/unir_cli/unir_cli2.png)

Al terminar la instalación se nos abrirá automáticamente un configurador de paquetes.

---
En caso de querer abrir este configurador en un futuro o cambiar algo si nos hemos equivocado pedemos ejecutar

```bash
sudo dpkg-reconfigure ldap-auth-config
```

![configurador](./imagenes/unir_cli/unir_cli3.png)

---
Ahora seguimos las indicaciones del configurador

![configurador](./imagenes/unir_cli/unir_cli4.png)

![configurador](./imagenes/unir_cli/unir_cli5.png)

![configurador](./imagenes/unir_cli/unir_cli6.png)

![configurador](./imagenes/unir_cli/unir_cli7.png)

![configurador](./imagenes/unir_cli/unir_cli8.png)

![configurador](./imagenes/unir_cli/unir_cli9.png)

![configurador](./imagenes/unir_cli/unir_cli10.png)

![configurador](./imagenes/unir_cli/unir_cli11.png)

![configurador](./imagenes/unir_cli/unir_cli12.png)

![configurador](./imagenes/unir_cli/unir_cli13.png)

![configurador](./imagenes/unir_cli/unir_cli14.png)

![configurador](./imagenes/unir_cli/unir_cli15.png)

---
Editar el archivo `/etc/nsswitch.conf` para usar LDAP:

```bash
sudo nano /etc/nsswitch.conf
```

Hay que asegurarse de que las líneas `passwd`, `group`, y `shadow` incluyan `ldap`:

![/etc/nsswitch.conf](./imagenes/unir_cli/unir_cli16.png)

---
Editar el archivo `/etc/pam.d/common-session` para indicar el skel y los permisos predeterminados para los usuarios.

![/etc/pam.d/common-session](./imagenes/unir_cli/unir_cli17.png)

---
Editar el archivo `/usr/share/lightdm/lightdm.conf.d/59-ubuntu.conf` para poder iniciar sesión de manera gráfica.

![/usr/share/lightdm/lightdm.conf.d/59-ubuntu.conf](./imagenes/unir_cli/unir_cli18.png)

---
Para comprobar si lo estamos haciendo bien podemos ejecutar el comando:

![getent passwd](./imagenes/unir_cli/unir_cli19.png)

Deberia salirnos el usuario que hemos creado en el anterior apartado.

---
Sabiendo que está bien hecho ya podriamos iniciar sesión con alu1 como miembro del dominio. Lo voy a comprobar reiniciando el PC ya que si solo cierro sesión no va a funcionar.

![correcto_funcionamiento](./imagenes/unir_cli/unir_cli20.png)