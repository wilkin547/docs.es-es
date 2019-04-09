---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121191"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="22a87-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="22a87-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="22a87-102">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="22a87-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="22a87-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="22a87-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="22a87-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="22a87-104">\<behaviors></span></span>  
<span data-ttu-id="22a87-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="22a87-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="22a87-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="22a87-106">\<behavior></span></span>  
<span data-ttu-id="22a87-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="22a87-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a87-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a87-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22a87-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22a87-109">Attributes and Elements</span></span>  
 <span data-ttu-id="22a87-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22a87-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22a87-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="22a87-111">Attributes</span></span>  
 <span data-ttu-id="22a87-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22a87-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22a87-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22a87-113">Child Elements</span></span>  
  
|<span data-ttu-id="22a87-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="22a87-114">Element</span></span>|<span data-ttu-id="22a87-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a87-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a87-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="22a87-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="22a87-117">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="22a87-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22a87-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22a87-118">Parent Elements</span></span>  
  
|<span data-ttu-id="22a87-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="22a87-119">Element</span></span>|<span data-ttu-id="22a87-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a87-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a87-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="22a87-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="22a87-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="22a87-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22a87-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a87-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
