---
description: 'Más información sobre: publicar puntos de conexión de metadatos'
title: Publicación de puntos de conexión de metadatos
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 8204a62413e09c0fbc6effaae1fd752aee397147
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726681"
---
# <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos

Los servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o más extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código. Para habilitar la publicación de extremos de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.  
  
## <a name="in-this-section"></a>En esta sección  

 [Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio WCF para publicar metadatos de modo que los clientes puedan recuperar los metadatos mediante una WS-MetadataExchange o una solicitud HTTP/GET mediante la `?wsdl` cadena de consulta.  
  
 [Procedimiento para publicar metadatos para un servicio mediante código](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes puedan recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando la `?wsdl` cadena de consulta.  
  
## <a name="see-also"></a>Vea también

- [Publicación de metadatos](./feature-details/publishing-metadata.md)
