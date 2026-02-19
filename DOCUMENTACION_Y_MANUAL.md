# CromaHogar — Documentación Técnica de Actualizaciones

**Fecha de actualización:** 19 de febrero de 2026
**Versión del Proyecto:** 2.1.0 (PWA Ready)

## 1. Nuevas Funcionalidades Implementadas

### 1.1 Persistencia de Datos de Empresa y Pagos
Se ha implementado una lógica de almacenamiento local (`localStorage`) para que el usuario no tenga que reintroducir los datos de su empresa ni sus condiciones de pago en cada sesión.
- **Campos persistidos:** Nombre, NIF/CIF, Dirección, Teléfono, Email, Logotipo y **Condiciones de Pago**.
- **Condiciones de Pago:** Se incluye un campo fijo editable con los datos bancarios para transferencia, que aparece automáticamente en todos los presupuestos.

### 1.2 Sistema de Impuestos y Exenciones Inteligente
Se ha mejorado la lógica de cálculo tributario y cumplimiento legal:
- **Detección Automática:** Selección de IVA (21%), IGIC (7% para Canarias) o Exento (Ceuta/Melilla/IPSI).
- **Validación de Provincia:** El sistema impide marcar la exención de impuestos si no se ha seleccionado primero una provincia, mostrando una advertencia al usuario.
- **Lógica de Franquicia Fiscal:** Al marcar "Exento de impuesto", el sistema redacta automáticamente la nota legal correspondiente ("Exento de IGIC/IVA por franquicia fiscal") en el apartado de observaciones.
- **Prevención de Duplicados:** Si se cambia la provincia después de activar la exención, el sistema actualiza automáticamente la nota legal sin duplicarla. Si se desmarca la exención, la nota se elimina automáticamente.
- **Sincronización con PDF:** El nombre del impuesto y las notas legales se reflejan dinámicamente en el documento generado.

### 1.3 Nuevos Tipos de Producto
Se ha ampliado el catálogo de tipos de línea para mayor flexibilidad:
- **Novedad:** Añadido el tipo "Material y Mano de obra incluido".
- **Visualización:** Identificación visual diferenciada en la tabla de presupuesto (distintivo azul).

### 1.4 Temas de Color Personalizables
Se ha añadido la posibilidad de cambiar el aspecto visual de la aplicación para adaptarse al gusto del usuario.
- **Selector en Header:** Un nuevo menú desplegable permite elegir entre varios estilos.
- **Temas Disponibles:**
  - **Tradicional:** El estilo original crema y terracota.
  - **Azul Profesional:** Un diseño limpio en tonos azules.
  - **Bosque:** Tonos verdes relajantes.
  - **Naranja:** Una interfaz vibrante y cálida.
- **Persistencia:** El tema elegido se guarda automáticamente en el dispositivo.

### 1.5 Conversión a PWA (Progressive Web App)
La aplicación ahora puede instalarse en dispositivos móviles y escritorio.
- **Manifiesto:** Archivo `manifest.json` configurado con iconos y colores corporativos.
- **Service Worker:** Archivo `sw.js` implementado para el almacenamiento en caché de activos principales (`index.html`, iconos, fuentes).
- **Modo Offline:** Permite la carga básica de la interfaz sin conexión a internet.

### 1.6 Icono de Ayuda Contextual
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
   - Revisa las **Condiciones de Pago** (cuenta bancaria). Lo que escribas aquí aparecerá siempre por defecto en tus nuevos presupuestos.
   - Sube tu logotipo (preferiblemente PNG de 300x100px).
2. **Crear Presupuesto:**
   - Introduce los datos del cliente.
   - Selecciona la **Provincia** para que el sistema aplique el impuesto correspondiente automáticamente.
   - Si eres autónomo en franquicia fiscal, marca **"Exento de impuesto"**; la aplicación añadirá la frase legal obligatoria automáticamente a las notas.
   - Añade líneas con el botón "＋ Añadir Línea". Puedes elegir entre Material, Mano de Obra o un pack completo de "Material y Mano de Obra".
3. **Gestión y Descarga:**
   - Pulsa "💾 Guardar" para almacenar el presupuesto en tu historial local.
   - Pulsa "📄 Generar PDF" para descargar un documento profesional listo para enviar por email o WhatsApp.
4. **Instalación como App:**
   - En móviles: Pulsa "Compartir" y luego "Añadir a la pantalla de inicio".
   - En ordenadores: Pulsa el icono de instalación en la barra de direcciones de Chrome o Edge.
5. **Ayuda rápida:**
   - Pulsa el icono **?** de la cabecera para abrir una guía breve dentro de la app.
