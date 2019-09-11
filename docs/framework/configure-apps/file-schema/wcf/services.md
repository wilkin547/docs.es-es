---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854981"
---
# <a name="services"></a><span data-ttu-id="f0288-101">\<> de servicios</span><span class="sxs-lookup"><span data-stu-id="f0288-101">\<services></span></span>
<span data-ttu-id="f0288-102">Los servicios se definen en la sección de `services` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f0288-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="f0288-103">Cada servicio tiene su propia sección de configuración de `service`.</span><span class="sxs-lookup"><span data-stu-id="f0288-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="f0288-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f0288-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f0288-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f0288-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f0288-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> de servicios**</span><span class="sxs-lookup"><span data-stu-id="f0288-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0288-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0288-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0288-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0288-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f0288-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f0288-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0288-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0288-110">Attributes</span></span>  
 <span data-ttu-id="f0288-111">None</span><span class="sxs-lookup"><span data-stu-id="f0288-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0288-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0288-112">Child Elements</span></span>  
  
|<span data-ttu-id="f0288-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0288-113">Element</span></span>|<span data-ttu-id="f0288-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0288-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0288-115">\<service></span><span class="sxs-lookup"><span data-stu-id="f0288-115">\<service></span></span>](service.md)|<span data-ttu-id="f0288-116">Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="f0288-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0288-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0288-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f0288-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0288-118">Element</span></span>|<span data-ttu-id="f0288-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0288-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0288-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f0288-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="f0288-121">El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f0288-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0288-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0288-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
