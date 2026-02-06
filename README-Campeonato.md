# 🎾 Campeonato Cementerio - CEIP Puente de Simancas

## 📱 App PWA Instalable + Firebase

Sistema completo de gestión de torneos deportivos con sincronización en tiempo real mediante Firebase.

---

## 📦 Archivos Incluidos

- **campeonato-firebase.html** - Aplicación principal
- **manifest-campeonato.json** - Configuración PWA
- **sw-campeonato.js** - Service Worker para modo offline
- **icon-campeonato-192.png** - Icono 192x192px
- **icon-campeonato-512.png** - Icono 512x512px

---

## 🔥 Conexión Firebase

La app está conectada a tu base de datos Firebase:
- **Proyecto:** app-reserva-de-portatiles
- **Database:** Firebase Realtime Database
- **Ruta:** `/campeonato-torneo/state`

### Estructura en Firebase:
```
campeonato-torneo/
  └── state/
      ├── isAdmin: false
      ├── teams: [...]
      ├── matches: [...]
      ├── teamNames: {...}
      └── playoffs: {...}
```

**IMPORTANTE:** Los datos se sincronizan en tiempo real entre todos los dispositivos conectados.

---

## 🚀 Instalación

### 1️⃣ Subir archivos al servidor

Sube los 5 archivos a tu servidor web en **HTTPS**:
- campeonato-firebase.html
- manifest-campeonato.json
- sw-campeonato.js
- icon-campeonato-192.png
- icon-campeonato-512.png

### 2️⃣ Acceder desde el navegador

Abre la URL:
```
https://tu-dominio.com/campeonato-firebase.html
```

### 3️⃣ Instalar como App

#### 📱 Android (Chrome/Edge):
1. Abre la app en el navegador
2. Botón flotante **"Instalar App"** (esquina inferior derecha)
3. O menú ⋮ → **"Instalar aplicación"**
4. Confirma

#### 🍎 iOS (Safari):
1. Abre en Safari
2. Botón **Compartir** 🔼
3. **"Añadir a pantalla de inicio"**
4. Confirma

#### 💻 PC/Mac (Chrome/Edge):
1. Abre en el navegador
2. Botón **"Instalar App"** o icono ➕ en barra de direcciones
3. Confirma

---

## 👥 Modos de Uso

### 🔐 Modo Profesor (Administrador)
**Clave:** `112233`

Funcionalidades:
- ✅ Cargar listado de alumnos desde Excel
- ✅ Crear equipos automáticamente
- ✅ Editar resultados de partidos
- ✅ Gestionar fase de playoffs
- ✅ Exportar estadísticas a Excel
- ✅ Backup y restauración
- ✅ Simular resultados aleatorios

### 👁️ Modo Espectador
Acceso sin clave.

Funcionalidades:
- ✅ Ver clasificación en tiempo real
- ✅ Ver calendario de partidos
- ✅ Ver fase de playoffs
- ✅ Ver estadísticas del torneo
- ❌ No puede editar nada

---

## 📊 Funcionalidades Principales

### 📋 Pestaña EQUIPOS
- Listado de todos los equipos
- Capitanes y jugadores
- Género y curso de cada jugador

### 🗓️ Pestaña PARTIDOS
- Calendario completo (9 jornadas)
- Filtro por equipo
- Introducción de resultados (solo admin)
- Contador de partidos completados

### 🏆 Pestaña TABLA
- Clasificación actualizada en tiempo real
- Puntos, victorias, empates, derrotas
- Goles a favor, en contra, diferencia
- TOP 8 clasifican a playoffs

### ⚡ Pestaña FINALES
- Cuartos de final (1º vs 8º, 2º vs 7º, etc.)
- Semifinales
- Final
- Visualización en bracket interactivo

### 📈 Pestaña STATS
- Goles totales
- Media de goles por partido
- Número de empates
- Top goleadores (equipos)
- Mejores defensas
- Evolución por jornadas

---

## 📁 Formato del Excel

Para cargar alumnos, el Excel debe tener 3 columnas:

| Nombre | Curso | Género |
|--------|-------|--------|
| Juan Pérez | 6ºA | M |
| María García | 6ºB | F |
| ... | ... | ... |

