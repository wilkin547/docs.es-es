---
title: Seguimientos significativos
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: c230c65b4d3fd45c4905d4ae5f4cbbf90e10faad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784968"
---
# <a name="significant-traces"></a>Seguimientos significativos
En este tema se enumera algunos de los principales seguimientos emitidos por Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Seguimientos significativos  
  
|Seguimiento|Descripción|  
|-----------|-----------------|  
|Seguimiento del registro de mensajes|El seguimiento se genera cuando se registra un mensaje de WCF mediante el registro de mensajes característica cuando el `System.ServiceModel.MessageLogging` origen de seguimiento está habilitado. Al hacer clic en este seguimiento, se muestra el mensaje. Hay cuatro puntos de registro configurables para un mensaje: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, también indicado por el atributo Message Source en el seguimiento del registro de mensajes.|  
|Seguimiento de mensajes recibidos|Este seguimiento se emite cuando se recibe un mensaje de WCF si la `System.ServiceModel` origen de seguimiento está habilitado en informativo o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Seguimiento de mensajes enviados|Este seguimiento se emite cuando se envía un mensaje WCF si la `System.ServiceModel` origen de seguimiento está habilitado en informativo o detallado. Este seguimiento es necesario para ver la flecha de correlación de mensajes en la vista gráfica de actividad.|  
|Obtener ChannelEndpointElement|Este seguimiento se emite en el generador de canales de construcción, a modo informativo. Proporciona una descripción del extremo (dirección remota, enlazando, nombre del contrato) con el que el cliente está hablando.|  
|Obtener ServiceElement|Este seguimiento se emite en el host de servicio de construcción, a modo informativo. Proporciona una descripción del enlace y contrato de servicios.|  
|Creación de SocketConnection|Este seguimiento se emite en la primera acción de proceso realizada por el cliente y en la actividad de bytes recibidos del servicio. Proporciona las direcciones IP locales y remotas. Se emite a modo informativo.|
