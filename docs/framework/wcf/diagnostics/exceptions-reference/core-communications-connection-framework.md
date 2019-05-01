---
title: 'Comunicaciones básicas: marco de conexión'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: a3f52ac82c2bf09ded504e412d7f216dd0b39959
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998691"
---
# <a name="core-communications-connection-framework"></a>Comunicaciones básicas: marco de conexión
En este tema se enumera todas las excepciones generadas por el marco de conexión de Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|CloseTimedOut|El método Close superó el tiempo de espera especificado. Aumente el valor del tiempo de espera que se pasa a la llamada a Close o aumente el valor CloseTimeout en el enlace. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.|  
|ContentTypeMismatch|El tipo de contenido especificado se envió a un servicio que esperaba lo especificado. Los enlaces de servicio y cliente puede que no coincidan.|  
|DuplexChannelAbortedDuringOpen|El canal dúplex especificado se terminó durante el proceso Open.|  
|FramingValueNotAvailable|No se puede tener acceso al valor porque no está totalmente descodificado.|  
|OperationAbortedDuringConnectionEstablishment|Se finalizó la operación mientras se establecía una conexión a lo especificado.|  
|ReceiveTimedOut2|La operación de recepción ha agotado su tiempo de espera después de la hora especificada. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.|  
|SendCannotBeCalledAfterCloseOutputSession|No puede enviar los mensajes en un canal después de que se haya llamado a CloseOutputSession.|
