---
title: '&lt;add&gt; de &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 0932ef9afacb6278c4857dcfd6ba545595ff8f9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147725"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="2d3e8-102">&lt;add&gt; de &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="2d3e8-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="2d3e8-103">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="2d3e8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2d3e8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d3e8-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-105">\<behaviors></span></span>  
<span data-ttu-id="2d3e8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2d3e8-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-107">\<behavior></span></span>  
<span data-ttu-id="2d3e8-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="2d3e8-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-109">\<defaultPorts></span></span>  
<span data-ttu-id="2d3e8-110">\<add></span><span class="sxs-lookup"><span data-stu-id="2d3e8-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d3e8-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d3e8-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d3e8-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2d3e8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2d3e8-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d3e8-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="2d3e8-114">Attributes</span></span>  
  
|<span data-ttu-id="2d3e8-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="2d3e8-115">Attribute</span></span>|<span data-ttu-id="2d3e8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d3e8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d3e8-117">puerto</span><span class="sxs-lookup"><span data-stu-id="2d3e8-117">port</span></span>|<span data-ttu-id="2d3e8-118">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="2d3e8-119">scheme</span><span class="sxs-lookup"><span data-stu-id="2d3e8-119">scheme</span></span>|<span data-ttu-id="2d3e8-120">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d3e8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2d3e8-121">Child Elements</span></span>  
 <span data-ttu-id="2d3e8-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d3e8-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2d3e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2d3e8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2d3e8-124">Element</span></span>|<span data-ttu-id="2d3e8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d3e8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d3e8-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="2d3e8-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="2d3e8-127">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="2d3e8-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d3e8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d3e8-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
