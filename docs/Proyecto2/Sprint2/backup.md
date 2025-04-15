# __Script de copia y automatización__

En este apartado configuraremos un sistema de copias de seguridad automáticas del perfil del usuario, usando un script por lotes (.bat) que se ejecutará al iniciar sesión.

---

## __Preparación Prévia__
Para este apartado necesito un tercer disco, para ello:

1. Apaga la máquina virtual.
2. Desde **VirtualBox > Configuración > Almacenamiento**, añade un nuevo disco virtual.
3. Crea el disco con formato **VDI**, almacenamiento dinámico, tamaño recomendado: **2-4 GB**.
4. Inicia la máquina virtual.
5. Entra en **Administración de discos** y formatea este disco como **NTFS**.
6. Asígnale el nombre **Backups** y la letra `E:`.

---

### __Crear carpeta CòpiesUsuaris__

1. Accede al nuevo disco **E:** desde el explorador de archivos.
2. Crea una carpeta llamada `CòpiesUsuaris`.

---

### __Crear script de copia__

1. Abre el Bloc de notas.
2. Escribe lo siguiente:

   ```bat
   @echo off
   xcopy "C:\Users\%USERNAME%" "E:\CòpiesUsuaris\%USERNAME%" /E /H /C /I /Y
   ```

3. Guarda el archivo como `copia_perfil.bat` en `C:\scripts` (crear la carpeta si no existe).

---

### __Configurar ejecución automática del script__

1. Pulsa `Win + R` y escribe `gpedit.msc`.
2. Navega a **Configuración de usuario > Configuración de Windows > Scripts (inicio/cierre de sesión)**.
3. Haz doble clic en **Inicio de sesión** y pulsa **Agregar**.
4. Selecciona el script `copia_perfil.bat` desde la ubicación donde lo guardaste.

---

### __Asignar el script a los usuarios__

1. Asegúrate de que tanto `alumne1` como `alumne2` tengan acceso a la carpeta `C:\scripts`.
2. Inicia sesión con cada uno y verifica que al hacerlo se copia automáticamente su carpeta de usuario a `E:\CòpiesUsuaris\`.

---

## __Verificación y documentación__

Una vez configurados los discos, usuarios, cuotas y scripts, toca comprobar que todo funcione correctamente, para ello:

1. Inicia sesión con el usuario `alumne1`.
2. Comprueba que se ha creado correctamente una copia de su carpeta de usuario dentro de `E:\CòpiesUsuaris\alumne1`.
3. Intenta copiar archivos en la unidad **Dades (D:)** hasta superar los 300 MB.
4. Confirma que el sistema muestra una advertencia y, posteriormente, deniega la operación.

---

## __Revisión final__

Verifico que:

- Las tres particiones existen (C: principal, D: Dades, E: Backups).
- Las cuotas de disco están activas en D: con límite de 300 MB por usuario.
- Los usuarios `alumne1` y `alumne2` están creados y pertenecen al grupo `Limitats`.
- El script se ejecuta correctamente al iniciar sesión y hace la copia correspondiente.
- Las letras de unidad y nombres coinciden con los indicados.
