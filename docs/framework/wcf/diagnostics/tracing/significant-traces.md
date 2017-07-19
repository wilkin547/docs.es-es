---
title: "Seguimientos significativos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Seguimientos significativos
En este tema se enumeran algunos de los principales seguimientos emitidos por [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Seguimientos significativos  
  
|Seguimiento|Descripción|  
|-----------------|-----------------|  
|Seguimiento del registro de mensajes|Se emite el seguimiento cuando la característica de registro de mensajes registra un mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] cuando el origen de seguimiento de `System.ServiceModel.MessageLogging` está habilitado.Al hacer clic en este seguimiento, se muestra el mensaje.Hay cuatro puntos de registro configurables para un mensaje: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, también indicado por el atributo Message Source en el seguimiento del registro de mensajes.|  
|Seguimiento de mensajes recibidos|Se emite este seguimiento cuando se recibe un mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] si el origen de seguimiento de `System.ServiceModel` está habilitado a modo informativo o detallado.Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Seguimiento de mensajes enviados|Se emite este seguimiento cuando se envía un mensaje de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] si el origen de seguimiento de `System.ServiceModel` está habilitado a modo informativo o detallado.Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Obtener ChannelEndpointElement|Este seguimiento se emite en el generador de canales de construcción, a modo informativo.Proporciona una descripción del extremo \(dirección remota, enlazando, nombre del contrato\) con el que el cliente está hablando.|  
|Obtener ServiceElement|Este seguimiento se emite en el host de servicio de construcción, a modo informativo.Proporciona una descripción del enlace y contrato de servicios.|  
|Creación de SocketConnection|Este seguimiento se emite en la primera acción de proceso realizada por el cliente y en la actividad de bytes recibidos del servicio.Proporciona las direcciones IP locales y remotas.Se emite a modo informativo.|