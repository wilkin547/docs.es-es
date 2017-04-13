---
title: "Servicios de confianza | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "contratos de servicio [WCF], servicios de confianza"
  - "WCF [WCF], mensajería de confianza."
  - "WCF [WCF], sesiones de confianza"
  - "Windows Communication Foundation [WCF], mensajería de confianza."
  - "Windows Communication Foundation [WCF], sesiones de confianza"
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Servicios de confianza
Las colas y las sesiones de confianza son las características de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] que implementan la mensajería de confianza.En este tema se explican las características de mensajería confiable de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 La *mensajería de confianza* se define como la manera en que un origen de mensajería de confianza \(denominado *origen*\) transfiere mensajes de manera fiable a un destino de mensajería de confianza \(denominado *destino*\).  
  
 La mensajería de confianza realiza las funciones siguientes:  
  
-   Transfiere garantías para los mensajes enviados desde un origen a un destino sin tener en cuenta la transferencia de los mensajes o los errores de transporte.  
  
-   Separa el origen del destino.Este hecho proporciona un error independiente y la recuperación del origen y el destino, además de la transferencia confiable y la entrega de los mensajes aun cuando no está disponible el origen o el destino.  
  
 La mensajería de confianza viene aparejada con frecuencia al coste de la latencia alta.La *latencia* es el tiempo que tarda un mensaje en alcanzar el destino desde el origen.Por consiguiente, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona los tipos siguientes de mensajería de confianza:  
  
-   [Sesiones de confianza](../../../docs/framework/wcf/feature-details/reliable-sessions.md), que proporciona la transferencia de confianza sin el coste de una latencia alta.  
  
-   [Colas en WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), que proporciona transferencias de confianza y la separación entre el origen y el destino.  
  
## Sesiones de confianza  
 Las sesiones de confianza proporcionan transferencia confiable de un extremo a otro de mensajes entre un origen y un destino mediante el protocolo de mensajería de confianza WS, sin tener en cuenta el número o tipo de intermediarios que separan los extremos de la mensajería \(origen y destino\).Esto incluye a cualquier intermediario de transporte que no utiliza SOAP \(por ejemplo, los servidores proxy HTTP\) o los intermediarios que utilizan SOAP \(por ejemplo, los enrutadores basados en SOAP o los puentes\) que son necesarios para que los mensajes fluyan entre los extremos.Las sesiones confiables utilizan una ventana de transferencia en memoria para enmascarar errores de nivel de mensaje de SOAP y restablecer las conexiones en el caso de errores de transporte.  
  
 Las sesiones de confianza proporcionan transferencias de mensajes de confianza de latencia baja.Los proporcionan para los mensajes SOAP sobre cualquier proxy o intermediario, el equivalente a lo que TCP proporciona para los paquetes sobre puentes de IP.[!INCLUDE[crabout](../../../includes/crabout-md.md)] sesiones confiables, vea [Sesiones de confianza](../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### Colas  
 Las colas de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporcionan transferencias confiables de mensajes y separación entre los orígenes y los destinos a costa de una latencia alta.La comunicación puesta en cola de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se basa en Message Queuing \(MSMQ\).  
  
 MSMQ se distribuye como un componente opcional con Windows.El servicio de MSMQ se ejecuta como un servicio de Windows.Captura mensajes para la transmisión en una cola de transmisión en nombre del origen y lo entrega a una cola de destino.La cola de destino acepta los mensajes en nombre del destino para la entrega posterior siempre que el destino solicite mensajes.Los administradores de MSMQ implementan un protocolo de transferencias de mensajes de confianza de manera que los mensajes no se pierdan durante la transmisión.El protocolo puede ser nativo o un protocolo basado en SOAP denominado "Protocolo de mensajería de confianza de SOAP" \(SRMP\).  
  
 La separación, acoplada con las transferencias de mensaje de confianza entre las colas, permite que las aplicaciones que están acopladas se comuniquen de forma fiable.A diferencia de las sesiones de confianza, el origen y el destino no tienen que ejecutarse a la vez.Esto habilita escenarios de forma implícita allí donde se usan las colas como un mecanismo de nivelación de carga cuando la tasa de origen de la producción de mensajes y la tasa de destino de consumo de mensajes no coinciden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] las colas, vea [Colas en WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## Vea también  
 [Información general de sesiones confiables](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
 [Las colas en WCF](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)