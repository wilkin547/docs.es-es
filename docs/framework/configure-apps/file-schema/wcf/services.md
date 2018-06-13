---
title: '&lt;Servicios de&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 789fc52f628174ef61a9c7169cb0cae0f1ba8e31
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749236"
---
# <a name="ltservicesgt"></a><span data-ttu-id="bf55f-102">&lt;Servicios de&gt;</span><span class="sxs-lookup"><span data-stu-id="bf55f-102">&lt;services&gt;</span></span>
<span data-ttu-id="bf55f-103">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf55f-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="bf55f-104">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="bf55f-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="bf55f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bf55f-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf55f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf55f-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf55f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf55f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bf55f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf55f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf55f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf55f-109">Attributes</span></span>  
 <span data-ttu-id="bf55f-110">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bf55f-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf55f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf55f-111">Child Elements</span></span>  
  
|<span data-ttu-id="bf55f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf55f-112">Element</span></span>|<span data-ttu-id="bf55f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf55f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf55f-114">\<servicio ></span><span class="sxs-lookup"><span data-stu-id="bf55f-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="bf55f-115">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="bf55f-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf55f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf55f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bf55f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf55f-117">Element</span></span>|<span data-ttu-id="bf55f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf55f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf55f-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bf55f-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="bf55f-120">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bf55f-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf55f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf55f-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
