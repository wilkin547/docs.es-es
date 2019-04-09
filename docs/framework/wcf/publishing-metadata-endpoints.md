---
title: Publicación de puntos de conexión de metadatos
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121737"
---
# <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos
Servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o varios extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código. Para habilitar la publicación de extremos de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.  
  
## <a name="in-this-section"></a>En esta sección  
 [Filtrar para publicar metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio WCF para publicar metadatos para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
 [Filtrar para publicar metadatos para un servicio mediante código](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
## <a name="see-also"></a>Vea también

- [Publicación de metadatos](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
