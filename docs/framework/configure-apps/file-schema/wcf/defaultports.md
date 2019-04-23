---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130629"
---
# <a name="defaultports"></a><span data-ttu-id="dd3d0-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="dd3d0-101">\<defaultPorts></span></span>
<span data-ttu-id="dd3d0-102">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="dd3d0-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="dd3d0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dd3d0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd3d0-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="dd3d0-104">\<behaviors></span></span>  
<span data-ttu-id="dd3d0-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dd3d0-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="dd3d0-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="dd3d0-106">\<behavior></span></span>  
<span data-ttu-id="dd3d0-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="dd3d0-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="dd3d0-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="dd3d0-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd3d0-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd3d0-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd3d0-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dd3d0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dd3d0-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dd3d0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd3d0-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd3d0-112">Attributes</span></span>  
 <span data-ttu-id="dd3d0-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dd3d0-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd3d0-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dd3d0-114">Child Elements</span></span>  
  
|<span data-ttu-id="dd3d0-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd3d0-115">Element</span></span>|<span data-ttu-id="dd3d0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd3d0-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd3d0-117">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="dd3d0-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="dd3d0-118">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="dd3d0-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd3d0-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dd3d0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dd3d0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd3d0-120">Element</span></span>|<span data-ttu-id="dd3d0-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd3d0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd3d0-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="dd3d0-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="dd3d0-123">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="dd3d0-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd3d0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd3d0-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
