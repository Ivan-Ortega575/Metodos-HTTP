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
<h3>El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.</h3>

<h2>4.-PATCH</h2>
<h3>El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.</h3>

<h2>5.-PUT</h2>
<h3>El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.</h3>

<h2>6.-DELETE</h2>
<h3>El método DELETE borra un recurso en específico.</h3>

<h2>7.-OPTIONS</h2>
<h3>El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.</h3>

<h2>8.-TRACE</h2>
<h3>El método TRACE  realiza una prueba de bucle de retorno de mensaje a lo largo de la ruta al recurso de destino.
</h3>
<h2>9.-CONNECT</h2>
<h3>El método CONNECT establece un túnel hacia el servidor identificado por el recurso.</h3>

