---
title: "Comunicaciones b&#225;sicas: Marco de conexi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Comunicaciones b&#225;sicas: Marco de conexi&#243;n
En este tema se enumeran todas las excepciones generadas por el marco de conexiones de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-----------------------|-----------------------|  
|CloseTimedOut|El método Close superó el tiempo de espera especificado.Aumente el valor del tiempo de espera que se pasa a la llamada a Close o aumente el valor CloseTimeout en el enlace.El tiempo asignado a esta operación puede ser parte de un tiempo de espera más largo.|  
|ContentTypeMismatch|El tipo de contenido especificado se envió a un servicio que esperaba lo especificado.Los enlaces de servicio y cliente puede que no coincidan.|  
|DuplexChannelAbortedDuringOpen|El canal dúplex especificado se terminó durante el proceso Open.|  
|FramingValueNotAvailable|No se puede tener acceso al valor porque no está totalmente descodificado.|  
|OperationAbortedDuringConnectionEstablishment|Se finalizó la operación mientras se establecía una conexión a lo especificado.|  
|ReceiveTimedOut2|La operación de recepción ha agotado su tiempo de espera después de la hora especificada.El tiempo asignado a esta operación puede ser parte de un tiempo de espera más largo.|  
|SendCannotBeCalledAfterCloseOutputSession|No puede enviar los mensajes en un canal después de que se haya llamado a CloseOutputSession.|