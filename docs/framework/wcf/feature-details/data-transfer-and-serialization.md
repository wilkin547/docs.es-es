---
title: "Transferencia y serializaci&#243;n de datos | Microsoft Docs"
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
  - "serialización de datos [WCF]"
  - "transferencia de datos [WCF]"
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Transferencia y serializaci&#243;n de datos
En un sistema conectado, los servicios y clientes dependen del intercambio de datos para realizar cualquier tarea.Como programador de un servicio o cliente, también debe entender cómo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] administra los datos y la serialización de los datos para crear aplicaciones eficaces y fáciles de mantener.  
  
## En esta sección  
 [Especificación de transferencia de datos en contratos de servicio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Describe los conceptos básicos de la transferencia de datos en los servicios.  
  
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Describe qué son los contratos de datos y cómo crearlos y utilizarlos.  
  
 [El serializador de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Describe cómo lograr la serialización de los datos con la clase <xref:System.Runtime.Serialization.DataContractSerializer> o cualquier extensión de la clase <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [Utilización de la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Describe cómo y por qué utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, una alternativa a la clase <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Usar contratos de mensaje](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Describe cómo permiten los contratos de mensajes un control estrecho sobre los mensajes SOAP.  
  
 [Uso de la clase de mensajes](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Describe cómo utilizar las características de la clase Message.  
  
 [Filtrado](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Describe el filtrado, que permite el preprocesado de un mensaje en función de varios criterios.  
  
 [Datos de gran tamaño y secuencias](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Describe cómo enviar un bloque grande de datos, como, por ejemplo, un archivo binario.  
  
 [Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Describe los elementos que se han de tener en cuenta a la hora de programar la transferencia y serialización de datos.  
  
 [Información general sobre la arquitectura de transferencia de datos](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Describe una vista del diseño general de la transferencia de datos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## Secciones relacionadas  
 [Extensión de codificadores y serializadores](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## Vea también  
 [Procedimientos recomendados: Creación de versiones de contratos de datos](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)   
 [Control de versiones del servicio](../../../../docs/framework/wcf/service-versioning.md)