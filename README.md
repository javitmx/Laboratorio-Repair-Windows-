# Laboratorio-Repair-Windows-
Solución a la configuración del orden de arranque (Boot Priority) realizando una instalación limpia y reparación de BCD.

## 🚨 Problema en cuestión
<p align="center">
  <img src="./screenshots/ERROR.png" height="300" alt="fallo del sistema">
</p>

---

## 🛠️ Laboratorio de Reparación y Mantenimiento de Windows

Este repositorio contiene la documentación de mis prácticas en entornos controlados (**VMware**) sobre reparación de sistemas operativos, recuperación de datos y gestión de errores.

### 🩺 Práctica 1: Recuperación del Arranque (Boot Repair) en Windows 11
**Problema:** El sistema no inicia debido a la corrupción del archivo BCD (Boot Configuration Data). Error: `0xc000000f`.

#### Pasos realizados:
1. **Simulación de fallo:** Eliminación de la partición EFI y el archivo BCD mediante `diskpart` y comandos `del`.
2. **Entorno de recuperación:** Inicio desde ISO de Windows 11 -> Solucionar problemas -> CMD.
3. **Comandos de reparación utilizados:**
   - `bootrec /fixmbr`: Reparación del registro maestro de arranque.
   - `bcdboot C:\Windows /l es-es`: Reconstrucción total de los archivos de arranque desde la imagen del sistema.

**Resultado:** Sistema recuperado exitosamente sin pérdida de datos.

---

## 💻 Gestión del Sistema vía CLI (Modo Server)
Práctica de administración de Windows prescindiendo de la interfaz gráfica (`explorer.exe`).

## ✅ Solución Paso a Paso:

### 1. Configuración de BIOS/Boot Manager
Lo primero es acceder al **Boot Manager** (o BIOS). Debemos priorizar el arranque desde el medio que contiene la ISO de Windows 11 (CD-ROM/DVD). Selecciona la opción **CD-ROM Drive** usando las flechas y presiona `Enter`.

<p align="center">
  <img src="./screenshots/Boot Manager.png" height="300" alt="Bios de la maquina">
</p>

### 2. Acceso al Menú de Recuperación
Una vez cargue el instalador, selecciona la opción **Reparar el equipo** en la esquina inferior izquierda.

<p align="center">
  <img src="./screenshots/reparar.png" height="300" alt="menu contextual">
</p>

### 3. Solucionar Problemas
Dentro del menú contextual, elegimos la opción de **Solucionar problemas**.

<p align="center">
  <img src="./screenshots/Solucionar Problemas.png" height="300" alt="guia">
</p>

### 4. Abrir Símbolo del Sistema
Para realizar la reparación manual, iniciamos el **Símbolo del sistema**.

<p align="center">
  <img src="./screenshots/Simbolo del Sistema.png" height="300" alt="paso 3">
</p>

### 5. Ejecución de Comandos de Reparación
Con la consola abierta, introducimos el primer comando para reconstruir el almacén BCD:

<p align="center">
  <img src="./screenshots/Comando 1 .png" height="300" alt="command one">
</p>

Luego, ejecutamos el comando final para asegurar la correcta ruta de arranque:

<p align="center">
  <img src="./screenshots/Comando 2.png" height="300" alt="command two">
</p>

### 6. Finalización
Para terminar, escribimos `exit` para cerrar la consola y seleccionamos **Continuar**. El sistema se reiniciará con el arranque totalmente reconstruido y funcional.

<p align="center">
  <img src="./screenshots/Continuar.png" height="300" alt="end">
</p>
