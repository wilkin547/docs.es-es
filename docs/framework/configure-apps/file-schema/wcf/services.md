---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168082"
---
# <a name="services"></a><span data-ttu-id="52987-101">\<services></span><span class="sxs-lookup"><span data-stu-id="52987-101">\<services></span></span>
<span data-ttu-id="52987-102">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="52987-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="52987-103">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="52987-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="52987-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="52987-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52987-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52987-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52987-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="52987-106">Attributes and Elements</span></span>  
 <span data-ttu-id="52987-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="52987-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52987-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="52987-108">Attributes</span></span>  
 <span data-ttu-id="52987-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="52987-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52987-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="52987-110">Child Elements</span></span>  
  
|<span data-ttu-id="52987-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="52987-111">Element</span></span>|<span data-ttu-id="52987-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="52987-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52987-113">\<service></span><span class="sxs-lookup"><span data-stu-id="52987-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="52987-114">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="52987-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52987-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="52987-115">Parent Elements</span></span>  
  
|<span data-ttu-id="52987-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="52987-116">Element</span></span>|<span data-ttu-id="52987-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="52987-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52987-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="52987-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="52987-119">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="52987-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52987-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="52987-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
