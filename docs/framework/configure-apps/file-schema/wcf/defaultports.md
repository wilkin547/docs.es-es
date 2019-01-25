---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2c742f98315c0e497ac4117953424bae913cb5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614502"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="b0ae7-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="b0ae7-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="b0ae7-103">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="b0ae7-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="b0ae7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0ae7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0ae7-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b0ae7-105">\<behaviors></span></span>  
<span data-ttu-id="b0ae7-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b0ae7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b0ae7-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b0ae7-107">\<behavior></span></span>  
<span data-ttu-id="b0ae7-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="b0ae7-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="b0ae7-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="b0ae7-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ae7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0ae7-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0ae7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0ae7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b0ae7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0ae7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0ae7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0ae7-113">Attributes</span></span>  
 <span data-ttu-id="b0ae7-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0ae7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0ae7-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0ae7-115">Child Elements</span></span>  
  
|<span data-ttu-id="b0ae7-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0ae7-116">Element</span></span>|<span data-ttu-id="b0ae7-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0ae7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0ae7-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="b0ae7-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="b0ae7-119">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="b0ae7-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0ae7-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0ae7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0ae7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0ae7-121">Element</span></span>|<span data-ttu-id="b0ae7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0ae7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0ae7-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="b0ae7-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="b0ae7-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b0ae7-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0ae7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0ae7-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
