---
description: 'Más información sobre: escenarios asincrónicos con HTTP, TCP o Named-Pipe'
title: Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 5e01866cd20d63796741a097a6d7d774ea45d3d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99770955"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre

En este tema se describen las actividades y transferencias para diferentes escenarios asincrónicos de solicitud-respuesta, con solicitudes de varios subprocesos, utilizando HTTP, TCP o canalización con nombre.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Solicitud-respuesta asincrónica sin errores  

 En esta sección se describen las actividades y transferencias para un escenario asincrónico de solicitud-respuesta válido, con clientes de varios subprocesos.  
  
 La actividad de llamador finaliza cuando `beginCall` vuelve, y `endCall` vuelve. Si se llama a una devolución de llamada, la devolución de llamada vuelve.  
  
 La actividad llamada finaliza cuando `beginCall` vuelve, `endCall` vuelve o cuando la devolución de llamada vuelve si fue llamada desde esa actividad.  
  
### <a name="asynchronous-client-without-callback"></a>Cliente asincrónico sin devolución de llamada  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>La propagación está habilitada en ambos lados, utilizando HTTP  

 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en true en ambos lados.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)
  
 Si `propagateActivity=true` , ProcessMessage indica a qué actividad de ProcessAction se va a transferir.  
  
 Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>La propagación está deshabilitada en cualquier lado, utilizando HTTP  

 Si `propagateActivity=false` en cualquier lado, ProcessMessage no indica a qué actividad de ProcessAction se va a transferir. Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id. Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local. La actividad ProcessAction actual se puede transferir a con ese id.  
  
 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en false en cualquier lado.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  

 Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.  
  
 Una actividad procesar acción se crea en un cliente asincrónico en `propagateActivity=false` el llamador o destinatario y cuando el mensaje de respuesta no incluye un encabezado de acción.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>La propagación está habilitada en ambos lados, utilizando TCP o canalización con nombre  

 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en true en ambos lados y con nombre Pipe/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.  
  
 Similar a la primera imagen, si `propagateActivity=true` , ProcessMessage indica a qué actividad de ProcessAction se va a transferir.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>La propagación está deshabilitada en cualquier lado, utilizando TCP o canalización con nombre  

 Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.  
  
 De forma similar a la segunda imagen, si se `propagateActivity=false` encuentra en cualquier lado, ProcessMessage no indica a qué actividad de ProcessAction se va a transferir. Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id. Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local. La actividad ProcessAction actual se puede transferir a con ese id.  
  
 ![Cliente asincrónico sin devolución de llamada en la que propagateActivity está establecido en false en cualquier lado y canalización con nombre/TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  

### <a name="asynchronous-client-with-callback"></a>Cliente asincrónico con devolución de llamada  

 Este escenario agrega las actividades G y A', para la devolución de llamada y `endCall`y sus transferencias dentro/fuera.  
  
 En esta sección solo se muestra el uso de HTTP con `propagateActivity` = `true` . Sin embargo, las actividades y transferencias adicionales también se aplican a los otros casos (es decir, `propagateActivity` = `false` mediante TCP o canalizaciones con nombre).  
  
 La devolución de llamada crea una nueva actividad (G) cuando el cliente llama al código de usuario para notificar que los resultados están listos. A continuación, el código de usuario llama a `endCall` dentro de la devolución de llamada (como se muestra en la figura 5) o fuera de la devolución de llamada (figura 6). Dado que no se sabe a qué actividad `endCall` de usuario se está llamando, esta actividad se etiqueta `A’` . Es posible que A' puede ser idéntico o diferente de A.  
  
 ![Muestra un cliente asincrónico con devolución de llamada, endcall en devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  

 ![Muestra un cliente asincrónico con devolución de llamada, endcall fuera de la devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  

### <a name="asynchronous-server-with-callback"></a>Servidor asincrónico con devolución de llamada  

 ![Muestra un servidor asincrónico con devolución de llamada.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  

 La pila del canal llama al cliente al recibir el mensaje: las trazas para este procesamiento se emiten en la propia actividad ProcessRequest.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Solicitud-respuesta asincrónica con errores  

 Los errores del mensaje de error se reciben durante `endCall`. De lo contrario, las actividades y transferencias son similares a los escenarios anteriores.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Unidireccional asincrónico con o sin errores  

 No se devuelve ninguna respuesta o error al cliente.
