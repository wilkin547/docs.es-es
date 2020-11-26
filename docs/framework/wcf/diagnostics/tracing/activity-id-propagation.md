---
title: Propagación de ID de actividad
ms.date: 03/30/2017
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
ms.openlocfilehash: 0f0478b16bf2ca0975ae0290a8855756ecfc383e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236109"
---
# <a name="activity-id-propagation"></a>Propagación de ID de actividad

La propagación se produce cuando el seguimiento de la actividad ServiceModel está habilitada (propagación de ServiceModel) o deshabilitada (propagación de actividad entre usuarios).  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a>Seguimiento de actividad ServiceModel está habilitado  

 Si ServiceModel ActivityTracing está habilitado, se produce la propagación entre las actividades ProcessAction.  
  
### <a name="server"></a>Server  

 Cuando el `propagateActivity` atributo se establece en `true` tanto en el cliente como en el servidor, el identificador de la `ProcessAction` actividad en el servidor es idéntico al identificador del encabezado del mensaje propagado `ActivityId` .  
  
 Cuando no hay ningún `ActivityId` encabezado en el mensaje (es decir, `propagateActivity` = `false` en el cliente) o cuando se encuentra `propagateActivity` = `false` en el servidor, el servidor genera un nuevo ID. de actividad.  
  
### <a name="client"></a>Cliente  

 Si el cliente es un subproceso único de forma sincrónica, el cliente no tiene en cuenta los valores de `propagateActivity` del cliente o servidor. En su lugar, la respuesta se administra en la actividad de solicitud. Si el cliente es un multiproceso asincrónico o sincrónico, `propagateActivity` = `true` en el cliente, y hay un encabezado de ID. de actividad en el mensaje enviado por el servidor, el cliente recupera el ID. de actividad del mensaje y transfiere a la actividad procesar acción que contiene el identificador de actividad propagado. De lo contrario, el cliente se transfiere de la actividad de procesamiento de mensajes a una nueva actividad de acción de procesos. Se realiza esta transferencia adicional a una nueva actividad de procesamiento de acción por coherencia. Dentro de esta actividad, el cliente recupera el id. de actividad de la actividad BeginCall del contexto del subproceso local, cuando se asigna el subproceso para procesamiento del mensaje de respuesta. Se transfiere, a continuación, a la actividad inicial de procesamiento de acción.  
  
 Si el cliente es dúplex, el cliente actúa como servidor al recibir el mensaje.  
  
### <a name="propagation-in-fault-messages"></a>Propagación en mensajes de error  

 No hay ninguna diferencia a la hora de administrar mensajes válidos y mensajes de error. Si `propagateActivity` = `true` es, el ID. de actividad agregado a los encabezados de mensaje de error de SOAP es idéntico a la actividad de ambiente.  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a>El seguimiento de actividad ServiceModel está deshabilitad  

 Si ServiceModel ActivityTracing está deshabilitado, la propagación se produce directamente entre las actividades de código de usuario sin pasar por las actividades ServiceModel. Un id. de actividad definido por el usuario también se propaga a través del encabezado de id. de actividad de mensaje.   
  
 Si `propagateActivity` = `true` y `ActivityTracing` = `off` para un agente de escucha de seguimiento de ServiceModel (independientemente de si el seguimiento está habilitado en ServiceModel), ocurre lo siguiente en el cliente o el servidor:  
  
- En la solicitud de operación o respuesta de envío, el id. de actividad en TLS se propaga fuera del código de usuario hasta que se forma un mensaje. También se inserta en el mensaje un encabezado de id. de actividad antes de enviarse.  
  
- Al recibir la solicitud o recibir la respuesta, el id. de actividad se recupera del encabezado del mensaje en cuanto se cree el objeto de mensaje recibido. Se propaga el id. de actividad en TLS en cuanto el mensaje desaparece del ámbito hasta que se alcance el código de usuario.  
  
 Estas acciones garantizan que los seguimientos del usuario aparecerán en la misma actividad si la propagación está activada. Sin embargo, no hay garantía en seguimientos de ServiceModel. Los seguimientos de ServiceModel se producen en una actividad de código de usuario si se ejecuta el procesamiento de esos seguimientos en el mismo subproceso donde se estableció la actividad de código de usuario.  
  
 En general, los seguimientos de ServiceModel se puede observar en los lugares siguientes:  
  
- Si el seguimiento de ServiceModel está deshabilitado, todos los seguimientos emitidos aparecen en actividades de usuario. Si la propagación está habilitada en el servidor y cliente, estos seguimientos estarán en la misma actividad.  
  
- Si el seguimiento de ServiceModel está habilitado, pero ActivityTracing está deshabilitado, los seguimientos del usuario aparecen en la misma actividad si la propagación está habilitada en ambos. Los seguimientos de ServiceModel aparecen en la actividad predeterminada 0000, a menos que se produzcan en el mismo subproceso que el procesamiento de código de usuario donde se establece la actividad inicialmente.  
  
- Si están habilitados ambos seguimientos de ServiceModel y ActivityTracing, los seguimientos del usuario aparecen en actividades definidas por el usuario y los seguimientos de ServiceModel aparecen en actividades definidas por ServiceModel. La propagación se produce en el nivel de ServiceModel.
