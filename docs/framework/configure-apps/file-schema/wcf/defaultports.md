---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 595970a56e05c4fc1c9b2c0eb669ec3b3a120fe1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262399"
---
# <a name="defaultports"></a><span data-ttu-id="95ed3-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="95ed3-101">\<defaultPorts></span></span>
<span data-ttu-id="95ed3-102">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="95ed3-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="95ed3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="95ed3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="95ed3-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="95ed3-104">\<behaviors></span></span>  
<span data-ttu-id="95ed3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="95ed3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="95ed3-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="95ed3-106">\<behavior></span></span>  
<span data-ttu-id="95ed3-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="95ed3-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="95ed3-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="95ed3-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ed3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95ed3-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95ed3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95ed3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="95ed3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95ed3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95ed3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="95ed3-112">Attributes</span></span>  
 <span data-ttu-id="95ed3-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="95ed3-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95ed3-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95ed3-114">Child Elements</span></span>  
  
|<span data-ttu-id="95ed3-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="95ed3-115">Element</span></span>|<span data-ttu-id="95ed3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="95ed3-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95ed3-117">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="95ed3-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="95ed3-118">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="95ed3-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95ed3-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95ed3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="95ed3-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="95ed3-120">Element</span></span>|<span data-ttu-id="95ed3-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="95ed3-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95ed3-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="95ed3-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="95ed3-123">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="95ed3-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95ed3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="95ed3-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
