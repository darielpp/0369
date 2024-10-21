# __Recuperación gestor de arranque__

Con estas dos herramientas de recuperación del gestor de arranque, para simular un fallo, borraremos el directorio grub de /boot. 

### __Boot-Repair__

![a](./imagenes/restgrub/restgrub1.png)

![a](./imagenes/restgrub/restgrub2.png)

Con esta captura se demuestra que el gestor de arranque falla.

Ahora mediante una iso haciendo como si fuera un liveUSB, ponemos el boot-repair en la máquina virtual y empezamos la recuperación.

![a](./imagenes/restgrub/restgrub3.png)

En este caso no he querido probar de utilizar la ultima versión, asi que le doy a no.

![a](./imagenes/restgrub/restgrub4.png)

En esta pantalla he seleccionado la opción recomendada.

![a](./imagenes/restgrub/restgrub5.png)

Aqui hago click en si.

![a](./imagenes/restgrub/restgrub6.png)

![a](./imagenes/restgrub/restgrub7.png)

Al terminar muestra un archivo .txt con información de lo que ha hecho boot-repair.

![a](./imagenes/restgrub/restgrub8.png)

Esta captura muestra como ha funcionado correctamente.

![a](./imagenes/restgrub/restgrub9.png)

### __SuperGrub 2__

![a](./imagenes/restgrub/restgrub10.png)

![a](./imagenes/restgrub/restgrub11.png)

Vuelvo a repetir la simulación de fallo borrando el directorio grub y vuelvo a repetir el proceso de antes pero ahora con la iso de supergrub.

![a](./imagenes/restgrub/restgrub12.png)

Entro en la opcion de detectar y mostrar los metodos de boot.

![a](./imagenes/restgrub/restgrub13.png)

Busco la opción de linux y le doy al enter para que empiece la recuperación.

![a](./imagenes/restgrub/restgrub14.png)

Al terminar cierro el pc y extraigo la iso que simula el liveUSB, el sistema operativo vuelve a cargar correctamente.

![a](./imagenes/restgrub/restgrub9.png)

Con SuperGrub2, al terminal hay que poner unos comandos en la terminal para que se aplique la restauración, sino al reiniciar vuelve a petarse.

![a](./imagenes/restgrub/restgrub15.png)

![a](./imagenes/restgrub/restgrub16.png)