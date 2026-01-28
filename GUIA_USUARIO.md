# 📖 Guía Completa del Bot - Manual de Usuario

## 📌 Índice
- [Introducción](#introducción)
- [Configuración Inicial](#configuración-inicial)
- [Sistema de Moderación](#sistema-de-moderación)
- [Sistema Anti-Raid](#sistema-anti-raid)
- [Sistema de Tickets](#sistema-de-tickets)
- [Sistema de Música](#sistema-de-música)
- [Gamificación (Niveles y Reputación)](#gamificación-niveles-y-reputación)
- [Sistema de Bienvenida y Despedida](#sistema-de-bienvenida-y-despedida)
- [Canales Temporales](#canales-temporales)
- [Notificaciones de Plataformas](#notificaciones-de-plataformas)
- [Encuestas y Sugerencias](#encuestas-y-sugerencias)
- [Inteligencia Artificial](#inteligencia-artificial)
- [Información y Estadísticas](#información-y-estadísticas)
- [Funciones Adicionales](#funciones-adicionales)

---

## 🎯 Introducción

Este bot es una solución completa para la gestión de tu servidor de Discord. Incluye sistemas de moderación avanzada, gamificación, música, tickets de soporte, protección anti-raid y mucho más.

### ✨ Características Principales
- 🛡️ **Moderación Completa**: Advertencias, bans, kicks, mutes y más
- 🚫 **Protección Anti-Raid**: Sistema inteligente contra ataques masivos
- 🎫 **Sistema de Tickets**: Soporte organizado para tu comunidad
- 🎵 **Reproductor de Música**: Música de alta calidad con playlists
- 🎮 **Gamificación**: Sistema de niveles, reputación y rankings
- 💬 **Mensajes Personalizados**: Bienvenida y despedida configurables
- 🔔 **Notificaciones Automáticas**: YouTube, Twitch, TikTok y Kick
- 🤖 **Inteligencia Artificial**: Respuestas automáticas inteligentes
- 📊 **Auditoría Completa**: Registro de todas las acciones importantes

---

## ⚙️ Configuración Inicial

### 1️⃣ Configurar Rol de Administrador
**Comando:** `/setadminrole`
- **Descripción**: Define qué rol tendrá acceso a las funciones administrativas del bot
- **Uso**: `/setadminrole rol:@NombreRol`
- **Importante**: Solo el dueño del servidor puede ejecutar este comando

### 2️⃣ Configurar Canal de Logs
**Comando:** `/setlogchannel`
- **Descripción**: Define dónde se enviarán los registros de moderación
- **Uso**: `/setlogchannel canal:#logs`
- **Recomendación**: Crea un canal privado solo visible para administradores

### 3️⃣ Configurar IP del Servidor (Opcional)
**Comandos:**
- `/ipconfig` - Configurar la IP por primera vez
- `/ip` - Ver la IP configurada
- `/ip-edit` - Editar la IP existente

**Ejemplo:**
```
/ipconfig ip:play.miservidor.com puerto:25565
```

---

## 🛡️ Sistema de Moderación

### 📝 Sistema de Advertencias (Warns)

#### Advertir a un Usuario
**Comando:** `/warn`
- **Uso**: `/warn usuario:@Usuario razón:Motivo de la advertencia`
- **Función**: Registra una advertencia en el historial del usuario
- **Nota**: El usuario recibe un mensaje privado con la advertencia

#### Ver Advertencias
**Comando:** `/warn-list`
- **Uso**: `/warn-list usuario:@Usuario`
- **Función**: Muestra todas las advertencias activas de un usuario

#### Eliminar una Advertencia
**Comando:** `/warn-remove`
- **Uso**: `/warn-remove usuario:@Usuario id:1`
- **Función**: Elimina una advertencia específica por su ID

#### Ver Estadísticas de Advertencias
**Comando:** `/warn-stats`
- **Función**: Muestra el total de advertencias activas en el servidor

### 🚫 Sanciones

#### Banear Usuario
**Comando:** `/banear`
- **Uso**: `/banear usuario:@Usuario razón:Razón del ban`
- **Función**: Expulsa permanentemente al usuario del servidor
- **Permisos Requeridos**: Banear Miembros

#### Desbanear Usuario
**Comando:** `/desbanear`
- **Uso**: `/desbanear usuario_id:123456789 razón:Razón del desbaneo`
- **Función**: Levanta el ban de un usuario
- **Nota**: Necesitas el ID del usuario (no se puede mencionar)

#### Expulsar Usuario
**Comando:** `/expulsar`
- **Uso**: `/expulsar usuario:@Usuario razón:Razón de la expulsión`
- **Función**: Expulsa al usuario (puede volver a entrar)
- **Permisos Requeridos**: Expulsar Miembros

#### Mutear Usuario
**Comando:** `/mutear`
- **Uso**: `/mutear usuario:@Usuario duracion:10m razón:Razón del mute`
- **Función**: Silencia temporalmente a un usuario
- **Duraciones**: 
  - Minutos: `10m`, `30m`
  - Horas: `1h`, `2h`, `24h`
  - Días: `1d`, `7d`
- **Permisos Requeridos**: Moderar Miembros

#### Quitar Mute
**Comando:** `/quitarmute`
- **Uso**: `/quitarmute usuario:@Usuario razón:Razón`
- **Función**: Levanta el silenciamiento de un usuario

### 🧹 Limpieza de Mensajes

**Comando:** `/clear`
- **Uso**: `/clear cantidad:50`
- **Función**: Elimina la cantidad especificada de mensajes
- **Límite**: Máximo 100 mensajes por comando
- **Permisos Requeridos**: Gestionar Mensajes

### ⏱️ Modo Lento (Slowmode)

**Comando:** `/slowmode`
- **Uso**: `/slowmode segundos:5 canal:#general`
- **Función**: Establece un retraso entre mensajes
- **Rango**: 0-21600 segundos (0 = desactivar)

### 🔍 Filtro de Palabras

**Comando:** `/filtro`
- **Acciones Disponibles:**
  - `add` - Agregar palabra prohibida
  - `remove` - Eliminar palabra del filtro
  - `list` - Ver todas las palabras filtradas
  - `allow` - Permitir una palabra específica

**Ejemplos:**
```
/filtro accion:add palabra:palabramala
/filtro accion:list
/filtro accion:remove palabra:palabramala
```

### 📋 Sistema de Auditoría

#### Ver Logs de Auditoría
**Comando:** `/audit-logs`
- **Uso**: `/audit-logs página:1`
- **Función**: Muestra el historial de eventos del servidor

#### Ver Estadísticas de Auditoría
**Comando:** `/audit-stats`
- **Función**: Muestra estadísticas de eventos por tipo

#### Configurar Canal de Auditoría
**Comando:** `/audit-channel`
- **Uso**: `/audit-channel canal:#auditoria`
- **Función**: Define dónde se enviarán las notificaciones de auditoría

#### Limpiar Logs Antiguos
**Comando:** `/audit-clean`
- **Uso**: `/audit-clean días:30`
- **Función**: Elimina logs más antiguos que X días

---

## 🚫 Sistema Anti-Raid

El sistema anti-raid protege tu servidor contra ataques masivos y bots.

### 📊 Ver Estado del Anti-Raid
**Comando:** `/antiraid-estado`
- **Función**: Muestra si está activado y estadísticas actuales

### ⚙️ Ver Configuración
**Comando:** `/antiraid-config`
- **Función**: Muestra todos los parámetros configurados

### ✅ Activar Protección
**Comando:** `/antiraid-activar`
- **Función**: Activa el sistema de protección anti-raid

### ❌ Desactivar Protección
**Comando:** `/antiraid-desactivar`
- **Función**: Desactiva el sistema temporalmente

### 🔧 Configuraciones Avanzadas

#### Configurar Canal de Notificaciones
**Comando:** `/antiraid-set-canal`
- **Uso**: `/antiraid-set-canal id:123456789`
- **Función**: Define dónde se enviarán las alertas de raid

#### Configurar Umbral de Detección
**Comando:** `/antiraid-set-umbral`
- **Uso**: `/antiraid-set-umbral numero:10`
- **Función**: Número de usuarios que deben unirse rápidamente para detectar raid
- **Recomendado**: 5-15 usuarios

#### Configurar Edad Mínima de Cuenta
**Comando:** `/antiraid-set-edad`
- **Uso**: `/antiraid-set-edad milisegundos:604800000`
- **Función**: Edad mínima de cuenta para no ser considerado sospechoso
- **Nota**: 604800000 ms = 7 días

#### Configurar Acción Automática
**Comando:** `/antiraid-set-accion`
- **Uso**: `/antiraid-set-accion accion:kick`
- **Opciones:**
  - `kick` - Expulsar usuarios sospechosos
  - `ban` - Banear usuarios sospechosos

#### Configurar Roles en Whitelist
**Comando:** `/antiraid-set-whitelist`
- **Uso**: `/antiraid-set-whitelist roles:123456789,987654321`
- **Función**: Roles que nunca serán afectados por el anti-raid

#### Configurar Roles Protegidos
**Comando:** `/antiraid-set-protect`
- **Uso**: `/antiraid-set-protect roles:123456789`
- **Función**: Roles adicionales que están protegidos

---

## 🎫 Sistema de Tickets

### ⚙️ Configuración Inicial (Obligatorio)

Antes de usar el sistema de tickets, un **administrador** debe configurarlo:

**1. Configurar la Categoría de Tickets**
```
/ticket-config categoria canal:[categoría]
```
- Selecciona la categoría donde se crearán todos los tickets
- Debe ser una categoría (no un canal de texto)

**2. Configurar el Rol de Staff**
```
/ticket-config rol-staff rol:@Staff
```
- Define qué rol puede ver y gestionar todos los tickets
- Este rol tendrá acceso automático a todos los tickets creados

**3. Ver Configuración Actual**
```
/ticket-config ver
```
- Muestra la configuración actual del sistema de tickets

### 🎪 Mostrar Menú de Tickets

**Comando:** `/ticket-menu`
- **Uso**: `/ticket-menu`
- **Función**: Muestra un menú interactivo con todas las categorías de tickets
- **Permisos Requeridos**: Administrador
- **Ubicación**: El menú aparece donde ejecutas el comando

**¿Para qué sirve?**
- Los usuarios pueden ver todas las opciones disponibles
- Seleccionan el tipo de ticket desde un menú desplegable
- Es más visual e intuitivo que el comando `/ticket`

**Ejemplo de uso:**
1. Un admin ejecuta `/ticket-menu` en el canal de soporte
2. El bot muestra el panel con el menú
3. Los usuarios seleccionan el tipo de ticket que necesitan
4. Se crea automáticamente el canal privado

### 🎪 Crear un Ticket Directamente

**Comando:** `/ticket`
- **Uso**: `/ticket categoria:[opción]`
- **Función**: Crea un ticket de soporte con la categoría seleccionada
- **Permisos Requeridos**: Ninguno (todos los usuarios pueden crear tickets)
- **Ubicación**: El ticket se crea en la categoría configurada

**Ejemplo:**
```
/ticket categoria:Soporte
```

**💡 Nota:** Puedes usar `/ticket-menu` para que los usuarios elijan desde un menú, o `/ticket` para crear directamente.

### 📋 Categorías de Tickets Disponibles
- 🙏🏼 **Soporte**: Ayuda general y dudas del servidor
- ❌ **Bugs**: Reportar errores del servidor o bot
- 🎮 **Reportes**: Reportar comportamiento de otros usuarios
- 🚫 **Apelación**: Apelar advertencias o sanciones
- 🎁 **Recompensas**: Solicitar recompensas por acciones
- 🤝 **Ally**: Solicitudes de alianza con la comunidad

### 🎛️ Panel Administrativo de Tickets
**Comando:** `/ticket-panel`
- **Uso**: `/ticket-panel`
- **Función**: Muestra el panel de gestión del ticket
- **Nota**: Solo funciona dentro de un canal de ticket

### ➕ Agregar Usuario a un Ticket
**Comando:** `/agregar`
- **Uso**: `/agregar usuario:@Usuario`
- **Función**: Da acceso a otro usuario al ticket actual
- **Nota**: Solo funciona dentro de un canal de ticket

### ⚙️ Funcionamiento Automático
- Al ejecutar `/ticket`, se genera un canal privado automáticamente
- El canal se crea en la categoría configurada para tu servidor
- Solo el creador y el rol de staff pueden ver el ticket
- Cada servidor tiene su propia configuración independiente
- Dentro del ticket encontrarás botones para:
  - **Cerrar ticket**: Elimina el canal después de 5 segundos
  - **Valorar atención**: Califica el servicio recibido (del 1 al 5)
  - **Agregar usuario**: Invita a otra persona al ticket
  - **Reclamar ticket** (staff): Toma el ticket como responsable
  - **Liberar ticket** (staff): Libera el ticket para que otro staff lo atienda

### 💡 Notas Importantes
- **Cada servidor** tiene su propia configuración de tickets
- La configuración se guarda automáticamente
- Si cambias la categoría o el rol, todos los tickets nuevos usarán la nueva configuración
- Los tickets ya abiertos mantienen sus permisos originales

---

## 🎵 Sistema de Música

### 🎹 Reproducir Música
**Comando:** `/play`
- **Uso**: `/play cancion:nombre de la canción`
- **Función**: Busca y reproduce la canción solicitada
- **Soporta**: YouTube, Spotify, SoundCloud y URLs directas
- **Nota**: Debes estar en un canal de voz

**Proceso:**
1. El bot busca hasta 10 resultados
2. Te muestra un menú para elegir
3. Seleccionas la canción deseada
4. ¡Comienza la reproducción!

### 📋 Ver Cola de Reproducción
**Comando:** `/queue`
- **Función**: Muestra todas las canciones en espera
- **Información mostrada:**
  - Canción actual
  - Próximas canciones
  - Duración total
  - Número de canciones

### ⏹️ Detener Música
**Comando:** `/stop`
- **Función**: Detiene la reproducción y limpia la cola
- **Efecto**: El bot sale del canal de voz

### ⏭️ Saltar Canción
**Comando:** `/pasar`
- **Función**: Salta a la siguiente canción de la cola

### 🎛️ Menú de Control de Música
**Comando:** `/menu-music`
- **Función**: Abre un panel interactivo con botones de control
- **Permisos Requeridos**: Administrador

**Controles Disponibles:**
- ⏮️ **Anterior**: Volver a la canción anterior
- ⏸️ **Pausa**: Pausar la reproducción
- ▶️ **Play**: Reanudar la reproducción
- ⏭️ **Siguiente**: Saltar a la siguiente canción
- 🔁 **Repetir**: Activar/desactivar modo repetición
- 🔀 **Aleatorio**: Reproducción aleatoria
- 🔊 **Volumen +**: Subir volumen
- 🔉 **Volumen -**: Bajar volumen
- ⏹️ **Stop**: Detener completamente

### 📚 Sistema de Playlists Personales

#### Ver Tus Playlists
**Comando:** `/playlist`
- **Función**: Muestra un menú con todas tus playlists
- **Opciones:**
  - Ver canciones de una playlist
  - Reproducir playlist completa
  - Crear nueva playlist
  - Eliminar playlist

#### Agregar Canción a Playlist
**Comando:** `/playlist-add`
- **Uso**: `/playlist-add cancion:nombre playlist:Mi Playlist`
- **Función**: Busca una canción y la agrega a tu playlist
- **Nota**: Si la playlist no existe, se crea automáticamente

#### Reproducir Playlist
**Comando:** `/playlist-play`
- **Uso**: `/playlist-play playlist:Mi Playlist`
- **Función**: Reproduce todas las canciones de tu playlist

### 📺 Configurar Canal de Música
**Comando:** `/set-music-channel`
- **Uso**: `/set-music-channel canal:#música`
- **Función**: Define dónde se mostrarán las canciones en reproducción
- **Permisos Requeridos**: Gestionar Servidor

### 🔌 Estado de Lavalink
**Comando:** `/lavalink`
- **Función**: Verifica la conexión del servidor de música
- **Útil para**: Diagnosticar problemas de reproducción

---

## 🎮 Gamificación (Niveles y Reputación)

### 📊 Sistema de Niveles

#### ¿Cómo Funciona?
- Los usuarios ganan experiencia (XP) al enviar mensajes
- Al acumular suficiente XP, suben de nivel
- Los niveles se anuncian automáticamente en el canal configurado

#### Ver Ranking de Niveles
**Comando:** `/leaderboard`
- **Función**: Muestra los usuarios con más nivel del servidor
- **Información mostrada:**
  - Posición en el ranking
  - Nivel actual
  - Experiencia total
  - Progreso al siguiente nivel

### ⭐ Sistema de Reputación

#### Dar Voto Positivo
**Comando:** `/reputation-upvote`
- **Uso**: `/reputation-upvote usuario:@Usuario motivo:Por su ayuda`
- **Función**: Otorga +1 punto de reputación
- **Límite**: 1 voto por usuario cada 24 horas

#### Dar Voto Negativo
**Comando:** `/reputation-downvote`
- **Uso**: `/reputation-downvote usuario:@Usuario motivo:Comportamiento inadecuado`
- **Función**: Otorga -1 punto de reputación
- **Límite**: 1 voto por usuario cada 24 horas
- **Permisos Requeridos**: Moderador (recomendado)

#### Ver Perfil de Reputación
**Comando:** `/reputation-profile`
- **Uso**: `/reputation-profile usuario:@Usuario`
- **Función**: Muestra el perfil completo de reputación
- **Información mostrada:**
  - Puntos totales de reputación
  - Votos positivos recibidos
  - Votos negativos recibidos
  - Historial reciente

#### Ver Ranking de Reputación
**Comando:** `/reputation-leaderboard`
- **Función**: Muestra los usuarios con mejor reputación
- **Ordenado por**: Puntos de reputación totales

---

## 💬 Sistema de Bienvenida y Despedida

### 👋 Mensajes de Bienvenida

#### Configurar Bienvenida (Método Simple)
**Comando:** `/welcome-set`
- **Uso**: 
```
/welcome-set canal:#bienvenida mensaje:¡Bienvenido {user} a {server}!
```
- **Variables disponibles:**
  - `{user}` - Mención del usuario
  - `{server}` - Nombre del servidor

#### Configurar Bienvenida (Método Avanzado)
**Comando:** `/welcome-configure`
- **Uso**: 
```
/welcome-configure canal:#bienvenida mensaje:Texto imagen:https://url.com/imagen.png
```
- **Opciones:**
  - **canal**: Canal donde aparecerá el mensaje
  - **mensaje**: Texto personalizado
  - **imagen**: URL de imagen de fondo (opcional)

#### Editar Configuración
**Comando:** `/welcome-edit`
- **Uso**: `/welcome-edit canal:#nuevo-canal mensaje:Nuevo mensaje`
- **Función**: Modifica la configuración existente

#### Ver Configuración Actual
**Comando:** `/welcome-config`
- **Función**: Muestra cómo está configurada la bienvenida

#### Vista Previa
**Comando:** `/welcome-preview`
- **Función**: Muestra cómo se verá el mensaje de bienvenida
- **Útil para**: Probar antes de activar

#### Eliminar Bienvenida
**Comando:** `/welcome-delete`
- **Función**: Desactiva completamente el sistema de bienvenida

### 👋 Mensajes de Despedida

#### Configurar Despedida
**Comando:** `/despedida-set`
- **Uso**: 
```
/despedida-set canal:#despedidas mensaje:{user} ha abandonado {server}
```
- **Variables disponibles:**
  - `{user}` - Nombre del usuario (no mención)
  - `{server}` - Nombre del servidor

#### Editar Despedida
**Comando:** `/despedida-edit`
- **Uso**: `/despedida-edit canal:#nuevo-canal mensaje:Nuevo mensaje`
- **Función**: Modifica la configuración de despedida

#### Eliminar Despedida
**Comando:** `/despedida-delete`
- **Función**: Desactiva el sistema de despedida

---

## 📢 Canales Temporales

### ¿Qué son los Canales Temporales?
Son canales de voz que se crean automáticamente cuando un usuario entra a un canal específico (hub), y se eliminan cuando ya no hay nadie en ellos.

### ⚙️ Configurar Sistema
**Comando:** `/settempcfg`
- **Uso**: `/settempcfg hub:#🔊-Crear-Canal categoria:CANALES TEMPORALES`
- **Parámetros:**
  - **hub**: Canal de voz que creará canales temporales
  - **categoria**: Categoría donde se crearán los canales

**Funcionamiento:**
1. Un usuario entra al canal hub
2. Se crea automáticamente un canal temporal
3. El usuario es movido al nuevo canal
4. El usuario tiene control total de su canal
5. Cuando todos salen, el canal se elimina

### 🎛️ Panel de Control del Canal
**Comando:** `/temp-panel`
- **Función**: Abre un panel para controlar tu canal temporal
- **Solo disponible para**: El dueño del canal temporal
- **Permisos Requeridos**: Administrador del canal

**Opciones del Panel:**
- 👥 **Invitar usuarios**: Permite a usuarios específicos entrar
- 🔒 **Cambiar visibilidad**: Hacer el canal público o privado
- 📝 **Cambiar nombre**: Personalizar el nombre del canal
- 👑 **Transferir propiedad**: Dar control a otro usuario

---

## 🔔 Notificaciones de Plataformas

### 📺 Configurar Canal de Notificaciones
**Comando:** `/setnotifychannel`
- **Uso**: Ejecuta el comando en el canal deseado
- **Función**: Define dónde se enviarán todas las notificaciones de plataformas

### 🎥 YouTube

**Comando:** `/youtube`
- **Uso**: `/youtube canal:@NombreCanal` o `/youtube canal:UCxxxxxxxxx`
- **Función**: Notifica cuando el canal sube un video nuevo
- **Formatos aceptados:**
  - URL completa del canal
  - ID del canal (UC...)
  - @nombrecanal

**Ejemplo:**
```
/youtube canal:https://www.youtube.com/@MiCanal
```

### 🟣 Twitch

**Comando:** `/twitch`
- **Uso**: `/twitch canal:nombre_streamer`
- **Función**: Notifica cuando el streamer comienza a transmitir
- **Nota**: Solo el nombre de usuario, sin URL

**Ejemplo:**
```
/twitch canal:nombrestreamer
```

### 🎬 TikTok

**Comando:** `/tiktok`
- **Uso**: `/tiktok canal:usuario_tiktok`
- **Función**: Notifica cuando se sube nuevo contenido
- **Nota**: Sin el símbolo @

**Ejemplo:**
```
/tiktok canal:usuario
```

### 🎮 Kick.com

**Comando:** `/kickstream`
- **Uso**: `/kickstream canal:nombre_streamer`
- **Función**: Notifica cuando comienza a transmitir en Kick

**Ejemplo:**
```
/kickstream canal:streamer
```

---

## 📊 Encuestas y Sugerencias

### 📋 Sistema de Encuestas

#### Crear Encuesta
**Comando:** `/crearencuesta`
- **Función**: Abre un formulario interactivo para crear una encuesta
- **Proceso:**
  1. Se abre un formulario modal
  2. Ingresas el título de la encuesta
  3. Agregas las opciones (una por línea)
  4. La encuesta se publica con botones de votación

#### Panel de Encuestas
**Comando:** `/panelencuesta`
- **Función**: Crea un panel permanente para lanzar encuestas rápidas
- **Permisos Requeridos**: Administrador

**Características de las Encuestas:**
- ✅ Votación con reacciones
- 📊 Conteo automático en tiempo real
- ⏱️ Tiempo límite configurable
- 🔒 Un voto por persona
- 📈 Resultados visuales

### 💡 Sistema de Sugerencias

#### Configurar Canal de Sugerencias
**Comando:** `/setcanalsugerencia`
- **Uso**: `/setcanalsugerencia canal:#sugerencias`
- **Función**: Define dónde aparecerán las sugerencias

#### Enviar una Sugerencia
**Comando:** `/sugerencia`
- **Uso**: `/sugerencia texto:Mi sugerencia para mejorar el servidor`
- **Función**: Publica tu sugerencia en el canal configurado

**Características:**
- ✅ Votación con reacciones (👍 👎)
- 📊 Conteo automático de votos
- 👤 Se muestra el autor
- 📝 Los administradores pueden responder directamente

---

## 🤖 Inteligencia Artificial

### 💬 Configurar Canal de IA
**Comando:** `/ia`
- **Uso**: `/ia canal:#chat-ia`
- **Función**: Configura un canal donde la IA responderá automáticamente

**Funcionamiento:**
- El bot responde a TODOS los mensajes en ese canal
- Usa inteligencia artificial conversacional
- Mantiene contexto de la conversación
- Respuestas naturales y coherentes

### 🔍 Búsqueda de Información
**Comando:** `/info`
- **Uso**: `/info pregunta:¿Qué es Minecraft?`
- **Función**: Busca información real sobre Minecraft o Hytale
- **Fuente**: Información actualizada y verificada

### ❌ Eliminar Canal de IA
**Comando:** `/ia-remove`
- **Función**: Desactiva la IA en el canal configurado

### 🗣️ Saludos Inteligentes
- El bot responde automáticamente a saludos
- Reconoce: "hola", "buenos días", "buenas tardes", etc.
- Respuestas personalizadas y naturales

---

## 📈 Información y Estadísticas

### 🏰 Información del Servidor
**Comando:** `/serverinfo`
- **Función**: Muestra información completa del servidor
- **Información mostrada:**
  - Nombre y descripción del servidor
  - Dueño del servidor
  - Fecha de creación
  - Número de miembros (humanos y bots)
  - Canales de texto y voz
  - Número de roles
  - Nivel de boost y cantidad de boosts
  - Icono del servidor

### 👤 Información de Usuario
**Comando:** `/userinfo`
- **Uso**: `/userinfo` (para ti mismo) o `/userinfo usuario:@Usuario`
- **Función**: Muestra información del usuario
- **Información mostrada:**
  - Nombre de usuario y apodo
  - ID de usuario
  - Avatar
  - Fecha de creación de la cuenta
  - Fecha de ingreso al servidor
  - Roles asignados
  - Color del rol principal
  - Estado actual

### 🤖 Información del Bot
**Comando:** `/botinfo`
- **Función**: Muestra información sobre el bot
- **Información mostrada:**
  - Versión del bot
  - Tiempo en línea
  - Número de servidores
  - Número total de usuarios
  - Comandos disponibles
  - Uso de memoria
  - Ping/latencia

### 📊 Estadísticas del Servidor
**Comando:** `/stats`
- **Función**: Muestra estadísticas detalladas del servidor
- **Información incluida:**
  - Actividad de miembros
  - Mensajes enviados
  - Comandos ejecutados
  - Canales más activos
  - Usuarios más activos

---

## 🔧 Funciones Adicionales

### ⏱️ Sistema de Cooldowns

#### Configurar Cooldown de Comando
**Comando:** `/cooldown-set`
- **Uso**: `/cooldown-set comando:play segundos:10`
- **Función**: Establece tiempo de espera entre usos de un comando
- **Útil para**: Prevenir spam de comandos

#### Ver Estadísticas de Cooldowns
**Comando:** `/cooldown-stats`
- **Función**: Muestra cooldowns activos en el servidor

#### Limpiar Cooldowns
**Comando:** `/cooldown-clear`
- **Función**: Reinicia todos los cooldowns expirados
- **Permisos Requeridos**: Administrador

### 🎨 Sistema de Embeds Personalizados

Los embeds son mensajes con formato especial, colores y campos organizados.

#### Crear Embed
**Comando:** `/embed` (disponible próximamente)
- **Función**: Crea mensajes embebidos personalizados
- **Opciones configurables:**
  - Título y descripción
  - Color personalizado
  - Campos múltiples
  - Imagen y thumbnail
  - Footer con texto e icono
  - Timestamp

### 🗨️ Comando Say
**Comando:** `/say`
- **Uso**: `/say mensaje:Texto que el bot repetirá`
- **Función**: El bot envía el mensaje que escribas
- **Permisos Requeridos**: Administrador
- **Útil para**: Anuncios oficiales

### 🎤 Sistema Text-to-Speech (TTS)

#### Leer Texto en Voz Alta
**Comando:** `/tts`
- **Uso**: `/tts texto:Hola a todos`
- **Función**: El bot lee el texto en el canal de voz
- **Requisito**: Estar en un canal de voz

#### Detener TTS
**Comando:** `/tts-stop`
- **Función**: Detiene la lectura de voz actual

#### TTS Automático
**Comando:** `/tts-auto`
- **Función**: Activa lectura automática de mensajes en el canal
- **Nota**: Todos los mensajes del canal de texto se leerán en voz

### 🎮 Integración con Pterodactyl

Pterodactyl es un panel de control para servidores de juegos.

#### Configurar Panel
**Comando:** `/ptero-config`
- **Función**: Abre un formulario para configurar tu panel
- **Información requerida:**
  - URL del panel
  - API Key
  - ID del servidor

#### Abrir Panel de Control
**Comando:** `/ptero-panel`
- **Función**: Muestra un panel interactivo para controlar tu servidor
- **Acciones disponibles:**
  - Iniciar servidor
  - Detener servidor
  - Reiniciar servidor
  - Ver estado
  - Ver recursos (CPU, RAM)

### 🏷️ Sistema de Nametags

**Comando:** `/fijar_canal_nametag`
- **Función**: Configura el canal para recibir solicitudes de nametags
- **Uso típico**: Whitelist de servidores de Minecraft
- **Proceso:**
  1. Los usuarios envían su nombre en el canal
  2. Los administradores aprueban o rechazan
  3. Se registra para el servidor

### 🔄 Respuestas Automáticas

#### Agregar Respuesta Automática
**Comando:** `/autoresponse-add`
- **Uso**: `/autoresponse-add palabra:hola respuesta:¡Hola! ¿En qué puedo ayudarte?`
- **Función**: El bot responde automáticamente cuando detecta la palabra

**Características:**
- 🔍 Detección de palabras clave
- 📝 Respuestas personalizadas
- 💬 Se activa en todos los canales (configurable)
- ⚡ Respuesta instantánea

---

## 📖 Tips y Buenas Prácticas

### ✅ Recomendaciones Generales

1. **Organización de Canales**
   - Crea categorías separadas para tickets, logs, moderación
   - Mantén canales privados solo visibles para staff
   - Usa nombres claros y descriptivos

2. **Configuración de Permisos**
   - Define claramente el rol de administrador
   - Limita comandos de moderación solo a staff
   - Usa el sistema de cooldowns para prevenir spam

3. **Sistema de Tickets**
   - Crea una categoría específica para tickets
   - Configura el rol de administrador antes de usar tickets
   - Revisa regularmente los tickets antiguos

4. **Sistema Anti-Raid**
   - Actívalo siempre que sea posible
   - Ajusta el umbral según el tamaño de tu servidor
   - Configura las notificaciones en un canal privado

5. **Gamificación**
   - Anuncia el sistema de niveles a tu comunidad
   - Considera recompensas por niveles altos
   - Usa el sistema de reputación para reconocer buenos miembros

6. **Música**
   - Crea un canal dedicado solo para música
   - Usa playlists para sesiones largas
   - Considera limitar el comando play con cooldown

### ⚠️ Errores Comunes a Evitar

1. ❌ No configurar el rol de administrador antes de usar tickets
2. ❌ No configurar canales de logs para moderación
3. ❌ Abusar de advertencias sin un sistema claro
4. ❌ No activar el sistema anti-raid en servidores grandes
5. ❌ Configurar canales de IA en canales principales (genera spam)
6. ❌ No revisar la configuración del sistema de bienvenida antes de activarlo

### 🎯 Comandos Más Útiles para Empezar

1. `/setadminrole` - Configura permisos
2. `/setlogchannel` - Activa logs de moderación
3. `/welcome-set` - Bienvenida a nuevos miembros
4. `/antiraid-activar` - Protección básica
5. `/setcanalsugerencia` - Recibe feedback de usuarios
6. `!ticket` - Sistema de soporte

---

## 🆘 Solución de Problemas

### El bot no responde a comandos
- ✅ Verifica que el bot esté en línea (punto verde)
- ✅ Asegúrate de usar `/` antes del comando
- ✅ Verifica que tienes los permisos necesarios
- ✅ Comprueba que el bot tenga permisos en el canal

### Los tickets no se crean
- ✅ Configura el rol de administrador con `/setadminrole`
- ✅ Verifica que el bot pueda crear canales
- ✅ Asegúrate de que hay una categoría disponible

### La música no se reproduce
- ✅ Verifica que estés en un canal de voz
- ✅ Comprueba el estado con `/lavalink`
- ✅ Asegúrate de que el bot tenga permiso para conectarse al canal
- ✅ Verifica que el bot pueda hablar en el canal de voz

### El sistema de bienvenida no funciona
- ✅ Verifica la configuración con `/welcome-config`
- ✅ Asegúrate de que el canal configurado existe
- ✅ Comprueba que el bot puede enviar mensajes en ese canal

### El anti-raid no detecta raids
- ✅ Verifica que está activado con `/antiraid-estado`
- ✅ Ajusta el umbral con `/antiraid-set-umbral`
- ✅ Configura el canal de notificaciones

### La IA no responde
- ✅ Verifica que el canal está configurado
- ✅ Comprueba que el bot puede leer y enviar mensajes
- ✅ El servicio de IA podría estar temporalmente no disponible

---

## 📞 Soporte Adicional

Si tienes algún problema que no se menciona en esta guía:

1. 📧 Contacta al administrador del bot
2. 🎫 Usa el sistema de tickets del servidor de soporte
3. 📚 Revisa la documentación en el servidor oficial

---

## 🔄 Actualizaciones

Este bot se actualiza regularmente con nuevas características. Mantente atento a los anuncios en tu servidor para conocer las novedades.

**Versión de la Guía:** 1.0
**Última Actualización:** Enero 2026

---

## 🎉 ¡Disfruta del Bot!

Este bot está diseñado para hacer tu servidor más dinámico, organizado y divertido. Explora todas las funciones y personalízalo según tus necesidades.

**¡Gracias por usar nuestro bot!** 🚀
