---
title: "Comunicaciones básicas: Marco de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 878d2b01ee22d339115925e101f7349ecd5207bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-connection-framework"></a>Comunicaciones básicas: Marco de conexión
En este tema se enumeran todas las excepciones generadas por el marco de conexiones de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
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
