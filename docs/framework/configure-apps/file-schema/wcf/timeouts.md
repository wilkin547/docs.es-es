---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 8a8a352380fe6eedb41ead089405e7b79fad29fe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272788"
---
# <a name="timeouts"></a><span data-ttu-id="53f47-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="53f47-101">\<timeOuts></span></span>
<span data-ttu-id="53f47-102">Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.</span><span class="sxs-lookup"><span data-stu-id="53f47-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="53f47-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53f47-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="53f47-104">\<client></span><span class="sxs-lookup"><span data-stu-id="53f47-104">\<client></span></span>  
<span data-ttu-id="53f47-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="53f47-105">\<endpoint></span></span>  
<span data-ttu-id="53f47-106">\<host ></span><span class="sxs-lookup"><span data-stu-id="53f47-106">\<host></span></span>  
<span data-ttu-id="53f47-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="53f47-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f47-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53f47-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53f47-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53f47-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53f47-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53f47-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53f47-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="53f47-111">Attributes</span></span>  
  
|<span data-ttu-id="53f47-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="53f47-112">Attribute</span></span>|<span data-ttu-id="53f47-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="53f47-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="53f47-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.</span><span class="sxs-lookup"><span data-stu-id="53f47-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="53f47-115">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.</span><span class="sxs-lookup"><span data-stu-id="53f47-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53f47-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53f47-116">Child Elements</span></span>  
 <span data-ttu-id="53f47-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="53f47-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53f47-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53f47-118">Parent Elements</span></span>  
  
|<span data-ttu-id="53f47-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="53f47-119">Element</span></span>|<span data-ttu-id="53f47-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="53f47-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53f47-121">\<host></span><span class="sxs-lookup"><span data-stu-id="53f47-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="53f47-122">Un elemento de configuración que especifica valores para un host de servicio.</span><span class="sxs-lookup"><span data-stu-id="53f47-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53f47-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="53f47-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="53f47-124">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="53f47-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
