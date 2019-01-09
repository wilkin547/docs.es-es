---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: bcbf1c633e0796c6056759dfbb55014838e0e293
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151415"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="7f351-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="7f351-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="7f351-103">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7f351-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="7f351-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7f351-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f351-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="7f351-105">\<behaviors></span></span>  
<span data-ttu-id="7f351-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7f351-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7f351-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7f351-107">\<behavior></span></span>  
<span data-ttu-id="7f351-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="7f351-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f351-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f351-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f351-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f351-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f351-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f351-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f351-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f351-112">Attributes</span></span>  
 <span data-ttu-id="7f351-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f351-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f351-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f351-114">Child Elements</span></span>  
  
|<span data-ttu-id="7f351-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f351-115">Element</span></span>|<span data-ttu-id="7f351-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f351-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f351-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="7f351-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="7f351-118">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="7f351-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f351-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f351-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7f351-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f351-120">Element</span></span>|<span data-ttu-id="7f351-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f351-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f351-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7f351-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7f351-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7f351-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f351-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f351-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