**Género:** F/M, Femenino/Masculino, Chica/Chico

La app creará automáticamente:
- Equipos mixtos de 2 jugadores
- Asignará capitanes
- Generará calendario de 9 jornadas

---

## 💾 Backup y Restauración

### Descargar Backup
1. Acceso profesor → Icono 💾
2. **"Descargar Backup (JSON)"**
3. Se descarga archivo `.json` con todos los datos

### Restaurar Backup
1. Acceso profesor → Icono 💾
2. **"Restaurar desde Backup"**
3. Seleccionar archivo `.json` previamente descargado
4. Confirmar restauración

**NOTA:** El backup local es independiente de Firebase. Úsalo como respaldo de seguridad.

---

## 📤 Exportar a Excel

Acceso profesor → Icono 📊 → Descarga Excel con:
- Hoja 1: Clasificación completa
- Hoja 2: Todos los partidos con resultados

---

## 🔄 Sincronización en Tiempo Real

Gracias a Firebase:
- ✅ Todos ven los mismos datos al instante
- ✅ Cambios de un profesor se reflejan inmediatamente en todos los espectadores
- ✅ Múltiples profesores pueden gestionar el torneo simultáneamente
- ✅ Funciona en cualquier dispositivo (móvil, tablet, PC)

---

## 🆚 Diferencias con la app de Portátiles

| Característica | App Portátiles | App Campeonato |
|----------------|----------------|----------------|
| Propósito | Reservar portátiles | Gestionar torneo |
| Ruta Firebase | `/reservas/` | `/campeonato-torneo/state` |
| localStorage | userId local | No usado |
| Datos compartidos | Solo por fecha/hora | Todo el estado del torneo |
| Instalable | ✅ | ✅ |

Ambas apps comparten:
- La misma base de datos Firebase
- Rutas diferentes (no interfieren entre sí)
- Capacidad de instalación PWA

---

## 🔧 Personalización

### Cambiar la clave de profesor:
Línea ~423:
```javascript
if (document.getElementById('pass-input').value === "112233") {
```

### Cambiar número de jornadas:
Buscar función `generateLeagueMatches()` y modificar el bucle de jornadas.

### Cambiar colores:
Buscar y reemplazar:
- `#059669` → Color verde principal
- `#10b981` → Color verde claro
- `#047857` → Color verde oscuro

---

## 🐛 Solución de Problemas

### No se conecta a Firebase
- ✅ Verifica que estés en HTTPS
- ✅ Revisa las reglas de Firebase (deben permitir lectura/escritura)
- ✅ Comprueba la consola del navegador (F12)

### No se instala la app
- ✅ Debe estar en HTTPS
- ✅ Todos los archivos deben estar accesibles
- ✅ El manifest.json debe ser válido

### Los datos no se sincronizan
- ✅ Verifica conexión a internet
- ✅ Comprueba que todos usan la misma URL
- ✅ Revisa que la configuración de Firebase sea correcta

### Error al cargar Excel
- ✅ Verifica que tenga las columnas: Nombre, Curso, Género
- ✅ Asegúrate de que el género sea F/M/Femenino/Masculino/Chica/Chico
- ✅ El archivo debe ser .xlsx o .xls

---

## 📱 Reglas de Firebase Recomendadas

Para que funcione correctamente, configura en Firebase Console:

```json
{
  "rules": {
    "campeonato-torneo": {
      ".read": true,
      ".write": true
    }
  }
}
```

**NOTA:** Estas reglas permiten acceso total. Para producción, considera reglas más restrictivas.

---

## 🎓 Uso Educativo

Esta app está diseñada para:
- Gestionar torneos deportivos escolares
- Enseñar organización de competiciones
- Trabajar estadísticas y matemáticas
- Fomentar el deporte y la competición sana
- Practicar uso de tecnología en el aula

---

## 👨‍💻 Créditos

App elaborada por **@luisgeria** · Enero 2026  
Versión Mejorada 2.0 + Firebase + PWA

---

## 📄 Licencia

Uso libre para CEIP Puente de Simancas.

---

**¡Disfruta gestionando tu torneo de cementerio! 🏆**
