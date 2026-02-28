🌐 [English](README.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Português](README.pt.md) · [Français](README.fr.md) · [日本語](README.ja.md)

# 📺 Buscador de YouTube

Una herramienta web para buscar videos y transmisiones en vivo de YouTube en orden cronológico real usando tu propia clave API. No requiere inicio de sesión — solo pega tu clave y busca.

## **Buscador de YouTube:** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutorial de clave API:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Características

* 🔍 Busca videos o transmisiones en vivo ordenados por más recientes primero
* 📅 Filtra por fecha — elige un solo día o un rango de fechas con un calendario interactivo
* 🕐 Filtro de hora — limita los resultados a una ventana de tiempo específica (convierte automáticamente tu zona horaria local a UTC)
* 🚫 Filtrar Shorts — oculta videos que contienen hashtags (`#`) en su título o descripción
* ⏱️ Filtro de duración — cuando se selecciona Videos, filtra por Corto (<4 min), Medio (4–20 min) o Largo (20+ min)
* 🎨 8 temas de color — Morado, Cian, Esmeralda, Rosa, Ámbar, Azul, Rosa y Lima
* 💾 La clave API y el tema de color se guardan automáticamente en tu navegador
* ✨ Fondo de partículas animadas
* 🕒 Muestra el tiempo transcurrido para cada resultado
* 🖱️ Haz clic en cualquier resultado para abrir el video directamente
* ⭐ Marca cualquier video como favorito con un toque — los favoritos persisten entre sesiones
* 📋 Añade notas a cualquier video — toca el botón Notas en una tarjeta para expandir un área de texto, guardado automáticamente
* 📄 Exporta tu sesión completa como archivo `.md` — incluye todos los resultados de cada búsqueda realizada, con URLs, enlaces de miniaturas, favoritos y notas, sin cuota adicional

> **Nota:** El modo Transmisiones en vivo se desactiva cuando el filtro de fecha está activo. El filtro de duración solo está disponible en modo Videos.

---

## 🔑 Cómo obtener una clave API de YouTube

1. Abre una nueva pestaña, ve a [Gmail](https://mail.google.com) e inicia sesión en tu cuenta de Google
2. Navega a [console.cloud.google.com](https://console.cloud.google.com)
3. Acepta los **Términos de Servicio** y haz clic en **Acepto y continúo**
4. En la parte superior izquierda, haz clic en **Seleccionar proyecto**, luego en **Nuevo proyecto**
5. Dale un nombre a tu proyecto y haz clic en **Crear** — espera a que termine
6. Abre el **Menú de navegación** (las tres barras arriba a la izquierda), ve a **APIs y Servicios → Biblioteca**
7. Desplázate hasta encontrar **YouTube Data API v3** y haz clic en ella
8. Haz clic en **Habilitar** y espera a que se active
9. En el lado izquierdo, haz clic en **Credenciales**
10. En la parte superior, haz clic en **Crear credenciales → Clave API → Crear**
11. Una vez generada, haz clic en la **Clave API** para abrir su configuración
12. En **Restricciones de API**, haz clic en **Restringir clave → Seleccionar APIs**
    - Si YouTube Data API v3 no aparece de inmediato, actualiza la página
    - Selecciona **YouTube Data API v3** y haz clic en **Aceptar**
13. Haz clic en **Guardar**
14. Haz clic en **Mostrar clave**, luego cópiala
15. Ve al [Buscador de YouTube](https://slotchy.github.io/YouTube-Search-Tool), pega tu clave y realiza una búsqueda para confirmar que funciona

> **Cuota:** El nivel gratuito proporciona 10,000 unidades/día. Cada búsqueda cuesta ~100 unidades (~100 búsquedas/día gratis).

---

## 🚀 Uso

1. Pega tu clave API de YouTube — se guarda automáticamente para visitas futuras
2. Elige **Videos** o **En vivo**
3. Escribe tu tema de búsqueda
4. *(Opcional)* Selecciona una **Duración de video** para filtrar (solo modo Videos)
5. *(Opcional)* Marca **Filtrar Shorts** para excluir videos con hashtags
6. *(Opcional)* Activa **Filtrar por fecha** y selecciona un día o rango en el calendario
7. *(Opcional)* Si hay una fecha seleccionada, establece una hora de **Inicio** y **Fin**
8. Haz clic en **Encontrar más recientes** (o **Buscar** con filtro de fecha activo)
9. Haz clic en cualquier tarjeta para abrir el video
10. *(Opcional)* Haz clic en **☆ Favorite** en cualquier tarjeta para guardarlo como favorito
11. *(Opcional)* Haz clic en **📋 Notes** para expandir un área de notas
12. Haz clic en **Export .MD** para descargar tu sesión completa como archivo Markdown
13. Usa los swatches de color a la derecha para cambiar el tema — se recuerda entre visitas

---

## 📄 Exportación

El botón de exportación aparece automáticamente después de tu primera búsqueda y acumula resultados durante toda la sesión.

El archivo `.md` se organiza así:

* **⭐ Favoritos** — todos los videos marcados, listados primero
* **📝 Notas** — todos los videos con notas adjuntas
* **Todos los resultados** — cada resultado agrupado por término de búsqueda

Los favoritos y las notas persisten en tu navegador entre recargas de página mediante `localStorage`.

---

## 🔒 Privacidad

* La clave API se almacena localmente en tu navegador (`localStorage`) — nunca se envía a ningún lugar excepto a Google
* El tema de color, los favoritos y las notas se almacenan localmente
* Sin backend — todo el procesamiento ocurre en el lado del cliente
* Las únicas solicitudes externas son a la YouTube Data API v3 de Google

---

## 🛠️ Detalles técnicos

| Detalle | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript puro — sin frameworks |
| Backend | Ninguno — totalmente del lado del cliente |
| API | YouTube Data API v3 |
| Resultados | Hasta 50 por búsqueda, ordenados por fecha |
| Filtro de fecha | Usa los parámetros `publishedAfter` / `publishedBefore` |
| Filtro de duración | Usa el parámetro `videoDuration` (`short` / `medium` / `long`) |
| Filtro de Shorts | Del lado del cliente — elimina resultados con `#` en título o descripción |
| Temas | Propiedades CSS personalizadas (`var(--accent)`) cambiadas con JavaScript |
| Partículas | Valores negativos de `animation-delay` para pre-poblar la pantalla al cargar |
| Almacenamiento | `localStorage` para clave API, tema, favoritos y notas |
| Exportación | Descarga Blob del lado del cliente — sin llamadas API adicionales |
