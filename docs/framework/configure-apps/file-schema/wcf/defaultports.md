---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925886"
---
# <a name="defaultports"></a><span data-ttu-id="9de0a-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9de0a-101">\<defaultPorts></span></span>
<span data-ttu-id="9de0a-102">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="9de0a-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="9de0a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9de0a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9de0a-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9de0a-104">\<behaviors></span></span>  
<span data-ttu-id="9de0a-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9de0a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9de0a-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9de0a-106">\<behavior></span></span>  
<span data-ttu-id="9de0a-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9de0a-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="9de0a-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9de0a-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de0a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9de0a-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9de0a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9de0a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9de0a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9de0a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9de0a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9de0a-112">Attributes</span></span>  
 <span data-ttu-id="9de0a-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9de0a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9de0a-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9de0a-114">Child Elements</span></span>  
  
|<span data-ttu-id="9de0a-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="9de0a-115">Element</span></span>|<span data-ttu-id="9de0a-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9de0a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9de0a-117">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="9de0a-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="9de0a-118">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="9de0a-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9de0a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9de0a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9de0a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9de0a-120">Element</span></span>|<span data-ttu-id="9de0a-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9de0a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9de0a-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9de0a-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="9de0a-123">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9de0a-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9de0a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de0a-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
