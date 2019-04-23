---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103004"
---
# <a name="host"></a><span data-ttu-id="3c3a9-101">\<host ></span><span class="sxs-lookup"><span data-stu-id="3c3a9-101">\<host></span></span>
<span data-ttu-id="3c3a9-102">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="3c3a9-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="3c3a9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c3a9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c3a9-104">\<services></span><span class="sxs-lookup"><span data-stu-id="3c3a9-104">\<services></span></span>  
<span data-ttu-id="3c3a9-105">\<service></span><span class="sxs-lookup"><span data-stu-id="3c3a9-105">\<service></span></span>  
<span data-ttu-id="3c3a9-106">\<host ></span><span class="sxs-lookup"><span data-stu-id="3c3a9-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3a9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c3a9-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="3c3a9-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="3c3a9-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c3a9-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c3a9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3c3a9-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c3a9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c3a9-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c3a9-111">Attributes</span></span>  
 <span data-ttu-id="3c3a9-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c3a9-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c3a9-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c3a9-113">Child Elements</span></span>  
  
|<span data-ttu-id="3c3a9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c3a9-114">Element</span></span>|<span data-ttu-id="3c3a9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c3a9-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c3a9-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="3c3a9-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="3c3a9-117">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="3c3a9-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="3c3a9-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="3c3a9-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="3c3a9-119">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="3c3a9-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c3a9-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c3a9-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3c3a9-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c3a9-121">Element</span></span>|<span data-ttu-id="3c3a9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c3a9-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c3a9-123">\<service></span><span class="sxs-lookup"><span data-stu-id="3c3a9-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="3c3a9-124">Especifica la configuración para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3c3a9-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c3a9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c3a9-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="3c3a9-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3c3a9-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
