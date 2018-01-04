---
title: "Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76c4c225b333af6d376fa409a05ea5727ede6e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Escenarios asincrónicos en los que se usa HTTP, TCP o canalizaciones con nombre
En este tema se describen las actividades y transferencias para diferentes escenarios asincrónicos de solicitud-respuesta, con solicitudes de varios subprocesos, utilizando HTTP, TCP o canalización con nombre.  
  
## <a name="asynchronous-requestreply-without-errors"></a>Solicitud-respuesta asincrónica sin errores  
 En esta sección se describen las actividades y transferencias para un escenario asincrónico de solicitud-respuesta válido, con clientes de varios subprocesos.  
  
 La actividad de llamador finaliza cuando `beginCall` vuelve, y `endCall` vuelve. Si se llama a una devolución de llamada, la devolución de llamada vuelve.  
  
 La actividad llamada finaliza cuando `beginCall` vuelve, `endCall` vuelve o cuando la devolución de llamada vuelve si fue llamada desde esa actividad.  
  
### <a name="asynchronous-client-without-callback"></a>Cliente asincrónico sin devolución de llamada  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>La propagación está habilitada en ambos lados, utilizando HTTP  
 ![Escenarios asincrónicos](../../../../../docs/framework/wcf/diagnostics/tracing/media/asyn1.gif "Asyn1")  
  
 Figura 1. Cliente asincrónico, sin devolución de llamada, `propagateActivity` = `true` en ambos lados, HTTP  
  
 Si `propagateActivity` = `true`, ProcessMessage indica a qué actividad processaction debe transferirse a.  
  
 Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>La propagación está deshabilitada en cualquier lado, utilizando HTTP  
 Si `propagateActivity` = `false` en cualquier lado, ProcessMessage no indica a qué actividad processaction debe transferirse a. Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id. Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local. La actividad ProcessAction actual se puede transferir a con ese id.  
  
 ![Escenarios asincrónicos mediante HTTP &#47; TCP &#47; Canalización con nombre](../../../../../docs/framework/wcf/diagnostics/tracing/media/async2.gif "Async2")  
  
 Figura 2. Cliente asincrónico, sin devolución de llamada, `propagateActivity` = `false` a ambos lados, HTTP  
  
 Para los escenarios basados en HTTP, ReceiveBytes se invoca en el primer mensaje para enviar y existe para la duración de la solicitud.  
  
 Se crea una actividad procesar acción en un cliente asincrónico cuando `propagateActivity` = `false` en el llamador o destinatario, y cuando el mensaje de respuesta no incluye un encabezado de acción.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>La propagación está habilitada en ambos lados, utilizando TCP o canalización con nombre  
 ![Escenarios asincrónicos mediante HTTP &#47; TCP &#47; Canalización con nombre](../../../../../docs/framework/wcf/diagnostics/tracing/media/async3.gif "Async3")  
  
 Figura 3: Cliente asincrónico, sin devolución de llamada, `propagateActivity` = `true` en ambos lados, canalización con nombre/TCP  
  
 Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.  
  
 Similar a la figura 1, si `propagateActivity` = `true`, ProcessMessage indica a qué actividad processaction debe transferirse a.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>La propagación está deshabilitada en cualquier lado, utilizando TCP o canalización con nombre  
 Para una canalización con nombre o escenario basado en TCP, ReceiveBytes se invoca cuando se abre el cliente, y existe para la duración de la conexión.  
  
 Similar a Fig.2, si `propagateActivity` = `false` en cualquier lado, ProcessMessage no indica a qué actividad processaction debe transferirse a. Por consiguiente, se invoca una nueva actividad ProcessAction temporal con un nuevo id. Cuando la respuesta asincrónica coincide con la solicitud en el código ServiceModel, el id. de actividad se puede recuperar del contexto local. La actividad ProcessAction actual se puede transferir a con ese id.  
  
 ![Escenarios asincrónicos mediante HTTP &#47; TCP &#47; Canalizaciones con nombre](../../../../../docs/framework/wcf/diagnostics/tracing/media/async4.gif "Async4")  
  
 Figura 4. Cliente asincrónico, sin devolución de llamada, `propagateActivity` = `false` a ambos lados, canalización con nombre/TCP  
  
### <a name="asynchronous-client-with-callback"></a>Cliente asincrónico con devolución de llamada  
 Este escenario agrega las actividades G y A', para la devolución de llamada y `endCall`y sus transferencias dentro/fuera.  
  
 Esta sección solo se muestra el uso de HTTP con `propragateActivity` = `true`. Sin embargo, las actividades adicionales y transferencias también se aplican a los otros casos (es decir, `propagateActivity` = `false`, utilizando TCP o canalizaciones con nombre).  
  
 La devolución de llamada crea una nueva actividad (G) cuando el cliente llama al código de usuario para notificar que los resultados están listos. A continuación, el código de usuario llama a `endCall` dentro de la devolución de llamada (como se muestra en la figura 5) o fuera de la devolución de llamada (figura 6). Dado que no se sabe qué actividad de usuario `endCall` se llama desde, esta actividad con la etiqueta `A’`. Es posible que A' puede ser idéntico o diferente de A.  
  
 ![Escenarios asincrónicos](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback1.gif "AsyncCallback1")  
  
 Figura 5. Cliente asincrónico con devolución de llamada, `endCall` en la devolución de llamada  
  
 ![Escenarios asincrónicos](../../../../../docs/framework/wcf/diagnostics/tracing/media/asynccallback2.gif "AsyncCallback2")  
  
 Figura 6. Cliente asincrónico con devolución de llamada, `endCall` fuera de la devolución de llamada  
  
### <a name="asynchronous-server-with-callback"></a>Servidor asincrónico con devolución de llamada  
 ![Escenarios asincrónicos mediante HTTP &#47; TCP &#47; Con el nombre &#45; Canalización](../../../../../docs/framework/wcf/diagnostics/tracing/media/aynchserver.gif "AynchServer")  
  
 Figura 7. Servidor asincrónico con devolución de llamada  
  
 La pila del canal llama al cliente al recibir el mensaje: las trazas para este procesamiento se emiten en la propia actividad ProcessRequest.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Solicitud-respuesta asincrónica con errores  
 Los errores del mensaje de error se reciben durante `endCall`. De lo contrario, las actividades y transferencias son similares a los escenarios anteriores.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Unidireccional asincrónico con o sin errores  
 No se devuelve ninguna respuesta o error al cliente.
