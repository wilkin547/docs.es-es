---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758163"
---
# <a name="services"></a><span data-ttu-id="410a9-101">\<services></span><span class="sxs-lookup"><span data-stu-id="410a9-101">\<services></span></span>
<span data-ttu-id="410a9-102">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="410a9-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="410a9-103">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="410a9-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="410a9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="410a9-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="410a9-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="410a9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="410a9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="410a9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="410a9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="410a9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="410a9-108">Attributes</span></span>  
 <span data-ttu-id="410a9-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="410a9-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="410a9-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="410a9-110">Child Elements</span></span>  
  
|<span data-ttu-id="410a9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="410a9-111">Element</span></span>|<span data-ttu-id="410a9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="410a9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a9-113">\<service></span><span class="sxs-lookup"><span data-stu-id="410a9-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="410a9-114">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="410a9-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="410a9-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="410a9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="410a9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="410a9-116">Element</span></span>|<span data-ttu-id="410a9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="410a9-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a9-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="410a9-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="410a9-119">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="410a9-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="410a9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="410a9-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
