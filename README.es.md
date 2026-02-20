# 📺 Buscador de YouTube

Una herramienta web para buscar videos y transmisiones en vivo de YouTube en orden cronológico real usando tu propia clave API. No requiere inicio de sesión — solo pega tu clave y busca.

## **Buscador de YouTube:** https://slotchy.github.io/YouTube-Search-Tool

---

## ✨ Características

* 🔍 Busca videos o transmisiones en vivo ordenados por más recientes primero
* 📅 Filtrar por fecha — elige un día específico o un rango de fechas personalizado con un calendario interactivo
* 🕐 Filtro de hora — acota los resultados a una ventana de tiempo específica dentro de una fecha seleccionada (convierte automáticamente tu zona horaria local a UTC)
* 🚫 Filtrar Shorts — oculta videos que contienen hashtags (`#`) en su título o descripción
* ⏱️ Filtro de duración — cuando se selecciona Videos, filtra por Corto (<4 min), Medio (4–20 min) o Largo (20+ min)
* 🎨 8 temas de color — Morado, Cian, Esmeralda, Rosa, Ámbar, Azul, Rosa fuerte y Lima mediante un panel de muestras
* 💾 La clave API y el tema de color se guardan automáticamente en tu navegador
* ✨ Fondo de partículas animado, precargado al iniciar
* 🕒 Muestra el tiempo transcurrido para cada resultado
* 🖱️ Haz clic en cualquier resultado para abrir el video directamente

> **Nota:** El modo de transmisiones en vivo se desactiva cuando el filtro de fecha está activo. El filtro de duración solo está disponible en el modo Videos.

---

## 🔑 Cómo obtener una clave API de YouTube

1. Ve a [console.cloud.google.com](https://console.cloud.google.com)
2. Crea un nuevo proyecto o selecciona uno existente
3. Habilita **YouTube Data API v3**
4. Navega a **Credenciales → Crear credenciales → Clave API**
5. Copia tu clave API y pégala en la herramienta

> **Cuota:** El nivel gratuito proporciona 10,000 unidades/día. Cada búsqueda cuesta ~100 unidades (~100 búsquedas/día de forma gratuita).

---

## 🚀 Uso

1. Pega tu clave API de YouTube — se guarda automáticamente para futuras visitas
2. Elige **Videos** o **Transmisiones en vivo**
3. Escribe tu tema de búsqueda
4. *(Opcional)* Selecciona una **Duración de video** para filtrar por duración (solo en modo Videos)
5. *(Opcional)* Marca **Filtrar Shorts** para excluir videos con hashtags en su título o descripción
6. *(Opcional)* Activa **Filtrar por fecha** y selecciona un día o rango de fechas en el calendario
7. *(Opcional)* Si se selecciona una fecha, establece una hora de **Inicio** y **Fin** para filtrar por hora del día
8. Haz clic en **Encontrar más recientes** (o **Buscar** cuando el filtro de fecha está activo)
9. Haz clic en cualquier tarjeta de resultado para abrir el video
10. Usa las muestras de color a la derecha para cambiar el tema — se recuerda entre visitas

---

## 🔒 Privacidad

* La clave API se almacena localmente en tu navegador (`localStorage`) — nunca se envía a ningún lugar excepto a Google
* La preferencia de tema de color se almacena localmente en tu navegador
* Sin backend — todo el procesamiento ocurre del lado del cliente
* Las únicas solicitudes externas son a la API de Datos de YouTube v3 de Google

---

## 🛠️ Detalles técnicos

| Detalle | Información |
|---|---|
| Stack | HTML, CSS, JavaScript puro — sin frameworks |
| Backend | Ninguno — completamente del lado del cliente |
| API | YouTube Data API v3 |
| Resultados | Hasta 50, ordenados por fecha |
| Filtro de fecha | Usa los parámetros `publishedAfter` / `publishedBefore` de la API |
| Filtro de duración | Usa el parámetro `videoDuration` de la API (`short` / `medium` / `long`) |
| Filtro de Shorts | Del lado del cliente — elimina cualquier resultado con `#` en título o descripción |
| Temas | Propiedades personalizadas de CSS (`var(--accent)`) intercambiadas con JavaScript |
| Partículas | Valores negativos de `animation-delay` para que las partículas se precarguen al inicio |
| Almacenamiento | `localStorage` para la clave API y la preferencia de tema |
