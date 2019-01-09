---
title: '&lt;servicios&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: a48bd0ac30c1a85602122b2fd9213c2aa5159e91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148102"
---
# <a name="ltservicesgt"></a><span data-ttu-id="afd60-102">&lt;servicios&gt;</span><span class="sxs-lookup"><span data-stu-id="afd60-102">&lt;services&gt;</span></span>
<span data-ttu-id="afd60-103">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="afd60-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="afd60-104">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="afd60-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="afd60-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="afd60-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afd60-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afd60-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afd60-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="afd60-107">Attributes and Elements</span></span>  
 <span data-ttu-id="afd60-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="afd60-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afd60-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="afd60-109">Attributes</span></span>  
 <span data-ttu-id="afd60-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="afd60-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="afd60-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="afd60-111">Child Elements</span></span>  
  
|<span data-ttu-id="afd60-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="afd60-112">Element</span></span>|<span data-ttu-id="afd60-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="afd60-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afd60-114">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="afd60-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="afd60-115">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="afd60-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afd60-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="afd60-116">Parent Elements</span></span>  
  
|<span data-ttu-id="afd60-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="afd60-117">Element</span></span>|<span data-ttu-id="afd60-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="afd60-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afd60-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="afd60-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="afd60-120">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="afd60-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afd60-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="afd60-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
