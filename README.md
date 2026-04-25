# Cristalito — Sistema de Gestión
## Fábrica Frigorífica Lanza

Sistema PWA Mobile-First para gestión de producción y ventas de hielo.

---

## 📁 Estructura de archivos

```
cristalito/
├── index.html        → App completa (toda la lógica en un archivo)
├── sw.js             → Service Worker (funciona offline)
├── manifest.json     → Config PWA (instalable como app nativa)
├── icon-192.png      → Ícono PWA (agregar manualmente)
├── icon-512.png      → Ícono PWA (agregar manualmente)
└── README.md         → Esta guía
```

---

## 🚀 Deploy en GitHub Pages (pasos)

1. Crear repositorio en GitHub (ej: `cristalito`)
2. Subir todos los archivos a la rama `main`
3. Ir a Settings → Pages → Source: `main` / `root`
4. URL resultante: `https://tu-usuario.github.io/cristalito/`

---

## 🔧 Conectar Google Sheets (backend)

### 1. Crear Google Sheet
Crear una hoja con estas pestañas:
- `Turnos` — Fecha | Máquina | Operario | HsInicio | HsFin | KgProducidos | Bolsas1.7 | Bolsas3 | Bolsas6 | Bolsas12
- `Retiros` — Fecha | Hora | Repartidor | Cámara | Bolsas1.7 | Bolsas3 | Bolsas6 | Bolsas12 | ClienteDestino
- `Mermas` — Fecha | Quien | TipoBolsa | Cantidad | Motivo
- `Ventas` — Fecha | Vendedor | Cliente | Heladera | Bolsas1.7 | Bolsas3 | Bolsas6 | Bolsas12 | PV1 | PV2 | FormaPago | Cobrado
- `Clientes` — ID | Nombre | Tipo | Dirección | Distancia | VendedorAsignado | FormaPagoHabitual
- `Heladeras` — ID | ClienteAsignado | Capacidad | Estado
- `Vendedores` — ID | Nombre | Rol | Email
- `Usuarios` — Email | Nombre | Rol

### 2. Apps Script
En Google Sheets → Extensiones → Apps Script, crear un script con endpoint GET/POST para leer y escribir cada hoja.

### 3. Configurar URL
En la app → Más → Configuración → pegar la URL del Web App desplegado.

---

## 👥 Usuarios demo

| Usuario    | Rol      | Contraseña |
|-----------|----------|------------|
| Admin     | Dueño    | 1234       |
| Carlos    | Vendedor | 1234       |
| Lucía     | Vendedora| 1234       |
| Roberto   | Operario | 1234       |

---

## 📱 Instalar como app nativa

1. Abrir la URL en Chrome móvil
2. Menú (3 puntos) → "Agregar a pantalla de inicio"
3. Listo — funciona como app nativa

---

## 🧊 Fase 1 — Funcionalidades incluidas

- ✅ Login con roles (admin / vendedor / operario)
- ✅ Dashboard con métricas del día
- ✅ Stock en tiempo real (producción − retiros − mermas)
- ✅ Registro de retiros de cámara
- ✅ Registro de ventas (PV1 y PV2, forma de pago, cobrado)
- ✅ Gestión de clientes con ficha detallada
- ✅ Gestión de heladeras en consignación
- ✅ Registro de turnos de producción
- ✅ Reporte de mermas
- ✅ Liquidaciones semanales por vendedor
- ✅ Reportes por período (semana / mes / todo)
- ✅ Ranking de vendedores y top clientes
- ✅ Visibilidad por rol (vendedor ve solo sus clientes)

## ⏳ Fase 2 — Próximamente

- Proyección de demanda
- Logística programada
- Google Sheets como base de datos real
- Google OAuth
- Notificaciones push
