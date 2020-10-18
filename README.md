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

<h2>3.-POST</h2>
<h3>El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
Aunque se puedan enviar datos a través del método GET, en muchos casos se utiliza POST por las limitaciones de GET. En caso de respuesta positiva devuelve 201 (created). Los POST requests se envían normalmente con formularios:</h3>


![POST](https://user-images.githubusercontent.com/72004435/96373759-329c2e80-1134-11eb-9ead-ef7a986783ce.PNG)


<h2>4.-PATCH</h2>
<h3>El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.</h3>

<h2>5.-PUT</h2>
<h3>El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
PUT. Utilizado normalmente para actualizar contenidos, pero también pueden crearlos. Tampoco muestra ninguna información en la URL. En caso de éxito devuelve 201 (created, en caso de que la acción haya creado un elemento) o 204 (no response, si el servidor no devuelve ningún contenido). A diferencia de POST es idempotente, si se crea o edita un resource con PUT y se hace el mismo request otra vez, el resource todavía está ahí y mantiene el mismo estado que en la primera llamada. Si con una llamada PUT se cambia aunque sea sólo un contador en el resource, la llamada ya no es idempotente, ya que se cambian contenidos.</h3>

PUT ejemplo.com/usuario/peter HTTP/1.1

<h2>6.-DELETE</h2>
<h3>El método DELETE borra un recurso en específico.
DELETE. Simplemente elimina un resource identificado en la URI. Si se elimina correctamente devuelve 200 junto con un body response, o 204 sin body. DELETE, al igual que PUT y GET, también es idempotente.</H3>
    
DELETE ejemplo.com/usuario/peter HTTP/1.1

<h2>7.-OPTIONS</h2>
<h3>El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.</h3>

<h2>8.-TRACE</h2>
<h3>El método TRACE  realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.
</h3>
<h2>9.-CONNECT</h2>
<h3>El método CONNECT establece un túnel hacia el servidor identificado por el recurso.</h3>

