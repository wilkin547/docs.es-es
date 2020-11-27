---
title: puntos de conexión en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: d3281ac648ecb43ce5248fe86b6da1d268e382f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262156"
---
# <a name="windows-communication-foundation-endpoints"></a>puntos de conexión en Windows Communication Foundation

Toda la comunicación con un servicio de Windows Communication Foundation (WCF) se produce a través de los *extremos* del servicio. Los extremos proporcionan a los clientes acceso a la funcionalidad que ofrece un servicio WCF.  
  
 Para obtener información general sobre cómo crear un punto de conexión, consulte [información general](endpoint-creation-overview.md)sobre la creación de puntos de conexión. Cada punto de conexión contiene:  
  
- Una dirección que indica dónde buscar el punto de conexión.  
  
- Un enlace que especifica cómo un se puede comunicar un cliente con el punto de conexión.  
  
- Un contrato que identifica los métodos disponibles.  
  
 Para obtener descripciones acerca de cómo especificar estas partes individuales de un punto de conexión, consulte:  
  
- [Especificación de una dirección de punto de conexión](specifying-an-endpoint-address.md)  
  
- [Utilización de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)  
  
- [Diseño e implementación de servicios](designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a>En esta sección  

 [Información general acerca de la creación de puntos finales](endpoint-creation-overview.md)  
 Describe la estructura de un extremo y detalla cómo definir un extremo en la configuración y el código, así como el uso de los extremos, enlaces y comportamientos predeterminados proporcionados por el tiempo de ejecución.  
  
 [Especificación de una dirección de punto de conexión](specifying-an-endpoint-address.md)  
 Describe cómo se produce la comunicación con un servicio WCF a través de los extremos.  
  
 [Procedimiento para crear un punto de conexión de servicio en la configuración](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Muestra cómo crear un punto de conexión de servicio en configuración.  
  
 [Procedimiento para crear un punto de conexión de servicio mediante código](./feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Muestra cómo crear un extremo de servicio en código.  
  
 [Publicación de puntos de conexión de metadatos](publishing-metadata-endpoints.md)  
 Muestra cómo publicar los metadatos mediante la publicación de los extremos de metadatos en configuración y en código.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Ciclo de vida de programación básica](basic-programming-lifecycle.md)
