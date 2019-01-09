---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 7ddfddaa13778ce98bd93b6d8029438377fc7e94
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145190"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="5b0d3-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="5b0d3-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="5b0d3-103">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="5b0d3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5b0d3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b0d3-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-105">\<behaviors></span></span>  
<span data-ttu-id="5b0d3-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5b0d3-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-107">\<behavior></span></span>  
<span data-ttu-id="5b0d3-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="5b0d3-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0d3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b0d3-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b0d3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b0d3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5b0d3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b0d3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b0d3-113">Attributes</span></span>  
 <span data-ttu-id="5b0d3-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b0d3-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b0d3-115">Child Elements</span></span>  
  
|<span data-ttu-id="5b0d3-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b0d3-116">Element</span></span>|<span data-ttu-id="5b0d3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b0d3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b0d3-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="5b0d3-119">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b0d3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b0d3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5b0d3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b0d3-121">Element</span></span>|<span data-ttu-id="5b0d3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b0d3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b0d3-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="5b0d3-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="5b0d3-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5b0d3-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b0d3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b0d3-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
