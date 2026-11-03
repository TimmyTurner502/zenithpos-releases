# 📖 Manual de Usuario Oficial — ZenithPOS Pro (Guatemala)

Bienvenido a **ZenithPOS Pro**, el sistema integral de Punto de Venta, Control de Inventarios, Créditos (Khata) y Facturación Electrónica SAT FEL diseñado para el comercio guatemalteco.

---

## Índice de Contenidos

1. [Instalación en Dispositivos Android](#1-instalación-en-dispositivos-android)
2. [Configuración Inicial de la Empresa](#2-configuración-inicial-de-la-empresa)
3. [Control de Caja y Turnos (Arqueo Z)](#3-control-de-caja-y-turnos-arqueo-z)
4. [Módulo de Venta en Mostrador (Cobro Rápido)](#4-módulo-de-venta-en-mostrador-cobro-rápido)
5. [Facturación Electrónica SAT FEL](#5-facturación-electrónica-sat-fel)
6. [Cuentas Corrientes y Fiados (Estilo Khata)](#6-cuentas-corrientes-y-fiados-estilo-khata)
7. [Inventarios, Compras y Kardex](#7-inventarios-compras-y-kardex)
8. [Historial de Ventas, Reimpresión y Anulaciones](#8-historial-de-ventas-reimpresión-y-anulaciones)
9. [Reportes Financieros (P&L) y Guía Fiscal SAT](#9-reportes-financieros-pl-y-guía-fiscal-sat)
10. [Respaldos .ZNP y Sincronización con Google Drive](#10-respaldos-znp-y-sincronización-con-google-drive)
11. [Terminal Web de Pasillo (Wi-Fi Local)](#11-terminal-web-de-pasillo-wi-fi-local)
12. [Gestión de Usuarios, Roles y Permisos](#12-gestión-de-usuarios-roles-y-permisos)

---

## 1. Instalación en Dispositivos Android

ZenithPOS Pro se distribuye como una aplicación nativa Android independiente (APK):

### Paso 1: Descarga
Desde tu teléfono o tablet, abre el enlace oficial de descarga del APK:
`https://github.com/TimmyTurner502/zenithpos-releases/releases/latest/download/zenithpos-pro.apk`

### Paso 2: Habilitar Fuentes Desconocidas
Si es la primera vez que instalas un APK externo:
* **Xiaomi / Redmi (MIUI / HyperOS)**: Al abrir el archivo descargado, selecciona *Ajustes* → activa *Permitir desde esta fuente* → espera el contador de seguridad y confirma.
* **Samsung (One UI)**: Selecciona *Ajustes* → activa *Instalar apps desconocidas* para la app de Archivos o Chrome.
* **Motorola / Otros**: Acepta el permiso emergente para continuar.

### Paso 3: Instalación y Permisos
Pulsa **Instalar**. Al terminar, abre **ZenithPOS Pro**. La app creará automáticamente su base de datos local y estará lista para operar.

---

## 2. Configuración Inicial de la Empresa

Antes de comenzar a facturar:
1. Abre el menú lateral izquierdo (icono de tres líneas `☰`) y selecciona **Ajustes**.
2. En la sección **Datos de la Empresa**:
   * **Nombre Comercial**: Nombre de tu tienda o negocio (ej. *Abarrotería El Esfuerzo*).
   * **Razón Social**: Nombre legal registrado ante SAT.
   * **NIT**: Tu Número de Identificación Tributaria con guión (ej. `4488392-1`).
   * **Dirección y Teléfono**: Datos que aparecerán en la cabecera de los tickets.
   * **Símbolo de Moneda**: Por defecto configurado en **Q** (Quetzales).
   * **Régimen SAT**: Selecciona entre *Pequeño Contribuyente (5%)* o *Régimen General (12% IVA)*.

---

## 3. Control de Caja y Turnos (Arqueo Z)

Para garantizar que el dinero cuadre al centavo:

### Apertura de Turno
1. Al iniciar la jornada laboral, la app solicitará abrir un turno si no hay uno activo.
2. Ingresa el **Saldo Inicial en Efectivo** (el dinero base que dejas en la gaveta para dar cambio, ej. `Q200.00`).
3. Presiona **Abrir Turno**.

### Cierre de Turno y Arqueo Z
1. Al finalizar el día o cambiar de cajero, ve a **Caja y Turnos** en el menú.
2. El sistema calculará el **Efectivo Esperado**:
   $$\text{Efectivo Esperado} = \text{Saldo Inicial} + \text{Ventas en Efectivo} + \text{Entradas de Caja} - \text{Gastos/Salidas}$$
3. Cuenta el dinero físico de la gaveta e ingrésalo en **Efectivo Contado**.
4. La app te indicará si la caja está cuadrada o si existe un **Sobrante** o **Faltante**.
5. Presiona **Cerrar Turno e Imprimir Corte Z**.

---

## 4. Módulo de Venta en Mostrador (Cobro Rápido)

La pantalla principal está diseñada ergonómicamente para despachar en 2 segundos:

* **Agregar productos al carrito**: Toca cualquier tarjeta de producto o escanea su código de barras con el lector USB/Bluetooth o la cámara. Cada toque produce un rebote elástico táctil de confirmación.
* **Ajustar cantidades**: Usa los botones `+` y `-` en el panel derecho del carrito o toca la cantidad para digitar un número exacto.
* **⚡ Botón RÁPIDO CF (Cobro en 2 Segundos)**: Si el cliente paga en efectivo exacto como Consumidor Final, presiona el botón pulsante esmeralda. La venta se registrará de inmediato, descontará stock y abrirá el recibo.
* **Cobro Detallado / Mixto**: Presiona **COBRAR** para seleccionar:
  * Efectivo (ingresa el billete recibido para ver el vuelto exacto).
  * Tarjeta de Crédito/Débito.
  * Transferencia Bancaria.
  * **Crédito / Fiado** (requiere seleccionar un cliente).

---

## 5. Facturación Electrónica SAT FEL

ZenithPOS Pro cumple con la normativa de la SAT de Guatemala:
* **Validación de NIT**: El sistema valida el dígito verificador según el algoritmo legal Módulo 11 de la SAT.
* **Límite legal de Consumidor Final**: Si una venta supera los **Q2,500.00**, la ley prohíbe emitir a CF; la app solicitará obligatoriamente un NIT o CUI válido.
* **Comprobante Digital**: Cada venta genera un comprobante con el identificador único UUID, serie, número y código QR verificable directamente en el portal de la SAT.

---

## 6. Cuentas Corrientes y Fiados (Estilo Khata)

Ideal para tiendas que confían en sus vecinos y clientes habituales:

### Registrar una Venta Fiada
1. En el mostrador, selecciona al cliente en la barra superior del carrito.
2. Añade los productos.
3. Presiona **COBRAR** → selecciona **Crédito / Fiado**.
4. La deuda se acumulará automáticamente en la cuenta corriente del cliente.

### Registrar un Abono de Deuda
1. Ve a **Clientes & Fiados (Khata)** en el menú lateral.
2. Selecciona al cliente (verás su saldo deudor en rojo).
3. Presiona **Registrar Abono**.
4. Digita la cantidad entregada en efectivo y confirma.
5. El saldo se reducirá al instante y podrás enviarle el recibo del abono por WhatsApp.

---

## 7. Inventarios, Compras y Kardex

* **Catálogo de Productos**: Agrega productos con nombre, código de barras, categoría, precio de costo (compra) y precio de venta.
* **Módulo de Compras**: Cuando llegue el camión repartidor o proveedor, registra la compra para aumentar automáticamente las existencias y actualizar el costo promedio ponderado.
* **Kardex Físico y Valorado**: Cada unidad que entra o sale de la tienda queda grabada con fecha, hora, documento de respaldo, existencias previas y existencias resultantes.

---

## 8. Historial de Ventas, Reimpresión y Anulaciones

En la pantalla **Historial de Ventas**:
* 🔍 **Buscar**: Encuentra cualquier ticket por fecha, correlativo, nombre o NIT.
* 🖨️ **Reimprimir**: Vuelve a imprimir un ticket térmico en 58mm/80mm o formato PDF.
* 💬 **Reenviar por WhatsApp**: Envía el comprobante digital al teléfono del cliente con un solo toque.
* ↩️ **Devolución de Mercadería**: Emite una Nota de Crédito por productos devueltos o dañados.
* 🚫 **Anular Venta**: Cancela la factura, reponiendo el stock al almacén y anulando la deuda si era al crédito. **Nunca se borra información para auditoría fiscal**.

---

## 9. Reportes Financieros (P&L) y Guía Fiscal SAT

En el módulo de **Reportes**:
* **Ganancias y Pérdidas (P&L)**:
  * Ventas Netas $-$ Costo de Mercancía Vendida (COGS) $=$ **Ganancia Bruta**.
  * Ganancia Bruta $-$ Gastos Operativos (Luz, Alquiler, Sueldos) $=$ **Ganancia Neta Real**.
* **Valoración de Inventario**:
  * Conoce en todo momento cuánto dinero tienes invertido en mercadería a precio de costo.
* **Guía Fiscal SAT**:
  * **Pequeño Contribuyente**: Muestra el 5% mensual a declarar sobre tus ventas brutas y te alerta al acercarte al tope de Q150,000 anuales.
  * **Régimen General 12%**: Desglosa el débito fiscal para tu perito contador.

---

## 10. Respaldos .ZNP y Sincronización con Google Drive

Tus datos son tu mayor activo y están protegidos contra pérdida o daño del teléfono:

### Generar Respaldo
1. Ve a **Ajustes** → sección **Copia de Seguridad y Sincronización**.
2. Presiona **GENERAR .ZNP**.
3. La app creará el archivo de respaldo y abrirá el menú de compartir de Android.
4. Selecciona **Guardar en Drive** (o envíatelo por WhatsApp o correo).

### Restaurar en un Teléfono Nuevo
1. Instala ZenithPOS Pro en el teléfono nuevo.
2. Abre el archivo `.znp` y copia su contenido de texto.
3. En la app, ve a **Ajustes** → **RESTAURAR** → presiona el botón **PEGAR**.
4. En 2 segundos todos tus productos, clientes, deudas y ventas estarán restaurados.

---

## 11. Terminal Web de Pasillo (Wi-Fi Local)

¿Tienes dependientes o vendedores en los pasillos de la tienda?
1. En la caja principal, ve a **Ajustes** y activa el **Servidor LAN Wi-Fi**.
2. Verás una dirección como `http://192.168.1.50:8080`.
3. Cualquier empleado conectado al mismo Wi-Fi puede abrir esa dirección en el navegador de su propio celular (Chrome o Safari).
4. Podrá ver el catálogo con existencias en tiempo real, armar pedidos con nombre del cliente y pulsar **Enviar a Caja Central**.
5. La caja principal recibirá el pedido listo para cobrar en segundos.

---

## 12. Gestión de Usuarios, Roles y Permisos

Para proteger tu información financiera, ZenithPOS Pro soporta perfiles de usuario:

| Rol | Permisos |
|---|---|
| **Administrador / Dueño** | Acceso total: finanzas, costos, precios, anulaciones y configuración. |
| **Encargado de Tienda** | Supervisión operativa: apertura/cierre de turnos, inventario, compras y devoluciones. |
| **Cajero Mostrador** | Operación de mostrador: cobro rápido, emisión FEL SAT, gastos menores y arqueo de caja. |
| **Vendedor de Pasillo** | Consulta de existencias, precios y armado de preventas en pasillo. |
| **Contador / Auditor** | Acceso de **sólo lectura**: exportación de libros SAT, Kardex y P&L sin modificar datos. |

---

## Soporte y Preguntas Frecuentes

* **¿Requiere internet para vender?**  
  No. ZenithPOS Pro funciona al 100% de forma local y autónoma.
* **¿Qué pasa si se apaga el teléfono repentinamente?**  
  La base de datos SQLite con modo WAL (*Write-Ahead Logging*) previene cualquier corrupción de datos. La última venta guardada permanecerá segura.
* **¿Puedo exportar a Excel para mi contador?**  
  Sí, en la pantalla de Historial de Ventas puedes descargar el archivo `.csv` compatible con Microsoft Excel y Google Sheets.
