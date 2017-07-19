---
title: "Detecci&#243;n de WCF | Microsoft Docs"
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
  - "detección [WCF]"
  - "WCF [WCF], detección"
  - "Windows Communication Foundation [WCF], detección"
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Detecci&#243;n de WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite habilitar el reconocimiento de los servicios en tiempo de ejecución de forma interoperable mediante el protocolo WS\-Discovery.Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o a un servidor proxy de detección.Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios.Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.  
  
## En esta sección  
 [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 Proporciona información general acerca del soporte de WS\-Discovery proporcionado por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Modelo de objetos de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 Describe las clases de modelo de objetos y extensibilidad del soporte de WS\-Discovery.  
  
 [Cómo: Agregar detectabilidad mediante programación a un cliente y un servicio de WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Muestra cómo hacer que un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sea reconocible.  
  
 [Implementar un proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.  
  
 [Versión de la detección](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección.También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.  
  
 [Configurar la detección en un archivo de configuración](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 Muestra cómo configurar detección en la configuración.  
  
 [Usar el canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 Muestra cómo usar un canal del cliente de detección al escribir una aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].