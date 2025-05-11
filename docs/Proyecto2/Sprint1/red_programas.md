# __Configuración de red y software base tras la instalación__

Una vez completada la instalación de Windows 10 Enterprise, es fundamental configurar adecuadamente los servicios de red y asegurar el sistema con herramientas básicas. A continuación, se detallan los pasos necesarios:

---

## __Configuración de red__

### DHCP (por defecto)
1. Ir a `Panel de control > Centro de redes y recursos compartidos`.
2. Seleccionar "Cambiar configuración del adaptador".
3. Clic derecho en el adaptador de red > "Propiedades".
4. Seleccionar `Protocolo de Internet versión 4 (TCP/IPv4)` > "Propiedades".
5. Asegurarse de que esté seleccionada la opción:
   - "Obtener una dirección IP automáticamente"
   - "Obtener la dirección del servidor DNS automáticamente"

![Red](./img/red_programas/red_programas1.png)
![Red](./img/red_programas/red_programas2.png)

---

### IP estática (opcional)
1. En la misma ventana, seleccionar "Usar la siguiente dirección IP" y configurar por ejemplo:
   - IP: `192.168.1.150`
   - Máscara: `255.255.255.0`
   - Puerta de enlace: `192.168.1.1`
   - DNS: `8.8.8.8` y `1.1.1.1`

![Red](./img/red_programas/red_programas3.png)

---

### Grupo de trabajo
1. Ir a `Este equipo > Propiedades > Cambiar configuración (Nombre del equipo)`.
2. Pulsar en "Cambiar" y establecer:
   - Nombre del equipo: `PC-W10`
   - Grupo de trabajo: `OFICINA`
3. Reiniciar el sistema para aplicar cambios.

![Red](./img/red_programas/red_programas4.png)
![Red](./img/red_programas/red_programas5.png)
![Red](./img/red_programas/red_programas6.png)

---

### Verificación
- En `CMD`, ejecutar:
  ```cmd
  ipconfig /all
  ping 8.8.8.8
  ping google.com
  ```
- Comprobar que hay conexión a Internet y que se resuelven nombres DNS.

![Red](./img/red_programas/red_programas7.png)

---
## __Instalación del software base__

### Antivirus
- Verificar que **Windows Defender** esté activo desde `Configuración > Seguridad de Windows`.
- Opcional: instalar antivirus adicional (Avast, Bitdefender, etc.).

---

### Cortafuegos
- Asegurarse de que el **Firewall de Windows** esté habilitado en:
  `Panel de control > Sistema y seguridad > Firewall de Windows Defender`.

![Red](./img/red_programas/red_programas8.png)

---
### Herramientas de actualización
- Ir a `Configuración > Actualización y seguridad > Windows Update`.
- Pulsar en "Buscar actualizaciones" y aplicar todas las disponibles.

![Red](./img/red_programas/red_programas9.png)

---
### Compresor de archivos
- Descargar e instalar **7-Zip** desde [https://www.7-zip.org](https://www.7-zip.org).
- Verificar su funcionamiento creando y extrayendo un `.zip`.

![Red](./img/red_programas/red_programas10.png)
![Red](./img/red_programas/red_programas11.png)

---
### Navegador alternativo
- Instalar un navegador como:
  - Firefox: [https://www.mozilla.org](https://www.mozilla.org)
  - Chrome: [https://www.google.com/chrome](https://www.google.com/chrome)


---
### Herramientas de administración
- Recomendaciones:
  - **CCleaner** (limpieza del sistema)
  - **Process Explorer** (monitor de procesos)
  - **HWMonitor** (monitor de hardware)

