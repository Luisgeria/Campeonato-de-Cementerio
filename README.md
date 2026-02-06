# 🏆 App Campeonato - CEIP Puente de Simancas

## 📱 PWA Instalable en Móvil y Ordenador

Esta es una aplicación web progresiva (PWA) completamente funcional que permite gestionar reservas para el campeonato del CEIP Puente de Simancas.

---

## 📦 Archivos Incluidos

- **campeonato-mejorado-pwa.html** - Archivo principal de la aplicación
- **manifest.json** - Configuración de la PWA
- **sw.js** - Service Worker para funcionamiento offline
- **icon-192.png** - Icono 192x192px
- **icon-512.png** - Icono 512x512px

---

## 🚀 Instrucciones de Instalación

### 1️⃣ Subir archivos a tu servidor web

Todos los archivos deben estar en la **misma carpeta** en tu servidor:
- campeonato-mejorado-pwa.html
- manifest.json
- sw.js
- icon-192.png
- icon-512.png

### 2️⃣ Acceder desde el navegador

Abre la URL donde subiste los archivos, por ejemplo:
```
https://tu-dominio.com/campeonato-mejorado-pwa.html
```

**IMPORTANTE:** La app DEBE estar en HTTPS (no funciona en HTTP) para poder instalarse.

### 3️⃣ Instalar en dispositivos

#### 📱 En Android (Chrome/Edge):
1. Abre la app en el navegador
2. Verás un botón flotante **"Instalar App"** en la esquina inferior derecha
3. Haz clic en el botón o en los 3 puntos ⋮ → **"Instalar aplicación"** / **"Añadir a pantalla de inicio"**
4. Confirma la instalación
5. ¡Listo! La app aparecerá como una app nativa en tu móvil

#### 🍎 En iOS (Safari):
1. Abre la app en Safari
2. Toca el botón de **Compartir** (cuadrado con flecha hacia arriba)
3. Desplázate y selecciona **"Añadir a pantalla de inicio"**
4. Dale un nombre y confirma
5. ¡Listo! La app aparecerá en tu pantalla de inicio

#### 💻 En PC/Mac (Chrome/Edge):
1. Abre la app en el navegador
2. Haz clic en el botón **"Instalar App"** que aparece en la esquina inferior derecha
   - O bien: Icono ➕ en la barra de direcciones
   - O bien: Menú ⋮ → **"Instalar Campeonato CEIP..."**
3. Confirma la instalación
4. ¡Listo! Se abrirá como una app independiente

---

## 🔥 Conexión con Firebase

La app está conectada a tu Firebase existente:
- **Proyecto:** app-reserva-de-portatiles
- **Base de datos:** Firebase Realtime Database
- **Ruta de datos:** `/campeonato/` (diferente de la app de portátiles que usa `/reservas/`)

### Estructura de datos en Firebase:
```
campeonato/
  └── 2026-02-10/
      ├── p1/
      │   ├── slotId: "p1"
      │   ├── date: "2026-02-10"
      │   ├── profe: "María García"
      │   ├── curso: "6ºA"
      │   ├── timestamp: 1707567890123
      │   └── userId: "user_1707567890_abc123"
      └── p2/
          └── ...
```

---

## ✨ Características

✅ **Instalable** en móvil y ordenador como app nativa
✅ **Funciona offline** gracias al Service Worker
✅ **Base de datos en tiempo real** con Firebase
✅ **Diseño responsive** adaptado a todos los dispositivos
✅ **Scroll horizontal** visible y estilizado en la tabla
✅ **Sistema de permisos** - Solo puedes liberar tus propias reservas
✅ **Navegación semanal** - Avanza y retrocede semanas
✅ **Indicador de conexión** en tiempo real

---

## 🎯 Cómo Usar la App

1. **Hacer una reserva:**
   - Haz clic en cualquier horario disponible (cuadro blanco)
   - Rellena el formulario con tu nombre y curso
   - Confirma la reserva

2. **Liberar una reserva:**
   - Solo puedes liberar las reservas que TÚ hiciste desde este dispositivo
   - Haz clic en el botón "Liberar" que aparece en tus reservas
   - Confirma la liberación

3. **Navegar entre semanas:**
   - Usa las flechas ← → para cambiar de semana
   - La semana actual se muestra en el centro

---

## 🔧 Personalización

Si quieres cambiar el título, colores o periodos horarios, edita el archivo `campeonato-mejorado-pwa.html`:

### Cambiar el título:
```html
<h1 class="text-3xl md:text-4xl font-black text-green-800 tracking-tight mb-2">🏆 Campeonato</h1>
```

### Cambiar los horarios:
```javascript
const periods = [
    { id: 'p1', h: "09:00 - 10:00" }, 
    { id: 'p2', h: "10:00 - 11:00" },
    // Añade más aquí...
];
```

### Cambiar los colores:
Busca `#16a34a` (verde principal) y `#15803d` (verde oscuro) y cámbialo por tus colores.

---

## 📊 Ventajas de esta App

- **Dos apps independientes:** Esta app (Campeonato) y la de Portátiles funcionan en la misma base de datos de Firebase pero con rutas separadas
- **Sin conflictos:** Cada app tiene su propio `userId` y su propia ruta de datos
- **Fácil de mantener:** Puedes tener múltiples apps similares sin que interfieran entre sí
- **Escalable:** Puedes crear más apps (Biblioteca, Sala de profesores, etc.) usando el mismo patrón

---

## 🐛 Solución de Problemas

### La app no se instala:
- ✅ Verifica que estés en HTTPS (no HTTP)
- ✅ Asegúrate de que todos los archivos estén en la misma carpeta
- ✅ Revisa la consola del navegador (F12) para ver errores

### No se conecta a Firebase:
- ✅ Verifica que los archivos manifest.json y sw.js estén accesibles
- ✅ Comprueba las reglas de seguridad de Firebase
- ✅ Revisa la consola del navegador para ver mensajes de error

### El scroll horizontal no funciona:
- ✅ Asegúrate de tener la última versión del archivo
- ✅ Prueba en diferentes navegadores
- ✅ En móvil, arrastra la tabla horizontalmente con el dedo

---

## 👨‍💻 Soporte

App elaborada por **@luisgeria** · Enero 2026

Para más información sobre Firebase:
- [Documentación oficial de Firebase](https://firebase.google.com/docs)
- [Consola de Firebase](https://console.firebase.google.com/)

---

## 📝 Licencia

Uso libre para CEIP Puente de Simancas.

---

**¡Disfruta de tu nueva app instalable! 🎉**
