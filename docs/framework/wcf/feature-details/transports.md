---
title: Transportes en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933736"
---
# <a name="transports-in-windows-communication-foundation"></a>Transportes en Windows Communication Foundation
El nivel de transporte está en el nivel más bajo de la pila del canal. Los transportes principales utilizados en Windows Communication Foundation (WCF) son HTTP, HTTPS, TCP y canalizaciones con nombre. Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.  
  
 WCF incluye transportes adicionales. Para obtener información sobre el transporte de Message Queuing (también conocido como MSMQ), consulte [colas y sesiones confiables](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Para obtener información sobre el transporte de punto a punto, vea [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Elección del transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Describe los tres transportes principales y las consideraciones para seleccionar uno.  
  
 [Elección de un codificador de mensajes](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.  
  
 [Transferencia de mensajes por streaming](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Describe cómo configurar el nivel de transporte para la transmisión por secuencias.  
  
 [Configuración de HTTP y HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.  
  
 [Cómo: Reemplazar la reserva de direcciones URL de WCF con una reserva restringida](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Describe cómo usar las reservas WCFURL restringido.  
  
 [Cuotas de transporte](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.  
  
 [Trabajo con NAT y firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red (NAT) está presente.  
  
 [Uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Describe cómo usar el componente de uso compartido de puertos Net.TCP de WCF.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)
