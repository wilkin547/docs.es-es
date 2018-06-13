---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 7e661570f8b94b979595a615b3f6819d41ed5e35
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766704"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="d6abd-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="d6abd-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="d6abd-103">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d6abd-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="d6abd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6abd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6abd-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d6abd-105">\<behaviors></span></span>  
<span data-ttu-id="d6abd-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d6abd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d6abd-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d6abd-107">\<behavior></span></span>  
<span data-ttu-id="d6abd-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d6abd-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6abd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6abd-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6abd-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6abd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6abd-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6abd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6abd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6abd-112">Attributes</span></span>  
 <span data-ttu-id="d6abd-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d6abd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6abd-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6abd-114">Child Elements</span></span>  
  
|<span data-ttu-id="d6abd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6abd-115">Element</span></span>|<span data-ttu-id="d6abd-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6abd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6abd-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d6abd-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="d6abd-118">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="d6abd-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6abd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6abd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d6abd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6abd-120">Element</span></span>|<span data-ttu-id="d6abd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6abd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6abd-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d6abd-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d6abd-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d6abd-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6abd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6abd-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
