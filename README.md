# Proyecto ProcesosUDistMejorados
Este proyecto tiene como objetivo principal optimizar el proceso de inscripción de trámites administrativos en la Universidad Distrital Francisco José de Caldas.

## Configuración de Conexión por WhatsApp
Para establecer la conexión a través de WhatsApp, se requiere utilizar las siguientes credenciales proporcionadas por la aplicación "https://www.twilio.com":
- Correo electrónico: jdcamargouseche@gmail.com
- Contraseña: JuanDavid14242023*

Dado que esta aplicación es fundamental para lograr la conexión exitosa, se han preparado una serie de videos instructivos que pueden resultar útiles:
- [Video tutorial: Cómo conectar con Rasa](https://www.youtube.com/watch?v=gLt8j8ebDK8)
- [Video tutorial: Instalación y uso de NGROK](https://www.youtube.com/watch?v=YyvDQTk4CEI)

## Configuración Adicional para la Conexión por WhatsApp
Es importante tener en mente que si deseamos cargar un bot nuevo o reutilizar uno existente, únicamente es necesario crear el punto de entrada mediante NGROK, ya que todo lo demás debería estar operativo. Esto no aplica en el caso de la conexión con WhatsApp.

Adicionalmente, recomendamos revisar el siguiente video en caso de que surja la necesidad de crear un nuevo chat:
- [Video tutorial: Cómo crear un chat en Telegram](https://www.youtube.com/watch?v=QuyWEbKMzcA)

Nuestro objetivo es mejorar la experiencia en los procesos administrativos de la universidad, y esta guía debería brindarte la orientación necesaria para lograr una configuración exitosa. ¡No dudes en contactarnos si necesitas más ayuda o información!

# SafeChatDB

## Descripción:
**SafeChatDB** es una base de datos diseñada para gestionar un chat seguro, especialmente dirigido a personas que pueden estar experimentando algún tipo de violencia.

## Tablas y sus Descripciones:

### 1. Usuarios
**Descripción**: Almacena la información personal de los usuarios del chat.

**Campos**:
- `idUsuarios`: Identificador único del usuario.
- `nombres`: Nombre del usuario.
- `apellidos`: Apellidos del usuario.
- `tipoIdentificacion`: Tipo de documento de identidad del usuario (por ejemplo, DNI, pasaporte).
- `numeroIdentificacion`: Número de identificación del usuario.
- `correoElectronico`: Correo electrónico del usuario.
- `numeroCelular`: Número de celular del usuario.
- `Domicilio`: Domicilio del usuario.

### 2. TiposDeRecursos
**Descripción**: Almacena diferentes tipos de recursos que pueden ser recomendados o proporcionados a los usuarios.

**Campos**:
- `idTiposDeRecursos`: Identificador único del tipo de recurso.
- `nombre`: Nombre del tipo de recurso.
- `descripcionTipo`: Descripción breve del tipo de recurso.

### 3. Recursos
**Descripción**: Almacena recursos específicos relacionados con los diferentes tipos de recursos.

**Campos**:
- `idRecursos`: Identificador único del recurso.
- `nombre`: Nombre del recurso.
- `descripcion`: Descripción del recurso.
- `ubicacion`: Ubicación o dirección del recurso.
- `contacto`: Información de contacto para el recurso.
- `TiposDeRecursos_idTiposDeRecursos`: Relación con la tabla `TiposDeRecursos`.

### 4. TiposDeViolencias
**Descripción**: Almacena diferentes tipos de violencias que pueden ser experimentadas por los usuarios.

**Campos**:
- `idTiposDeViolencias`: Identificador único del tipo de violencia.
- `nombre`: Nombre del tipo de violencia.
- `descripcionTipo`: Descripción breve del tipo de violencia.

### 5. Cargos
**Descripción**: Almacena diferentes cargos que pueden tener los asesores.

**Campos**:
- `idCargos`: Identificador único del cargo.
- `nombre`: Nombre del cargo.
- `descripcion`: Descripción breve del cargo.

(Continúa con las demás tablas: Asesores, Status, Conversaciones, Interacciones, Agendas...)

## Relaciones:
- La tabla `Recursos` tiene una relación con `TiposDeRecursos`.
- La tabla `Asesores` tiene una relación con `Cargos`.
- La tabla `Conversaciones` se relaciona con `Usuarios`, `Status` y `Recursos`.
- La tabla `Interacciones` se relaciona con `Conversaciones`, `Usuarios` y `TiposDeViolencias`.
- La tabla `Agendas` se relaciona con `Usuarios` y `Asesores`.
