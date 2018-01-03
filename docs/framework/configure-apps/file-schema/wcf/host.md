---
title: '&lt;host&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7177c62af8501258ad8709bff88cb85488b56727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lthostgt"></a><span data-ttu-id="ea9b1-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="ea9b1-102">&lt;host&gt;</span></span>
<span data-ttu-id="ea9b1-103">Especifica los valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="ea9b1-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ea9b1-105">\<Servicios ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-105">\<services></span></span>  
<span data-ttu-id="ea9b1-106">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-106">\<service></span></span>  
<span data-ttu-id="ea9b1-107">\<host ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea9b1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea9b1-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="ea9b1-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="ea9b1-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea9b1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea9b1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea9b1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea9b1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea9b1-112">Attributes</span></span>  
 <span data-ttu-id="ea9b1-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea9b1-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea9b1-114">Child Elements</span></span>  
  
|<span data-ttu-id="ea9b1-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea9b1-115">Element</span></span>|<span data-ttu-id="ea9b1-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea9b1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea9b1-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="ea9b1-118">Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="ea9b1-119">\<los tiempos de espera ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="ea9b1-120">Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="ea9b1-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea9b1-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea9b1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ea9b1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea9b1-122">Element</span></span>|<span data-ttu-id="ea9b1-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea9b1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea9b1-124">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="ea9b1-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="ea9b1-125">Especifica la configuración para un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea9b1-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea9b1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea9b1-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="ea9b1-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ea9b1-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
