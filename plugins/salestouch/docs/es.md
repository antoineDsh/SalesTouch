# SalesTouch

[English](../README.md) · [Français](fr.md) · [Deutsch](de.md) · [Español](es.md) · [Português](pt.md) · [Italiano](it.md)

**Prospección en LinkedIn para agentes de IA.** SalesTouch es un MCP de LinkedIn que conecta Claude con la investigación de prospectos, conversaciones, mensajes, publicaciones, seguimientos y colas. SalesTouch no está afiliado a LinkedIn ni cuenta con su respaldo.

## Requisitos

Un espacio de SalesTouch con un plan activo y una cuenta de LinkedIn conectada. Las funciones de Sales Navigator requieren los permisos correspondientes. Los resultados dependen de los permisos, los datos disponibles y los límites de la plataforma.

## Instalar en Claude Code

Ejecuta en Claude Code:

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Reinicia Claude Code, ejecuta `/mcp`, selecciona SalesTouch y autoriza la conexión en el navegador. No incluyas contraseñas de LinkedIn, cookies ni claves API en la conversación o configuración del plugin.

## Instalar en Claude Desktop o Cowork

Abre **Customize → Plugins**. En **Personal plugins**, selecciona **+ → Add marketplace**, elige la opción de repositorio e introduce `antoineDsh/SalesTouch`. Instala y activa `salestouch`, y autoriza su conector de SalesTouch. Las opciones disponibles dependen de tu plan de Claude y de la configuración de tu organización.

## Cursor

Clona este repositorio público en `~/.cursor/plugins/local/salestouch` y recarga Cursor. Abre **Settings → Tools & MCPs**, busca `salestouch`, pulsa **Connect** y autoriza SalesTouch en el navegador. Tu organización puede restringir los plugins locales. La inclusión en el marketplace está sujeta a la revisión de Cursor.

También puedes añadir la [configuración MCP](../../../README.md#cursor) a `.cursor/mcp.json` para el proyecto o a `~/.cursor/mcp.json` para tu perfil. Completa la autorización enseguida: Cursor puede dejar de esperar tras 30 segundos. Si ocurre, vuelve a pulsar **Connect**. Empieza con el prompt de comprobación de cuentas que aparece abajo. Mantén activadas las aprobaciones de herramientas y revisa los destinatarios y el contenido antes de permitir acciones externas.

El plugin MIT se instala gratis. El servicio alojado de SalesTouch requiere una suscripción aparte. No incluyas credenciales de LinkedIn en la configuración MCP.

## Tres prompts para empezar

1. «Lista mis cuentas de LinkedIn conectadas con SalesTouch».
2. «Investiga este perfil de LinkedIn y sus publicaciones recientes. Redacta una presentación pertinente sin enviarla: [URL del perfil]».
3. «Lee esta conversación de LinkedIn, resume las necesidades del prospecto y prepara una respuesta sin enviarla: [ID de conversación o URL del perfil]».

Sustituye los valores entre corchetes por tus destinatarios. También puedes extraer resultados de búsqueda o personas que interactuaron con publicaciones, recorrer los resultados guardados y descargar exportaciones. Revisa el destinatario, el contenido y la hora antes de aprobar una acción. Pendiente no significa entregado. Consulta la cola antes de repetir una operación de escritura.

## Conexión y ayuda

El endpoint MCP remoto es `https://www.salestouch.io/api/mcp`, con Streamable HTTP y OAuth. Si falla la autorización, vuelve a conectar el conector, comprueba el espacio y la conexión de LinkedIn y repite el prompt de cuentas. Comparte con soporte solo un código de error y pasos de reproducción sin credenciales, tokens ni mensajes privados.

[Configuración](../SETUP.md) · [Soporte](https://www.salestouch.io/support) · [Seguridad](../SECURITY.md) · [Documentación](https://www.salestouch.io/docs) · [Privacidad](https://www.salestouch.io/privacy) · [Condiciones](https://www.salestouch.io/terms) · [support@salestouch.io](mailto:support@salestouch.io)

Los archivos del plugin usan la [licencia MIT](../LICENSE). El backend alojado es propietario.

## Versión 0.9.3

Instala SalesTouch localmente en Cursor, conéctalo mediante OAuth y empieza comprobando las cuentas. El paquete de Cursor incluye ahora su logotipo e instrucciones más claras.

## Versión 0.9.2

Conexión con Claude Code corregida: solo se solicitan los permisos necesarios para el MCP.

## Versión 0.9.1

Instalación actualizada en seis idiomas; configuración y soporte incluidos en el paquete; analítica MCP técnica sin objetivos de conversación ni contenido de las llamadas. [Historial de cambios](../CHANGELOG.md).
