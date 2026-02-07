# 🎾 Campeonato Cementerio - PWA Instalable

Aplicación web progresiva (PWA) para gestionar el campeonato de cementerio del CEIP Puente de Simancas.

## 📱 Instalación en Dispositivos Móviles

### Android (Chrome/Edge)
1. Abre la web en Chrome o Edge
2. Toca el botón **"📱 Instalar App"** que aparece en la esquina inferior derecha
   - O ve al menú (⋮) → "Instalar aplicación" / "Añadir a pantalla de inicio"
3. Confirma la instalación
4. La app aparecerá en tu cajón de aplicaciones

### iOS (Safari)
1. Abre la web en Safari
2. Toca el botón **Compartir** (□ con flecha hacia arriba)
3. Desplázate y selecciona **"Añadir a pantalla de inicio"**
4. Personaliza el nombre si quieres
5. Toca **"Añadir"**
6. La app aparecerá en tu pantalla de inicio

## 💻 Instalación en Ordenador

### Windows/Mac/Linux (Chrome/Edge)
1. Abre la web en Chrome o Edge
2. Haz clic en el botón **"📱 Instalar App"** 
   - O haz clic en el icono de instalación (➕) en la barra de direcciones
   - O ve al menú (⋮) → "Instalar Campeonato Cementerio..."
3. Confirma la instalación
4. La app se abrirá en su propia ventana

### Desinstalar
- **Android**: Mantén presionado el icono → "Desinstalar"
- **iOS**: Mantén presionado el icono → "Eliminar app"
- **Ordenador**: 
  - Chrome: Ve a chrome://apps → Click derecho en la app → "Desinstalar"
  - O desde el menú de la app (⋮) → "Desinstalar Campeonato Cementerio..."

## 📂 Archivos de la PWA

```
.
├── index.html                 # Archivo principal (renombra campeonato-cementerio-firebase-FIXED.html)
├── manifest.json              # Configuración de la PWA
├── sw.js                      # Service Worker (funcionalidad offline)
├── icon-192.png              # Icono 192x192
└── icon-512.png              # Icono 512x512
```

## 🚀 Despliegue en GitHub Pages

1. **Renombrar archivo principal:**
   ```bash
   mv campeonato-cementerio-firebase-FIXED.html index.html
   ```

2. **Estructura del repositorio:**
   ```
   tu-repositorio/
   ├── index.html
   ├── manifest.json
   ├── sw.js
   ├── icon-192.png
   └── icon-512.png
   ```

3. **Configurar GitHub Pages:**
   - Ve a Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: main (o master) → / (root)
   - Guarda los cambios

4. **Acceder a la app:**
   - URL: `https://tu-usuario.github.io/tu-repositorio/`

## ✨ Características de la PWA

- ✅ **Instalable**: Se instala como app nativa en móvil y escritorio
- ✅ **Funciona offline**: Caché de recursos para uso sin conexión
- ✅ **Actualizaciones automáticas**: Service Worker gestiona las actualizaciones
- ✅ **Sincronización en tiempo real**: Firebase Realtime Database
- ✅ **Responsive**: Se adapta a cualquier tamaño de pantalla
- ✅ **Icono personalizado**: Iconos optimizados para todas las plataformas
- ✅ **Modo standalone**: Se ejecuta en su propia ventana sin barra de navegador

## 🔑 Credenciales

- **Contraseña profesor**: `112233`
- **Modo espectador**: Sin contraseña

## 🔧 Requisitos Técnicos

- Navegador moderno con soporte para:
  - Service Workers
  - Web App Manifest
  - localStorage
  - Fetch API
- Conexión a internet (para sincronización)
- HTTPS (requerido para PWA - GitHub Pages lo proporciona automáticamente)

## 📊 Firebase Configuration

La app está conectada a Firebase Realtime Database:
- **Ruta de datos**: `tournament/`
- **Sincronización**: Automática en tiempo real
- **Backup**: Exportable en formato JSON

## 🛠️ Solución de Problemas

**No aparece el botón "Instalar App":**
- Verifica que estés usando HTTPS
- Asegúrate de que todos los archivos estén en el servidor
- Recarga la página con Ctrl+F5 (o Cmd+Shift+R en Mac)

**La app no funciona offline:**
- Abre la app al menos una vez con conexión para que se cachee
- Verifica que el Service Worker esté registrado (Herramientas de desarrollador → Application → Service Workers)

**Los iconos no se muestran:**
- Verifica que `icon-192.png` y `icon-512.png` estén en el mismo directorio que `index.html`
- Asegúrate de que las rutas en `manifest.json` sean correctas

## 📞 Soporte

Para problemas o sugerencias, contacta al administrador del colegio.

---

**CEIP Puente de Simancas** - Curso 2025/2026
