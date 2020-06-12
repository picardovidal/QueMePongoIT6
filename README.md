# QueMePongoIT6
iteracion 6 de que me pongo

A la clase generador de sugerencias que teniamos de entregas anteriores, le agregamos el metodo GenerarSugerenciasDiaria, que recibira un listado de usuarios, y por cada uno calculara las sugerencias para ese dia.
La clase generador de alertas tendra una referencia a la interface servicio de clima, que creamos anteriormente, agregue un metodo para recibir la implementacion de esa interface como inyeccion de dependencia. También esta clase tendra un listado de alertaObserver y metodos para agregar y quitar alertaObserver. Y un metodo generar alertas que utilizara el servicio de clima inyectado para obtener las alertas y luego recorrera el listado de alertaObserver llamando al metodo AlertaRecibida

pense en una interface alertaObserver, que sera implentada por diferentes clases dependiendo de lo que querramos alertar. Así existirá un AlertaTormentaObserver que cuando se llame al metodo AlertaRecibida, en caso de que la alerta sea efectivamente de tormenta, utilizara la Api del sistema NotificationService, para informar la alerta.
Del mismo modo la clase AlertaMailObserver, cuando se llame al AlertaRecibida, se encargara de enviarla por mail usando la API de mailSender.
La clase ActualizarSugerenciaObserver también implementara la interface AlertaObserver y cuando se llame al AlertaRecibida de esta clase se encargara de llamar al generador de sugerencias para actualizar las sugerencias del dia de cada usuario.