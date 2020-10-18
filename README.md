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

*Respuestas informativas (100–199),
*Respuestas satisfactorias (200–299),
*Redirecciones (300–399),
*Errores de los clientes (400–499),
*y errores de los servidores (500–599).
Los códigos de estado se definen en la sección 10 de RFC 2616. 
Puedes obtener las especificaciones actualizadas en RFC 7231.

<h2>Respuestas informativas</h2>
100 Continue
<h3>Esta respuesta provisional indica que todo hasta ahora está bien y que el cliente debe continuar con la solicitud o ignorarla si ya está terminada.
101 Switching Protocol</h3>
<h3>Este código se envía en respuesta a un encabezado de solicitud Upgrade por el cliente e indica que el servidor acepta el cambio de protocolo propuesto por el agente de usuario.</h3>
102 Processing (WebDAV)
<h3>Este código indica que el servidor ha recibido la solicitud y aún se encuentra procesandola, por lo que no hay respuesta disponible.</h3>
103 Early Hints
<h3>Este código de estado está pensado principalmente para ser usado con el encabezado Link, permitiendo que el agente de usuario empiece a pre-cargar recursos mientras el servidor prepara una respuesta.</h3>
