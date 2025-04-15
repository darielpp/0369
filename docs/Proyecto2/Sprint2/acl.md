# __Gestión de permisos (ACLs)__

En esta última fase vamos a trabajar con las **Listas de Control de Acceso (ACLs)** de Windows para establecer permisos específicos sobre carpetas. El objetivo es restringir o permitir el acceso según el usuario o grupo.

---

## __¿Qué son las ACLs?__

Las ACLs (Access Control Lists) permiten definir, con gran detalle, quién puede hacer qué con un archivo o carpeta. Cada entrada en una ACL se llama ACE (Access Control Entry) y especifica:

- A qué usuario o grupo afecta.
- Qué permisos se conceden (lectura, escritura, modificación, etc.).

Este sistema permite una gestión avanzada mucho más precisa que los permisos básicos de compartición.

---

## __Objetivo de este apartado__

Queremos que la carpeta `D:\Projectes` tenga los siguientes permisos:

- El grupo `Limitats` debe tener **control total**.
- El usuario `alumne2`, aunque pertenezca al grupo, solo podrá **leer**, pero no modificar.

---

### __Crear la carpeta__

1. Inicia sesión como administrador.
2. Abre el explorador de archivos y accede a la partición `D:\`.
3. Crea una carpeta llamada `Projectes`.

---

### __Asignar permisos al grupo__

1. Haz clic derecho sobre `D:\Projectes` > **Propiedades**.
2. Ve a la pestaña **Seguridad** > **Avanzado**.
3. Desactiva la **herencia** y conserva los permisos existentes.
4. Elimina entradas como `Users` o `Everyone` si están presentes.
5. Añade el grupo `Limitats` y asígnale **control total**.
6. Aplica los cambios.

---

### __Verificar acceso con `alumne1`__

1. Inicia sesión como `alumne1`.
2. Accede a `D:\Projectes`.
3. Crea un archivo de prueba, edítalo y elimínalo.
4. Todo debería funcionar correctamente (hereda permisos de `Limitats`).

---

### __Aplicar una excepción para `alumne2`__

1. Vuelve a iniciar sesión como administrador.
2. Abre CMD y ejecuta:

   ```cmd
   icacls "D:\Projectes" /grant:r alumne2:(R)
   ```

   Esto revoca cualquier otro permiso anterior para `alumne2` y le asigna solo permiso de lectura.

---

### __Verificar la excepción con `alumne2`__

1. Inicia sesión como `alumne2`.
2. Accede a `D:\Projectes` y abre un archivo existente.
3. Intenta modificarlo o crear uno nuevo: deberías recibir un mensaje de acceso denegado.

---

### __Consultar permisos aplicados__

1. Desde la cuenta de administrador, abre una consola CMD.
2. Ejecuta:

   ```cmd
   icacls "D:\Projectes"
   ```

3. Deberías ver una salida similar a:

   ```
   D:\Projectes Limitats:(OI)(CI)(F)
                alumne2:(R)
   ```

   Esto confirma que el grupo tiene control total y `alumne2` tiene solo lectura.

---

Con esto concluye la configuración de permisos específicos mediante ACLs, asegurando un control preciso sobre los accesos a recursos compartidos.
