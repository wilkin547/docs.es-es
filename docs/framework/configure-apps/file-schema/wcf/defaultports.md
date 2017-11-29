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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0e127935977795181411dfa6b03d8b09fe88e0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="970c1-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="970c1-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="970c1-103">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="970c1-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="970c1-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="970c1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="970c1-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="970c1-105">\<behaviors></span></span>  
<span data-ttu-id="970c1-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="970c1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="970c1-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="970c1-107">\<behavior></span></span>  
<span data-ttu-id="970c1-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="970c1-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="970c1-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="970c1-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970c1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="970c1-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="970c1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="970c1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="970c1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="970c1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="970c1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="970c1-113">Attributes</span></span>  
 <span data-ttu-id="970c1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="970c1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="970c1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="970c1-115">Child Elements</span></span>  
  
|<span data-ttu-id="970c1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="970c1-116">Element</span></span>|<span data-ttu-id="970c1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="970c1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="970c1-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="970c1-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="970c1-119">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="970c1-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="970c1-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="970c1-120">Parent Elements</span></span>  
  
|<span data-ttu-id="970c1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="970c1-121">Element</span></span>|<span data-ttu-id="970c1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="970c1-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="970c1-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="970c1-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="970c1-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="970c1-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="970c1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="970c1-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
