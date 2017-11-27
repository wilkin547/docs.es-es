---
title: "Publicación de puntos de conexión de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0f3f134526fd24a724ba593302ba2bf1f27fa3e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="3504a-102">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="3504a-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="3504a-103">Los servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] publican metadatos mediante la publicación de uno o más extremos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3504a-103">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="3504a-104">La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="3504a-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="3504a-105">Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código.</span><span class="sxs-lookup"><span data-stu-id="3504a-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="3504a-106">Para habilitar la publicación de extremos de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.</span><span class="sxs-lookup"><span data-stu-id="3504a-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3504a-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3504a-107">In This Section</span></span>  
 [<span data-ttu-id="3504a-108">Cómo: publicar los metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3504a-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="3504a-109">Muestra cómo configurar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para publicar metadatos de tal modo que los clientes puedan recuperar los metadatos mediante una solicitud HTTP/GET o WS-MetadataExchange mediante la cadena de consulta `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="3504a-109">Demonstrates how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="3504a-110">Cómo: publicar los metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="3504a-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="3504a-111">Muestra cómo habilitar la publicación de metadatos para un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en código de tal modo que los clientes puedan recuperar los datos mediante una solicitud HTTP/GET o WS-MetadataExchange mediante la cadena de consulta `?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="3504a-111">Demonstrates how to enable metadata publishing for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3504a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3504a-112">See Also</span></span>  
 [<span data-ttu-id="3504a-113">Publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="3504a-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
