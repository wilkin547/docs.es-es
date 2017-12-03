---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e7f69da871376f83422fb330f8babd56bb1fdcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="964fd-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="964fd-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="964fd-103">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="964fd-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="964fd-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="964fd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="964fd-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="964fd-105">\<behaviors></span></span>  
<span data-ttu-id="964fd-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="964fd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="964fd-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="964fd-107">\<behavior></span></span>  
<span data-ttu-id="964fd-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="964fd-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964fd-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="964fd-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="964fd-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="964fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="964fd-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="964fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="964fd-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="964fd-112">Attributes</span></span>  
 <span data-ttu-id="964fd-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="964fd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="964fd-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="964fd-114">Child Elements</span></span>  
  
|<span data-ttu-id="964fd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="964fd-115">Element</span></span>|<span data-ttu-id="964fd-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="964fd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="964fd-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="964fd-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="964fd-118">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="964fd-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="964fd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="964fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="964fd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="964fd-120">Element</span></span>|<span data-ttu-id="964fd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="964fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="964fd-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="964fd-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="964fd-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="964fd-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="964fd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="964fd-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
