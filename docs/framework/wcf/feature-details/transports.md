---
title: "Transportes en Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "transportes [WCF]"
  - "WCF, transportes"
  - "Windows Communication Foundation, transportes"
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Transportes en Windows Communication Foundation
El nivel de transporte está en el nivel más bajo de la pila del canal.Los transportes principales utilizados en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son HTTP, HTTPS, TCP y canalizaciones con nombre.Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye transportes adicionales.Para obtener información sobre el transporte de Message Queuing \(también conocido como MSMQ\), vea [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).Para obtener información sobre el transporte del mismo nivel, vea [Conexión de redes punto a punto](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## En esta sección  
 [Elección del transporte](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Describe los tres transportes principales y las consideraciones para seleccionar uno.  
  
 [Elección de un codificador de mensajes](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.  
  
 [Transferencia de mensajes por secuencias](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Describe cómo configurar el nivel de transporte para la transmisión por secuencias.  
  
 [Configuración de HTTP y HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.  
  
 [Cómo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Describe cómo usar las reservas de direcciones URL restringidas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Cuotas de transporte](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.  
  
 [Trabajar con NAT y firewalls](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red \(NAT\) está presente.  
  
 [Uso compartido de puertos Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Describe cómo utilizar el componente compartido de puerto Net.TCP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Referencia  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## Secciones relacionadas  
 [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Extensión de enlaces](../../../../docs/framework/wcf/extending/extending-bindings.md)