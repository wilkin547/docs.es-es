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
ms.openlocfilehash: 1886f6efdfaa8f4105e6ef16ad72093867e0f3fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="c57eb-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="c57eb-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="c57eb-103">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c57eb-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="c57eb-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c57eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c57eb-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c57eb-105">\<behaviors></span></span>  
<span data-ttu-id="c57eb-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c57eb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c57eb-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c57eb-107">\<behavior></span></span>  
<span data-ttu-id="c57eb-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="c57eb-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="c57eb-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c57eb-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c57eb-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c57eb-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c57eb-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c57eb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c57eb-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c57eb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c57eb-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="c57eb-113">Attributes</span></span>  
 <span data-ttu-id="c57eb-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c57eb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c57eb-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c57eb-115">Child Elements</span></span>  
  
|<span data-ttu-id="c57eb-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c57eb-116">Element</span></span>|<span data-ttu-id="c57eb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c57eb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c57eb-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c57eb-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="c57eb-119">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c57eb-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c57eb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c57eb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c57eb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c57eb-121">Element</span></span>|<span data-ttu-id="c57eb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c57eb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c57eb-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="c57eb-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="c57eb-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c57eb-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c57eb-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c57eb-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
