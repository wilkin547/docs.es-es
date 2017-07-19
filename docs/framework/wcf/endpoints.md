---
title: "Extremos en Windows Communication Foundation | Microsoft Docs"
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
  - "extremos [WCF]"
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Extremos en Windows Communication Foundation
Toda comunicación con un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se produce a través de los *extremos* del servicio.  Los extremos proporcionan a los clientes acceso a la funcionalidad que un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ofrece.  
  
 Para obtener información general acerca de cómo crear un extremo, consulte [Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md).  Cada extremo contiene:  
  
-   Una dirección que indica dónde buscar el extremo.  
  
-   Un enlace que especifica cómo un se puede comunicar un cliente con el extremo.  
  
-   Un contrato que identifica los métodos disponibles.  
  
 Para obtener descripciones acerca de cómo especificar estas partes individuales de un extremo, consulte:  
  
-   [Especificación de una dirección de extremo](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [Diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## En esta sección  
 [Información general acerca de la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 Describe la estructura de un extremo y detalla cómo definir un extremo en la configuración y el código, así como el uso de los extremos, enlaces y comportamientos predeterminados proporcionados por el tiempo de ejecución.  
  
 [Especificación de una dirección de extremo](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 Describe cómo se produce la comunicación con un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a través de los extremos.  
  
 [Cómo crear un extremo de servicio en configuración](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Muestra cómo crear un extremo de servicio en configuración.  
  
 [Cómo crear un extremo de servicio en código](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Muestra cómo crear un extremo de servicio en código.  
  
 [Publicación de extremos de metadatos](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 Muestra cómo publicar los metadatos mediante la publicación de los extremos de metadatos en configuración y en código.  
  
## Referencia  
 <xref:System.ServiceModel.EndpointAddress>  
  
## Secciones relacionadas  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)