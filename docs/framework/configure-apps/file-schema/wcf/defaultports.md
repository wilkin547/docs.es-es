---
title: '&lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd4fba4d7d5bcb0adc5a1a638598af2746ad4cf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="a0482-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="a0482-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="a0482-103">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="a0482-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="a0482-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a0482-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0482-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a0482-105">\<behaviors></span></span>  
<span data-ttu-id="a0482-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a0482-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a0482-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a0482-107">\<behavior></span></span>  
<span data-ttu-id="a0482-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="a0482-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="a0482-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="a0482-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0482-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0482-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0482-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0482-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a0482-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0482-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0482-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0482-113">Attributes</span></span>  
 <span data-ttu-id="a0482-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0482-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0482-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0482-115">Child Elements</span></span>  
  
|<span data-ttu-id="a0482-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0482-116">Element</span></span>|<span data-ttu-id="a0482-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0482-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0482-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="a0482-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="a0482-119">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="a0482-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0482-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0482-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a0482-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0482-121">Element</span></span>|<span data-ttu-id="a0482-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0482-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0482-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="a0482-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="a0482-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a0482-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0482-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0482-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
