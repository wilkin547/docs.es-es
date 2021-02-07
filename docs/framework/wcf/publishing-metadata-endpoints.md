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
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="7338f-103">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="7338f-103">Publishing Metadata Endpoints</span></span>

<span data-ttu-id="7338f-104">Los servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o más extremos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7338f-104">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="7338f-105">La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="7338f-105">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="7338f-106">Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código.</span><span class="sxs-lookup"><span data-stu-id="7338f-106">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="7338f-107">Para habilitar la publicación de extremos de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.</span><span class="sxs-lookup"><span data-stu-id="7338f-107">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7338f-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7338f-108">In This Section</span></span>  

 [<span data-ttu-id="7338f-109">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7338f-109">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="7338f-110">Muestra cómo configurar un servicio WCF para publicar metadatos de modo que los clientes puedan recuperar los metadatos mediante una WS-MetadataExchange o una solicitud HTTP/GET mediante la `?wsdl` cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="7338f-110">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="7338f-111">Procedimiento para publicar metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="7338f-111">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="7338f-112">Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes puedan recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando la `?wsdl` cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="7338f-112">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7338f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7338f-113">See also</span></span>

- [<span data-ttu-id="7338f-114">Publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="7338f-114">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
