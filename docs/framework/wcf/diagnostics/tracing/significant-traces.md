---
title: Seguimientos significativos
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 2dc5010874285ba14dae625fcbf92740eb1707b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="significant-traces"></a>Seguimientos significativos
Este tema enumeran algunos de los principales seguimientos emitidos por Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Seguimientos significativos  
  
|Seguimiento|Descripción|  
|-----------|-----------------|  
|Seguimiento del registro de mensajes|Se emite el seguimiento cuando la característica de registro de mensajes registra un mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] cuando el origen de seguimiento de `System.ServiceModel.MessageLogging` está habilitado. Al hacer clic en este seguimiento, se muestra el mensaje. Hay cuatro puntos de registro configurables para un mensaje: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, también indicado por el atributo Message Source en el seguimiento del registro de mensajes.|  
|Seguimiento de mensajes recibidos|Este seguimiento se emite cuando se recibe un mensaje [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] si el origen de seguimiento de `System.ServiceModel` está habilitado de modo informativo o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Seguimiento de mensajes enviados|Este seguimiento se emite cuando se envía un mensaje de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] si el origen de seguimiento de `System.ServiceModel` está habilitado a modo informativo o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Obtener ChannelEndpointElement|Este seguimiento se emite en el generador de canales de construcción, a modo informativo. Proporciona una descripción del extremo (dirección remota, enlazando, nombre del contrato) con el que el cliente está hablando.|  
|Obtener ServiceElement|Este seguimiento se emite en el host de servicio de construcción, a modo informativo. Proporciona una descripción del enlace y contrato de servicios.|  
|Creación de SocketConnection|Este seguimiento se emite en la primera acción de proceso realizada por el cliente y en la actividad de bytes recibidos del servicio. Proporciona las direcciones IP locales y remotas. Se emite a modo informativo.|
