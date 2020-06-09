---
title: Transportes en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 077d63d8038b245a68083611897c1e6c68971071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598676"
---
# <a name="transports-in-windows-communication-foundation"></a>Transportes en Windows Communication Foundation
El nivel de transporte está en el nivel más bajo de la pila del canal. Los transportes principales utilizados en Windows Communication Foundation (WCF) son HTTP, HTTPS, TCP y canalizaciones con nombre. Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.  
  
 WCF incluye transportes adicionales. Para obtener información sobre el transporte de Message Queuing (también conocido como MSMQ), vea [colas y sesiones confiables](queues-and-reliable-sessions.md). Para obtener información sobre el transporte punto a punto, vea [redes punto a punto](peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Elección del transporte](choosing-a-transport.md)  
 Describe los tres transportes principales y las consideraciones para seleccionar uno.  
  
 [Elección de un codificador de mensajes](choosing-a-message-encoder.md)  
 Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.  
  
 [Transferencia de mensajes por secuencias](streaming-message-transfer.md)  
 Describe cómo configurar el nivel de transporte para la transmisión por secuencias.  
  
 [Configuración de HTTP y HTTPS](configuring-http-and-https.md)  
 Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.  
  
 [Procedimiento para reemplazar la reserva de direcciones URL de WCF por una reserva restringida](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Describe cómo usar las reservas restringidas de WCFURL.  
  
 [Cuotas de transporte](transport-quotas.md)  
 Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.  
  
 [Trabajar con NAT y firewalls](working-with-nats-and-firewalls.md)  
 Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red (NAT) está presente.  
  
 [Uso compartido de puertos Net.TCP](net-tcp-port-sharing.md)  
 Describe cómo usar el componente de uso compartido de puertos net. TCP de WCF.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Enlaces](bindings.md)  
  
 [Extensión de enlaces](../extending/extending-bindings.md)
