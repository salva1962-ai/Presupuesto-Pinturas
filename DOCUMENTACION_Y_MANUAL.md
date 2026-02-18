# CromaHogar — Documentación Técnica de Actualizaciones

**Fecha de actualización:** 18 de febrero de 2026
**Versión del Proyecto:** 2.0.0 (PWA Ready)

## 1. Nuevas Funcionalidades Implementadas

### 1.1 Persistencia de Datos de Empresa
Se ha implementado una lógica de almacenamiento local (`localStorage`) para que el usuario no tenga que reintroducir los datos de su empresa en cada sesión.
- **Campos persistidos:** Nombre, NIF/CIF, Dirección, Teléfono, Email y Logotipo.
- **Funcionamiento:** Los datos se guardan automáticamente al guardar un presupuesto y se precargan al iniciar la aplicación o crear uno nuevo.

### 1.2 Sistema de Impuestos Inteligente
Se ha corregido y mejorado la lógica de cálculo tributario:
- **Detección Automática:** Selección de IVA (21%), IGIC (7% para Canarias) o Exento (Ceuta/Melilla/IPSI).
- **Control Manual:** Opción de marcar "Exento de impuesto" manualmente para casos especiales.
- **Sincronización con PDF:** El nombre del impuesto (IVA/IGIC/EXENTO) se refleja dinámicamente en el documento generado.

### 1.3 Conversión a PWA (Progressive Web App)
La aplicación ahora puede instalarse en dispositivos móviles y escritorio.
- **Manifiesto:** Archivo `manifest.json` configurado con iconos y colores corporativos.
- **Service Worker:** Archivo `sw.js` implementado para el almacenamiento en caché de activos principales (`index.html`, iconos, fuentes).
- **Modo Offline:** Permite la carga básica de la interfaz sin conexión a internet.

### 1.4 Icono de Ayuda Contextual
Se ha añadido un botón de ayuda (`?`) en la cabecera para facilitar el uso desde cualquier pantalla.
- **Acceso rápido:** Abre un cuadro con instrucciones clave de configuración, impuestos, líneas y cierre del presupuesto.
- **Usabilidad:** El cuadro se puede cerrar con botón, clic fuera o tecla `Esc`.
- **Accesibilidad:** El botón incorpora `aria-label` y `title` para una mejor interacción en escritorio y móvil.

## 2. Mejoras de Código y Estándares
- **Eliminación de Estilos Inline:** Migración de estilos `style=""` a clases de utilidad CSS para mejorar el rendimiento y la mantenibilidad.
- **Compatibilidad con Safari:** Añadidos prefijos `-webkit-` para propiedades de diseño modernas como `backdrop-filter`.
- **Accesibilidad:** Vinculación correcta de etiquetas `<label>` con sus IDs de entrada correspondientes.

---

# CromaHogar — Manual de Usuario Actualizado

## Guía Rápida de Uso

1. **Configuración Inicial:** 
   - Abre la aplicación y completa "Datos de la Empresa". Estos datos se guardarán para siempre en este dispositivo.
   - Sube tu logotipo (preferiblemente PNG de 300x100px).
2. **Crear Presupuesto:**
   - Introduce los datos del cliente.
   - Selecciona la **Provincia** para que el sistema aplique el impuesto correspondiente automáticamente.
   - Añade líneas de productos o mano de obra usando el botón "＋ Añadir Línea".
3. **Gestión y Descarga:**
   - Pulsa "💾 Guardar" para almacenar el presupuesto en tu historial local.
   - Pulsa "📄 Generar PDF" para descargar un documento profesional listo para enviar por email o WhatsApp.
4. **Instalación como App:**
   - En móviles: Pulsa "Compartir" y luego "Añadir a la pantalla de inicio".
   - En ordenadores: Pulsa el icono de instalación en la barra de direcciones de Chrome o Edge.
5. **Ayuda rápida:**
   - Pulsa el icono **?** de la cabecera para abrir una guía breve dentro de la app.
