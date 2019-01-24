---
title: Publicación de puntos de conexión de metadatos
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5de1122a4b603e4c0cd3ae55f3ac7424a7fd77f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626599"
---
# <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos
Servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o varios extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código. Para habilitar la publicación de puntos de conexión de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio WCF para publicar metadatos para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
 [Cómo: Publicación de metadatos para un servicio mediante código](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
## <a name="see-also"></a>Vea también
- [Publicación de metadatos](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
