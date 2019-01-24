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
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="6e001-102">Publicación de puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="6e001-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="6e001-103">Servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o varios extremos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6e001-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="6e001-104">La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET.</span><span class="sxs-lookup"><span data-stu-id="6e001-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="6e001-105">Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio mediante configuración o código.</span><span class="sxs-lookup"><span data-stu-id="6e001-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="6e001-106">Para habilitar la publicación de puntos de conexión de metadatos, debe agregar el comportamiento de servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio.</span><span class="sxs-lookup"><span data-stu-id="6e001-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e001-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6e001-107">In This Section</span></span>  
 [<span data-ttu-id="6e001-108">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="6e001-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="6e001-109">Muestra cómo configurar un servicio WCF para publicar metadatos para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="6e001-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="6e001-110">Cómo: Publicación de metadatos para un servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="6e001-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="6e001-111">Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="6e001-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e001-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e001-112">See also</span></span>
- [<span data-ttu-id="6e001-113">Publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="6e001-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
