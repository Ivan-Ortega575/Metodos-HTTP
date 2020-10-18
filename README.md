<h1>Metodos-HTTP</h1>


<h2>1.-GET</h2>
<h3>El método GET  solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.</h3>

<h3>GET. El método GET se emplea para leer una representación de un resource. En caso de respuesta positiva (200 OK), GET devuelve la representación en un formato concreto: HTML, XML, JSON o imágenes, JavaScript, CSS, etc. En caso de respuesta negativa devuelve 404 (not found) o 400 (bad request). Por ejemplo en la carga de una página web, primero se carga la url solicitada:</h3>
GET php.net/docs HTTP/1.1
<h3>En este caso devolverá HTML. Y después los demás resources como CSS, JS, o imágenes:</h3>
GET php.net/images/logo.png HTTP/1.1


![headerGET](https://user-images.githubusercontent.com/72004435/96373647-93773700-1133-11eb-9bca-8fce03f229a2.PNG)

    

<h2>2.-HEAD</h2>
<h3>El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.</h3>

![HEAD](https://user-images.githubusercontent.com/72004435/96374026-d934ff00-1135-11eb-9468-f69dcf360278.PNG)


<h2>3.-POST</h2>
<h3>El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
Aunque se puedan enviar datos a través del método GET, en muchos casos se utiliza POST por las limitaciones de GET. En caso de respuesta positiva devuelve 201 (created). Los POST requests se envían normalmente con formularios:</h3>


![POST](https://user-images.githubusercontent.com/72004435/96373759-329c2e80-1134-11eb-9ead-ef7a986783ce.PNG)


<h2>4.-PATCH</h2>
<h3>El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.</h3>

![PATCH](https://user-images.githubusercontent.com/72004435/96374392-1b5f4000-1138-11eb-9be8-420120250627.PNG)


<h2>5.-PUT</h2>
<h3>El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
PUT. Utilizado normalmente para actualizar contenidos, pero también pueden crearlos. Tampoco muestra ninguna información en la URL. En caso de éxito devuelve 201 (created, en caso de que la acción haya creado un elemento) o 204 (no response, si el servidor no devuelve ningún contenido). A diferencia de POST es idempotente, si se crea o edita un resource con PUT y se hace el mismo request otra vez, el resource todavía está ahí y mantiene el mismo estado que en la primera llamada. Si con una llamada PUT se cambia aunque sea sólo un contador en el resource, la llamada ya no es idempotente, ya que se cambian contenidos.</h3>

PUT ejemplo.com/usuario/peter HTTP/1.1

![PUT](https://user-images.githubusercontent.com/72004435/96374146-8f004d80-1136-11eb-918e-5eb801187c24.PNG)


<h2>6.-DELETE</h2>
<h3>El método DELETE borra un recurso en específico.
DELETE. Simplemente elimina un resource identificado en la URI. Si se elimina correctamente devuelve 200 junto con un body response, o 204 sin body. DELETE, al igual que PUT y GET, también es idempotente.</H3>
    
DELETE ejemplo.com/usuario/peter HTTP/1.1

![DELATE](https://user-images.githubusercontent.com/72004435/96374198-cff86200-1136-11eb-94c1-ad2f875e7a8f.PNG)


<h2>7.-OPTIONS</h2>
<h3>El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.</h3>

![OPTIONS](https://user-images.githubusercontent.com/72004435/96374290-73e20d80-1137-11eb-9525-ce8d750e971d.PNG)


<h2>8.-TRACE</h2>
<h3>El método TRACE  realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.
</h3>

![TRACE](https://user-images.githubusercontent.com/72004435/96374257-3aa99d80-1137-11eb-913d-07c51f65a878.PNG)


<h2>9.-CONNECT</h2>
<h3>El método CONNECT establece un túnel hacia el servidor identificado por el recurso.</h3>

![CONNECT](https://user-images.githubusercontent.com/72004435/96374238-1221a380-1137-11eb-8b01-169d799e1aa7.PNG)


<h1> TIPOS DE MENSAJES DE LAS PETICIONES HTTPs</h1>

Los códigos de estado de respuesta HTTP indican si se ha completado satisfactoriamente una solicitud HTTP específica. 
Las respuestas se agrupan en cinco clases:

<h2>Respuestas informativas (100–199),</h2>
<h2>Respuestas satisfactorias (200–299),</h2>
<h2>Redirecciones (300–399),</h2>
<h2>Errores de los clientes (400–499),</h2>
<h2>y errores de los servidores (500–599).</h2>
Los códigos de estado se definen en la sección 10 de RFC 2616. 
Puedes obtener las especificaciones actualizadas en RFC 7231.

<h2>Respuestas informativas</h2>
<h3>100 Continue</h3>
Esta respuesta provisional indica que todo hasta ahora está bien y que el cliente debe continuar con la solicitud o ignorarla si ya está terminada.
<h3>101 Switching Protocol</h3>
Este código se envía en respuesta a un encabezado de solicitud Upgrade por el cliente e indica que el servidor acepta el cambio de protocolo propuesto por el agente de usuario.
<h3>102 Processing (WebDAV)</h3>
Este código indica que el servidor ha recibido la solicitud y aún se encuentra procesandola, por lo que no hay respuesta disponible.
<h3>103 Early Hints</h3>
Este código de estado está pensado principalmente para ser usado con el encabezado Link, permitiendo que el agente de usuario empiece a pre-cargar recursos mientras el servidor prepara una respuesta.
<h3>HTTP - Error 150 cannot view directory. (SCI7779)</h3>
El propietario del servidor web y el servlet debe tener el mismo ID de usuario.
Asegúrese de que el propietario del servlet tenga permiso de escritura en el directorio cehttp.

<h2>Respuestas satisfactorias</h2>

<h3>200 OK</h3>
La solicitud ha tenido éxito. El significado de un éxito varía dependiendo del método HTTP:
<h3>201 Created</h3>
La solicitud ha tenido éxito y se ha creado un nuevo recurso como resultado de ello. Ésta es típicamente la respuesta enviada después de una petición PUT.
<h3>202 Accepted</h3>
La solicitud se ha recibido, pero aún no se ha actuado. Es una petición "sin compromiso", lo que significa que no hay manera en HTTP que permite enviar una respuesta asíncrona que indique el resultado del procesamiento de la solicitud. Está pensado para los casos en que otro proceso o servidor maneja la solicitud, o para el procesamiento por lotes.
<h3>203 Non-Authoritative Information</h3>
La petición se ha completado con éxito, pero su contenido no se ha obtenido de la fuente originalmente solicitada, sino que se recoge de una copia local o de un tercero. Excepto esta condición, se debe preferir una respuesta de 200 OK en lugar de esta respuesta.
<h3>204 No Content</h3>
La petición se ha completado con éxito pero su respuesta no tiene ningún contenido, aunque los encabezados pueden ser útiles. El agente de usuario puede actualizar sus encabezados en caché para este recurso con los nuevos valores.
<h3>205 Reset Content</h3>
La petición se ha completado con éxito, pero su respuesta no tiene contenidos y además, el agente de usuario tiene que inicializar la página desde la que se realizó la petición, este código es útil por ejemplo para páginas con formularios cuyo contenido debe borrarse después de que el usuario lo envíe.

<h2>Redirecciones</h2>

<h3>300 Multiple Choice</h3>
Esta solicitud tiene más de una posible respuesta. User-Agent o el usuario debe escoger uno de ellos. No hay forma estandarizada de seleccionar una de las respuestas.
<h3>301 Moved Permanently</h3>
Este código de respuesta significa que la URI  del recurso solicitado ha sido cambiado. Probablemente una nueva URI sea devuelta en la respuesta.
<h3>302 Found</h3>
Este código de respuesta significa que el recurso de la URI solicitada ha sido cambiado temporalmente. Nuevos cambios en la URI serán agregados en el futuro. Por lo tanto, la misma URI debe ser usada por el cliente en futuras solicitudes.
<h3>303 See Other</h3>
El servidor envía esta respuesta para dirigir al cliente a un nuevo recurso solicitado a otra dirección usando una petición GET.
<h3>304 Not Modified</h3>
Esta es usada para propósitos de "caché". Le indica al cliente que la respuesta no ha sido modificada. Entonces, el cliente puede continuar usando la misma versión almacenada en su caché.
<h3>305 Use Proxy </h3>
Fue definida en una versión previa de la especificación del protocolo HTTP para indicar que una respuesta solicitada debe ser accedida desde un proxy. Ha quedado obsoleta debido a preocupaciones de seguridad correspondientes a la configuración de un proxy.

<h2>Errores de cliente</h2>

<h3>400 Bad Request</h3>
Esta respuesta significa que el servidor no pudo interpretar la solicitud dada una sintaxis inválida.
<h3>401 Unauthorized</h3>
Es necesario autenticar para obtener la respuesta solicitada. Esta es similar a 403, pero en este caso, la autenticación es posible.
<h3>402 Payment Required</h3>
Este código de respuesta está reservado para futuros usos. El objetivo inicial de crear este código fue para ser utilizado en sistemas digitales de pagos. Sin embargo, no está siendo usado actualmente.
<h3>403 Forbidden</h3>
El cliente no posee los permisos necesarios para cierto contenido, por lo que el servidor está rechazando otorgar una respuesta apropiada.
<h3>404 Not Found</h3>
El servidor no pudo encontrar el contenido solicitado. Este código de respuesta es uno de los más famosos dada su alta ocurrencia en la web.
<h3>405 Method Not Allowed</h3>
El método solicitado es conocido por el servidor pero ha sido deshabilitado y no puede ser utilizado. Los dos métodos obligatorios, GET y HEAD, nunca deben ser deshabilitados y no deberían retornar este código de error.

<h2>Errores de servidor</h2>

<h3>500 Internal Server Error</h3>
El servidor ha encontrado una situación que no sabe cómo manejarla.
<h3>501 Not Implemented</h3>
El método solicitado no está soportado por el servidor y no puede ser manejado. Los únicos métodos que los servidores requieren soporte (y por lo tanto no deben retornar este código) son GET y HEAD.
<h3>502 Bad Gateway</h3>
Esta respuesta de error significa que el servidor, mientras trabaja como una puerta de enlace para obtener una respuesta necesaria para manejar la petición, obtuvo una respuesta inválida.
<h3>503 Service Unavailable</h3>
El servidor no está listo para manejar la petición. Causas comunes puede ser que el servidor está caído por mantenimiento o está sobrecargado. Hay que tomar en cuenta que junto con esta respuesta, una página usuario-amigable explicando el problema debe ser enviada. Estas respuestas deben ser usadas para condiciones temporales y el encabezado HTTP Retry-After: debería, si es posible, contener el tiempo estimado antes de la recuperación del servicio. El webmaster debe también cuidar los encabezados relacionados al caché que son enviados junto a esta respuesta, ya que estas respuestas de condición temporal deben usualmente no estar en el caché.
<h3>504 Gateway Timeout</h3>
Esta respuesta de error es dada cuando el servidor está actuando como una puerta de enlace y no puede obtener una respuesta a tiempo.
<h3>505 HTTP Version Not Supported</h3>
La versión de HTTP usada en la petición no está soportada por el servidor.
<h3>506 Variant Also Negotiates</h3>
El servidor tiene un error de configuración interna: negociación de contenido transparente para la petición resulta en una referencia circular.
