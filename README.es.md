🌐 [English](README.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Português](README.pt.md) · [Français](README.fr.md) · [日本語](README.ja.md)

# 📺 YouTube Search Tool

Una herramienta web para buscar videos y transmisiones en vivo de YouTube en orden cronológico real usando tu propia clave de API de YouTube. No es necesario iniciar sesión — solo pega tu clave y busca.

## **YouTube Search Tool:** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutorial de Clave API:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Características

* 🔍 Busca videos o transmisiones en vivo ordenados por más recientes primero
* 📅 Filtrar por fecha — elige un solo día o un rango de fechas personalizado usando un calendario interactivo
* 🕐 Filtro de hora — limita los resultados a una ventana de tiempo específica dentro de la fecha seleccionada (convierte automáticamente tu zona horaria local a UTC)
* 🚫 Filtrar Shorts — oculta videos que contienen hashtags (`#`) en su título o descripción
* ⏱️ Filtro de duración de video — cuando se selecciona Videos, filtra por Corto (<4 min), Medio (4–20 min) o Largo (20+ min)
* 🎨 8 temas de color — Morado, Cian, Esmeralda, Rosa, Ámbar, Azul, Rosado y Lima mediante un panel de muestras
* 💾 Clave de API y tema de color guardados en tu navegador automáticamente
* ✨ Fondo de partículas animadas, precargado al abrir
* 🕒 Muestra hace cuánto tiempo fue publicado cada resultado
* 🖱️ Haz clic en cualquier resultado para abrir el video directamente

> **Nota:** El modo Transmisiones en vivo está deshabilitado cuando el filtro de fecha está activo. El filtro de duración de video solo está disponible en el modo Videos.

---

## 🔑 Cómo Obtener una Clave de API de YouTube

1. Abre una nueva pestaña, ve a [Gmail](https://mail.google.com) e inicia sesión en tu cuenta de Google
2. Navega a [console.cloud.google.com](https://console.cloud.google.com)
3. Cuando se te solicite, acepta los **Términos de Servicio** y haz clic en **Acepto y continúo**
4. En la parte superior izquierda, haz clic en **Seleccionar un proyecto**, luego en la parte superior derecha de esa ventana haz clic en **Nuevo proyecto**
5. Dale un nombre a tu proyecto y haz clic en **Crear** — espera a que termine de crearse
6. Abre el **Menú de navegación** (las tres barras en la parte superior izquierda), desplázate hacia abajo hasta **APIs y servicios** y haz clic en **Biblioteca**
7. Desplázate hacia abajo hasta encontrar **YouTube Data API v3** y haz clic en ella
8. Haz clic en **Habilitar** y espera a que se active completamente
9. En el lado izquierdo, haz clic en **Credenciales**
10. En la parte superior, haz clic en **Crear credenciales → Clave de API**, luego haz clic en **Crear**
11. Una vez generada tu clave, haz clic en la **Clave de API** para abrir su configuración
12. En **Restricciones de API**, haz clic en **Restringir clave**, luego en **Seleccionar APIs**
    - Si YouTube Data API v3 no aparece de inmediato, actualiza la página
    - Desplázate hacia abajo, selecciona **YouTube Data API v3** y haz clic en **Aceptar**
13. Haz clic en **Guardar**
14. Haz clic en **Mostrar clave**, luego cópiala
15. Ve a [YouTube Search Tool](https://slotchy.github.io/YouTube-Search-Tool), pega tu clave y realiza una búsqueda para confirmar que funciona

> **Cuota:** El nivel gratuito proporciona 10,000 unidades/día. Cada búsqueda cuesta ~100 unidades (~100 búsquedas/día gratis).

---

## 🚀 Uso

1. Pega tu clave de API de YouTube — se guarda automáticamente para futuras visitas
2. Elige **Videos** o **Transmisiones en vivo**
3. Escribe tu tema de búsqueda
4. *(Opcional)* Selecciona una **Duración de video** para filtrar por duración (solo modo Videos)
5. *(Opcional)* Marca **Filtrar Shorts** para excluir videos con hashtags en su título o descripción
6. *(Opcional)* Activa **Filtrar por fecha** y selecciona un día o rango de fechas en el calendario
7. *(Opcional)* Si hay una fecha seleccionada, establece una hora de **Inicio** y **Fin** para filtrar por hora del día
8. Haz clic en **Buscar más recientes** (o **Buscar** cuando el filtro de fecha esté activo)
9. Haz clic en cualquier tarjeta de resultado para abrir el video
10. Usa las muestras de color a la derecha para cambiar el tema de acento — se recuerda entre visitas

---

## 🔒 Privacidad

* La clave de API se almacena localmente en tu navegador (`localStorage`) — nunca se envía a ningún lugar excepto a Google
* La preferencia de tema de color se almacena localmente en tu navegador
* Sin backend — todo el procesamiento ocurre del lado del cliente
* Las únicas solicitudes externas son a la API de YouTube Data v3 de Google

---

## 🛠️ Detalles Técnicos

| Detalle | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript puro — sin frameworks |
| Backend | Ninguno — completamente del lado del cliente |
| API | YouTube Data API v3 |
| Resultados | Hasta 50, ordenados por fecha |
| Filtro de fecha | Usa los parámetros `publishedAfter` / `publishedBefore` de la API |
| Filtro de duración | Usa el parámetro `videoDuration` de la API (`short` / `medium` / `long`) |
| Filtro de Shorts | Del lado del cliente — elimina cualquier resultado que contenga `#` en título o descripción |
| Temas | Propiedades personalizadas de CSS (`var(--accent)`) cambiadas con JavaScript |
| Partículas | Valores negativos de `animation-delay` para que las partículas se carguen al inicio |
| Almacenamiento | `localStorage` para la clave de API y preferencia de tema |
