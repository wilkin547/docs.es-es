---
title: '&lt;add&gt; de &lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efe61bf5f4276836c65e9c81d316dc0664f3de2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="061ea-102">&lt;add&gt; de &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="061ea-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="061ea-103">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="061ea-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="061ea-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="061ea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="061ea-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="061ea-105">\<behaviors></span></span>  
<span data-ttu-id="061ea-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="061ea-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="061ea-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="061ea-107">\<behavior></span></span>  
<span data-ttu-id="061ea-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="061ea-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="061ea-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="061ea-109">\<defaultPorts></span></span>  
<span data-ttu-id="061ea-110">\<add></span><span class="sxs-lookup"><span data-stu-id="061ea-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="061ea-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="061ea-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="061ea-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="061ea-112">Attributes and Elements</span></span>  
 <span data-ttu-id="061ea-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="061ea-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="061ea-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="061ea-114">Attributes</span></span>  
  
|<span data-ttu-id="061ea-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="061ea-115">Attribute</span></span>|<span data-ttu-id="061ea-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="061ea-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="061ea-117">puerto</span><span class="sxs-lookup"><span data-stu-id="061ea-117">port</span></span>|<span data-ttu-id="061ea-118">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="061ea-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="061ea-119">scheme</span><span class="sxs-lookup"><span data-stu-id="061ea-119">scheme</span></span>|<span data-ttu-id="061ea-120">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="061ea-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="061ea-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="061ea-121">Child Elements</span></span>  
 <span data-ttu-id="061ea-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="061ea-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="061ea-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="061ea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="061ea-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="061ea-124">Element</span></span>|<span data-ttu-id="061ea-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="061ea-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="061ea-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="061ea-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="061ea-127">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="061ea-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="061ea-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="061ea-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
