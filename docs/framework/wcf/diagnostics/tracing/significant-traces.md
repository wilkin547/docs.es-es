---
description: 'Más información acerca de: seguimientos significativos'
title: Seguimientos significativos
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 6d3e12c82312c2a8a3f0a19b4dc50e99e21b9730
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99635550"
---
# <a name="significant-traces"></a>Seguimientos significativos

En este tema se enumeran algunos de los seguimientos principales emitidos por Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Seguimientos significativos  
  
|Seguimiento|Descripción|  
|-----------|-----------------|  
|Seguimiento del registro de mensajes|El seguimiento se emite cuando la característica de registro de mensajes registra un mensaje WCF cuando el `System.ServiceModel.MessageLogging` origen de seguimiento está habilitado. Al hacer clic en este seguimiento, se muestra el mensaje. Hay cuatro puntos de registro configurables para un mensaje: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, también indicado por el atributo Message Source en el seguimiento del registro de mensajes.|  
|Seguimiento de mensajes recibidos|Este seguimiento se emite cuando se recibe un mensaje WCF si el `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Seguimiento de mensajes enviados|Este seguimiento se emite cuando se envía un mensaje WCF si el `System.ServiceModel` origen de seguimiento está habilitado en el nivel de información o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Obtener ChannelEndpointElement|Este seguimiento se emite en el generador de canales de construcción, a modo informativo. Proporciona una descripción del extremo (dirección remota, enlazando, nombre del contrato) con el que el cliente está hablando.|  
|Obtener ServiceElement|Este seguimiento se emite en el host de servicio de construcción, a modo informativo. Proporciona una descripción del enlace y contrato de servicios.|  
|Creación de SocketConnection|Este seguimiento se emite en la primera acción de proceso realizada por el cliente y en la actividad de bytes recibidos del servicio. Proporciona las direcciones IP locales y remotas. Se emite a modo informativo.|
