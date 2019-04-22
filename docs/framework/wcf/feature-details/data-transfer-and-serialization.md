---
title: Transferencia y serialización de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 1eefd82a149d0bc215ca441e92c7d737a744b1e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088410"
---
# <a name="data-transfer-and-serialization"></a>Transferencia y serialización de datos
En un sistema conectado, los servicios y clientes dependen del intercambio de datos para realizar cualquier tarea. Como desarrollador de un servicio o cliente, también debe entender cómo Windows Communication Foundation (WCF) controla la serialización de datos y datos con el fin de crear aplicaciones eficaces y fáciles de mantener.  
  
## <a name="in-this-section"></a>En esta sección  
 [Definición de transferencias de datos en contratos de servicio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Describe los conceptos básicos de la transferencia de datos en los servicios.  
  
 [Utilización de contratos de datos](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Describe qué son los contratos de datos y cómo crearlos y utilizarlos.  
  
 [Serializador de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Describe cómo lograr la serialización de los datos con la clase <xref:System.Runtime.Serialization.DataContractSerializer> o cualquier extensión de la clase <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [Utilización de la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Describe cómo y por qué utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, una alternativa a la clase <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Uso de contratos de mensaje](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Describe cómo permiten los contratos de mensajes un control estrecho sobre los mensajes SOAP.  
  
 [Uso de la clase de mensajes](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Describe cómo utilizar las características de la clase Message.  
  
 [Filtrado](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Describe el filtrado, que permite el preprocesado de un mensaje en función de varios criterios.  
  
 [Grandes datos y streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Describe cómo enviar un bloque grande de datos, como, por ejemplo, un archivo binario.  
  
 [Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Describe los elementos que se han de tener en cuenta a la hora de programar la transferencia y serialización de datos.  
  
 [Información general sobre la arquitectura de transferencia de datos](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Describe una vista del diseño general de transferencia de datos de WCF.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Extensión de codificadores y serializadores](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Vea también

- [Procedimientos recomendados: Versiones de contratos de datos](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [Control de versiones del servicio](../../../../docs/framework/wcf/service-versioning.md)
