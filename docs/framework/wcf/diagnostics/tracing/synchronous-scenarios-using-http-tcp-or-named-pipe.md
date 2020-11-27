---
title: Escenarios sincrónicos en los que se utiliza HTTP, TCP o canalizaciones con nombre
ms.date: 03/30/2017
ms.assetid: 7e90af1b-f8f6-41b9-a63a-8490ada502b1
ms.openlocfilehash: 906bceadf56d82570b41cfbb2c96e4b89d595d02
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274444"
---
# <a name="synchronous-scenarios-using-http-tcp-or-named-pipe"></a>Escenarios sincrónicos en los que se utiliza HTTP, TCP o canalizaciones con nombre

En este tema se describen las actividades y transferencias para diferentes escenarios sincrónicos de solicitud/respuesta, con un cliente de un único subproceso, utilizando HTTP, TCP o canalización con nombre. Vea [escenarios asincrónicos mediante http, TCP o canalizaciones con nombre](asynchronous-scenarios-using-http-tcp-or-named-pipe.md) para obtener más información sobre las solicitudes multiproceso.  
  
## <a name="synchronous-requestreply-without-errors"></a>Solicitud/respuesta sincrónica sin errores  

 En esta sección se describen las actividades y transferencias para un escenario válido sincrónico de solicitud/respuesta, con cliente de un único subproceso.  
  
### <a name="client"></a>Cliente  
  
#### <a name="establishing-communication-with-service-endpoint"></a>Establecer la comunicación con el punto de conexión de servicio  

 Un cliente se construye y se abre. Para cada uno de estos pasos, la actividad ambiente (A) se transfiere a una actividad "construir cliente" (B) y "abrir cliente" (C), respectivamente. Por cada actividad a la que se transfiere, la actividad ambiente se suspende hasta que se devuelve una transferencia, es decir, hasta que se ejecuta el código de ServiceModel.  
  
#### <a name="making-a-request-to-service-endpoint"></a>Realizar una solicitud al extremo de servicio  

 La actividad ambiente se transfiere a una actividad "ProcessAction" (D). Dentro de esta actividad, se envía un mensaje de solicitud y se recibe un mensaje de respuesta. La actividad finaliza cuando el control vuelve al código de usuario. Dado que se trata de una solicitud sincrónica, la actividad ambiente se suspende hasta que el control vuelve.  
  
#### <a name="closing-communication-with-service-endpoint"></a>Cerrar la comunicación con el punto de conexión de servicio  

 La actividad de cierre (I) del cliente se crea a partir de la actividad ambiente. Esto es idéntico a nuevo y abrir.  
  
### <a name="server"></a>Server  
  
#### <a name="setting-up-a-service-host"></a>Configurar un host de servicio  

 Las actividades nuevas y de abrir (N y O) del ServiceHost se crean a partir de la actividad ambiente (M).  
  
 Una actividad de escucha (P) se crea abriendo un ServiceHost para cada escucha. La actividad de la escucha espera a recibir y procesar los datos.  
  
#### <a name="receiving-data-on-the-wire"></a>Recibir los datos en la conexión  

 Cuando los datos llegan en la conexión, se crea una actividad "ReceiveBytes" Si aún no existe (Q) para procesar los datos recibidos. Esta actividad se puede reutilizar para varios mensajes dentro de una conexión o cola.  
  
 La actividad ReceiveBytes inicia una actividad ProcessMessage (R) si tiene bastantes datos para formar un mensaje de acción SOAP.  
  
 En actividad R, se procesan los encabezados del mensaje y se comprueba el encabezado de activityID. Si este encabezado está presente, el id. de actividad se establece en la actividad ProcessAction; de lo contrario, se crea un nuevo id.  
  
 Se crea la actividad ProcessAction (S) y se transfiere cuando se procesa la llamada. Esta actividad finaliza cuando todo el procesamiento relacionado con el mensaje entrante se completa, incluidos la ejecución del código de usuario (T) y el envío del mensaje de respuesta si es aplicable.  
  
#### <a name="closing-a-service-host"></a>Cerrar un host de servicio  

 La actividad de cierre del ServiceHost (Z) se crea a partir de la actividad ambiente.  
  
 ![Diagrama que muestra escenarios sincrónicos: HTTP, TCP o canalizaciones con nombre.](./media/synchronous-scenarios-using-http-tcp-or-named-pipe/synchronous-scenario-http-tcp-named-pipes.gif)  
  
 En \<A: name> , `A` es un símbolo de acceso directo que describe la actividad en el texto anterior y en la tabla 3. `Name` es un nombre abreviado de la actividad.  
  
 Si es `propagateActivity` = `true` , la acción procesar en el cliente y el servicio tienen el mismo identificador de actividad.  
  
## <a name="synchronous-requestreply-with-errors"></a>Solicitud/respuesta sincrónica con Errores  

 La única diferencia con el escenario anterior es que un mensaje de error SOAP se devuelve como un mensaje de respuesta. Si `propagateActivity` = `true` es, se agrega el ID. de actividad del mensaje de solicitud al mensaje de error de SOAP.  
  
## <a name="synchronous-one-way-without-errors"></a>Unidireccional sincrónico sin errores  

 La única diferencia con el primer escenario es que ningún mensaje se devuelve al servidor. Para los protocolos basados en HTTP, un estado (valid o error) se devuelve todavía al cliente. Esto se debe a que HTTP es el único protocolo con una semántica de solicitud-respuesta que forma parte de la pila del protocolo WCF. Dado que el procesamiento de TCP está oculto en WCF, no se envía ninguna confirmación al cliente.  
  
## <a name="synchronous-one-way-with-errors"></a>Unidireccional sincrónico con errores  

 Si un error se produce procesando el mensaje (Q o más allá), ninguna notificación se devuelve al cliente. Esto es idéntico al escenario "Unidireccional sincrónico sin errores". No debería utilizar un escenario unidireccional si desea recibir un mensaje de error.  
  
## <a name="duplex"></a>Dúplex  

 La diferencia con los escenarios anteriores es que el cliente actúa como un servicio, en el que crea las actividades ReceiveBytes y ProcessMessage, similares a los escenarios asincrónicos.
